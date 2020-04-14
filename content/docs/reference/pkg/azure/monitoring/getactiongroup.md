
---
title: "GetActionGroup"
block_external_search_index: true
---



Use this data source to access the properties of an Action Group.

> This content is derived from https://github.com/terraform-providers/terraform-provider-azurerm/blob/master/website/docs/d/monitor_action_group.html.markdown.





## Using GetActionGroup

{{< chooser language "javascript,typescript,python,go,csharp" / >}}


{{% choosable language typescript %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">function </span>getActionGroup<span class="p">(</span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/azure/monitoring/#GetActionGroupArgs">GetActionGroupArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#InvokeOptions">InvokeOptions</a></span><span class="p">): Promise&lt;<span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/azure/monitoring/#GetActionGroupResult">GetActionGroupResult</a></span>></span></code></pre></div>
{{% /choosable %}}


{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">function </span> get_action_group(</span>name=None<span class="p">, </span>resource_group_name=None<span class="p">, </span>opts=None<span class="p">)</span></code></pre></div>
{{% /choosable %}}


{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>LookupActionGroup<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">Context</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/monitoring?tab=doc#LookupActionGroupArgs">LookupActionGroupArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#InvokeOption">InvokeOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/monitoring?tab=doc#LookupActionGroupResult">LookupActionGroupResult</a></span>, error)</span></code></pre></div>
{{% /choosable %}}


{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static class </span><span class="nx">GetActionGroup </span><span class="p">{</span><span class="k">
    public static </span>Task&lt;<span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Monitoring.GetActionGroupResult.html">GetActionGroupResult</a></span>> <span class="p">InvokeAsync(</span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Monitoring.GetActionGroupArgs.html">GetActionGroupArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.InvokeOptions.html">InvokeOptions</a></span>? <span class="nx">opts = null<span class="p">)</span><span class="p">
}</span></code></pre></div>
{{% /choosable %}}



The following arguments are supported:



{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">
        <span>Name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies the name of the Action Group.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>Resource<wbr>Group<wbr>Name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies the name of the resource group the Action Group is located in.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">
        <span>Name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies the name of the Action Group.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>Resource<wbr>Group<wbr>Name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies the name of the resource group the Action Group is located in.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">
        <span>name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies the name of the Action Group.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>resource<wbr>Group<wbr>Name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies the name of the resource group the Action Group is located in.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">
        <span>name</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specifies the name of the Action Group.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>resource_<wbr>group_<wbr>name</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specifies the name of the resource group the Action Group is located in.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}








## GetActionGroup Result

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">
        <span>Arm<wbr>Role<wbr>Receivers</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getactiongrouparmrolereceiver">List&lt;Get<wbr>Action<wbr>Group<wbr>Arm<wbr>Role<wbr>Receiver&gt;</a></span>
    </dt>
    <dd>{{% md %}}One or more `arm_role_receiver` blocks as defined below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>Automation<wbr>Runbook<wbr>Receivers</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getactiongroupautomationrunbookreceiver">List&lt;Get<wbr>Action<wbr>Group<wbr>Automation<wbr>Runbook<wbr>Receiver&gt;</a></span>
    </dt>
    <dd>{{% md %}}One or more `automation_runbook_receiver` blocks as defined below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>Azure<wbr>App<wbr>Push<wbr>Receivers</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getactiongroupazureapppushreceiver">List&lt;Get<wbr>Action<wbr>Group<wbr>Azure<wbr>App<wbr>Push<wbr>Receiver&gt;</a></span>
    </dt>
    <dd>{{% md %}}One or more `azure_app_push_receiver` blocks as defined below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>Azure<wbr>Function<wbr>Receivers</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getactiongroupazurefunctionreceiver">List&lt;Get<wbr>Action<wbr>Group<wbr>Azure<wbr>Function<wbr>Receiver&gt;</a></span>
    </dt>
    <dd>{{% md %}}One or more `azure_function_receiver` blocks as defined below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>Email<wbr>Receivers</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getactiongroupemailreceiver">List&lt;Get<wbr>Action<wbr>Group<wbr>Email<wbr>Receiver&gt;</a></span>
    </dt>
    <dd>{{% md %}}One or more `email_receiver` blocks as defined below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>Enabled</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether this action group is enabled.
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>Id</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}id is the provider-assigned unique ID for this managed resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>Itsm<wbr>Receivers</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getactiongroupitsmreceiver">List&lt;Get<wbr>Action<wbr>Group<wbr>Itsm<wbr>Receiver&gt;</a></span>
    </dt>
    <dd>{{% md %}}One or more `itsm_receiver` blocks as defined below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>Logic<wbr>App<wbr>Receivers</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getactiongrouplogicappreceiver">List&lt;Get<wbr>Action<wbr>Group<wbr>Logic<wbr>App<wbr>Receiver&gt;</a></span>
    </dt>
    <dd>{{% md %}}One or more `logic_app_receiver` blocks as defined below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>Name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the webhook receiver.
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>Resource<wbr>Group<wbr>Name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>Short<wbr>Name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The short name of the action group.
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>Sms<wbr>Receivers</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getactiongroupsmsreceiver">List&lt;Get<wbr>Action<wbr>Group<wbr>Sms<wbr>Receiver&gt;</a></span>
    </dt>
    <dd>{{% md %}}One or more `sms_receiver` blocks as defined below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>Voice<wbr>Receivers</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getactiongroupvoicereceiver">List&lt;Get<wbr>Action<wbr>Group<wbr>Voice<wbr>Receiver&gt;</a></span>
    </dt>
    <dd>{{% md %}}One or more `voice_receiver` blocks as defined below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>Webhook<wbr>Receivers</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getactiongroupwebhookreceiver">List&lt;Get<wbr>Action<wbr>Group<wbr>Webhook<wbr>Receiver&gt;</a></span>
    </dt>
    <dd>{{% md %}}One or more `webhook_receiver` blocks as defined below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">
        <span>Arm<wbr>Role<wbr>Receivers</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getactiongrouparmrolereceiver">[]Get<wbr>Action<wbr>Group<wbr>Arm<wbr>Role<wbr>Receiver</a></span>
    </dt>
    <dd>{{% md %}}One or more `arm_role_receiver` blocks as defined below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>Automation<wbr>Runbook<wbr>Receivers</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getactiongroupautomationrunbookreceiver">[]Get<wbr>Action<wbr>Group<wbr>Automation<wbr>Runbook<wbr>Receiver</a></span>
    </dt>
    <dd>{{% md %}}One or more `automation_runbook_receiver` blocks as defined below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>Azure<wbr>App<wbr>Push<wbr>Receivers</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getactiongroupazureapppushreceiver">[]Get<wbr>Action<wbr>Group<wbr>Azure<wbr>App<wbr>Push<wbr>Receiver</a></span>
    </dt>
    <dd>{{% md %}}One or more `azure_app_push_receiver` blocks as defined below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>Azure<wbr>Function<wbr>Receivers</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getactiongroupazurefunctionreceiver">[]Get<wbr>Action<wbr>Group<wbr>Azure<wbr>Function<wbr>Receiver</a></span>
    </dt>
    <dd>{{% md %}}One or more `azure_function_receiver` blocks as defined below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>Email<wbr>Receivers</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getactiongroupemailreceiver">[]Get<wbr>Action<wbr>Group<wbr>Email<wbr>Receiver</a></span>
    </dt>
    <dd>{{% md %}}One or more `email_receiver` blocks as defined below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>Enabled</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether this action group is enabled.
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>Id</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}id is the provider-assigned unique ID for this managed resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>Itsm<wbr>Receivers</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getactiongroupitsmreceiver">[]Get<wbr>Action<wbr>Group<wbr>Itsm<wbr>Receiver</a></span>
    </dt>
    <dd>{{% md %}}One or more `itsm_receiver` blocks as defined below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>Logic<wbr>App<wbr>Receivers</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getactiongrouplogicappreceiver">[]Get<wbr>Action<wbr>Group<wbr>Logic<wbr>App<wbr>Receiver</a></span>
    </dt>
    <dd>{{% md %}}One or more `logic_app_receiver` blocks as defined below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>Name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the webhook receiver.
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>Resource<wbr>Group<wbr>Name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>Short<wbr>Name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The short name of the action group.
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>Sms<wbr>Receivers</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getactiongroupsmsreceiver">[]Get<wbr>Action<wbr>Group<wbr>Sms<wbr>Receiver</a></span>
    </dt>
    <dd>{{% md %}}One or more `sms_receiver` blocks as defined below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>Voice<wbr>Receivers</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getactiongroupvoicereceiver">[]Get<wbr>Action<wbr>Group<wbr>Voice<wbr>Receiver</a></span>
    </dt>
    <dd>{{% md %}}One or more `voice_receiver` blocks as defined below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>Webhook<wbr>Receivers</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getactiongroupwebhookreceiver">[]Get<wbr>Action<wbr>Group<wbr>Webhook<wbr>Receiver</a></span>
    </dt>
    <dd>{{% md %}}One or more `webhook_receiver` blocks as defined below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">
        <span>arm<wbr>Role<wbr>Receivers</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getactiongrouparmrolereceiver">Get<wbr>Action<wbr>Group<wbr>Arm<wbr>Role<wbr>Receiver[]</a></span>
    </dt>
    <dd>{{% md %}}One or more `arm_role_receiver` blocks as defined below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>automation<wbr>Runbook<wbr>Receivers</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getactiongroupautomationrunbookreceiver">Get<wbr>Action<wbr>Group<wbr>Automation<wbr>Runbook<wbr>Receiver[]</a></span>
    </dt>
    <dd>{{% md %}}One or more `automation_runbook_receiver` blocks as defined below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>azure<wbr>App<wbr>Push<wbr>Receivers</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getactiongroupazureapppushreceiver">Get<wbr>Action<wbr>Group<wbr>Azure<wbr>App<wbr>Push<wbr>Receiver[]</a></span>
    </dt>
    <dd>{{% md %}}One or more `azure_app_push_receiver` blocks as defined below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>azure<wbr>Function<wbr>Receivers</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getactiongroupazurefunctionreceiver">Get<wbr>Action<wbr>Group<wbr>Azure<wbr>Function<wbr>Receiver[]</a></span>
    </dt>
    <dd>{{% md %}}One or more `azure_function_receiver` blocks as defined below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>email<wbr>Receivers</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getactiongroupemailreceiver">Get<wbr>Action<wbr>Group<wbr>Email<wbr>Receiver[]</a></span>
    </dt>
    <dd>{{% md %}}One or more `email_receiver` blocks as defined below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>enabled</span>
        <span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}Whether this action group is enabled.
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>id</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}id is the provider-assigned unique ID for this managed resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>itsm<wbr>Receivers</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getactiongroupitsmreceiver">Get<wbr>Action<wbr>Group<wbr>Itsm<wbr>Receiver[]</a></span>
    </dt>
    <dd>{{% md %}}One or more `itsm_receiver` blocks as defined below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>logic<wbr>App<wbr>Receivers</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getactiongrouplogicappreceiver">Get<wbr>Action<wbr>Group<wbr>Logic<wbr>App<wbr>Receiver[]</a></span>
    </dt>
    <dd>{{% md %}}One or more `logic_app_receiver` blocks as defined below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the webhook receiver.
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>resource<wbr>Group<wbr>Name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>short<wbr>Name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The short name of the action group.
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>sms<wbr>Receivers</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getactiongroupsmsreceiver">Get<wbr>Action<wbr>Group<wbr>Sms<wbr>Receiver[]</a></span>
    </dt>
    <dd>{{% md %}}One or more `sms_receiver` blocks as defined below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>voice<wbr>Receivers</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getactiongroupvoicereceiver">Get<wbr>Action<wbr>Group<wbr>Voice<wbr>Receiver[]</a></span>
    </dt>
    <dd>{{% md %}}One or more `voice_receiver` blocks as defined below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>webhook<wbr>Receivers</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getactiongroupwebhookreceiver">Get<wbr>Action<wbr>Group<wbr>Webhook<wbr>Receiver[]</a></span>
    </dt>
    <dd>{{% md %}}One or more `webhook_receiver` blocks as defined below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">
        <span>arm_<wbr>role_<wbr>receivers</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getactiongrouparmrolereceiver">List[Get<wbr>Action<wbr>Group<wbr>Arm<wbr>Role<wbr>Receiver]</a></span>
    </dt>
    <dd>{{% md %}}One or more `arm_role_receiver` blocks as defined below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>automation_<wbr>runbook_<wbr>receivers</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getactiongroupautomationrunbookreceiver">List[Get<wbr>Action<wbr>Group<wbr>Automation<wbr>Runbook<wbr>Receiver]</a></span>
    </dt>
    <dd>{{% md %}}One or more `automation_runbook_receiver` blocks as defined below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>azure_<wbr>app_<wbr>push_<wbr>receivers</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getactiongroupazureapppushreceiver">List[Get<wbr>Action<wbr>Group<wbr>Azure<wbr>App<wbr>Push<wbr>Receiver]</a></span>
    </dt>
    <dd>{{% md %}}One or more `azure_app_push_receiver` blocks as defined below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>azure_<wbr>function_<wbr>receivers</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getactiongroupazurefunctionreceiver">List[Get<wbr>Action<wbr>Group<wbr>Azure<wbr>Function<wbr>Receiver]</a></span>
    </dt>
    <dd>{{% md %}}One or more `azure_function_receiver` blocks as defined below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>email_<wbr>receivers</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getactiongroupemailreceiver">List[Get<wbr>Action<wbr>Group<wbr>Email<wbr>Receiver]</a></span>
    </dt>
    <dd>{{% md %}}One or more `email_receiver` blocks as defined below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>enabled</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether this action group is enabled.
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>id</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}id is the provider-assigned unique ID for this managed resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>itsm_<wbr>receivers</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getactiongroupitsmreceiver">List[Get<wbr>Action<wbr>Group<wbr>Itsm<wbr>Receiver]</a></span>
    </dt>
    <dd>{{% md %}}One or more `itsm_receiver` blocks as defined below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>logic_<wbr>app_<wbr>receivers</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getactiongrouplogicappreceiver">List[Get<wbr>Action<wbr>Group<wbr>Logic<wbr>App<wbr>Receiver]</a></span>
    </dt>
    <dd>{{% md %}}One or more `logic_app_receiver` blocks as defined below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>name</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the webhook receiver.
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>resource_<wbr>group_<wbr>name</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>short_<wbr>name</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The short name of the action group.
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>sms_<wbr>receivers</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getactiongroupsmsreceiver">List[Get<wbr>Action<wbr>Group<wbr>Sms<wbr>Receiver]</a></span>
    </dt>
    <dd>{{% md %}}One or more `sms_receiver` blocks as defined below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>voice_<wbr>receivers</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getactiongroupvoicereceiver">List[Get<wbr>Action<wbr>Group<wbr>Voice<wbr>Receiver]</a></span>
    </dt>
    <dd>{{% md %}}One or more `voice_receiver` blocks as defined below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>webhook_<wbr>receivers</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getactiongroupwebhookreceiver">List[Get<wbr>Action<wbr>Group<wbr>Webhook<wbr>Receiver]</a></span>
    </dt>
    <dd>{{% md %}}One or more `webhook_receiver` blocks as defined below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}








## Supporting Types

<h4>Get<wbr>Action<wbr>Group<wbr>Arm<wbr>Role<wbr>Receiver</h4>
{{% choosable language nodejs %}}
> See the   <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#GetActionGroupArmRoleReceiver">output</a> API doc for this type.
{{% /choosable %}}

{{% choosable language go %}}
> See the   <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/monitoring?tab=doc#GetActionGroupArmRoleReceiver">output</a> API doc for this type.
{{% /choosable %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">
        <span>Name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies the name of the Action Group.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>Role<wbr>Id</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The arm role id.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>Use<wbr>Common<wbr>Alert<wbr>Schema</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Indicates whether to use common alert schema.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">
        <span>Name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies the name of the Action Group.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>Role<wbr>Id</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The arm role id.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>Use<wbr>Common<wbr>Alert<wbr>Schema</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Indicates whether to use common alert schema.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">
        <span>name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies the name of the Action Group.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>role<wbr>Id</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The arm role id.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>use<wbr>Common<wbr>Alert<wbr>Schema</span>
        <span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}Indicates whether to use common alert schema.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">
        <span>name</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specifies the name of the Action Group.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>role<wbr>Id</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The arm role id.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>use<wbr>Common<wbr>Alert<wbr>Schema</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Indicates whether to use common alert schema.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





<h4>Get<wbr>Action<wbr>Group<wbr>Automation<wbr>Runbook<wbr>Receiver</h4>
{{% choosable language nodejs %}}
> See the   <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#GetActionGroupAutomationRunbookReceiver">output</a> API doc for this type.
{{% /choosable %}}

{{% choosable language go %}}
> See the   <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/monitoring?tab=doc#GetActionGroupAutomationRunbookReceiver">output</a> API doc for this type.
{{% /choosable %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">
        <span>Automation<wbr>Account<wbr>Id</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The automation account ID which holds this runbook and authenticates to Azure resources.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>Is<wbr>Global<wbr>Runbook</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Indicates whether this instance is global runbook.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>Name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies the name of the Action Group.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>Runbook<wbr>Name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name for this runbook.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>Service<wbr>Uri</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The URI where webhooks should be sent.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>Use<wbr>Common<wbr>Alert<wbr>Schema</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Indicates whether to use common alert schema.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>Webhook<wbr>Resource<wbr>Id</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The resource id for webhook linked to this runbook.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">
        <span>Automation<wbr>Account<wbr>Id</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The automation account ID which holds this runbook and authenticates to Azure resources.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>Is<wbr>Global<wbr>Runbook</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Indicates whether this instance is global runbook.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>Name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies the name of the Action Group.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>Runbook<wbr>Name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name for this runbook.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>Service<wbr>Uri</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The URI where webhooks should be sent.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>Use<wbr>Common<wbr>Alert<wbr>Schema</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Indicates whether to use common alert schema.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>Webhook<wbr>Resource<wbr>Id</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The resource id for webhook linked to this runbook.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">
        <span>automation<wbr>Account<wbr>Id</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The automation account ID which holds this runbook and authenticates to Azure resources.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>is<wbr>Global<wbr>Runbook</span>
        <span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}Indicates whether this instance is global runbook.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies the name of the Action Group.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>runbook<wbr>Name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name for this runbook.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>service<wbr>Uri</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The URI where webhooks should be sent.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>use<wbr>Common<wbr>Alert<wbr>Schema</span>
        <span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}Indicates whether to use common alert schema.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>webhook<wbr>Resource<wbr>Id</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The resource id for webhook linked to this runbook.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">
        <span>automation<wbr>Account<wbr>Id</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The automation account ID which holds this runbook and authenticates to Azure resources.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>is<wbr>Global<wbr>Runbook</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Indicates whether this instance is global runbook.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>name</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specifies the name of the Action Group.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>runbook_<wbr>name</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name for this runbook.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>service_<wbr>uri</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The URI where webhooks should be sent.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>use<wbr>Common<wbr>Alert<wbr>Schema</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Indicates whether to use common alert schema.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>webhook<wbr>Resource<wbr>Id</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The resource id for webhook linked to this runbook.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





<h4>Get<wbr>Action<wbr>Group<wbr>Azure<wbr>App<wbr>Push<wbr>Receiver</h4>
{{% choosable language nodejs %}}
> See the   <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#GetActionGroupAzureAppPushReceiver">output</a> API doc for this type.
{{% /choosable %}}

{{% choosable language go %}}
> See the   <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/monitoring?tab=doc#GetActionGroupAzureAppPushReceiver">output</a> API doc for this type.
{{% /choosable %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">
        <span>Email<wbr>Address</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The email address of this receiver.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>Name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies the name of the Action Group.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">
        <span>Email<wbr>Address</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The email address of this receiver.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>Name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies the name of the Action Group.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">
        <span>email<wbr>Address</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The email address of this receiver.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies the name of the Action Group.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">
        <span>email_<wbr>address</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The email address of this receiver.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>name</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specifies the name of the Action Group.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





<h4>Get<wbr>Action<wbr>Group<wbr>Azure<wbr>Function<wbr>Receiver</h4>
{{% choosable language nodejs %}}
> See the   <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#GetActionGroupAzureFunctionReceiver">output</a> API doc for this type.
{{% /choosable %}}

{{% choosable language go %}}
> See the   <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/monitoring?tab=doc#GetActionGroupAzureFunctionReceiver">output</a> API doc for this type.
{{% /choosable %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">
        <span>Function<wbr>App<wbr>Resource<wbr>Id</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>Function<wbr>Name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The function name in the function app.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>Http<wbr>Trigger<wbr>Url</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The http trigger url where http request sent to.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>Name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies the name of the Action Group.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>Use<wbr>Common<wbr>Alert<wbr>Schema</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Indicates whether to use common alert schema.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">
        <span>Function<wbr>App<wbr>Resource<wbr>Id</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>Function<wbr>Name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The function name in the function app.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>Http<wbr>Trigger<wbr>Url</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The http trigger url where http request sent to.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>Name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies the name of the Action Group.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>Use<wbr>Common<wbr>Alert<wbr>Schema</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Indicates whether to use common alert schema.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">
        <span>function<wbr>App<wbr>Resource<wbr>Id</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>function<wbr>Name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The function name in the function app.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>http<wbr>Trigger<wbr>Url</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The http trigger url where http request sent to.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies the name of the Action Group.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>use<wbr>Common<wbr>Alert<wbr>Schema</span>
        <span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}Indicates whether to use common alert schema.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">
        <span>function<wbr>App<wbr>Resource<wbr>Id</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>function<wbr>Name</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The function name in the function app.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>http<wbr>Trigger<wbr>Url</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The http trigger url where http request sent to.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>name</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specifies the name of the Action Group.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>use<wbr>Common<wbr>Alert<wbr>Schema</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Indicates whether to use common alert schema.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





<h4>Get<wbr>Action<wbr>Group<wbr>Email<wbr>Receiver</h4>
{{% choosable language nodejs %}}
> See the   <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#GetActionGroupEmailReceiver">output</a> API doc for this type.
{{% /choosable %}}

{{% choosable language go %}}
> See the   <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/monitoring?tab=doc#GetActionGroupEmailReceiver">output</a> API doc for this type.
{{% /choosable %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">
        <span>Email<wbr>Address</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The email address of this receiver.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>Name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies the name of the Action Group.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>Use<wbr>Common<wbr>Alert<wbr>Schema</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Indicates whether to use common alert schema.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">
        <span>Email<wbr>Address</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The email address of this receiver.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>Name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies the name of the Action Group.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>Use<wbr>Common<wbr>Alert<wbr>Schema</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Indicates whether to use common alert schema.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">
        <span>email<wbr>Address</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The email address of this receiver.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies the name of the Action Group.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>use<wbr>Common<wbr>Alert<wbr>Schema</span>
        <span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}Indicates whether to use common alert schema.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">
        <span>email_<wbr>address</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The email address of this receiver.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>name</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specifies the name of the Action Group.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>use<wbr>Common<wbr>Alert<wbr>Schema</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Indicates whether to use common alert schema.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





<h4>Get<wbr>Action<wbr>Group<wbr>Itsm<wbr>Receiver</h4>
{{% choosable language nodejs %}}
> See the   <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#GetActionGroupItsmReceiver">output</a> API doc for this type.
{{% /choosable %}}

{{% choosable language go %}}
> See the   <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/monitoring?tab=doc#GetActionGroupItsmReceiver">output</a> API doc for this type.
{{% /choosable %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">
        <span>Connection<wbr>Id</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The unique connection identifier of the ITSM connection.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>Name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies the name of the Action Group.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>Region</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The region of the workspace.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>Ticket<wbr>Configuration</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A JSON blob for the configurations of the ITSM action. CreateMultipleWorkItems option will be part of this blob as well.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>Workspace<wbr>Id</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Azure Log Analytics workspace ID where this connection is defined.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">
        <span>Connection<wbr>Id</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The unique connection identifier of the ITSM connection.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>Name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies the name of the Action Group.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>Region</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The region of the workspace.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>Ticket<wbr>Configuration</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A JSON blob for the configurations of the ITSM action. CreateMultipleWorkItems option will be part of this blob as well.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>Workspace<wbr>Id</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Azure Log Analytics workspace ID where this connection is defined.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">
        <span>connection<wbr>Id</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The unique connection identifier of the ITSM connection.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies the name of the Action Group.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>region</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The region of the workspace.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>ticket<wbr>Configuration</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A JSON blob for the configurations of the ITSM action. CreateMultipleWorkItems option will be part of this blob as well.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>workspace<wbr>Id</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Azure Log Analytics workspace ID where this connection is defined.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">
        <span>connection<wbr>Id</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The unique connection identifier of the ITSM connection.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>name</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specifies the name of the Action Group.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>region</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The region of the workspace.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>ticket<wbr>Configuration</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A JSON blob for the configurations of the ITSM action. CreateMultipleWorkItems option will be part of this blob as well.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>workspace_<wbr>id</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Azure Log Analytics workspace ID where this connection is defined.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





<h4>Get<wbr>Action<wbr>Group<wbr>Logic<wbr>App<wbr>Receiver</h4>
{{% choosable language nodejs %}}
> See the   <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#GetActionGroupLogicAppReceiver">output</a> API doc for this type.
{{% /choosable %}}

{{% choosable language go %}}
> See the   <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/monitoring?tab=doc#GetActionGroupLogicAppReceiver">output</a> API doc for this type.
{{% /choosable %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">
        <span>Callback<wbr>Url</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The callback url where http request sent to.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>Name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies the name of the Action Group.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>Resource<wbr>Id</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Azure resource ID of the logic app.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>Use<wbr>Common<wbr>Alert<wbr>Schema</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Indicates whether to use common alert schema.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">
        <span>Callback<wbr>Url</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The callback url where http request sent to.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>Name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies the name of the Action Group.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>Resource<wbr>Id</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Azure resource ID of the logic app.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>Use<wbr>Common<wbr>Alert<wbr>Schema</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Indicates whether to use common alert schema.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">
        <span>callback<wbr>Url</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The callback url where http request sent to.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies the name of the Action Group.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>resource<wbr>Id</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Azure resource ID of the logic app.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>use<wbr>Common<wbr>Alert<wbr>Schema</span>
        <span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}Indicates whether to use common alert schema.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">
        <span>callback<wbr>Url</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The callback url where http request sent to.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>name</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specifies the name of the Action Group.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>resource_<wbr>id</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Azure resource ID of the logic app.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>use<wbr>Common<wbr>Alert<wbr>Schema</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Indicates whether to use common alert schema.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





<h4>Get<wbr>Action<wbr>Group<wbr>Sms<wbr>Receiver</h4>
{{% choosable language nodejs %}}
> See the   <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#GetActionGroupSmsReceiver">output</a> API doc for this type.
{{% /choosable %}}

{{% choosable language go %}}
> See the   <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/monitoring?tab=doc#GetActionGroupSmsReceiver">output</a> API doc for this type.
{{% /choosable %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">
        <span>Country<wbr>Code</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The country code of the voice receiver.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>Name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies the name of the Action Group.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>Phone<wbr>Number</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The phone number of the voice receiver.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">
        <span>Country<wbr>Code</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The country code of the voice receiver.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>Name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies the name of the Action Group.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>Phone<wbr>Number</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The phone number of the voice receiver.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">
        <span>country<wbr>Code</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The country code of the voice receiver.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies the name of the Action Group.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>phone<wbr>Number</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The phone number of the voice receiver.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">
        <span>country<wbr>Code</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The country code of the voice receiver.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>name</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specifies the name of the Action Group.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>phone<wbr>Number</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The phone number of the voice receiver.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





<h4>Get<wbr>Action<wbr>Group<wbr>Voice<wbr>Receiver</h4>
{{% choosable language nodejs %}}
> See the   <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#GetActionGroupVoiceReceiver">output</a> API doc for this type.
{{% /choosable %}}

{{% choosable language go %}}
> See the   <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/monitoring?tab=doc#GetActionGroupVoiceReceiver">output</a> API doc for this type.
{{% /choosable %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">
        <span>Country<wbr>Code</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The country code of the voice receiver.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>Name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies the name of the Action Group.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>Phone<wbr>Number</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The phone number of the voice receiver.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">
        <span>Country<wbr>Code</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The country code of the voice receiver.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>Name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies the name of the Action Group.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>Phone<wbr>Number</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The phone number of the voice receiver.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">
        <span>country<wbr>Code</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The country code of the voice receiver.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies the name of the Action Group.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>phone<wbr>Number</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The phone number of the voice receiver.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">
        <span>country<wbr>Code</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The country code of the voice receiver.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>name</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specifies the name of the Action Group.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>phone<wbr>Number</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The phone number of the voice receiver.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





<h4>Get<wbr>Action<wbr>Group<wbr>Webhook<wbr>Receiver</h4>
{{% choosable language nodejs %}}
> See the   <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#GetActionGroupWebhookReceiver">output</a> API doc for this type.
{{% /choosable %}}

{{% choosable language go %}}
> See the   <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/monitoring?tab=doc#GetActionGroupWebhookReceiver">output</a> API doc for this type.
{{% /choosable %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">
        <span>Name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies the name of the Action Group.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>Service<wbr>Uri</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The URI where webhooks should be sent.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Use<wbr>Common<wbr>Alert<wbr>Schema</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Indicates whether to use common alert schema.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">
        <span>Name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies the name of the Action Group.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>Service<wbr>Uri</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The URI where webhooks should be sent.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Use<wbr>Common<wbr>Alert<wbr>Schema</span>
        <span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Indicates whether to use common alert schema.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">
        <span>name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies the name of the Action Group.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>service<wbr>Uri</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The URI where webhooks should be sent.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>use<wbr>Common<wbr>Alert<wbr>Schema</span>
        <span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Indicates whether to use common alert schema.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">
        <span>name</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specifies the name of the Action Group.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>service_<wbr>uri</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The URI where webhooks should be sent.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>use<wbr>Common<wbr>Alert<wbr>Schema</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Indicates whether to use common alert schema.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}






