---
date: "2020-05-08"
title: "Access Control for Pods on Amazon EKS"
authors: ["mike-metral"]
tags: ["EKS", "RBAC", "Kubernetes"]
meta_desc: "Amazon EKS clusters can use IAM roles and policies for Pods to assign fine-grained access control of AWS services."
meta_image: cluster.svg
---

Amazon [EKS][aws-eks] clusters can use [IAM][aws-iam] roles and policies for Pods
to assign fine-grained access control of AWS services. The AWS IAM entities map into Kubernetes
[RBAC][k8s-rbac] to configure the permissions of Pods that work with AWS
services.

Together, AWS IAM and Kubernetes RBAC enable least-privileged access for your
apps scoped to the appropriate policies and user requirements.

[k8s-rbac]: https://kubernetes.io/docs/reference/access-authn-authz/rbac/

<!--more-->

## Overview

In less than 100 lines of code, we'll demonstrate how EKS Pods can use AWS IAM to create
fine-grained permissions for apps that integrate with other AWS services.

* [Pod Access Control](#pod-access-control)
* [Create an OIDC provider](#create-an-oidc-provider)
* [Create IAM for a S3 app](#create-iam-for-a-s3-app)
* [Deploy a S3 app](#deploy-a-s3-app)
* [Wrap-Up](#wrap-up)
* [Next Steps](#next-steps)

## Pod Access Control

AWS EKS supports using IAM entities in a Pod [Service Account][k8s-sa] by
leveraging an [OIDC provider][aws-oidc] connected to the Kubernetes cluster.

Continuing with the example from the [AWS blog post][aws-pod-iam], when an [S3 app written in Go][s3-app] pushes
an object to a bucket with the AWS SDK, it will need write access to S3.

When a Pod is launched with a particular Service Account, the OIDC provider works
with Kubernetes to verify the Pod's identity, and in turn, collaborates with the
[AWS Secure Token Service (STS)][aws-sts] to grant the Pod temporary
credentials to use with the IAM role.

## Create an OIDC provider

Creating an OIDC provider is as simple as toggling the `createOidcProvider` option
in the definition of your EKS cluster.

When enabled, the OIDC provider will be created and associated with the
cluster's OIDC provider URL.

![Create an EKS Cluster and OIDC provider](cluster.svg)

## Create IAM for a S3 app

We'll use the OIDC provider URL and Amazon Resource Name (ARN) to compose the
[AssumeRoleWithWebIdentity][aws-assume-role-web], and S3 IAM policies that will
be attached to a new S3 IAM role.

After the role is configured, a Service Account for the S3 Pod is
created, and annotated with the ARN of the S3 role to bind the two together.

![Create the AWS IAM and Kubernetes Service Account for the Pod](iam.svg)

## Deploy a S3 app

We'll deploy the [S3 app][peks-oidc] to use the new IAM-backed Service Account.

Once the Pod is running, the Service Account annotation will be automatically
managed by a [Kubernetes dynamic admission controller][k8s-dynamic-webhook] run
by EKS on your behalf.

The [AWS EKS webhook][eks-webhook] manages Pod identity, and injects STS
credentials into the Pod to use with the S3 role.

With the credentials, the app can successfully upload data to S3.

![Deploy the S3 Pod using the IAM scoped Service Account](pod.svg)

## Wrap-Up

Leveraging AWS IAM for Pod workloads is a secure and effective means of limiting
privileged execution, and provides a native experience for users.

Pod IAM can be extended further by also using the Kubernetes RBAC system. This
allows configuring permissions for Kubernetes API resources, and handle scenarios
such as limiting the namespace an IAM role can use, and what resources can be
managed in the namespace.

## Next Steps

Learn more about how [Pulumi works with Kubernetes][pulumi-k8s], and [get started][p-get-started]
if you're new.

Check out code examples for the S3 app referenced in this post,
along with other access control scenarios for EKS.

* [S3 app: EKS and an OIDC provider for Pod IAM.][peks-oidc]
* [Create an EKS cluster with Kubernetes RBAC for a Developer scoped IAM role.][peks-scoped-kubeconfigs]
* [More EKS examples][eks-examples]

Watch the video below for more details on how OIDC and Kubernetes RBAC works in
EKS. We demonstrate how to deploy [fluentd-cloudwatch][fluentd-cloudwatch] with
IAM to forward Pod logs to [AWS CloudWatch][aws-cw].

You can also follow us on [Twitter](https://twitter.com/pulumicorp),
subscribe to [PulumiTV](https://www.youtube.com/channel/UC2Dhyn4Ev52YSbcpfnfP0Mw) on YouTube,
or join our [Community Slack](https://slack.pulumi.com/) channel if you have any questions.

{{< youtube "7qN9ABgmK9M" >}}

[peks-oidc]: https://github.com/pulumi/pulumi-eks/tree/master/nodejs/eks/examples/oidc-iam-sa
[peks-scoped-kubeconfigs]: https://github.com/pulumi/pulumi-eks/tree/master/nodejs/eks/examples/scoped-kubeconfigs
[fluentd-cloudwatch]: https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/Container-Insights-setup-logs.html
[aws-cw]: https://docs.aws.amazon.com/AmazonCloudWatch/latest/logs/WhatIsCloudWatchLogs.html
[aws-eks]: https://aws.amazon.com/eks/
[aws-iam]: https://aws.amazon.com/iam/
[aws-pod-iam]: https://aws.amazon.com/blogs/opensource/introducing-fine-grained-iam-roles-service-accounts/
[aws-oidc]: https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_providers_create_oidc.html
[s3-app]: https://github.com/mhausenblas/s3-echoer
[aws-sts]: https://docs.aws.amazon.com/STS/latest/APIReference/Welcome.html
[eks-examples]: https://github.com/pulumi/pulumi-eks/tree/master/nodejs/eks/examples
[aws-assume-role-web]: https://docs.aws.amazon.com/STS/latest/APIReference/API_AssumeRoleWithWebIdentity.html
[k8s-dynamic-webhook]: https://kubernetes.io/docs/reference/access-authn-authz/extensible-admission-controllers
[eks-webhook]: https://github.com/aws/amazon-eks-pod-identity-webhook/
[k8s-sa]: https://kubernetes.io/docs/tasks/configure-pod-container/configure-service-account/
[pulumi-k8s]: {{< relref "/docs/intro/cloud-providers/kubernetes" >}}
[p-get-started]: {{< relref "/docs/get-started/kubernetes" >}}
