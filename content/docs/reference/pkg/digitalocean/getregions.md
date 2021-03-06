
---
title: "GetRegions"
title_tag: "Function GetRegions | Package Digital Ocean"
meta_desc: "Explore the GetRegions function of the Digital Ocean package, including examples, input properties, output properties, and supporting types. Retrieve information about all supported DigitalOcean regions, with the ability to"
---



<!-- WARNING: this file was generated by Pulumi Docs Generator. -->
<!-- Do not edit by hand unless you're certain you know what you are doing! -->

Retrieve information about all supported DigitalOcean regions, with the ability to
filter and sort the results. If no filters are specified, all regions will be returned.

Note: You can use the [`digitalocean..getRegion`](https://www.terraform.io/docs/providers/do/d/region.html) data source
to obtain metadata about a single region if you already know the `slug` to retrieve.



{{% examples %}}
## Example Usage

{{< chooser language "typescript,python,go,csharp" / >}}

{{% example csharp %}}
Coming soon!
{{% /example %}}

{{% example go %}}
Coming soon!
{{% /example %}}

{{% example python %}}
```python
import pulumi
import pulumi_digitalocean as digitalocean

available = digitalocean.get_regions(filters=[{
    "key": "available",
    "values": ["true"],
}])
```
{{% /example %}}

{{% example typescript %}}
```typescript
import * as pulumi from "@pulumi/pulumi";
import * as digitalocean from "@pulumi/digitalocean";

const available = pulumi.output(digitalocean.getRegions({
    filters: [{
        key: "available",
        values: ["true"],
    }],
}, { async: true }));
```
{{% /example %}}

{{% /examples %}}


## Using GetRegions {#using}

{{< chooser language "typescript,python,go,csharp" / >}}


{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">function </span>getRegions<span class="p">(</span><span class="nx">args</span><span class="p">:</span> <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/digitalocean/#GetRegionsArgs">GetRegionsArgs</a></span><span class="p">, </span><span class="nx">opts</span><span class="p">?:</span> <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#InvokeOptions">InvokeOptions</a></span><span class="p">): Promise&lt;<span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/digitalocean/#GetRegionsResult">GetRegionsResult</a></span>></span></code></pre></div>
{{% /choosable %}}


{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">function </span> get_regions(</span>filters=None<span class="p">, </span>sorts=None<span class="p">, </span>opts=None<span class="p">)</span></code></pre></div>
{{% /choosable %}}


{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetRegions<span class="p">(</span><span class="nx">ctx</span><span class="p"> *</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v2/go/pulumi?tab=doc#Context">Context</a></span><span class="p">, </span><span class="nx">args</span><span class="p"> *</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-digitalocean/sdk/v2/go/digitalocean/?tab=doc#GetRegionsArgs">GetRegionsArgs</a></span><span class="p">, </span><span class="nx">opts</span><span class="p"> ...</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v2/go/pulumi?tab=doc#InvokeOption">InvokeOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-digitalocean/sdk/v2/go/digitalocean/?tab=doc#GetRegionsResult">GetRegionsResult</a></span>, error)</span></code></pre></div>

{{% /choosable %}}


{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static class </span><span class="nx">GetRegions </span><span class="p">{</span><span class="k">
    public static </span>Task&lt;<span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.DigitalOcean/Pulumi.DigitalOcean.GetRegionsResult.html">GetRegionsResult</a></span>> <span class="p">InvokeAsync(</span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.DigitalOcean/Pulumi.DigitalOcean.GetRegionsArgs.html">GetRegionsArgs</a></span><span class="p"> </span><span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.InvokeOptions.html">InvokeOptions</a></span><span class="p">? </span><span class="nx">opts = null<span class="p">)</span><span class="p">
}</span></code></pre></div>
{{% /choosable %}}



The following arguments are supported:



{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">
        <span>Filters</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getregionsfilter">List&lt;Pulumi.<wbr>Digital<wbr>Ocean.<wbr>Inputs.<wbr>Get<wbr>Regions<wbr>Filter<wbr>Args&gt;</a></span>
    </dt>
    <dd>{{% md %}}Filter the results.
The `filter` block is documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Sorts</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getregionssort">List&lt;Pulumi.<wbr>Digital<wbr>Ocean.<wbr>Inputs.<wbr>Get<wbr>Regions<wbr>Sort<wbr>Args&gt;</a></span>
    </dt>
    <dd>{{% md %}}Sort the results.
The `sort` block is documented below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">
        <span>Filters</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getregionsfilter">[]Get<wbr>Regions<wbr>Filter</a></span>
    </dt>
    <dd>{{% md %}}Filter the results.
The `filter` block is documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Sorts</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getregionssort">[]Get<wbr>Regions<wbr>Sort</a></span>
    </dt>
    <dd>{{% md %}}Sort the results.
The `sort` block is documented below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">
        <span>filters</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getregionsfilter">Get<wbr>Regions<wbr>Filter[]</a></span>
    </dt>
    <dd>{{% md %}}Filter the results.
The `filter` block is documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>sorts</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getregionssort">Get<wbr>Regions<wbr>Sort[]</a></span>
    </dt>
    <dd>{{% md %}}Sort the results.
The `sort` block is documented below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">
        <span>filters</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getregionsfilter">List[Get<wbr>Regions<wbr>Filter]</a></span>
    </dt>
    <dd>{{% md %}}Filter the results.
The `filter` block is documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>sorts</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getregionssort">List[Get<wbr>Regions<wbr>Sort]</a></span>
    </dt>
    <dd>{{% md %}}Sort the results.
The `sort` block is documented below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}








## GetRegions Result {#result}

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">
        <span>Id</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span>
    </dt>
    <dd>{{% md %}}The provider-assigned unique ID for this managed resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>Regions</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getregionsregion">List&lt;Pulumi.<wbr>Digital<wbr>Ocean.<wbr>Outputs.<wbr>Get<wbr>Regions<wbr>Region&gt;</a></span>
    </dt>
    <dd>{{% md %}}A set of regions satisfying any `filter` and `sort` criteria. Each region has the following attributes:  
- `slug` - A human-readable string that is used as a unique identifier for each region.
- `name` - The display name of the region.
- `available` - A boolean value that represents whether new Droplets can be created in this region.
- `sizes` - A set of identifying slugs for the Droplet sizes available in this region.
- `features` - A set of features available in this region.
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>Filters</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getregionsfilter">List&lt;Pulumi.<wbr>Digital<wbr>Ocean.<wbr>Outputs.<wbr>Get<wbr>Regions<wbr>Filter&gt;</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>Sorts</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getregionssort">List&lt;Pulumi.<wbr>Digital<wbr>Ocean.<wbr>Outputs.<wbr>Get<wbr>Regions<wbr>Sort&gt;</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">
        <span>Id</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="https://golang.org/pkg/builtin/#string">string</a></span>
    </dt>
    <dd>{{% md %}}The provider-assigned unique ID for this managed resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>Regions</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getregionsregion">[]Get<wbr>Regions<wbr>Region</a></span>
    </dt>
    <dd>{{% md %}}A set of regions satisfying any `filter` and `sort` criteria. Each region has the following attributes:  
- `slug` - A human-readable string that is used as a unique identifier for each region.
- `name` - The display name of the region.
- `available` - A boolean value that represents whether new Droplets can be created in this region.
- `sizes` - A set of identifying slugs for the Droplet sizes available in this region.
- `features` - A set of features available in this region.
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>Filters</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getregionsfilter">[]Get<wbr>Regions<wbr>Filter</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>Sorts</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getregionssort">[]Get<wbr>Regions<wbr>Sort</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">
        <span>id</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span>
    </dt>
    <dd>{{% md %}}The provider-assigned unique ID for this managed resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>regions</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getregionsregion">Get<wbr>Regions<wbr>Region[]</a></span>
    </dt>
    <dd>{{% md %}}A set of regions satisfying any `filter` and `sort` criteria. Each region has the following attributes:  
- `slug` - A human-readable string that is used as a unique identifier for each region.
- `name` - The display name of the region.
- `available` - A boolean value that represents whether new Droplets can be created in this region.
- `sizes` - A set of identifying slugs for the Droplet sizes available in this region.
- `features` - A set of features available in this region.
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>filters</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getregionsfilter">Get<wbr>Regions<wbr>Filter[]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>sorts</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getregionssort">Get<wbr>Regions<wbr>Sort[]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">
        <span>id</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="https://docs.python.org/3/library/stdtypes.html">str</a></span>
    </dt>
    <dd>{{% md %}}The provider-assigned unique ID for this managed resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>regions</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getregionsregion">List[Get<wbr>Regions<wbr>Region]</a></span>
    </dt>
    <dd>{{% md %}}A set of regions satisfying any `filter` and `sort` criteria. Each region has the following attributes:  
- `slug` - A human-readable string that is used as a unique identifier for each region.
- `name` - The display name of the region.
- `available` - A boolean value that represents whether new Droplets can be created in this region.
- `sizes` - A set of identifying slugs for the Droplet sizes available in this region.
- `features` - A set of features available in this region.
{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>filters</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getregionsfilter">List[Get<wbr>Regions<wbr>Filter]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">
        <span>sorts</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getregionssort">List[Get<wbr>Regions<wbr>Sort]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}








## Supporting Types


<h4 id="getregionsfilter">Get<wbr>Regions<wbr>Filter</h4>
{{% choosable language nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/digitalocean/types/input/#GetRegionsFilter">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/digitalocean/types/output/#GetRegionsFilter">output</a> API doc for this type.
{{% /choosable %}}

{{% choosable language go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-digitalocean/sdk/v2/go/digitalocean/?tab=doc#GetRegionsFilterArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-digitalocean/sdk/v2/go/digitalocean/?tab=doc#GetRegionsFilter">output</a> API doc for this type.
{{% /choosable %}}
{{% choosable language csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.DigitalOcean/Pulumi.DigitalOcean.Inputs.GetRegionsFilterArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.DigitalOcean/Pulumi.DigitalOcean.Outputs.GetRegionsFilter.html">output</a> API doc for this type.
{{% /choosable %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">
        <span>Key</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span>
    </dt>
    <dd>{{% md %}}Filter the regions by this key. This may be one of `slug`,
`name`, `available`, `features`, or `sizes`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>Values</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">List&lt;string&gt;</a></span>
    </dt>
    <dd>{{% md %}}A list of values to match against the `key` field. Only retrieves regions
where the `key` field takes on one or more of the values provided here.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">
        <span>Key</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="https://golang.org/pkg/builtin/#string">string</a></span>
    </dt>
    <dd>{{% md %}}Filter the regions by this key. This may be one of `slug`,
`name`, `available`, `features`, or `sizes`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>Values</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="https://golang.org/pkg/builtin/#string">[]string</a></span>
    </dt>
    <dd>{{% md %}}A list of values to match against the `key` field. Only retrieves regions
where the `key` field takes on one or more of the values provided here.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">
        <span>key</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span>
    </dt>
    <dd>{{% md %}}Filter the regions by this key. This may be one of `slug`,
`name`, `available`, `features`, or `sizes`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>values</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string[]</a></span>
    </dt>
    <dd>{{% md %}}A list of values to match against the `key` field. Only retrieves regions
where the `key` field takes on one or more of the values provided here.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">
        <span>key</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="https://docs.python.org/3/library/stdtypes.html">str</a></span>
    </dt>
    <dd>{{% md %}}Filter the regions by this key. This may be one of `slug`,
`name`, `available`, `features`, or `sizes`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>values</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="https://docs.python.org/3/library/stdtypes.html">List[str]</a></span>
    </dt>
    <dd>{{% md %}}A list of values to match against the `key` field. Only retrieves regions
where the `key` field takes on one or more of the values provided here.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





<h4 id="getregionsregion">Get<wbr>Regions<wbr>Region</h4>
{{% choosable language nodejs %}}
> See the   <a href="/docs/reference/pkg/nodejs/pulumi/digitalocean/types/output/#GetRegionsRegion">output</a> API doc for this type.
{{% /choosable %}}

{{% choosable language go %}}
> See the   <a href="https://pkg.go.dev/github.com/pulumi/pulumi-digitalocean/sdk/v2/go/digitalocean/?tab=doc#GetRegionsRegion">output</a> API doc for this type.
{{% /choosable %}}
{{% choosable language csharp %}}
> See the   <a href="/docs/reference/pkg/dotnet/Pulumi.DigitalOcean/Pulumi.DigitalOcean.Outputs.GetRegionsRegion.html">output</a> API doc for this type.
{{% /choosable %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">
        <span>Available</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">bool</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>Features</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">List&lt;string&gt;</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>Name</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>Sizes</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">List&lt;string&gt;</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>Slug</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">
        <span>Available</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="https://golang.org/pkg/builtin/#boolean">bool</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>Features</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="https://golang.org/pkg/builtin/#string">[]string</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>Name</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="https://golang.org/pkg/builtin/#string">string</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>Sizes</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="https://golang.org/pkg/builtin/#string">[]string</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>Slug</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="https://golang.org/pkg/builtin/#string">string</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">
        <span>available</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/boolean">boolean</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>features</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string[]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>name</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>sizes</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string[]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>slug</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">
        <span>available</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="https://docs.python.org/3/library/stdtypes.html">bool</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>features</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="https://docs.python.org/3/library/stdtypes.html">List[str]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>name</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="https://docs.python.org/3/library/stdtypes.html">str</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>sizes</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="https://docs.python.org/3/library/stdtypes.html">List[str]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">
        <span>slug</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="https://docs.python.org/3/library/stdtypes.html">str</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}





<h4 id="getregionssort">Get<wbr>Regions<wbr>Sort</h4>
{{% choosable language nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/digitalocean/types/input/#GetRegionsSort">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/digitalocean/types/output/#GetRegionsSort">output</a> API doc for this type.
{{% /choosable %}}

{{% choosable language go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-digitalocean/sdk/v2/go/digitalocean/?tab=doc#GetRegionsSortArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-digitalocean/sdk/v2/go/digitalocean/?tab=doc#GetRegionsSort">output</a> API doc for this type.
{{% /choosable %}}
{{% choosable language csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.DigitalOcean/Pulumi.DigitalOcean.Inputs.GetRegionsSortArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.DigitalOcean/Pulumi.DigitalOcean.Outputs.GetRegionsSort.html">output</a> API doc for this type.
{{% /choosable %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">
        <span>Key</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span>
    </dt>
    <dd>{{% md %}}Sort the regions by this key. This may be one of `slug`,
`name`, or `available`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Direction</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span>
    </dt>
    <dd>{{% md %}}The sort direction. This may be either `asc` or `desc`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">
        <span>Key</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="https://golang.org/pkg/builtin/#string">string</a></span>
    </dt>
    <dd>{{% md %}}Sort the regions by this key. This may be one of `slug`,
`name`, or `available`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>Direction</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="https://golang.org/pkg/builtin/#string">string</a></span>
    </dt>
    <dd>{{% md %}}The sort direction. This may be either `asc` or `desc`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">
        <span>key</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span>
    </dt>
    <dd>{{% md %}}Sort the regions by this key. This may be one of `slug`,
`name`, or `available`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>direction</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span>
    </dt>
    <dd>{{% md %}}The sort direction. This may be either `asc` or `desc`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">
        <span>key</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="https://docs.python.org/3/library/stdtypes.html">str</a></span>
    </dt>
    <dd>{{% md %}}Sort the regions by this key. This may be one of `slug`,
`name`, or `available`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">
        <span>direction</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="https://docs.python.org/3/library/stdtypes.html">str</a></span>
    </dt>
    <dd>{{% md %}}The sort direction. This may be either `asc` or `desc`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}









<h2 id="package-details">Package Details</h2>
<dl class="package-details">
	<dt>Repository</dt>
	<dd><a href="https://github.com/pulumi/pulumi-digitalocean">https://github.com/pulumi/pulumi-digitalocean</a></dd>
	<dt>License</dt>
	<dd>Apache-2.0</dd>
	<dt>Notes</dt>
	<dd>This Pulumi package is based on the [`digitalocean` Terraform Provider](https://github.com/terraform-providers/terraform-provider-digitalocean).</dd>
</dl>

