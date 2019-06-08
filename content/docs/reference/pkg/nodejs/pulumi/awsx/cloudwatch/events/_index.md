---
title: Module cloudwatch/events
---

<!-- WARNING: this page was generated by a tool. Do not edit it by hand. -->
<!-- To change it, please see https://github.com/pulumi/docs/tree/master/tools/tscdocgen. -->

<a href="../../index.html">@pulumi/awsx</a> &gt; <a href="../index.html">cloudwatch</a> &gt; events

<div class="toggleVisible" markdown="1">
<div class="collapsed" markdown="1">
<h2 class="pdoc-module-header toggleButton" title="Click to show Index">Index ▹</h2>
</div>
<div class="expanded" markdown="1">
<h2 class="pdoc-module-header toggleButton" title="Click to hide Index">Index ▾</h2>
<div class="pdoc-module-contents" markdown="1">
* <a href="#deadLetterInvocations">function deadLetterInvocations</a>
* <a href="#failedInvocations">function failedInvocations</a>
* <a href="#invocations">function invocations</a>
* <a href="#matchedEvents">function matchedEvents</a>
* <a href="#metric">function metric</a>
* <a href="#throttledRules">function throttledRules</a>
* <a href="#triggeredRules">function triggeredRules</a>
* <a href="#CloudWatchMetricChange">interface CloudWatchMetricChange</a>
* <a href="#CloudWatchEventMetricName">type CloudWatchEventMetricName</a>

<a href="https://github.com/pulumi/pulumi-awsx/blob/master/nodejs/awsx/cloudwatch/metrics.ts">cloudwatch/metrics.ts</a> 
</div>
</div>
</div>


<h2 class="pdoc-module-header" id="deadLetterInvocations">
<a class="pdoc-member-name" href="https://github.com/pulumi/pulumi-awsx/blob/master/nodejs/awsx/cloudwatch/metrics.ts#L70">function <b>deadLetterInvocations</b></a>
</h2>
<div class="pdoc-module-contents" markdown="1">

<pre class="highlight"><span class='kd'></span>deadLetterInvocations(change?: <a href='#CloudWatchMetricChange'>CloudWatchMetricChange</a>): <a href='#Metric'>Metric</a></pre>


Measures the number of times a rule’s target is not invoked in response to an event. This
includes invocations that would result in triggering the same rule again, causing an
infinite loop.

Valid Dimensions: RuleName
Units: Count

</div>
<h2 class="pdoc-module-header" id="failedInvocations">
<a class="pdoc-member-name" href="https://github.com/pulumi/pulumi-awsx/blob/master/nodejs/awsx/cloudwatch/metrics.ts#L96">function <b>failedInvocations</b></a>
</h2>
<div class="pdoc-module-contents" markdown="1">

<pre class="highlight"><span class='kd'></span>failedInvocations(change?: <a href='#CloudWatchMetricChange'>CloudWatchMetricChange</a>): <a href='#Metric'>Metric</a></pre>


Measures the number of invocations that failed permanently. This does not include invocations
that are retried, or that succeeded after a retry attempt. It also does not count failed
invocations that are counted in DeadLetterInvocations.

Valid Dimensions: RuleName
Units: Count

</div>
<h2 class="pdoc-module-header" id="invocations">
<a class="pdoc-member-name" href="https://github.com/pulumi/pulumi-awsx/blob/master/nodejs/awsx/cloudwatch/metrics.ts#L84">function <b>invocations</b></a>
</h2>
<div class="pdoc-module-contents" markdown="1">

<pre class="highlight"><span class='kd'></span>invocations(change?: <a href='#CloudWatchMetricChange'>CloudWatchMetricChange</a>): <a href='#Metric'>Metric</a></pre>


Measures the number of times a target is invoked for a rule in response to an event. This
includes successful and failed invocations, but does not include throttled or retried attempts
until they fail permanently. It does not include DeadLetterInvocations.

Note: CloudWatch Events only sends this metric to CloudWatch if it has a non-zero value.

Valid Dimensions: RuleName
Units: Count

</div>
<h2 class="pdoc-module-header" id="matchedEvents">
<a class="pdoc-member-name" href="https://github.com/pulumi/pulumi-awsx/blob/master/nodejs/awsx/cloudwatch/metrics.ts#L116">function <b>matchedEvents</b></a>
</h2>
<div class="pdoc-module-contents" markdown="1">

<pre class="highlight"><span class='kd'></span>matchedEvents(change?: <a href='#CloudWatchMetricChange'>CloudWatchMetricChange</a>): <a href='#Metric'>Metric</a></pre>


Measures the number of events that matched with any rule.

Valid Dimensions: None
Units: Count

</div>
<h2 class="pdoc-module-header" id="metric">
<a class="pdoc-member-name" href="https://github.com/pulumi/pulumi-awsx/blob/master/nodejs/awsx/cloudwatch/metrics.ts#L49">function <b>metric</b></a>
</h2>
<div class="pdoc-module-contents" markdown="1">

<pre class="highlight"><span class='kd'></span>metric(metricName: <a href='#CloudWatchEventMetricName'>CloudWatchEventMetricName</a>, change: <a href='#CloudWatchMetricChange'>CloudWatchMetricChange</a>): <a href='#Metric'>Metric</a></pre>


CloudWatch Events sends metrics to Amazon CloudWatch every minute.

Creates an AWS/Events metric with the requested [metricName]. See
https://docs.aws.amazon.com/AmazonCloudWatch/latest/events/CloudWatch-Events-Monitoring-CloudWatch-Metrics.html
for list of all metric-names.

Note, individual metrics can easily be obtained without supplying the name using the other
[metricXXX] functions.

All of these metrics use Count as the unit, so Sum and SampleCount are the most useful
statistics.

CloudWatch Events metrics have one dimension:
1. "RuleName": Filters the available metrics by rule name.

</div>
<h2 class="pdoc-module-header" id="throttledRules">
<a class="pdoc-member-name" href="https://github.com/pulumi/pulumi-awsx/blob/master/nodejs/awsx/cloudwatch/metrics.ts#L126">function <b>throttledRules</b></a>
</h2>
<div class="pdoc-module-contents" markdown="1">

<pre class="highlight"><span class='kd'></span>throttledRules(change?: <a href='#CloudWatchMetricChange'>CloudWatchMetricChange</a>): <a href='#Metric'>Metric</a></pre>


Measures the number of triggered rules that are being throttled.

Valid Dimensions: RuleName
Units: Count

</div>
<h2 class="pdoc-module-header" id="triggeredRules">
<a class="pdoc-member-name" href="https://github.com/pulumi/pulumi-awsx/blob/master/nodejs/awsx/cloudwatch/metrics.ts#L106">function <b>triggeredRules</b></a>
</h2>
<div class="pdoc-module-contents" markdown="1">

<pre class="highlight"><span class='kd'></span>triggeredRules(change?: <a href='#CloudWatchMetricChange'>CloudWatchMetricChange</a>): <a href='#Metric'>Metric</a></pre>


Measures the number of triggered rules that matched with any event.

Valid Dimensions: RuleName
Units: Count

</div>
<h2 class="pdoc-module-header" id="CloudWatchMetricChange">
<a class="pdoc-member-name" href="https://github.com/pulumi/pulumi-awsx/blob/master/nodejs/awsx/cloudwatch/metrics.ts#L26">interface <b>CloudWatchMetricChange</b></a>
</h2>
<div class="pdoc-module-contents" markdown="1">
<pre class="highlight"><span class='kd'>extends</span> <a href='#MetricChange'>MetricChange</a></pre>
<h3 class="pdoc-member-header" id="CloudWatchMetricChange-color">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-awsx/blob/master/nodejs/awsx/cloudwatch/metric.ts#L439">property <b>color</b></a>
</h3>
<div class="pdoc-member-contents" markdown="1">
<pre class="highlight"><span class='kd'></span>color?: <a href='https://pulumi.io/reference/pkg/nodejs/@pulumi/pulumi/#Input'>pulumi.Input</a>&lt;<span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span>&gt;;</pre>

The six-digit HTML hex color code to be used for this metric.

Only used if this metric is displayed in a [Dashboard] with a [MetricWidget].

</div>
<h3 class="pdoc-member-header" id="CloudWatchMetricChange-dimensions">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-awsx/blob/master/nodejs/awsx/cloudwatch/metric.ts#L408">property <b>dimensions</b></a>
</h3>
<div class="pdoc-member-contents" markdown="1">
<pre class="highlight"><span class='kd'></span>dimensions?: <a href='https://pulumi.io/reference/pkg/nodejs/@pulumi/pulumi/#Input'>pulumi.Input</a>&lt;Record&lt;<span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span>, <span class='kd'><a href='https://www.typescriptlang.org/docs/handbook/basic-types.html#any'>any</a></span>&gt;&gt;;</pre>

The new dimension for this metric.  If this object is missing this property, then no change
will be made.  However, if the property is there by set to [undefined] then the value will be
cleared.

</div>
<h3 class="pdoc-member-header" id="CloudWatchMetricChange-eventRule">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-awsx/blob/master/nodejs/awsx/cloudwatch/metrics.ts#L30">property <b>eventRule</b></a>
</h3>
<div class="pdoc-member-contents" markdown="1">
<pre class="highlight"><span class='kd'></span>eventRule?: aws.cloudwatch.EventRule;</pre>

Filters down events to those from the specified [EventRule].

</div>
<h3 class="pdoc-member-header" id="CloudWatchMetricChange-extendedStatistic">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-awsx/blob/master/nodejs/awsx/cloudwatch/metric.ts#L426">property <b>extendedStatistic</b></a>
</h3>
<div class="pdoc-member-contents" markdown="1">
<pre class="highlight"><span class='kd'></span>extendedStatistic?: <a href='https://pulumi.io/reference/pkg/nodejs/@pulumi/pulumi/#Input'>pulumi.Input</a>&lt;<span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number'>number</a></span>&gt;;</pre>

The new percentile statistic for the metric associated with the alarm.  If this object is
missing this property, then no change will be made.  However, if the property is there by set
to [undefined] then the value will be set to the default.

</div>
<h3 class="pdoc-member-header" id="CloudWatchMetricChange-label">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-awsx/blob/master/nodejs/awsx/cloudwatch/metric.ts#L448">property <b>label</b></a>
</h3>
<div class="pdoc-member-contents" markdown="1">
<pre class="highlight"><span class='kd'></span>label?: <a href='https://pulumi.io/reference/pkg/nodejs/@pulumi/pulumi/#Input'>pulumi.Input</a>&lt;<span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span>&gt;;</pre>

The label to display for this metric in the graph legend. If this is not specified, the
metric is given an autogenerated label that distinguishes it from the other metrics in the
widget.

Only used if this metric is displayed in a [Dashboard] with a [MetricWidget].

</div>
<h3 class="pdoc-member-header" id="CloudWatchMetricChange-period">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-awsx/blob/master/nodejs/awsx/cloudwatch/metric.ts#L414">property <b>period</b></a>
</h3>
<div class="pdoc-member-contents" markdown="1">
<pre class="highlight"><span class='kd'></span>period?: <a href='https://pulumi.io/reference/pkg/nodejs/@pulumi/pulumi/#Input'>pulumi.Input</a>&lt;<span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number'>number</a></span>&gt;;</pre>

The new period in seconds over which the specified `stat` is applied.  If this object is
missing this property, then no change will be made.  However, if the property is there by set
to [undefined] then the value will be set to the default (300s).

</div>
<h3 class="pdoc-member-header" id="CloudWatchMetricChange-statistic">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-awsx/blob/master/nodejs/awsx/cloudwatch/metric.ts#L420">property <b>statistic</b></a>
</h3>
<div class="pdoc-member-contents" markdown="1">
<pre class="highlight"><span class='kd'></span>statistic?: <a href='https://pulumi.io/reference/pkg/nodejs/@pulumi/pulumi/#Input'>pulumi.Input</a>&lt;<a href='#MetricStatistic'>MetricStatistic</a>&gt;;</pre>

The new statistic to apply to the alarm's associated metric.  If this object is missing this
property, then no change will be made.  However, if the property is there by set to
[undefined] then the value will be set to the default.

</div>
<h3 class="pdoc-member-header" id="CloudWatchMetricChange-unit">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-awsx/blob/master/nodejs/awsx/cloudwatch/metric.ts#L432">property <b>unit</b></a>
</h3>
<div class="pdoc-member-contents" markdown="1">
<pre class="highlight"><span class='kd'></span>unit?: <a href='https://pulumi.io/reference/pkg/nodejs/@pulumi/pulumi/#Input'>pulumi.Input</a>&lt;<a href='#MetricUnit'>MetricUnit</a>&gt;;</pre>

The new unit for this metric.   If this object is missing this property, then no change will
be made.  However, if the property is there by set to [undefined] then the value will be set
to the default.

</div>
<h3 class="pdoc-member-header" id="CloudWatchMetricChange-visible">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-awsx/blob/master/nodejs/awsx/cloudwatch/metric.ts#L456">property <b>visible</b></a>
</h3>
<div class="pdoc-member-contents" markdown="1">
<pre class="highlight"><span class='kd'></span>visible?: <a href='https://pulumi.io/reference/pkg/nodejs/@pulumi/pulumi/#Input'>pulumi.Input</a>&lt;<span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean'>boolean</a></span>&gt;;</pre>

Set this to true to have the metric appear in the graph, or false to have it be hidden. The
default is true.

Only used if this metric is displayed in a [Dashboard] with a [MetricWidget].

</div>
<h3 class="pdoc-member-header" id="CloudWatchMetricChange-yAxis">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-awsx/blob/master/nodejs/awsx/cloudwatch/metric.ts#L463">property <b>yAxis</b></a>
</h3>
<div class="pdoc-member-contents" markdown="1">
<pre class="highlight"><span class='kd'></span>yAxis?: <a href='https://pulumi.io/reference/pkg/nodejs/@pulumi/pulumi/#Input'>pulumi.Input</a>&lt;<span class='s2'>"left"</span> | <span class='s2'>"right"</span>&gt;;</pre>

Where on the graph to display the y-axis for this metric. The default is left.

Only used if this metric is displayed in a [Dashboard] with a [MetricWidget].

</div>
</div>
<h2 class="pdoc-module-header" id="CloudWatchEventMetricName">
<a class="pdoc-member-name" href="https://github.com/pulumi/pulumi-awsx/blob/master/nodejs/awsx/cloudwatch/metrics.ts#L22">type <b>CloudWatchEventMetricName</b></a>
</h2>
<div class="pdoc-module-contents" markdown="1">
<pre class="highlight"><span class='kd'>type</span> CloudWatchEventMetricName = <span class='s2'>"DeadLetterInvocations"</span> | <span class='s2'>"Invocations"</span> | <span class='s2'>"FailedInvocations"</span> | <span class='s2'>"TriggeredRules"</span> | <span class='s2'>"MatchedEvents"</span> | <span class='s2'>"ThrottledRules"</span>;</pre>
</div>