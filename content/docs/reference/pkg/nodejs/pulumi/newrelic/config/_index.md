---
title: "Module config"
title_tag: "Module config | Package @pulumi/newrelic | Node.js SDK"
linktitle: "config"
meta_desc: "Explore members of the config module in the @pulumi/newrelic package."
git_sha: "1d68615b2750410c3a5737712f6b6892e001d03e"
---

<!-- WARNING: this page was generated by a tool. Do not edit it by hand. -->
<!-- To change it, please see https://github.com/pulumi/docs/tree/master/tools/tscdocgen. -->


> This provider is a derived work of the [Terraform Provider](https://github.com/terraform-providers/terraform-provider-newrelic)
> distributed under [MPL 2.0](https://www.mozilla.org/en-US/MPL/2.0/). If you encounter a bug or missing feature,
> first check the [`pulumi/pulumi-newrelic` repo](https://github.com/pulumi/pulumi-newrelic/issues); however, if that doesn't turn up anything,
> please consult the source [`terraform-providers/terraform-provider-newrelic` repo](https://github.com/terraform-providers/terraform-provider-newrelic/issues).







<h3>APIs</h3>
<ul class="api">
    <li><a href="#apiKey"><span class="symbol api"></span>apiKey</a></li>
    <li><a href="#apiUrl"><span class="symbol api"></span>apiUrl</a></li>
    <li><a href="#cacertFile"><span class="symbol api"></span>cacertFile</a></li>
    <li><a href="#infraApiUrl"><span class="symbol api"></span>infraApiUrl</a></li>
    <li><a href="#infrastructureApiUrl"><span class="symbol api"></span>infrastructureApiUrl</a></li>
    <li><a href="#insecureSkipVerify"><span class="symbol api"></span>insecureSkipVerify</a></li>
    <li><a href="#insightsAccountId"><span class="symbol api"></span>insightsAccountId</a></li>
    <li><a href="#insightsInsertKey"><span class="symbol api"></span>insightsInsertKey</a></li>
    <li><a href="#insightsInsertUrl"><span class="symbol api"></span>insightsInsertUrl</a></li>
    <li><a href="#insightsQueryKey"><span class="symbol api"></span>insightsQueryKey</a></li>
    <li><a href="#insightsQueryUrl"><span class="symbol api"></span>insightsQueryUrl</a></li>
    <li><a href="#nerdgraphApiUrl"><span class="symbol api"></span>nerdgraphApiUrl</a></li>
    <li><a href="#personalApiKey"><span class="symbol api"></span>personalApiKey</a></li>
    <li><a href="#syntheticsApiUrl"><span class="symbol api"></span>syntheticsApiUrl</a></li>
</ul>




<h2 id="apis">APIs</h2>
<h3 class="pdoc-module-header" id="apiKey" data-link-title="apiKey">
    <a href="https://github.com/pulumi/pulumi-newrelic/blob/1d68615b2750410c3a5737712f6b6892e001d03e/sdk/nodejs/config/vars.ts#L9">
        let <strong>apiKey</strong>
    </a>
</h3>

<pre class="highlight"><code><span class='kd'>let</span> apiKey: <span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span> | <span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined'>undefined</a></span> = <span class='s2'> __config.get(&#34;apiKey&#34;) || utilities.getEnv(&#34;NEWRELIC_API_KEY&#34;)</span>;</code></pre>
<h3 class="pdoc-module-header" id="apiUrl" data-link-title="apiUrl">
    <a href="https://github.com/pulumi/pulumi-newrelic/blob/1d68615b2750410c3a5737712f6b6892e001d03e/sdk/nodejs/config/vars.ts#L10">
        let <strong>apiUrl</strong>
    </a>
</h3>

<pre class="highlight"><code><span class='kd'>let</span> apiUrl: <span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span> | <span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined'>undefined</a></span> = <span class='s2'> __config.get(&#34;apiUrl&#34;) || (utilities.getEnv(&#34;NEWRELIC_API_URL&#34;) || &#34;https://api.newrelic.com/v2&#34;)</span>;</code></pre>
<h3 class="pdoc-module-header" id="cacertFile" data-link-title="cacertFile">
    <a href="https://github.com/pulumi/pulumi-newrelic/blob/1d68615b2750410c3a5737712f6b6892e001d03e/sdk/nodejs/config/vars.ts#L11">
        let <strong>cacertFile</strong>
    </a>
</h3>

<pre class="highlight"><code><span class='kd'>let</span> cacertFile: <span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span> | <span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined'>undefined</a></span> = <span class='s2'> __config.get(&#34;cacertFile&#34;) || utilities.getEnv(&#34;NEWRELIC_API_CACERT&#34;)</span>;</code></pre>
<h3 class="pdoc-module-header" id="infraApiUrl" data-link-title="infraApiUrl">
    <a href="https://github.com/pulumi/pulumi-newrelic/blob/1d68615b2750410c3a5737712f6b6892e001d03e/sdk/nodejs/config/vars.ts#L12">
        let <strong>infraApiUrl</strong>
    </a>
</h3>

<pre class="highlight"><code><span class='kd'>let</span> infraApiUrl: <span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span> | <span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined'>undefined</a></span> = <span class='s2'> __config.get(&#34;infraApiUrl&#34;) || (utilities.getEnv(&#34;NEWRELIC_INFRA_API_URL&#34;) || &#34;https://infra-api.newrelic.com/v2&#34;)</span>;</code></pre>
<h3 class="pdoc-module-header" id="infrastructureApiUrl" data-link-title="infrastructureApiUrl">
    <a href="https://github.com/pulumi/pulumi-newrelic/blob/1d68615b2750410c3a5737712f6b6892e001d03e/sdk/nodejs/config/vars.ts#L13">
        let <strong>infrastructureApiUrl</strong>
    </a>
</h3>

<pre class="highlight"><code><span class='kd'>let</span> infrastructureApiUrl: <span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span> | <span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined'>undefined</a></span> = <span class='s2'> __config.get(&#34;infrastructureApiUrl&#34;) || utilities.getEnv(&#34;NEWRELIC_INFRASTRUCTURE_API_URL&#34;)</span>;</code></pre>
<h3 class="pdoc-module-header" id="insecureSkipVerify" data-link-title="insecureSkipVerify">
    <a href="https://github.com/pulumi/pulumi-newrelic/blob/1d68615b2750410c3a5737712f6b6892e001d03e/sdk/nodejs/config/vars.ts#L14">
        let <strong>insecureSkipVerify</strong>
    </a>
</h3>

<pre class="highlight"><code><span class='kd'>let</span> insecureSkipVerify: <span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean'>boolean</a></span> | <span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined'>undefined</a></span> = <span class='s2'> __config.getObject&lt;boolean&gt;(&#34;insecureSkipVerify&#34;) || utilities.getEnvBoolean(&#34;NEWRELIC_API_SKIP_VERIFY&#34;)</span>;</code></pre>
<h3 class="pdoc-module-header" id="insightsAccountId" data-link-title="insightsAccountId">
    <a href="https://github.com/pulumi/pulumi-newrelic/blob/1d68615b2750410c3a5737712f6b6892e001d03e/sdk/nodejs/config/vars.ts#L15">
        let <strong>insightsAccountId</strong>
    </a>
</h3>

<pre class="highlight"><code><span class='kd'>let</span> insightsAccountId: <span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span> | <span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined'>undefined</a></span> = <span class='s2'> __config.get(&#34;insightsAccountId&#34;) || utilities.getEnv(&#34;NEWRELIC_INSIGHTS_ACCOUNT_ID&#34;)</span>;</code></pre>
<h3 class="pdoc-module-header" id="insightsInsertKey" data-link-title="insightsInsertKey">
    <a href="https://github.com/pulumi/pulumi-newrelic/blob/1d68615b2750410c3a5737712f6b6892e001d03e/sdk/nodejs/config/vars.ts#L16">
        let <strong>insightsInsertKey</strong>
    </a>
</h3>

<pre class="highlight"><code><span class='kd'>let</span> insightsInsertKey: <span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span> | <span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined'>undefined</a></span> = <span class='s2'> __config.get(&#34;insightsInsertKey&#34;) || utilities.getEnv(&#34;NEWRELIC_INSIGHTS_INSERT_KEY&#34;)</span>;</code></pre>
<h3 class="pdoc-module-header" id="insightsInsertUrl" data-link-title="insightsInsertUrl">
    <a href="https://github.com/pulumi/pulumi-newrelic/blob/1d68615b2750410c3a5737712f6b6892e001d03e/sdk/nodejs/config/vars.ts#L17">
        let <strong>insightsInsertUrl</strong>
    </a>
</h3>

<pre class="highlight"><code><span class='kd'>let</span> insightsInsertUrl: <span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span> | <span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined'>undefined</a></span> = <span class='s2'> __config.get(&#34;insightsInsertUrl&#34;) || (utilities.getEnv(&#34;NEWRELIC_INSIGHTS_INSERT_URL&#34;) || &#34;https://insights-collector.newrelic.com/v1/accounts&#34;)</span>;</code></pre>
<h3 class="pdoc-module-header" id="insightsQueryKey" data-link-title="insightsQueryKey">
    <a href="https://github.com/pulumi/pulumi-newrelic/blob/1d68615b2750410c3a5737712f6b6892e001d03e/sdk/nodejs/config/vars.ts#L18">
        let <strong>insightsQueryKey</strong>
    </a>
</h3>

<pre class="highlight"><code><span class='kd'>let</span> insightsQueryKey: <span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span> | <span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined'>undefined</a></span> = <span class='s2'> __config.get(&#34;insightsQueryKey&#34;) || utilities.getEnv(&#34;NEWRELIC_INSIGHTS_QUERY_KEY&#34;)</span>;</code></pre>
<h3 class="pdoc-module-header" id="insightsQueryUrl" data-link-title="insightsQueryUrl">
    <a href="https://github.com/pulumi/pulumi-newrelic/blob/1d68615b2750410c3a5737712f6b6892e001d03e/sdk/nodejs/config/vars.ts#L19">
        let <strong>insightsQueryUrl</strong>
    </a>
</h3>

<pre class="highlight"><code><span class='kd'>let</span> insightsQueryUrl: <span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span> | <span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined'>undefined</a></span> = <span class='s2'> __config.get(&#34;insightsQueryUrl&#34;) || (utilities.getEnv(&#34;NEWRELIC_INSIGHTS_QUERY_URL&#34;) || &#34;https://insights-api.newrelic.com/v1/accounts&#34;)</span>;</code></pre>
<h3 class="pdoc-module-header" id="nerdgraphApiUrl" data-link-title="nerdgraphApiUrl">
    <a href="https://github.com/pulumi/pulumi-newrelic/blob/1d68615b2750410c3a5737712f6b6892e001d03e/sdk/nodejs/config/vars.ts#L20">
        let <strong>nerdgraphApiUrl</strong>
    </a>
</h3>

<pre class="highlight"><code><span class='kd'>let</span> nerdgraphApiUrl: <span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span> | <span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined'>undefined</a></span> = <span class='s2'> __config.get(&#34;nerdgraphApiUrl&#34;) || utilities.getEnv(&#34;NEWRELIC_NERDGRAPH_API_URL&#34;)</span>;</code></pre>
<h3 class="pdoc-module-header" id="personalApiKey" data-link-title="personalApiKey">
    <a href="https://github.com/pulumi/pulumi-newrelic/blob/1d68615b2750410c3a5737712f6b6892e001d03e/sdk/nodejs/config/vars.ts#L21">
        let <strong>personalApiKey</strong>
    </a>
</h3>

<pre class="highlight"><code><span class='kd'>let</span> personalApiKey: <span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span> | <span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined'>undefined</a></span> = <span class='s2'> __config.get(&#34;personalApiKey&#34;) || utilities.getEnv(&#34;NEWRELIC_PERSONAL_API_KEY&#34;)</span>;</code></pre>
<h3 class="pdoc-module-header" id="syntheticsApiUrl" data-link-title="syntheticsApiUrl">
    <a href="https://github.com/pulumi/pulumi-newrelic/blob/1d68615b2750410c3a5737712f6b6892e001d03e/sdk/nodejs/config/vars.ts#L22">
        let <strong>syntheticsApiUrl</strong>
    </a>
</h3>

<pre class="highlight"><code><span class='kd'>let</span> syntheticsApiUrl: <span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span> | <span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined'>undefined</a></span> = <span class='s2'> __config.get(&#34;syntheticsApiUrl&#34;) || (utilities.getEnv(&#34;NEWRELIC_SYNTHETICS_API_URL&#34;) || &#34;https://synthetics.newrelic.com/synthetics/api/v3&#34;)</span>;</code></pre>
