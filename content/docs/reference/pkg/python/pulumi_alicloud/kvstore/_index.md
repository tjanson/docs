---
title: Module kvstore
title_tag: Module kvstore | Package pulumi_alicloud | Python SDK
linktitle: kvstore
notitle: true
---

<div class="section" id="kvstore">
<h1>kvstore<a class="headerlink" href="#kvstore" title="Permalink to this headline">¶</a></h1>
<blockquote>
<div><p>This provider is a derived work of the <a class="reference external" href="https://github.com/terraform-providers/terraform-provider-alicloud">Terraform Provider</a> distributed under
<a class="reference external" href="https://www.mozilla.org/en-US/MPL/2.0/">MPL 2.0</a>. If you encounter a bug or missing feature, first check the
<a class="reference external" href="https://github.com/pulumi/pulumi-alicloud/issues">pulumi/pulumi-alicloud repo</a>; however, if that doesn’t turn up
anything, please consult the source <a class="reference external" href="https://github.com/terraform-providers/terraform-provider-alicloud/issues">terraform-providers/terraform-provider-alicloud repo</a>.</p>
</div></blockquote>
<span class="target" id="module-pulumi_alicloud.kvstore"></span><dl class="py class">
<dt id="pulumi_alicloud.kvstore.Account">
<em class="property">class </em><code class="sig-prename descclassname">pulumi_alicloud.kvstore.</code><code class="sig-name descname">Account</code><span class="sig-paren">(</span><em class="sig-param"><span class="n">resource_name</span></em>, <em class="sig-param"><span class="n">opts</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">account_name</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">account_password</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">account_privilege</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">account_type</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">description</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">instance_id</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">kms_encrypted_password</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">kms_encryption_context</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">__props__</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">__name__</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">__opts__</span><span class="o">=</span><span class="default_value">None</span></em><span class="sig-paren">)</span><a class="headerlink" href="#pulumi_alicloud.kvstore.Account" title="Permalink to this definition">¶</a></dt>
<dd><p>Provides a kvstore account resource and used to manage databases.</p>
<blockquote>
<div><p><strong>NOTE:</strong> Available in 1.66.0+</p>
</div></blockquote>
<div class="highlight-python notranslate"><div class="highlight"><pre><span></span><span class="kn">import</span> <span class="nn">pulumi</span>
<span class="kn">import</span> <span class="nn">pulumi_alicloud</span> <span class="k">as</span> <span class="nn">alicloud</span>

<span class="n">config</span> <span class="o">=</span> <span class="n">pulumi</span><span class="o">.</span><span class="n">Config</span><span class="p">()</span>
<span class="n">creation</span> <span class="o">=</span> <span class="n">config</span><span class="o">.</span><span class="n">get</span><span class="p">(</span><span class="s2">&quot;creation&quot;</span><span class="p">)</span>
<span class="k">if</span> <span class="n">creation</span> <span class="ow">is</span> <span class="kc">None</span><span class="p">:</span>
    <span class="n">creation</span> <span class="o">=</span> <span class="s2">&quot;KVStore&quot;</span>
<span class="n">name</span> <span class="o">=</span> <span class="n">config</span><span class="o">.</span><span class="n">get</span><span class="p">(</span><span class="s2">&quot;name&quot;</span><span class="p">)</span>
<span class="k">if</span> <span class="n">name</span> <span class="ow">is</span> <span class="kc">None</span><span class="p">:</span>
    <span class="n">name</span> <span class="o">=</span> <span class="s2">&quot;kvstoreinstancevpc&quot;</span>
<span class="n">default_zones</span> <span class="o">=</span> <span class="n">alicloud</span><span class="o">.</span><span class="n">get_zones</span><span class="p">(</span><span class="n">available_resource_creation</span><span class="o">=</span><span class="n">creation</span><span class="p">)</span>
<span class="n">default_network</span> <span class="o">=</span> <span class="n">alicloud</span><span class="o">.</span><span class="n">vpc</span><span class="o">.</span><span class="n">Network</span><span class="p">(</span><span class="s2">&quot;defaultNetwork&quot;</span><span class="p">,</span> <span class="n">cidr_block</span><span class="o">=</span><span class="s2">&quot;172.16.0.0/16&quot;</span><span class="p">)</span>
<span class="n">default_switch</span> <span class="o">=</span> <span class="n">alicloud</span><span class="o">.</span><span class="n">vpc</span><span class="o">.</span><span class="n">Switch</span><span class="p">(</span><span class="s2">&quot;defaultSwitch&quot;</span><span class="p">,</span>
    <span class="n">availability_zone</span><span class="o">=</span><span class="n">default_zones</span><span class="o">.</span><span class="n">zones</span><span class="p">[</span><span class="mi">0</span><span class="p">][</span><span class="s2">&quot;id&quot;</span><span class="p">],</span>
    <span class="n">cidr_block</span><span class="o">=</span><span class="s2">&quot;172.16.0.0/24&quot;</span><span class="p">,</span>
    <span class="n">vpc_id</span><span class="o">=</span><span class="n">default_network</span><span class="o">.</span><span class="n">id</span><span class="p">)</span>
<span class="n">default_instance</span> <span class="o">=</span> <span class="n">alicloud</span><span class="o">.</span><span class="n">kvstore</span><span class="o">.</span><span class="n">Instance</span><span class="p">(</span><span class="s2">&quot;defaultInstance&quot;</span><span class="p">,</span>
    <span class="n">engine_version</span><span class="o">=</span><span class="s2">&quot;4.0&quot;</span><span class="p">,</span>
    <span class="n">instance_class</span><span class="o">=</span><span class="s2">&quot;redis.master.small.default&quot;</span><span class="p">,</span>
    <span class="n">instance_name</span><span class="o">=</span><span class="n">name</span><span class="p">,</span>
    <span class="n">instance_type</span><span class="o">=</span><span class="s2">&quot;Redis&quot;</span><span class="p">,</span>
    <span class="n">private_ip</span><span class="o">=</span><span class="s2">&quot;172.16.0.10&quot;</span><span class="p">,</span>
    <span class="n">security_ips</span><span class="o">=</span><span class="p">[</span><span class="s2">&quot;10.0.0.1&quot;</span><span class="p">],</span>
    <span class="n">vswitch_id</span><span class="o">=</span><span class="n">default_switch</span><span class="o">.</span><span class="n">id</span><span class="p">)</span>
<span class="n">account</span> <span class="o">=</span> <span class="n">alicloud</span><span class="o">.</span><span class="n">kvstore</span><span class="o">.</span><span class="n">Account</span><span class="p">(</span><span class="s2">&quot;account&quot;</span><span class="p">,</span>
    <span class="n">account_name</span><span class="o">=</span><span class="s2">&quot;tftestnormal&quot;</span><span class="p">,</span>
    <span class="n">account_password</span><span class="o">=</span><span class="s2">&quot;Test12345&quot;</span><span class="p">,</span>
    <span class="n">instance_id</span><span class="o">=</span><span class="n">default_instance</span><span class="o">.</span><span class="n">id</span><span class="p">)</span>
</pre></div>
</div>
<dl class="field-list simple">
<dt class="field-odd">Parameters</dt>
<dd class="field-odd"><ul class="simple">
<li><p><strong>resource_name</strong> (<em>str</em>) – The name of the resource.</p></li>
<li><p><strong>opts</strong> (<a class="reference internal" href="../../pulumi/#pulumi.ResourceOptions" title="pulumi.ResourceOptions"><em>pulumi.ResourceOptions</em></a>) – Options for the resource.</p></li>
<li><p><strong>account_name</strong> (<em>pulumi.Input</em><em>[</em><em>str</em><em>]</em>) – Operation account requiring a uniqueness check. It may consist of lower case letters, numbers, and underlines, and must start with a letter and have no more than 16 characters.</p></li>
<li><p><strong>account_password</strong> (<em>pulumi.Input</em><em>[</em><em>str</em><em>]</em>) – Operation password. It may consist of letters, digits, or underlines, with a length of 6 to 32 characters. You have to specify one of <code class="docutils literal notranslate"><span class="pre">account_password</span></code> and <code class="docutils literal notranslate"><span class="pre">kms_encrypted_password</span></code> fields.</p></li>
<li><p><strong>account_privilege</strong> (<em>pulumi.Input</em><em>[</em><em>str</em><em>]</em>) – The privilege of account access database. Valid values:</p></li>
</ul>
</dd>
</dl>
<div class="highlight-default notranslate"><div class="highlight"><pre><span></span><span class="o">-</span> <span class="n">RoleReadOnly</span><span class="p">:</span> <span class="n">This</span> <span class="n">value</span> <span class="ow">is</span> <span class="n">only</span> <span class="k">for</span> <span class="n">Redis</span> <span class="ow">and</span> <span class="n">Memcache</span>
<span class="o">-</span> <span class="n">RoleReadWrite</span><span class="p">:</span> <span class="n">This</span> <span class="n">value</span> <span class="ow">is</span> <span class="n">only</span> <span class="k">for</span> <span class="n">Redis</span> <span class="ow">and</span> <span class="n">Memcache</span>
<span class="o">-</span> <span class="n">RoleRepl</span><span class="p">:</span> <span class="n">This</span> <span class="n">value</span> <span class="n">supports</span> <span class="n">instance</span> <span class="n">to</span> <span class="n">read</span><span class="p">,</span> <span class="n">write</span><span class="p">,</span> <span class="ow">and</span> <span class="nb">open</span> <span class="n">SYNC</span> <span class="o">/</span> <span class="n">PSYNC</span> <span class="n">commands</span><span class="o">.</span>
<span class="n">Only</span> <span class="k">for</span> <span class="n">Redis</span> <span class="n">which</span> <span class="n">engine</span> <span class="n">version</span> <span class="ow">is</span> <span class="mf">4.0</span> <span class="ow">and</span> <span class="n">architecture</span> <span class="nb">type</span> <span class="ow">is</span> <span class="n">standard</span>
</pre></div>
</div>
<dl class="field-list simple">
<dt class="field-odd">Parameters</dt>
<dd class="field-odd"><p><strong>account_type</strong> (<em>pulumi.Input</em><em>[</em><em>str</em><em>]</em>) – Privilege type of account.</p>
</dd>
</dl>
<div class="highlight-default notranslate"><div class="highlight"><pre><span></span><span class="o">-</span> <span class="n">Normal</span><span class="p">:</span> <span class="n">Common</span> <span class="n">privilege</span><span class="o">.</span>
<span class="n">Default</span> <span class="n">to</span> <span class="n">Normal</span><span class="o">.</span>
</pre></div>
</div>
<dl class="field-list simple">
<dt class="field-odd">Parameters</dt>
<dd class="field-odd"><ul class="simple">
<li><p><strong>description</strong> (<em>pulumi.Input</em><em>[</em><em>str</em><em>]</em>) – Database description. It cannot begin with <a class="reference external" href="https://">https://</a>. It must start with a Chinese character or English letter. It can include Chinese and English characters, underlines (_), hyphens (-), and numbers. The length may be 2-256 characters.</p></li>
<li><p><strong>instance_id</strong> (<em>pulumi.Input</em><em>[</em><em>str</em><em>]</em>) – The Id of instance in which account belongs. (The engine version of instance must be 4.0 or 4.0+)</p></li>
<li><p><strong>kms_encrypted_password</strong> (<em>pulumi.Input</em><em>[</em><em>str</em><em>]</em>) – An KMS encrypts password used to a KVStore account. If the <code class="docutils literal notranslate"><span class="pre">account_password</span></code> is filled in, this field will be ignored.</p></li>
<li><p><strong>kms_encryption_context</strong> (<em>pulumi.Input</em><em>[</em><em>dict</em><em>]</em>) – An KMS encryption context used to decrypt <code class="docutils literal notranslate"><span class="pre">kms_encrypted_password</span></code> before creating or updating a KVStore account with <code class="docutils literal notranslate"><span class="pre">kms_encrypted_password</span></code>. See <a class="reference external" href="https://www.alibabacloud.com/help/doc-detail/42975.htm">Encryption Context</a>. It is valid when <code class="docutils literal notranslate"><span class="pre">kms_encrypted_password</span></code> is set.</p></li>
</ul>
</dd>
</dl>
<dl class="py attribute">
<dt id="pulumi_alicloud.kvstore.Account.account_name">
<code class="sig-name descname">account_name</code><em class="property">: pulumi.Output[str]</em><em class="property"> = None</em><a class="headerlink" href="#pulumi_alicloud.kvstore.Account.account_name" title="Permalink to this definition">¶</a></dt>
<dd><p>Operation account requiring a uniqueness check. It may consist of lower case letters, numbers, and underlines, and must start with a letter and have no more than 16 characters.</p>
</dd></dl>

<dl class="py attribute">
<dt id="pulumi_alicloud.kvstore.Account.account_password">
<code class="sig-name descname">account_password</code><em class="property">: pulumi.Output[str]</em><em class="property"> = None</em><a class="headerlink" href="#pulumi_alicloud.kvstore.Account.account_password" title="Permalink to this definition">¶</a></dt>
<dd><p>Operation password. It may consist of letters, digits, or underlines, with a length of 6 to 32 characters. You have to specify one of <code class="docutils literal notranslate"><span class="pre">account_password</span></code> and <code class="docutils literal notranslate"><span class="pre">kms_encrypted_password</span></code> fields.</p>
</dd></dl>

<dl class="py attribute">
<dt id="pulumi_alicloud.kvstore.Account.account_privilege">
<code class="sig-name descname">account_privilege</code><em class="property">: pulumi.Output[str]</em><em class="property"> = None</em><a class="headerlink" href="#pulumi_alicloud.kvstore.Account.account_privilege" title="Permalink to this definition">¶</a></dt>
<dd><p>The privilege of account access database. Valid values:</p>
<ul class="simple">
<li><p>RoleReadOnly: This value is only for Redis and Memcache</p></li>
<li><p>RoleReadWrite: This value is only for Redis and Memcache</p></li>
<li><p>RoleRepl: This value supports instance to read, write, and open SYNC / PSYNC commands.
Only for Redis which engine version is 4.0 and architecture type is standard</p></li>
</ul>
</dd></dl>

<dl class="py attribute">
<dt id="pulumi_alicloud.kvstore.Account.account_type">
<code class="sig-name descname">account_type</code><em class="property">: pulumi.Output[str]</em><em class="property"> = None</em><a class="headerlink" href="#pulumi_alicloud.kvstore.Account.account_type" title="Permalink to this definition">¶</a></dt>
<dd><p>Privilege type of account.</p>
<ul class="simple">
<li><p>Normal: Common privilege.
Default to Normal.</p></li>
</ul>
</dd></dl>

<dl class="py attribute">
<dt id="pulumi_alicloud.kvstore.Account.description">
<code class="sig-name descname">description</code><em class="property">: pulumi.Output[str]</em><em class="property"> = None</em><a class="headerlink" href="#pulumi_alicloud.kvstore.Account.description" title="Permalink to this definition">¶</a></dt>
<dd><p>Database description. It cannot begin with <a class="reference external" href="https://">https://</a>. It must start with a Chinese character or English letter. It can include Chinese and English characters, underlines (_), hyphens (-), and numbers. The length may be 2-256 characters.</p>
</dd></dl>

<dl class="py attribute">
<dt id="pulumi_alicloud.kvstore.Account.instance_id">
<code class="sig-name descname">instance_id</code><em class="property">: pulumi.Output[str]</em><em class="property"> = None</em><a class="headerlink" href="#pulumi_alicloud.kvstore.Account.instance_id" title="Permalink to this definition">¶</a></dt>
<dd><p>The Id of instance in which account belongs. (The engine version of instance must be 4.0 or 4.0+)</p>
</dd></dl>

<dl class="py attribute">
<dt id="pulumi_alicloud.kvstore.Account.kms_encrypted_password">
<code class="sig-name descname">kms_encrypted_password</code><em class="property">: pulumi.Output[str]</em><em class="property"> = None</em><a class="headerlink" href="#pulumi_alicloud.kvstore.Account.kms_encrypted_password" title="Permalink to this definition">¶</a></dt>
<dd><p>An KMS encrypts password used to a KVStore account. If the <code class="docutils literal notranslate"><span class="pre">account_password</span></code> is filled in, this field will be ignored.</p>
</dd></dl>

<dl class="py attribute">
<dt id="pulumi_alicloud.kvstore.Account.kms_encryption_context">
<code class="sig-name descname">kms_encryption_context</code><em class="property">: pulumi.Output[dict]</em><em class="property"> = None</em><a class="headerlink" href="#pulumi_alicloud.kvstore.Account.kms_encryption_context" title="Permalink to this definition">¶</a></dt>
<dd><p>An KMS encryption context used to decrypt <code class="docutils literal notranslate"><span class="pre">kms_encrypted_password</span></code> before creating or updating a KVStore account with <code class="docutils literal notranslate"><span class="pre">kms_encrypted_password</span></code>. See <a class="reference external" href="https://www.alibabacloud.com/help/doc-detail/42975.htm">Encryption Context</a>. It is valid when <code class="docutils literal notranslate"><span class="pre">kms_encrypted_password</span></code> is set.</p>
</dd></dl>

<dl class="py method">
<dt id="pulumi_alicloud.kvstore.Account.get">
<em class="property">static </em><code class="sig-name descname">get</code><span class="sig-paren">(</span><em class="sig-param"><span class="n">resource_name</span></em>, <em class="sig-param"><span class="n">id</span></em>, <em class="sig-param"><span class="n">opts</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">account_name</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">account_password</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">account_privilege</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">account_type</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">description</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">instance_id</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">kms_encrypted_password</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">kms_encryption_context</span><span class="o">=</span><span class="default_value">None</span></em><span class="sig-paren">)</span><a class="headerlink" href="#pulumi_alicloud.kvstore.Account.get" title="Permalink to this definition">¶</a></dt>
<dd><p>Get an existing Account resource’s state with the given name, id, and optional extra
properties used to qualify the lookup.</p>
<dl class="field-list simple">
<dt class="field-odd">Parameters</dt>
<dd class="field-odd"><ul class="simple">
<li><p><strong>resource_name</strong> (<em>str</em>) – The unique name of the resulting resource.</p></li>
<li><p><strong>id</strong> (<em>str</em>) – The unique provider ID of the resource to lookup.</p></li>
<li><p><strong>opts</strong> (<a class="reference internal" href="../../pulumi/#pulumi.ResourceOptions" title="pulumi.ResourceOptions"><em>pulumi.ResourceOptions</em></a>) – Options for the resource.</p></li>
<li><p><strong>account_name</strong> (<em>pulumi.Input</em><em>[</em><em>str</em><em>]</em>) – Operation account requiring a uniqueness check. It may consist of lower case letters, numbers, and underlines, and must start with a letter and have no more than 16 characters.</p></li>
<li><p><strong>account_password</strong> (<em>pulumi.Input</em><em>[</em><em>str</em><em>]</em>) – Operation password. It may consist of letters, digits, or underlines, with a length of 6 to 32 characters. You have to specify one of <code class="docutils literal notranslate"><span class="pre">account_password</span></code> and <code class="docutils literal notranslate"><span class="pre">kms_encrypted_password</span></code> fields.</p></li>
<li><p><strong>account_privilege</strong> (<em>pulumi.Input</em><em>[</em><em>str</em><em>]</em>) – The privilege of account access database. Valid values:</p></li>
</ul>
</dd>
</dl>
<div class="highlight-default notranslate"><div class="highlight"><pre><span></span><span class="o">-</span> <span class="n">RoleReadOnly</span><span class="p">:</span> <span class="n">This</span> <span class="n">value</span> <span class="ow">is</span> <span class="n">only</span> <span class="k">for</span> <span class="n">Redis</span> <span class="ow">and</span> <span class="n">Memcache</span>
<span class="o">-</span> <span class="n">RoleReadWrite</span><span class="p">:</span> <span class="n">This</span> <span class="n">value</span> <span class="ow">is</span> <span class="n">only</span> <span class="k">for</span> <span class="n">Redis</span> <span class="ow">and</span> <span class="n">Memcache</span>
<span class="o">-</span> <span class="n">RoleRepl</span><span class="p">:</span> <span class="n">This</span> <span class="n">value</span> <span class="n">supports</span> <span class="n">instance</span> <span class="n">to</span> <span class="n">read</span><span class="p">,</span> <span class="n">write</span><span class="p">,</span> <span class="ow">and</span> <span class="nb">open</span> <span class="n">SYNC</span> <span class="o">/</span> <span class="n">PSYNC</span> <span class="n">commands</span><span class="o">.</span>
<span class="n">Only</span> <span class="k">for</span> <span class="n">Redis</span> <span class="n">which</span> <span class="n">engine</span> <span class="n">version</span> <span class="ow">is</span> <span class="mf">4.0</span> <span class="ow">and</span> <span class="n">architecture</span> <span class="nb">type</span> <span class="ow">is</span> <span class="n">standard</span>
</pre></div>
</div>
<dl class="field-list simple">
<dt class="field-odd">Parameters</dt>
<dd class="field-odd"><p><strong>account_type</strong> (<em>pulumi.Input</em><em>[</em><em>str</em><em>]</em>) – Privilege type of account.</p>
</dd>
</dl>
<div class="highlight-default notranslate"><div class="highlight"><pre><span></span><span class="o">-</span> <span class="n">Normal</span><span class="p">:</span> <span class="n">Common</span> <span class="n">privilege</span><span class="o">.</span>
<span class="n">Default</span> <span class="n">to</span> <span class="n">Normal</span><span class="o">.</span>
</pre></div>
</div>
<dl class="field-list simple">
<dt class="field-odd">Parameters</dt>
<dd class="field-odd"><ul class="simple">
<li><p><strong>description</strong> (<em>pulumi.Input</em><em>[</em><em>str</em><em>]</em>) – Database description. It cannot begin with <a class="reference external" href="https://">https://</a>. It must start with a Chinese character or English letter. It can include Chinese and English characters, underlines (_), hyphens (-), and numbers. The length may be 2-256 characters.</p></li>
<li><p><strong>instance_id</strong> (<em>pulumi.Input</em><em>[</em><em>str</em><em>]</em>) – The Id of instance in which account belongs. (The engine version of instance must be 4.0 or 4.0+)</p></li>
<li><p><strong>kms_encrypted_password</strong> (<em>pulumi.Input</em><em>[</em><em>str</em><em>]</em>) – An KMS encrypts password used to a KVStore account. If the <code class="docutils literal notranslate"><span class="pre">account_password</span></code> is filled in, this field will be ignored.</p></li>
<li><p><strong>kms_encryption_context</strong> (<em>pulumi.Input</em><em>[</em><em>dict</em><em>]</em>) – <p>An KMS encryption context used to decrypt <code class="docutils literal notranslate"><span class="pre">kms_encrypted_password</span></code> before creating or updating a KVStore account with <code class="docutils literal notranslate"><span class="pre">kms_encrypted_password</span></code>. See <a class="reference external" href="https://www.alibabacloud.com/help/doc-detail/42975.htm">Encryption Context</a>. It is valid when <code class="docutils literal notranslate"><span class="pre">kms_encrypted_password</span></code> is set.</p>
</p></li>
</ul>
</dd>
</dl>
</dd></dl>

<dl class="py method">
<dt id="pulumi_alicloud.kvstore.Account.translate_output_property">
<code class="sig-name descname">translate_output_property</code><span class="sig-paren">(</span><em class="sig-param"><span class="n">prop</span></em><span class="sig-paren">)</span><a class="headerlink" href="#pulumi_alicloud.kvstore.Account.translate_output_property" title="Permalink to this definition">¶</a></dt>
<dd><p>Provides subclasses of Resource an opportunity to translate names of output properties
into a format of their choosing before writing those properties to the resource object.</p>
<dl class="field-list simple">
<dt class="field-odd">Parameters</dt>
<dd class="field-odd"><p><strong>prop</strong> (<em>str</em>) – A property name.</p>
</dd>
<dt class="field-even">Returns</dt>
<dd class="field-even"><p>A potentially transformed property name.</p>
</dd>
<dt class="field-odd">Return type</dt>
<dd class="field-odd"><p>str</p>
</dd>
</dl>
</dd></dl>

<dl class="py method">
<dt id="pulumi_alicloud.kvstore.Account.translate_input_property">
<code class="sig-name descname">translate_input_property</code><span class="sig-paren">(</span><em class="sig-param"><span class="n">prop</span></em><span class="sig-paren">)</span><a class="headerlink" href="#pulumi_alicloud.kvstore.Account.translate_input_property" title="Permalink to this definition">¶</a></dt>
<dd><p>Provides subclasses of Resource an opportunity to translate names of input properties into
a format of their choosing before sending those properties to the Pulumi engine.</p>
<dl class="field-list simple">
<dt class="field-odd">Parameters</dt>
<dd class="field-odd"><p><strong>prop</strong> (<em>str</em>) – A property name.</p>
</dd>
<dt class="field-even">Returns</dt>
<dd class="field-even"><p>A potentially transformed property name.</p>
</dd>
<dt class="field-odd">Return type</dt>
<dd class="field-odd"><p>str</p>
</dd>
</dl>
</dd></dl>

</dd></dl>

<dl class="py class">
<dt id="pulumi_alicloud.kvstore.AwaitableGetInstanceClassesResult">
<em class="property">class </em><code class="sig-prename descclassname">pulumi_alicloud.kvstore.</code><code class="sig-name descname">AwaitableGetInstanceClassesResult</code><span class="sig-paren">(</span><em class="sig-param"><span class="n">architecture</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">classes</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">edition_type</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">engine</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">engine_version</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">id</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">instance_charge_type</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">instance_classes</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">node_type</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">output_file</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">package_type</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">performance_type</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">series_type</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">shard_number</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">sorted_by</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">storage_type</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">zone_id</span><span class="o">=</span><span class="default_value">None</span></em><span class="sig-paren">)</span><a class="headerlink" href="#pulumi_alicloud.kvstore.AwaitableGetInstanceClassesResult" title="Permalink to this definition">¶</a></dt>
<dd></dd></dl>

<dl class="py class">
<dt id="pulumi_alicloud.kvstore.AwaitableGetInstanceEnginesResult">
<em class="property">class </em><code class="sig-prename descclassname">pulumi_alicloud.kvstore.</code><code class="sig-name descname">AwaitableGetInstanceEnginesResult</code><span class="sig-paren">(</span><em class="sig-param"><span class="n">engine</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">engine_version</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">id</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">instance_charge_type</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">instance_engines</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">output_file</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">zone_id</span><span class="o">=</span><span class="default_value">None</span></em><span class="sig-paren">)</span><a class="headerlink" href="#pulumi_alicloud.kvstore.AwaitableGetInstanceEnginesResult" title="Permalink to this definition">¶</a></dt>
<dd></dd></dl>

<dl class="py class">
<dt id="pulumi_alicloud.kvstore.AwaitableGetInstancesResult">
<em class="property">class </em><code class="sig-prename descclassname">pulumi_alicloud.kvstore.</code><code class="sig-name descname">AwaitableGetInstancesResult</code><span class="sig-paren">(</span><em class="sig-param"><span class="n">id</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">ids</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">instance_class</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">instance_type</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">instances</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">name_regex</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">names</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">output_file</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">status</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">tags</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">vpc_id</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">vswitch_id</span><span class="o">=</span><span class="default_value">None</span></em><span class="sig-paren">)</span><a class="headerlink" href="#pulumi_alicloud.kvstore.AwaitableGetInstancesResult" title="Permalink to this definition">¶</a></dt>
<dd></dd></dl>

<dl class="py class">
<dt id="pulumi_alicloud.kvstore.AwaitableGetZonesResult">
<em class="property">class </em><code class="sig-prename descclassname">pulumi_alicloud.kvstore.</code><code class="sig-name descname">AwaitableGetZonesResult</code><span class="sig-paren">(</span><em class="sig-param"><span class="n">id</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">ids</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">instance_charge_type</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">multi</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">output_file</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">zones</span><span class="o">=</span><span class="default_value">None</span></em><span class="sig-paren">)</span><a class="headerlink" href="#pulumi_alicloud.kvstore.AwaitableGetZonesResult" title="Permalink to this definition">¶</a></dt>
<dd></dd></dl>

<dl class="py class">
<dt id="pulumi_alicloud.kvstore.BackupPolicy">
<em class="property">class </em><code class="sig-prename descclassname">pulumi_alicloud.kvstore.</code><code class="sig-name descname">BackupPolicy</code><span class="sig-paren">(</span><em class="sig-param"><span class="n">resource_name</span></em>, <em class="sig-param"><span class="n">opts</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">backup_periods</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">backup_time</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">instance_id</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">__props__</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">__name__</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">__opts__</span><span class="o">=</span><span class="default_value">None</span></em><span class="sig-paren">)</span><a class="headerlink" href="#pulumi_alicloud.kvstore.BackupPolicy" title="Permalink to this definition">¶</a></dt>
<dd><p>Provides a backup policy for ApsaraDB Redis / Memcache instance resource.</p>
<div class="highlight-python notranslate"><div class="highlight"><pre><span></span><span class="kn">import</span> <span class="nn">pulumi</span>
<span class="kn">import</span> <span class="nn">pulumi_alicloud</span> <span class="k">as</span> <span class="nn">alicloud</span>

<span class="n">config</span> <span class="o">=</span> <span class="n">pulumi</span><span class="o">.</span><span class="n">Config</span><span class="p">()</span>
<span class="n">creation</span> <span class="o">=</span> <span class="n">config</span><span class="o">.</span><span class="n">get</span><span class="p">(</span><span class="s2">&quot;creation&quot;</span><span class="p">)</span>
<span class="k">if</span> <span class="n">creation</span> <span class="ow">is</span> <span class="kc">None</span><span class="p">:</span>
    <span class="n">creation</span> <span class="o">=</span> <span class="s2">&quot;KVStore&quot;</span>
<span class="n">multi_az</span> <span class="o">=</span> <span class="n">config</span><span class="o">.</span><span class="n">get</span><span class="p">(</span><span class="s2">&quot;multiAz&quot;</span><span class="p">)</span>
<span class="k">if</span> <span class="n">multi_az</span> <span class="ow">is</span> <span class="kc">None</span><span class="p">:</span>
    <span class="n">multi_az</span> <span class="o">=</span> <span class="s2">&quot;false&quot;</span>
<span class="n">name</span> <span class="o">=</span> <span class="n">config</span><span class="o">.</span><span class="n">get</span><span class="p">(</span><span class="s2">&quot;name&quot;</span><span class="p">)</span>
<span class="k">if</span> <span class="n">name</span> <span class="ow">is</span> <span class="kc">None</span><span class="p">:</span>
    <span class="n">name</span> <span class="o">=</span> <span class="s2">&quot;kvstorebackuppolicyvpc&quot;</span>
<span class="n">default_zones</span> <span class="o">=</span> <span class="n">alicloud</span><span class="o">.</span><span class="n">get_zones</span><span class="p">(</span><span class="n">available_resource_creation</span><span class="o">=</span><span class="n">creation</span><span class="p">)</span>
<span class="n">default_network</span> <span class="o">=</span> <span class="n">alicloud</span><span class="o">.</span><span class="n">vpc</span><span class="o">.</span><span class="n">Network</span><span class="p">(</span><span class="s2">&quot;defaultNetwork&quot;</span><span class="p">,</span> <span class="n">cidr_block</span><span class="o">=</span><span class="s2">&quot;172.16.0.0/16&quot;</span><span class="p">)</span>
<span class="n">default_switch</span> <span class="o">=</span> <span class="n">alicloud</span><span class="o">.</span><span class="n">vpc</span><span class="o">.</span><span class="n">Switch</span><span class="p">(</span><span class="s2">&quot;defaultSwitch&quot;</span><span class="p">,</span>
    <span class="n">availability_zone</span><span class="o">=</span><span class="n">default_zones</span><span class="o">.</span><span class="n">zones</span><span class="p">[</span><span class="mi">0</span><span class="p">][</span><span class="s2">&quot;id&quot;</span><span class="p">],</span>
    <span class="n">cidr_block</span><span class="o">=</span><span class="s2">&quot;172.16.0.0/24&quot;</span><span class="p">,</span>
    <span class="n">vpc_id</span><span class="o">=</span><span class="n">default_network</span><span class="o">.</span><span class="n">id</span><span class="p">)</span>
<span class="n">default_instance</span> <span class="o">=</span> <span class="n">alicloud</span><span class="o">.</span><span class="n">kvstore</span><span class="o">.</span><span class="n">Instance</span><span class="p">(</span><span class="s2">&quot;defaultInstance&quot;</span><span class="p">,</span>
    <span class="n">engine_version</span><span class="o">=</span><span class="s2">&quot;2.8&quot;</span><span class="p">,</span>
    <span class="n">instance_class</span><span class="o">=</span><span class="s2">&quot;Memcache&quot;</span><span class="p">,</span>
    <span class="n">instance_name</span><span class="o">=</span><span class="n">name</span><span class="p">,</span>
    <span class="n">instance_type</span><span class="o">=</span><span class="s2">&quot;memcache.master.small.default&quot;</span><span class="p">,</span>
    <span class="n">private_ip</span><span class="o">=</span><span class="s2">&quot;172.16.0.10&quot;</span><span class="p">,</span>
    <span class="n">security_ips</span><span class="o">=</span><span class="p">[</span><span class="s2">&quot;10.0.0.1&quot;</span><span class="p">],</span>
    <span class="n">vswitch_id</span><span class="o">=</span><span class="n">default_switch</span><span class="o">.</span><span class="n">id</span><span class="p">)</span>
<span class="n">default_backup_policy</span> <span class="o">=</span> <span class="n">alicloud</span><span class="o">.</span><span class="n">kvstore</span><span class="o">.</span><span class="n">BackupPolicy</span><span class="p">(</span><span class="s2">&quot;defaultBackupPolicy&quot;</span><span class="p">,</span>
    <span class="n">backup_periods</span><span class="o">=</span><span class="p">[</span>
        <span class="s2">&quot;Tuesday&quot;</span><span class="p">,</span>
        <span class="s2">&quot;Wednesday&quot;</span><span class="p">,</span>
    <span class="p">],</span>
    <span class="n">backup_time</span><span class="o">=</span><span class="s2">&quot;10:00Z-11:00Z&quot;</span><span class="p">,</span>
    <span class="n">instance_id</span><span class="o">=</span><span class="n">default_instance</span><span class="o">.</span><span class="n">id</span><span class="p">)</span>
</pre></div>
</div>
<dl class="field-list simple">
<dt class="field-odd">Parameters</dt>
<dd class="field-odd"><ul class="simple">
<li><p><strong>resource_name</strong> (<em>str</em>) – The name of the resource.</p></li>
<li><p><strong>opts</strong> (<a class="reference internal" href="../../pulumi/#pulumi.ResourceOptions" title="pulumi.ResourceOptions"><em>pulumi.ResourceOptions</em></a>) – Options for the resource.</p></li>
<li><p><strong>backup_periods</strong> (<em>pulumi.Input</em><em>[</em><em>list</em><em>]</em>) – Backup Cycle. Allowed values: Monday, Tuesday, Wednesday, Thursday, Friday, Saturday, Sunday</p></li>
<li><p><strong>backup_time</strong> (<em>pulumi.Input</em><em>[</em><em>str</em><em>]</em>) – Backup time, in the format of HH:mmZ- HH:mm Z</p></li>
<li><p><strong>instance_id</strong> (<em>pulumi.Input</em><em>[</em><em>str</em><em>]</em>) – The id of ApsaraDB for Redis or Memcache intance.</p></li>
</ul>
</dd>
</dl>
<dl class="py attribute">
<dt id="pulumi_alicloud.kvstore.BackupPolicy.backup_periods">
<code class="sig-name descname">backup_periods</code><em class="property">: pulumi.Output[list]</em><em class="property"> = None</em><a class="headerlink" href="#pulumi_alicloud.kvstore.BackupPolicy.backup_periods" title="Permalink to this definition">¶</a></dt>
<dd><p>Backup Cycle. Allowed values: Monday, Tuesday, Wednesday, Thursday, Friday, Saturday, Sunday</p>
</dd></dl>

<dl class="py attribute">
<dt id="pulumi_alicloud.kvstore.BackupPolicy.backup_time">
<code class="sig-name descname">backup_time</code><em class="property">: pulumi.Output[str]</em><em class="property"> = None</em><a class="headerlink" href="#pulumi_alicloud.kvstore.BackupPolicy.backup_time" title="Permalink to this definition">¶</a></dt>
<dd><p>Backup time, in the format of HH:mmZ- HH:mm Z</p>
</dd></dl>

<dl class="py attribute">
<dt id="pulumi_alicloud.kvstore.BackupPolicy.instance_id">
<code class="sig-name descname">instance_id</code><em class="property">: pulumi.Output[str]</em><em class="property"> = None</em><a class="headerlink" href="#pulumi_alicloud.kvstore.BackupPolicy.instance_id" title="Permalink to this definition">¶</a></dt>
<dd><p>The id of ApsaraDB for Redis or Memcache intance.</p>
</dd></dl>

<dl class="py method">
<dt id="pulumi_alicloud.kvstore.BackupPolicy.get">
<em class="property">static </em><code class="sig-name descname">get</code><span class="sig-paren">(</span><em class="sig-param"><span class="n">resource_name</span></em>, <em class="sig-param"><span class="n">id</span></em>, <em class="sig-param"><span class="n">opts</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">backup_periods</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">backup_time</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">instance_id</span><span class="o">=</span><span class="default_value">None</span></em><span class="sig-paren">)</span><a class="headerlink" href="#pulumi_alicloud.kvstore.BackupPolicy.get" title="Permalink to this definition">¶</a></dt>
<dd><p>Get an existing BackupPolicy resource’s state with the given name, id, and optional extra
properties used to qualify the lookup.</p>
<dl class="field-list simple">
<dt class="field-odd">Parameters</dt>
<dd class="field-odd"><ul class="simple">
<li><p><strong>resource_name</strong> (<em>str</em>) – The unique name of the resulting resource.</p></li>
<li><p><strong>id</strong> (<em>str</em>) – The unique provider ID of the resource to lookup.</p></li>
<li><p><strong>opts</strong> (<a class="reference internal" href="../../pulumi/#pulumi.ResourceOptions" title="pulumi.ResourceOptions"><em>pulumi.ResourceOptions</em></a>) – Options for the resource.</p></li>
<li><p><strong>backup_periods</strong> (<em>pulumi.Input</em><em>[</em><em>list</em><em>]</em>) – Backup Cycle. Allowed values: Monday, Tuesday, Wednesday, Thursday, Friday, Saturday, Sunday</p></li>
<li><p><strong>backup_time</strong> (<em>pulumi.Input</em><em>[</em><em>str</em><em>]</em>) – Backup time, in the format of HH:mmZ- HH:mm Z</p></li>
<li><p><strong>instance_id</strong> (<em>pulumi.Input</em><em>[</em><em>str</em><em>]</em>) – The id of ApsaraDB for Redis or Memcache intance.</p></li>
</ul>
</dd>
</dl>
</dd></dl>

<dl class="py method">
<dt id="pulumi_alicloud.kvstore.BackupPolicy.translate_output_property">
<code class="sig-name descname">translate_output_property</code><span class="sig-paren">(</span><em class="sig-param"><span class="n">prop</span></em><span class="sig-paren">)</span><a class="headerlink" href="#pulumi_alicloud.kvstore.BackupPolicy.translate_output_property" title="Permalink to this definition">¶</a></dt>
<dd><p>Provides subclasses of Resource an opportunity to translate names of output properties
into a format of their choosing before writing those properties to the resource object.</p>
<dl class="field-list simple">
<dt class="field-odd">Parameters</dt>
<dd class="field-odd"><p><strong>prop</strong> (<em>str</em>) – A property name.</p>
</dd>
<dt class="field-even">Returns</dt>
<dd class="field-even"><p>A potentially transformed property name.</p>
</dd>
<dt class="field-odd">Return type</dt>
<dd class="field-odd"><p>str</p>
</dd>
</dl>
</dd></dl>

<dl class="py method">
<dt id="pulumi_alicloud.kvstore.BackupPolicy.translate_input_property">
<code class="sig-name descname">translate_input_property</code><span class="sig-paren">(</span><em class="sig-param"><span class="n">prop</span></em><span class="sig-paren">)</span><a class="headerlink" href="#pulumi_alicloud.kvstore.BackupPolicy.translate_input_property" title="Permalink to this definition">¶</a></dt>
<dd><p>Provides subclasses of Resource an opportunity to translate names of input properties into
a format of their choosing before sending those properties to the Pulumi engine.</p>
<dl class="field-list simple">
<dt class="field-odd">Parameters</dt>
<dd class="field-odd"><p><strong>prop</strong> (<em>str</em>) – A property name.</p>
</dd>
<dt class="field-even">Returns</dt>
<dd class="field-even"><p>A potentially transformed property name.</p>
</dd>
<dt class="field-odd">Return type</dt>
<dd class="field-odd"><p>str</p>
</dd>
</dl>
</dd></dl>

</dd></dl>

<dl class="py class">
<dt id="pulumi_alicloud.kvstore.GetInstanceClassesResult">
<em class="property">class </em><code class="sig-prename descclassname">pulumi_alicloud.kvstore.</code><code class="sig-name descname">GetInstanceClassesResult</code><span class="sig-paren">(</span><em class="sig-param"><span class="n">architecture</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">classes</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">edition_type</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">engine</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">engine_version</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">id</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">instance_charge_type</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">instance_classes</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">node_type</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">output_file</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">package_type</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">performance_type</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">series_type</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">shard_number</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">sorted_by</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">storage_type</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">zone_id</span><span class="o">=</span><span class="default_value">None</span></em><span class="sig-paren">)</span><a class="headerlink" href="#pulumi_alicloud.kvstore.GetInstanceClassesResult" title="Permalink to this definition">¶</a></dt>
<dd><p>A collection of values returned by getInstanceClasses.</p>
<dl class="py attribute">
<dt id="pulumi_alicloud.kvstore.GetInstanceClassesResult.classes">
<code class="sig-name descname">classes</code><em class="property"> = None</em><a class="headerlink" href="#pulumi_alicloud.kvstore.GetInstanceClassesResult.classes" title="Permalink to this definition">¶</a></dt>
<dd><p>A list of KVStore available instance classes when the <code class="docutils literal notranslate"><span class="pre">sorted_by</span></code> is “Price”. include:</p>
</dd></dl>

<dl class="py attribute">
<dt id="pulumi_alicloud.kvstore.GetInstanceClassesResult.id">
<code class="sig-name descname">id</code><em class="property"> = None</em><a class="headerlink" href="#pulumi_alicloud.kvstore.GetInstanceClassesResult.id" title="Permalink to this definition">¶</a></dt>
<dd><p>The provider-assigned unique ID for this managed resource.</p>
</dd></dl>

<dl class="py attribute">
<dt id="pulumi_alicloud.kvstore.GetInstanceClassesResult.instance_classes">
<code class="sig-name descname">instance_classes</code><em class="property"> = None</em><a class="headerlink" href="#pulumi_alicloud.kvstore.GetInstanceClassesResult.instance_classes" title="Permalink to this definition">¶</a></dt>
<dd><p>A list of KVStore available instance classes.</p>
</dd></dl>

</dd></dl>

<dl class="py class">
<dt id="pulumi_alicloud.kvstore.GetInstanceEnginesResult">
<em class="property">class </em><code class="sig-prename descclassname">pulumi_alicloud.kvstore.</code><code class="sig-name descname">GetInstanceEnginesResult</code><span class="sig-paren">(</span><em class="sig-param"><span class="n">engine</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">engine_version</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">id</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">instance_charge_type</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">instance_engines</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">output_file</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">zone_id</span><span class="o">=</span><span class="default_value">None</span></em><span class="sig-paren">)</span><a class="headerlink" href="#pulumi_alicloud.kvstore.GetInstanceEnginesResult" title="Permalink to this definition">¶</a></dt>
<dd><p>A collection of values returned by getInstanceEngines.</p>
<dl class="py attribute">
<dt id="pulumi_alicloud.kvstore.GetInstanceEnginesResult.engine">
<code class="sig-name descname">engine</code><em class="property"> = None</em><a class="headerlink" href="#pulumi_alicloud.kvstore.GetInstanceEnginesResult.engine" title="Permalink to this definition">¶</a></dt>
<dd><p>Database type.</p>
</dd></dl>

<dl class="py attribute">
<dt id="pulumi_alicloud.kvstore.GetInstanceEnginesResult.engine_version">
<code class="sig-name descname">engine_version</code><em class="property"> = None</em><a class="headerlink" href="#pulumi_alicloud.kvstore.GetInstanceEnginesResult.engine_version" title="Permalink to this definition">¶</a></dt>
<dd><p>KVStore Instance version.</p>
</dd></dl>

<dl class="py attribute">
<dt id="pulumi_alicloud.kvstore.GetInstanceEnginesResult.id">
<code class="sig-name descname">id</code><em class="property"> = None</em><a class="headerlink" href="#pulumi_alicloud.kvstore.GetInstanceEnginesResult.id" title="Permalink to this definition">¶</a></dt>
<dd><p>The provider-assigned unique ID for this managed resource.</p>
</dd></dl>

<dl class="py attribute">
<dt id="pulumi_alicloud.kvstore.GetInstanceEnginesResult.instance_engines">
<code class="sig-name descname">instance_engines</code><em class="property"> = None</em><a class="headerlink" href="#pulumi_alicloud.kvstore.GetInstanceEnginesResult.instance_engines" title="Permalink to this definition">¶</a></dt>
<dd><p>A list of KVStore available instance engines. Each element contains the following attributes:</p>
</dd></dl>

<dl class="py attribute">
<dt id="pulumi_alicloud.kvstore.GetInstanceEnginesResult.zone_id">
<code class="sig-name descname">zone_id</code><em class="property"> = None</em><a class="headerlink" href="#pulumi_alicloud.kvstore.GetInstanceEnginesResult.zone_id" title="Permalink to this definition">¶</a></dt>
<dd><p>The Zone to launch the KVStore instance.</p>
</dd></dl>

</dd></dl>

<dl class="py class">
<dt id="pulumi_alicloud.kvstore.GetInstancesResult">
<em class="property">class </em><code class="sig-prename descclassname">pulumi_alicloud.kvstore.</code><code class="sig-name descname">GetInstancesResult</code><span class="sig-paren">(</span><em class="sig-param"><span class="n">id</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">ids</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">instance_class</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">instance_type</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">instances</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">name_regex</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">names</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">output_file</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">status</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">tags</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">vpc_id</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">vswitch_id</span><span class="o">=</span><span class="default_value">None</span></em><span class="sig-paren">)</span><a class="headerlink" href="#pulumi_alicloud.kvstore.GetInstancesResult" title="Permalink to this definition">¶</a></dt>
<dd><p>A collection of values returned by getInstances.</p>
<dl class="py attribute">
<dt id="pulumi_alicloud.kvstore.GetInstancesResult.id">
<code class="sig-name descname">id</code><em class="property"> = None</em><a class="headerlink" href="#pulumi_alicloud.kvstore.GetInstancesResult.id" title="Permalink to this definition">¶</a></dt>
<dd><p>The provider-assigned unique ID for this managed resource.</p>
</dd></dl>

<dl class="py attribute">
<dt id="pulumi_alicloud.kvstore.GetInstancesResult.ids">
<code class="sig-name descname">ids</code><em class="property"> = None</em><a class="headerlink" href="#pulumi_alicloud.kvstore.GetInstancesResult.ids" title="Permalink to this definition">¶</a></dt>
<dd><p>A list of RKV instance IDs.</p>
</dd></dl>

<dl class="py attribute">
<dt id="pulumi_alicloud.kvstore.GetInstancesResult.instance_type">
<code class="sig-name descname">instance_type</code><em class="property"> = None</em><a class="headerlink" href="#pulumi_alicloud.kvstore.GetInstancesResult.instance_type" title="Permalink to this definition">¶</a></dt>
<dd><p>(Optional) Database type. Options are <code class="docutils literal notranslate"><span class="pre">Memcache</span></code>, and <code class="docutils literal notranslate"><span class="pre">Redis</span></code>. If no value is specified, all types are returned.</p>
<ul class="simple">
<li><p><code class="docutils literal notranslate"><span class="pre">instance_class</span></code>- (Optional) Type of the applied ApsaraDB for Redis instance.
For more information, see <a class="reference external" href="https://www.alibabacloud.com/help/doc-detail/61135.htm">Instance type table</a>.</p></li>
</ul>
</dd></dl>

<dl class="py attribute">
<dt id="pulumi_alicloud.kvstore.GetInstancesResult.instances">
<code class="sig-name descname">instances</code><em class="property"> = None</em><a class="headerlink" href="#pulumi_alicloud.kvstore.GetInstancesResult.instances" title="Permalink to this definition">¶</a></dt>
<dd><p>A list of RKV instances. Its every element contains the following attributes:</p>
</dd></dl>

<dl class="py attribute">
<dt id="pulumi_alicloud.kvstore.GetInstancesResult.status">
<code class="sig-name descname">status</code><em class="property"> = None</em><a class="headerlink" href="#pulumi_alicloud.kvstore.GetInstancesResult.status" title="Permalink to this definition">¶</a></dt>
<dd><p>Status of the instance.</p>
</dd></dl>

<dl class="py attribute">
<dt id="pulumi_alicloud.kvstore.GetInstancesResult.vpc_id">
<code class="sig-name descname">vpc_id</code><em class="property"> = None</em><a class="headerlink" href="#pulumi_alicloud.kvstore.GetInstancesResult.vpc_id" title="Permalink to this definition">¶</a></dt>
<dd><p>VPC ID the instance belongs to.</p>
</dd></dl>

<dl class="py attribute">
<dt id="pulumi_alicloud.kvstore.GetInstancesResult.vswitch_id">
<code class="sig-name descname">vswitch_id</code><em class="property"> = None</em><a class="headerlink" href="#pulumi_alicloud.kvstore.GetInstancesResult.vswitch_id" title="Permalink to this definition">¶</a></dt>
<dd><p>VSwitch ID the instance belongs to.</p>
</dd></dl>

</dd></dl>

<dl class="py class">
<dt id="pulumi_alicloud.kvstore.GetZonesResult">
<em class="property">class </em><code class="sig-prename descclassname">pulumi_alicloud.kvstore.</code><code class="sig-name descname">GetZonesResult</code><span class="sig-paren">(</span><em class="sig-param"><span class="n">id</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">ids</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">instance_charge_type</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">multi</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">output_file</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">zones</span><span class="o">=</span><span class="default_value">None</span></em><span class="sig-paren">)</span><a class="headerlink" href="#pulumi_alicloud.kvstore.GetZonesResult" title="Permalink to this definition">¶</a></dt>
<dd><p>A collection of values returned by getZones.</p>
<dl class="py attribute">
<dt id="pulumi_alicloud.kvstore.GetZonesResult.id">
<code class="sig-name descname">id</code><em class="property"> = None</em><a class="headerlink" href="#pulumi_alicloud.kvstore.GetZonesResult.id" title="Permalink to this definition">¶</a></dt>
<dd><p>The provider-assigned unique ID for this managed resource.</p>
</dd></dl>

<dl class="py attribute">
<dt id="pulumi_alicloud.kvstore.GetZonesResult.ids">
<code class="sig-name descname">ids</code><em class="property"> = None</em><a class="headerlink" href="#pulumi_alicloud.kvstore.GetZonesResult.ids" title="Permalink to this definition">¶</a></dt>
<dd><p>A list of zone IDs.</p>
</dd></dl>

<dl class="py attribute">
<dt id="pulumi_alicloud.kvstore.GetZonesResult.zones">
<code class="sig-name descname">zones</code><em class="property"> = None</em><a class="headerlink" href="#pulumi_alicloud.kvstore.GetZonesResult.zones" title="Permalink to this definition">¶</a></dt>
<dd><p>A list of availability zones. Each element contains the following attributes:</p>
</dd></dl>

</dd></dl>

<dl class="py class">
<dt id="pulumi_alicloud.kvstore.Instance">
<em class="property">class </em><code class="sig-prename descclassname">pulumi_alicloud.kvstore.</code><code class="sig-name descname">Instance</code><span class="sig-paren">(</span><em class="sig-param"><span class="n">resource_name</span></em>, <em class="sig-param"><span class="n">opts</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">auto_renew</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">auto_renew_period</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">availability_zone</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">backup_id</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">engine_version</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">instance_charge_type</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">instance_class</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">instance_name</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">instance_type</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">kms_encrypted_password</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">kms_encryption_context</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">maintain_end_time</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">maintain_start_time</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">parameters</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">password</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">period</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">private_ip</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">security_group_id</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">security_ips</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">tags</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">vpc_auth_mode</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">vswitch_id</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">__props__</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">__name__</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">__opts__</span><span class="o">=</span><span class="default_value">None</span></em><span class="sig-paren">)</span><a class="headerlink" href="#pulumi_alicloud.kvstore.Instance" title="Permalink to this definition">¶</a></dt>
<dd><p>Provides an ApsaraDB Redis / Memcache instance resource. A DB instance is an isolated database environment in the cloud. It can be associated with IP whitelists and backup configuration which are separate resource providers.</p>
<div class="highlight-python notranslate"><div class="highlight"><pre><span></span><span class="kn">import</span> <span class="nn">pulumi</span>
<span class="kn">import</span> <span class="nn">pulumi_alicloud</span> <span class="k">as</span> <span class="nn">alicloud</span>

<span class="n">config</span> <span class="o">=</span> <span class="n">pulumi</span><span class="o">.</span><span class="n">Config</span><span class="p">()</span>
<span class="n">creation</span> <span class="o">=</span> <span class="n">config</span><span class="o">.</span><span class="n">get</span><span class="p">(</span><span class="s2">&quot;creation&quot;</span><span class="p">)</span>
<span class="k">if</span> <span class="n">creation</span> <span class="ow">is</span> <span class="kc">None</span><span class="p">:</span>
    <span class="n">creation</span> <span class="o">=</span> <span class="s2">&quot;KVStore&quot;</span>
<span class="n">name</span> <span class="o">=</span> <span class="n">config</span><span class="o">.</span><span class="n">get</span><span class="p">(</span><span class="s2">&quot;name&quot;</span><span class="p">)</span>
<span class="k">if</span> <span class="n">name</span> <span class="ow">is</span> <span class="kc">None</span><span class="p">:</span>
    <span class="n">name</span> <span class="o">=</span> <span class="s2">&quot;kvstoreinstancevpc&quot;</span>
<span class="n">default_zones</span> <span class="o">=</span> <span class="n">alicloud</span><span class="o">.</span><span class="n">get_zones</span><span class="p">(</span><span class="n">available_resource_creation</span><span class="o">=</span><span class="n">creation</span><span class="p">)</span>
<span class="n">default_network</span> <span class="o">=</span> <span class="n">alicloud</span><span class="o">.</span><span class="n">vpc</span><span class="o">.</span><span class="n">Network</span><span class="p">(</span><span class="s2">&quot;defaultNetwork&quot;</span><span class="p">,</span> <span class="n">cidr_block</span><span class="o">=</span><span class="s2">&quot;172.16.0.0/16&quot;</span><span class="p">)</span>
<span class="n">default_switch</span> <span class="o">=</span> <span class="n">alicloud</span><span class="o">.</span><span class="n">vpc</span><span class="o">.</span><span class="n">Switch</span><span class="p">(</span><span class="s2">&quot;defaultSwitch&quot;</span><span class="p">,</span>
    <span class="n">availability_zone</span><span class="o">=</span><span class="n">default_zones</span><span class="o">.</span><span class="n">zones</span><span class="p">[</span><span class="mi">0</span><span class="p">][</span><span class="s2">&quot;id&quot;</span><span class="p">],</span>
    <span class="n">cidr_block</span><span class="o">=</span><span class="s2">&quot;172.16.0.0/24&quot;</span><span class="p">,</span>
    <span class="n">vpc_id</span><span class="o">=</span><span class="n">default_network</span><span class="o">.</span><span class="n">id</span><span class="p">)</span>
<span class="n">default_instance</span> <span class="o">=</span> <span class="n">alicloud</span><span class="o">.</span><span class="n">kvstore</span><span class="o">.</span><span class="n">Instance</span><span class="p">(</span><span class="s2">&quot;defaultInstance&quot;</span><span class="p">,</span>
    <span class="n">engine_version</span><span class="o">=</span><span class="s2">&quot;4.0&quot;</span><span class="p">,</span>
    <span class="n">instance_class</span><span class="o">=</span><span class="s2">&quot;redis.master.small.default&quot;</span><span class="p">,</span>
    <span class="n">instance_name</span><span class="o">=</span><span class="n">name</span><span class="p">,</span>
    <span class="n">instance_type</span><span class="o">=</span><span class="s2">&quot;Redis&quot;</span><span class="p">,</span>
    <span class="n">private_ip</span><span class="o">=</span><span class="s2">&quot;172.16.0.10&quot;</span><span class="p">,</span>
    <span class="n">security_ips</span><span class="o">=</span><span class="p">[</span><span class="s2">&quot;10.0.0.1&quot;</span><span class="p">],</span>
    <span class="n">vswitch_id</span><span class="o">=</span><span class="n">default_switch</span><span class="o">.</span><span class="n">id</span><span class="p">)</span>
</pre></div>
</div>
<dl class="field-list simple">
<dt class="field-odd">Parameters</dt>
<dd class="field-odd"><ul class="simple">
<li><p><strong>resource_name</strong> (<em>str</em>) – The name of the resource.</p></li>
<li><p><strong>opts</strong> (<a class="reference internal" href="../../pulumi/#pulumi.ResourceOptions" title="pulumi.ResourceOptions"><em>pulumi.ResourceOptions</em></a>) – Options for the resource.</p></li>
<li><p><strong>auto_renew</strong> (<em>pulumi.Input</em><em>[</em><em>bool</em><em>]</em>) – Whether to renewal a DB instance automatically or not. It is valid when instance_charge_type is <code class="docutils literal notranslate"><span class="pre">PrePaid</span></code>. Default to <code class="docutils literal notranslate"><span class="pre">false</span></code>.</p></li>
<li><p><strong>auto_renew_period</strong> (<em>pulumi.Input</em><em>[</em><em>float</em><em>]</em>) – Auto-renewal period of an instance, in the unit of the month. It is valid when instance_charge_type is <code class="docutils literal notranslate"><span class="pre">PrePaid</span></code>. Valid value:[1~12], Default to 1.</p></li>
<li><p><strong>availability_zone</strong> (<em>pulumi.Input</em><em>[</em><em>str</em><em>]</em>) – The Zone to launch the DB instance.</p></li>
<li><p><strong>backup_id</strong> (<em>pulumi.Input</em><em>[</em><em>str</em><em>]</em>) – If an instance created based on a backup set generated by another instance is valid, this parameter indicates the ID of the generated backup set.</p></li>
<li><p><strong>engine_version</strong> (<em>pulumi.Input</em><em>[</em><em>str</em><em>]</em>) – Engine version. Supported values: 2.8, 4.0 and 5.0. Default value: 2.8. Only 2.8 can be supported for Memcache Instance.</p></li>
<li><p><strong>instance_charge_type</strong> (<em>pulumi.Input</em><em>[</em><em>str</em><em>]</em>) – Valid values are <code class="docutils literal notranslate"><span class="pre">PrePaid</span></code>, <code class="docutils literal notranslate"><span class="pre">PostPaid</span></code>, Default to <code class="docutils literal notranslate"><span class="pre">PostPaid</span></code>.</p></li>
<li><p><strong>instance_name</strong> (<em>pulumi.Input</em><em>[</em><em>str</em><em>]</em>) – The name of DB instance. It a string of 2 to 256 characters.</p></li>
<li><p><strong>instance_type</strong> (<em>pulumi.Input</em><em>[</em><em>str</em><em>]</em>) – The engine to use: <code class="docutils literal notranslate"><span class="pre">Redis</span></code> or <code class="docutils literal notranslate"><span class="pre">Memcache</span></code>. Defaults to <code class="docutils literal notranslate"><span class="pre">Redis</span></code>.</p></li>
<li><p><strong>kms_encrypted_password</strong> (<em>pulumi.Input</em><em>[</em><em>str</em><em>]</em>) – An KMS encrypts password used to a instance. If the <code class="docutils literal notranslate"><span class="pre">password</span></code> is filled in, this field will be ignored.</p></li>
<li><p><strong>kms_encryption_context</strong> (<em>pulumi.Input</em><em>[</em><em>dict</em><em>]</em>) – <p>An KMS encryption context used to decrypt <code class="docutils literal notranslate"><span class="pre">kms_encrypted_password</span></code> before creating or updating instance with <code class="docutils literal notranslate"><span class="pre">kms_encrypted_password</span></code>. See <a class="reference external" href="https://www.alibabacloud.com/help/doc-detail/42975.htm">Encryption Context</a>. It is valid when <code class="docutils literal notranslate"><span class="pre">kms_encrypted_password</span></code> is set.</p>
</p></li>
<li><p><strong>maintain_end_time</strong> (<em>pulumi.Input</em><em>[</em><em>str</em><em>]</em>) – The end time of the operation and maintenance time period of the instance, in the format of HH:mmZ (UTC time).</p></li>
<li><p><strong>maintain_start_time</strong> (<em>pulumi.Input</em><em>[</em><em>str</em><em>]</em>) – The start time of the operation and maintenance time period of the instance, in the format of HH:mmZ (UTC time).</p></li>
<li><p><strong>parameters</strong> (<em>pulumi.Input</em><em>[</em><em>list</em><em>]</em>) – Set of parameters needs to be set after instance was launched. Available parameters can refer to the latest docs <a class="reference external" href="https://www.alibabacloud.com/help/doc-detail/61209.htm">Instance configurations table</a> .</p></li>
<li><p><strong>password</strong> (<em>pulumi.Input</em><em>[</em><em>str</em><em>]</em>) – The password of the DB instance. The password is a string of 8 to 30 characters and must contain uppercase letters, lowercase letters, and numbers.</p></li>
<li><p><strong>period</strong> (<em>pulumi.Input</em><em>[</em><em>float</em><em>]</em>) – The duration that you will buy DB instance (in month). It is valid when instance_charge_type is <code class="docutils literal notranslate"><span class="pre">PrePaid</span></code>. Valid values: [1~9], 12, 24, 36. Default to 1.</p></li>
<li><p><strong>private_ip</strong> (<em>pulumi.Input</em><em>[</em><em>str</em><em>]</em>) – Set the instance’s private IP.</p></li>
<li><p><strong>security_group_id</strong> (<em>pulumi.Input</em><em>[</em><em>str</em><em>]</em>) – The Security Group ID of ECS.</p></li>
<li><p><strong>security_ips</strong> (<em>pulumi.Input</em><em>[</em><em>list</em><em>]</em>) – Set the instance’s IP whitelist of the default security group.</p></li>
<li><p><strong>tags</strong> (<em>pulumi.Input</em><em>[</em><em>dict</em><em>]</em>) – A mapping of tags to assign to the resource.</p></li>
<li><p><strong>vpc_auth_mode</strong> (<em>pulumi.Input</em><em>[</em><em>str</em><em>]</em>) – Only meaningful if instance_type is <code class="docutils literal notranslate"><span class="pre">Redis</span></code> and network type is VPC. Valid values are <code class="docutils literal notranslate"><span class="pre">Close</span></code>, <code class="docutils literal notranslate"><span class="pre">Open</span></code>. Defaults to <code class="docutils literal notranslate"><span class="pre">Open</span></code>.  <code class="docutils literal notranslate"><span class="pre">Close</span></code> means the redis instance can be accessed without authentication. <code class="docutils literal notranslate"><span class="pre">Open</span></code> means authentication is required.</p></li>
<li><p><strong>vswitch_id</strong> (<em>pulumi.Input</em><em>[</em><em>str</em><em>]</em>) – The ID of VSwitch.</p></li>
</ul>
</dd>
</dl>
<p>The <strong>parameters</strong> object supports the following:</p>
<ul class="simple">
<li><p><code class="docutils literal notranslate"><span class="pre">name</span></code> (<code class="docutils literal notranslate"><span class="pre">pulumi.Input[str]</span></code>)</p></li>
<li><p><code class="docutils literal notranslate"><span class="pre">value</span></code> (<code class="docutils literal notranslate"><span class="pre">pulumi.Input[str]</span></code>)</p></li>
</ul>
<dl class="py attribute">
<dt id="pulumi_alicloud.kvstore.Instance.auto_renew">
<code class="sig-name descname">auto_renew</code><em class="property">: pulumi.Output[bool]</em><em class="property"> = None</em><a class="headerlink" href="#pulumi_alicloud.kvstore.Instance.auto_renew" title="Permalink to this definition">¶</a></dt>
<dd><p>Whether to renewal a DB instance automatically or not. It is valid when instance_charge_type is <code class="docutils literal notranslate"><span class="pre">PrePaid</span></code>. Default to <code class="docutils literal notranslate"><span class="pre">false</span></code>.</p>
</dd></dl>

<dl class="py attribute">
<dt id="pulumi_alicloud.kvstore.Instance.auto_renew_period">
<code class="sig-name descname">auto_renew_period</code><em class="property">: pulumi.Output[float]</em><em class="property"> = None</em><a class="headerlink" href="#pulumi_alicloud.kvstore.Instance.auto_renew_period" title="Permalink to this definition">¶</a></dt>
<dd><p>Auto-renewal period of an instance, in the unit of the month. It is valid when instance_charge_type is <code class="docutils literal notranslate"><span class="pre">PrePaid</span></code>. Valid value:[1~12], Default to 1.</p>
</dd></dl>

<dl class="py attribute">
<dt id="pulumi_alicloud.kvstore.Instance.availability_zone">
<code class="sig-name descname">availability_zone</code><em class="property">: pulumi.Output[str]</em><em class="property"> = None</em><a class="headerlink" href="#pulumi_alicloud.kvstore.Instance.availability_zone" title="Permalink to this definition">¶</a></dt>
<dd><p>The Zone to launch the DB instance.</p>
</dd></dl>

<dl class="py attribute">
<dt id="pulumi_alicloud.kvstore.Instance.backup_id">
<code class="sig-name descname">backup_id</code><em class="property">: pulumi.Output[str]</em><em class="property"> = None</em><a class="headerlink" href="#pulumi_alicloud.kvstore.Instance.backup_id" title="Permalink to this definition">¶</a></dt>
<dd><p>If an instance created based on a backup set generated by another instance is valid, this parameter indicates the ID of the generated backup set.</p>
</dd></dl>

<dl class="py attribute">
<dt id="pulumi_alicloud.kvstore.Instance.connection_domain">
<code class="sig-name descname">connection_domain</code><em class="property">: pulumi.Output[str]</em><em class="property"> = None</em><a class="headerlink" href="#pulumi_alicloud.kvstore.Instance.connection_domain" title="Permalink to this definition">¶</a></dt>
<dd><p>Instance connection domain (only Intranet access supported).</p>
</dd></dl>

<dl class="py attribute">
<dt id="pulumi_alicloud.kvstore.Instance.engine_version">
<code class="sig-name descname">engine_version</code><em class="property">: pulumi.Output[str]</em><em class="property"> = None</em><a class="headerlink" href="#pulumi_alicloud.kvstore.Instance.engine_version" title="Permalink to this definition">¶</a></dt>
<dd><p>Engine version. Supported values: 2.8, 4.0 and 5.0. Default value: 2.8. Only 2.8 can be supported for Memcache Instance.</p>
</dd></dl>

<dl class="py attribute">
<dt id="pulumi_alicloud.kvstore.Instance.instance_charge_type">
<code class="sig-name descname">instance_charge_type</code><em class="property">: pulumi.Output[str]</em><em class="property"> = None</em><a class="headerlink" href="#pulumi_alicloud.kvstore.Instance.instance_charge_type" title="Permalink to this definition">¶</a></dt>
<dd><p>Valid values are <code class="docutils literal notranslate"><span class="pre">PrePaid</span></code>, <code class="docutils literal notranslate"><span class="pre">PostPaid</span></code>, Default to <code class="docutils literal notranslate"><span class="pre">PostPaid</span></code>.</p>
</dd></dl>

<dl class="py attribute">
<dt id="pulumi_alicloud.kvstore.Instance.instance_name">
<code class="sig-name descname">instance_name</code><em class="property">: pulumi.Output[str]</em><em class="property"> = None</em><a class="headerlink" href="#pulumi_alicloud.kvstore.Instance.instance_name" title="Permalink to this definition">¶</a></dt>
<dd><p>The name of DB instance. It a string of 2 to 256 characters.</p>
</dd></dl>

<dl class="py attribute">
<dt id="pulumi_alicloud.kvstore.Instance.instance_type">
<code class="sig-name descname">instance_type</code><em class="property">: pulumi.Output[str]</em><em class="property"> = None</em><a class="headerlink" href="#pulumi_alicloud.kvstore.Instance.instance_type" title="Permalink to this definition">¶</a></dt>
<dd><p>The engine to use: <code class="docutils literal notranslate"><span class="pre">Redis</span></code> or <code class="docutils literal notranslate"><span class="pre">Memcache</span></code>. Defaults to <code class="docutils literal notranslate"><span class="pre">Redis</span></code>.</p>
</dd></dl>

<dl class="py attribute">
<dt id="pulumi_alicloud.kvstore.Instance.kms_encrypted_password">
<code class="sig-name descname">kms_encrypted_password</code><em class="property">: pulumi.Output[str]</em><em class="property"> = None</em><a class="headerlink" href="#pulumi_alicloud.kvstore.Instance.kms_encrypted_password" title="Permalink to this definition">¶</a></dt>
<dd><p>An KMS encrypts password used to a instance. If the <code class="docutils literal notranslate"><span class="pre">password</span></code> is filled in, this field will be ignored.</p>
</dd></dl>

<dl class="py attribute">
<dt id="pulumi_alicloud.kvstore.Instance.kms_encryption_context">
<code class="sig-name descname">kms_encryption_context</code><em class="property">: pulumi.Output[dict]</em><em class="property"> = None</em><a class="headerlink" href="#pulumi_alicloud.kvstore.Instance.kms_encryption_context" title="Permalink to this definition">¶</a></dt>
<dd><p>An KMS encryption context used to decrypt <code class="docutils literal notranslate"><span class="pre">kms_encrypted_password</span></code> before creating or updating instance with <code class="docutils literal notranslate"><span class="pre">kms_encrypted_password</span></code>. See <a class="reference external" href="https://www.alibabacloud.com/help/doc-detail/42975.htm">Encryption Context</a>. It is valid when <code class="docutils literal notranslate"><span class="pre">kms_encrypted_password</span></code> is set.</p>
</dd></dl>

<dl class="py attribute">
<dt id="pulumi_alicloud.kvstore.Instance.maintain_end_time">
<code class="sig-name descname">maintain_end_time</code><em class="property">: pulumi.Output[str]</em><em class="property"> = None</em><a class="headerlink" href="#pulumi_alicloud.kvstore.Instance.maintain_end_time" title="Permalink to this definition">¶</a></dt>
<dd><p>The end time of the operation and maintenance time period of the instance, in the format of HH:mmZ (UTC time).</p>
</dd></dl>

<dl class="py attribute">
<dt id="pulumi_alicloud.kvstore.Instance.maintain_start_time">
<code class="sig-name descname">maintain_start_time</code><em class="property">: pulumi.Output[str]</em><em class="property"> = None</em><a class="headerlink" href="#pulumi_alicloud.kvstore.Instance.maintain_start_time" title="Permalink to this definition">¶</a></dt>
<dd><p>The start time of the operation and maintenance time period of the instance, in the format of HH:mmZ (UTC time).</p>
</dd></dl>

<dl class="py attribute">
<dt id="pulumi_alicloud.kvstore.Instance.parameters">
<code class="sig-name descname">parameters</code><em class="property">: pulumi.Output[list]</em><em class="property"> = None</em><a class="headerlink" href="#pulumi_alicloud.kvstore.Instance.parameters" title="Permalink to this definition">¶</a></dt>
<dd><p>Set of parameters needs to be set after instance was launched. Available parameters can refer to the latest docs <a class="reference external" href="https://www.alibabacloud.com/help/doc-detail/61209.htm">Instance configurations table</a> .</p>
<ul class="simple">
<li><p><code class="docutils literal notranslate"><span class="pre">name</span></code> (<code class="docutils literal notranslate"><span class="pre">str</span></code>)</p></li>
<li><p><code class="docutils literal notranslate"><span class="pre">value</span></code> (<code class="docutils literal notranslate"><span class="pre">str</span></code>)</p></li>
</ul>
</dd></dl>

<dl class="py attribute">
<dt id="pulumi_alicloud.kvstore.Instance.password">
<code class="sig-name descname">password</code><em class="property">: pulumi.Output[str]</em><em class="property"> = None</em><a class="headerlink" href="#pulumi_alicloud.kvstore.Instance.password" title="Permalink to this definition">¶</a></dt>
<dd><p>The password of the DB instance. The password is a string of 8 to 30 characters and must contain uppercase letters, lowercase letters, and numbers.</p>
</dd></dl>

<dl class="py attribute">
<dt id="pulumi_alicloud.kvstore.Instance.period">
<code class="sig-name descname">period</code><em class="property">: pulumi.Output[float]</em><em class="property"> = None</em><a class="headerlink" href="#pulumi_alicloud.kvstore.Instance.period" title="Permalink to this definition">¶</a></dt>
<dd><p>The duration that you will buy DB instance (in month). It is valid when instance_charge_type is <code class="docutils literal notranslate"><span class="pre">PrePaid</span></code>. Valid values: [1~9], 12, 24, 36. Default to 1.</p>
</dd></dl>

<dl class="py attribute">
<dt id="pulumi_alicloud.kvstore.Instance.private_ip">
<code class="sig-name descname">private_ip</code><em class="property">: pulumi.Output[str]</em><em class="property"> = None</em><a class="headerlink" href="#pulumi_alicloud.kvstore.Instance.private_ip" title="Permalink to this definition">¶</a></dt>
<dd><p>Set the instance’s private IP.</p>
</dd></dl>

<dl class="py attribute">
<dt id="pulumi_alicloud.kvstore.Instance.security_group_id">
<code class="sig-name descname">security_group_id</code><em class="property">: pulumi.Output[str]</em><em class="property"> = None</em><a class="headerlink" href="#pulumi_alicloud.kvstore.Instance.security_group_id" title="Permalink to this definition">¶</a></dt>
<dd><p>The Security Group ID of ECS.</p>
</dd></dl>

<dl class="py attribute">
<dt id="pulumi_alicloud.kvstore.Instance.security_ips">
<code class="sig-name descname">security_ips</code><em class="property">: pulumi.Output[list]</em><em class="property"> = None</em><a class="headerlink" href="#pulumi_alicloud.kvstore.Instance.security_ips" title="Permalink to this definition">¶</a></dt>
<dd><p>Set the instance’s IP whitelist of the default security group.</p>
</dd></dl>

<dl class="py attribute">
<dt id="pulumi_alicloud.kvstore.Instance.tags">
<code class="sig-name descname">tags</code><em class="property">: pulumi.Output[dict]</em><em class="property"> = None</em><a class="headerlink" href="#pulumi_alicloud.kvstore.Instance.tags" title="Permalink to this definition">¶</a></dt>
<dd><p>A mapping of tags to assign to the resource.</p>
</dd></dl>

<dl class="py attribute">
<dt id="pulumi_alicloud.kvstore.Instance.vpc_auth_mode">
<code class="sig-name descname">vpc_auth_mode</code><em class="property">: pulumi.Output[str]</em><em class="property"> = None</em><a class="headerlink" href="#pulumi_alicloud.kvstore.Instance.vpc_auth_mode" title="Permalink to this definition">¶</a></dt>
<dd><p>Only meaningful if instance_type is <code class="docutils literal notranslate"><span class="pre">Redis</span></code> and network type is VPC. Valid values are <code class="docutils literal notranslate"><span class="pre">Close</span></code>, <code class="docutils literal notranslate"><span class="pre">Open</span></code>. Defaults to <code class="docutils literal notranslate"><span class="pre">Open</span></code>.  <code class="docutils literal notranslate"><span class="pre">Close</span></code> means the redis instance can be accessed without authentication. <code class="docutils literal notranslate"><span class="pre">Open</span></code> means authentication is required.</p>
</dd></dl>

<dl class="py attribute">
<dt id="pulumi_alicloud.kvstore.Instance.vswitch_id">
<code class="sig-name descname">vswitch_id</code><em class="property">: pulumi.Output[str]</em><em class="property"> = None</em><a class="headerlink" href="#pulumi_alicloud.kvstore.Instance.vswitch_id" title="Permalink to this definition">¶</a></dt>
<dd><p>The ID of VSwitch.</p>
</dd></dl>

<dl class="py method">
<dt id="pulumi_alicloud.kvstore.Instance.get">
<em class="property">static </em><code class="sig-name descname">get</code><span class="sig-paren">(</span><em class="sig-param"><span class="n">resource_name</span></em>, <em class="sig-param"><span class="n">id</span></em>, <em class="sig-param"><span class="n">opts</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">auto_renew</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">auto_renew_period</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">availability_zone</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">backup_id</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">connection_domain</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">engine_version</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">instance_charge_type</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">instance_class</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">instance_name</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">instance_type</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">kms_encrypted_password</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">kms_encryption_context</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">maintain_end_time</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">maintain_start_time</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">parameters</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">password</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">period</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">private_ip</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">security_group_id</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">security_ips</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">tags</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">vpc_auth_mode</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">vswitch_id</span><span class="o">=</span><span class="default_value">None</span></em><span class="sig-paren">)</span><a class="headerlink" href="#pulumi_alicloud.kvstore.Instance.get" title="Permalink to this definition">¶</a></dt>
<dd><p>Get an existing Instance resource’s state with the given name, id, and optional extra
properties used to qualify the lookup.</p>
<dl class="field-list simple">
<dt class="field-odd">Parameters</dt>
<dd class="field-odd"><ul class="simple">
<li><p><strong>resource_name</strong> (<em>str</em>) – The unique name of the resulting resource.</p></li>
<li><p><strong>id</strong> (<em>str</em>) – The unique provider ID of the resource to lookup.</p></li>
<li><p><strong>opts</strong> (<a class="reference internal" href="../../pulumi/#pulumi.ResourceOptions" title="pulumi.ResourceOptions"><em>pulumi.ResourceOptions</em></a>) – Options for the resource.</p></li>
<li><p><strong>auto_renew</strong> (<em>pulumi.Input</em><em>[</em><em>bool</em><em>]</em>) – Whether to renewal a DB instance automatically or not. It is valid when instance_charge_type is <code class="docutils literal notranslate"><span class="pre">PrePaid</span></code>. Default to <code class="docutils literal notranslate"><span class="pre">false</span></code>.</p></li>
<li><p><strong>auto_renew_period</strong> (<em>pulumi.Input</em><em>[</em><em>float</em><em>]</em>) – Auto-renewal period of an instance, in the unit of the month. It is valid when instance_charge_type is <code class="docutils literal notranslate"><span class="pre">PrePaid</span></code>. Valid value:[1~12], Default to 1.</p></li>
<li><p><strong>availability_zone</strong> (<em>pulumi.Input</em><em>[</em><em>str</em><em>]</em>) – The Zone to launch the DB instance.</p></li>
<li><p><strong>backup_id</strong> (<em>pulumi.Input</em><em>[</em><em>str</em><em>]</em>) – If an instance created based on a backup set generated by another instance is valid, this parameter indicates the ID of the generated backup set.</p></li>
<li><p><strong>connection_domain</strong> (<em>pulumi.Input</em><em>[</em><em>str</em><em>]</em>) – Instance connection domain (only Intranet access supported).</p></li>
<li><p><strong>engine_version</strong> (<em>pulumi.Input</em><em>[</em><em>str</em><em>]</em>) – Engine version. Supported values: 2.8, 4.0 and 5.0. Default value: 2.8. Only 2.8 can be supported for Memcache Instance.</p></li>
<li><p><strong>instance_charge_type</strong> (<em>pulumi.Input</em><em>[</em><em>str</em><em>]</em>) – Valid values are <code class="docutils literal notranslate"><span class="pre">PrePaid</span></code>, <code class="docutils literal notranslate"><span class="pre">PostPaid</span></code>, Default to <code class="docutils literal notranslate"><span class="pre">PostPaid</span></code>.</p></li>
<li><p><strong>instance_name</strong> (<em>pulumi.Input</em><em>[</em><em>str</em><em>]</em>) – The name of DB instance. It a string of 2 to 256 characters.</p></li>
<li><p><strong>instance_type</strong> (<em>pulumi.Input</em><em>[</em><em>str</em><em>]</em>) – The engine to use: <code class="docutils literal notranslate"><span class="pre">Redis</span></code> or <code class="docutils literal notranslate"><span class="pre">Memcache</span></code>. Defaults to <code class="docutils literal notranslate"><span class="pre">Redis</span></code>.</p></li>
<li><p><strong>kms_encrypted_password</strong> (<em>pulumi.Input</em><em>[</em><em>str</em><em>]</em>) – An KMS encrypts password used to a instance. If the <code class="docutils literal notranslate"><span class="pre">password</span></code> is filled in, this field will be ignored.</p></li>
<li><p><strong>kms_encryption_context</strong> (<em>pulumi.Input</em><em>[</em><em>dict</em><em>]</em>) – <p>An KMS encryption context used to decrypt <code class="docutils literal notranslate"><span class="pre">kms_encrypted_password</span></code> before creating or updating instance with <code class="docutils literal notranslate"><span class="pre">kms_encrypted_password</span></code>. See <a class="reference external" href="https://www.alibabacloud.com/help/doc-detail/42975.htm">Encryption Context</a>. It is valid when <code class="docutils literal notranslate"><span class="pre">kms_encrypted_password</span></code> is set.</p>
</p></li>
<li><p><strong>maintain_end_time</strong> (<em>pulumi.Input</em><em>[</em><em>str</em><em>]</em>) – The end time of the operation and maintenance time period of the instance, in the format of HH:mmZ (UTC time).</p></li>
<li><p><strong>maintain_start_time</strong> (<em>pulumi.Input</em><em>[</em><em>str</em><em>]</em>) – The start time of the operation and maintenance time period of the instance, in the format of HH:mmZ (UTC time).</p></li>
<li><p><strong>parameters</strong> (<em>pulumi.Input</em><em>[</em><em>list</em><em>]</em>) – <p>Set of parameters needs to be set after instance was launched. Available parameters can refer to the latest docs <a class="reference external" href="https://www.alibabacloud.com/help/doc-detail/61209.htm">Instance configurations table</a> .</p>
</p></li>
<li><p><strong>password</strong> (<em>pulumi.Input</em><em>[</em><em>str</em><em>]</em>) – The password of the DB instance. The password is a string of 8 to 30 characters and must contain uppercase letters, lowercase letters, and numbers.</p></li>
<li><p><strong>period</strong> (<em>pulumi.Input</em><em>[</em><em>float</em><em>]</em>) – The duration that you will buy DB instance (in month). It is valid when instance_charge_type is <code class="docutils literal notranslate"><span class="pre">PrePaid</span></code>. Valid values: [1~9], 12, 24, 36. Default to 1.</p></li>
<li><p><strong>private_ip</strong> (<em>pulumi.Input</em><em>[</em><em>str</em><em>]</em>) – Set the instance’s private IP.</p></li>
<li><p><strong>security_group_id</strong> (<em>pulumi.Input</em><em>[</em><em>str</em><em>]</em>) – The Security Group ID of ECS.</p></li>
<li><p><strong>security_ips</strong> (<em>pulumi.Input</em><em>[</em><em>list</em><em>]</em>) – Set the instance’s IP whitelist of the default security group.</p></li>
<li><p><strong>tags</strong> (<em>pulumi.Input</em><em>[</em><em>dict</em><em>]</em>) – A mapping of tags to assign to the resource.</p></li>
<li><p><strong>vpc_auth_mode</strong> (<em>pulumi.Input</em><em>[</em><em>str</em><em>]</em>) – Only meaningful if instance_type is <code class="docutils literal notranslate"><span class="pre">Redis</span></code> and network type is VPC. Valid values are <code class="docutils literal notranslate"><span class="pre">Close</span></code>, <code class="docutils literal notranslate"><span class="pre">Open</span></code>. Defaults to <code class="docutils literal notranslate"><span class="pre">Open</span></code>.  <code class="docutils literal notranslate"><span class="pre">Close</span></code> means the redis instance can be accessed without authentication. <code class="docutils literal notranslate"><span class="pre">Open</span></code> means authentication is required.</p></li>
<li><p><strong>vswitch_id</strong> (<em>pulumi.Input</em><em>[</em><em>str</em><em>]</em>) – The ID of VSwitch.</p></li>
</ul>
</dd>
</dl>
<p>The <strong>parameters</strong> object supports the following:</p>
<ul class="simple">
<li><p><code class="docutils literal notranslate"><span class="pre">name</span></code> (<code class="docutils literal notranslate"><span class="pre">pulumi.Input[str]</span></code>)</p></li>
<li><p><code class="docutils literal notranslate"><span class="pre">value</span></code> (<code class="docutils literal notranslate"><span class="pre">pulumi.Input[str]</span></code>)</p></li>
</ul>
</dd></dl>

<dl class="py method">
<dt id="pulumi_alicloud.kvstore.Instance.translate_output_property">
<code class="sig-name descname">translate_output_property</code><span class="sig-paren">(</span><em class="sig-param"><span class="n">prop</span></em><span class="sig-paren">)</span><a class="headerlink" href="#pulumi_alicloud.kvstore.Instance.translate_output_property" title="Permalink to this definition">¶</a></dt>
<dd><p>Provides subclasses of Resource an opportunity to translate names of output properties
into a format of their choosing before writing those properties to the resource object.</p>
<dl class="field-list simple">
<dt class="field-odd">Parameters</dt>
<dd class="field-odd"><p><strong>prop</strong> (<em>str</em>) – A property name.</p>
</dd>
<dt class="field-even">Returns</dt>
<dd class="field-even"><p>A potentially transformed property name.</p>
</dd>
<dt class="field-odd">Return type</dt>
<dd class="field-odd"><p>str</p>
</dd>
</dl>
</dd></dl>

<dl class="py method">
<dt id="pulumi_alicloud.kvstore.Instance.translate_input_property">
<code class="sig-name descname">translate_input_property</code><span class="sig-paren">(</span><em class="sig-param"><span class="n">prop</span></em><span class="sig-paren">)</span><a class="headerlink" href="#pulumi_alicloud.kvstore.Instance.translate_input_property" title="Permalink to this definition">¶</a></dt>
<dd><p>Provides subclasses of Resource an opportunity to translate names of input properties into
a format of their choosing before sending those properties to the Pulumi engine.</p>
<dl class="field-list simple">
<dt class="field-odd">Parameters</dt>
<dd class="field-odd"><p><strong>prop</strong> (<em>str</em>) – A property name.</p>
</dd>
<dt class="field-even">Returns</dt>
<dd class="field-even"><p>A potentially transformed property name.</p>
</dd>
<dt class="field-odd">Return type</dt>
<dd class="field-odd"><p>str</p>
</dd>
</dl>
</dd></dl>

</dd></dl>

<dl class="py function">
<dt id="pulumi_alicloud.kvstore.get_instance_classes">
<code class="sig-prename descclassname">pulumi_alicloud.kvstore.</code><code class="sig-name descname">get_instance_classes</code><span class="sig-paren">(</span><em class="sig-param"><span class="n">architecture</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">edition_type</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">engine</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">engine_version</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">instance_charge_type</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">node_type</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">output_file</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">package_type</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">performance_type</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">series_type</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">shard_number</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">sorted_by</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">storage_type</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">zone_id</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">opts</span><span class="o">=</span><span class="default_value">None</span></em><span class="sig-paren">)</span><a class="headerlink" href="#pulumi_alicloud.kvstore.get_instance_classes" title="Permalink to this definition">¶</a></dt>
<dd><p>This data source provides the KVStore instance classes resource available info of Alibaba Cloud.</p>
<blockquote>
<div><p><strong>NOTE:</strong> Available in v1.49.0+</p>
</div></blockquote>
<div class="highlight-python notranslate"><div class="highlight"><pre><span></span><span class="kn">import</span> <span class="nn">pulumi</span>
<span class="kn">import</span> <span class="nn">pulumi_alicloud</span> <span class="k">as</span> <span class="nn">alicloud</span>

<span class="n">resources_zones</span> <span class="o">=</span> <span class="n">alicloud</span><span class="o">.</span><span class="n">get_zones</span><span class="p">(</span><span class="n">available_resource_creation</span><span class="o">=</span><span class="s2">&quot;KVStore&quot;</span><span class="p">)</span>
<span class="n">resources_instance_classes</span> <span class="o">=</span> <span class="n">alicloud</span><span class="o">.</span><span class="n">kvstore</span><span class="o">.</span><span class="n">get_instance_classes</span><span class="p">(</span><span class="n">engine</span><span class="o">=</span><span class="s2">&quot;Redis&quot;</span><span class="p">,</span>
    <span class="n">engine_version</span><span class="o">=</span><span class="s2">&quot;5.0&quot;</span><span class="p">,</span>
    <span class="n">instance_charge_type</span><span class="o">=</span><span class="s2">&quot;PrePaid&quot;</span><span class="p">,</span>
    <span class="n">output_file</span><span class="o">=</span><span class="s2">&quot;./classes.txt&quot;</span><span class="p">,</span>
    <span class="n">zone_id</span><span class="o">=</span><span class="n">resources_zones</span><span class="o">.</span><span class="n">zones</span><span class="p">[</span><span class="mi">0</span><span class="p">][</span><span class="s2">&quot;id&quot;</span><span class="p">])</span>
<span class="n">pulumi</span><span class="o">.</span><span class="n">export</span><span class="p">(</span><span class="s2">&quot;firstKvstoreInstanceClass&quot;</span><span class="p">,</span> <span class="n">resources_instance_classes</span><span class="o">.</span><span class="n">instance_classes</span><span class="p">)</span>
</pre></div>
</div>
<dl class="field-list simple">
<dt class="field-odd">Parameters</dt>
<dd class="field-odd"><ul class="simple">
<li><p><strong>architecture</strong> (<em>str</em>) – The KVStore instance system architecture required by the user. Valid values: <code class="docutils literal notranslate"><span class="pre">standard</span></code>, <code class="docutils literal notranslate"><span class="pre">cluster</span></code> and <code class="docutils literal notranslate"><span class="pre">rwsplit</span></code>.</p></li>
<li><p><strong>edition_type</strong> (<em>str</em>) – The KVStore instance edition type required by the user. Valid values: <code class="docutils literal notranslate"><span class="pre">Community</span></code> and <code class="docutils literal notranslate"><span class="pre">Enterprise</span></code>.</p></li>
<li><p><strong>engine</strong> (<em>str</em>) – Database type. Options are <code class="docutils literal notranslate"><span class="pre">Redis</span></code>, <code class="docutils literal notranslate"><span class="pre">Memcache</span></code>. Default to <code class="docutils literal notranslate"><span class="pre">Redis</span></code>.</p></li>
<li><p><strong>engine_version</strong> (<em>str</em>) – Database version required by the user. Value options of Redis can refer to the latest docs <a class="reference external" href="https://www.alibabacloud.com/help/doc-detail/60873.htm">detail info</a> <code class="docutils literal notranslate"><span class="pre">EngineVersion</span></code>. Value of Memcache should be empty.</p></li>
<li><p><strong>instance_charge_type</strong> (<em>str</em>) – Filter the results by charge type. Valid values: <code class="docutils literal notranslate"><span class="pre">PrePaid</span></code> and <code class="docutils literal notranslate"><span class="pre">PostPaid</span></code>. Default to <code class="docutils literal notranslate"><span class="pre">PrePaid</span></code>.</p></li>
<li><p><strong>node_type</strong> (<em>str</em>) – The KVStore instance node type required by the user. Valid values: <code class="docutils literal notranslate"><span class="pre">double</span></code>, <code class="docutils literal notranslate"><span class="pre">single</span></code>, <code class="docutils literal notranslate"><span class="pre">readone</span></code>, <code class="docutils literal notranslate"><span class="pre">readthree</span></code> and <code class="docutils literal notranslate"><span class="pre">readfive</span></code>.</p></li>
<li><p><strong>package_type</strong> (<em>str</em>) – It has been deprecated from 1.68.0.</p></li>
<li><p><strong>performance_type</strong> (<em>str</em>) – It has been deprecated from 1.68.0.</p></li>
<li><p><strong>series_type</strong> (<em>str</em>) – The KVStore instance series type required by the user. Valid values: <code class="docutils literal notranslate"><span class="pre">enhanced_performance_type</span></code> and <code class="docutils literal notranslate"><span class="pre">hybrid_storage</span></code>.</p></li>
<li><p><strong>shard_number</strong> (<em>float</em>) – The number of shard.Valid values: <code class="docutils literal notranslate"><span class="pre">1</span></code>, <code class="docutils literal notranslate"><span class="pre">2</span></code>, <code class="docutils literal notranslate"><span class="pre">4</span></code>, <code class="docutils literal notranslate"><span class="pre">8</span></code>, <code class="docutils literal notranslate"><span class="pre">16</span></code>, <code class="docutils literal notranslate"><span class="pre">32</span></code>, <code class="docutils literal notranslate"><span class="pre">64</span></code>, <code class="docutils literal notranslate"><span class="pre">128</span></code>, <code class="docutils literal notranslate"><span class="pre">256</span></code>.</p></li>
<li><p><strong>storage_type</strong> (<em>str</em>) – It has been deprecated from 1.68.0.</p></li>
<li><p><strong>zone_id</strong> (<em>str</em>) – The Zone to launch the KVStore instance.</p></li>
</ul>
</dd>
</dl>
</dd></dl>

<dl class="py function">
<dt id="pulumi_alicloud.kvstore.get_instance_engines">
<code class="sig-prename descclassname">pulumi_alicloud.kvstore.</code><code class="sig-name descname">get_instance_engines</code><span class="sig-paren">(</span><em class="sig-param"><span class="n">engine</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">engine_version</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">instance_charge_type</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">output_file</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">zone_id</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">opts</span><span class="o">=</span><span class="default_value">None</span></em><span class="sig-paren">)</span><a class="headerlink" href="#pulumi_alicloud.kvstore.get_instance_engines" title="Permalink to this definition">¶</a></dt>
<dd><p>This data source provides the KVStore instance engines resource available info of Alibaba Cloud.</p>
<blockquote>
<div><p><strong>NOTE:</strong> Available in v1.51.0+</p>
</div></blockquote>
<div class="highlight-python notranslate"><div class="highlight"><pre><span></span><span class="kn">import</span> <span class="nn">pulumi</span>
<span class="kn">import</span> <span class="nn">pulumi_alicloud</span> <span class="k">as</span> <span class="nn">alicloud</span>

<span class="n">resources_zones</span> <span class="o">=</span> <span class="n">alicloud</span><span class="o">.</span><span class="n">get_zones</span><span class="p">(</span><span class="n">available_resource_creation</span><span class="o">=</span><span class="s2">&quot;KVStore&quot;</span><span class="p">)</span>
<span class="n">resources_instance_engines</span> <span class="o">=</span> <span class="n">alicloud</span><span class="o">.</span><span class="n">kvstore</span><span class="o">.</span><span class="n">get_instance_engines</span><span class="p">(</span><span class="n">engine</span><span class="o">=</span><span class="s2">&quot;Redis&quot;</span><span class="p">,</span>
    <span class="n">engine_version</span><span class="o">=</span><span class="s2">&quot;5.0&quot;</span><span class="p">,</span>
    <span class="n">instance_charge_type</span><span class="o">=</span><span class="s2">&quot;PrePaid&quot;</span><span class="p">,</span>
    <span class="n">output_file</span><span class="o">=</span><span class="s2">&quot;./engines.txt&quot;</span><span class="p">,</span>
    <span class="n">zone_id</span><span class="o">=</span><span class="n">resources_zones</span><span class="o">.</span><span class="n">zones</span><span class="p">[</span><span class="mi">0</span><span class="p">][</span><span class="s2">&quot;id&quot;</span><span class="p">])</span>
<span class="n">pulumi</span><span class="o">.</span><span class="n">export</span><span class="p">(</span><span class="s2">&quot;firstKvstoreInstanceClass&quot;</span><span class="p">,</span> <span class="n">resources_instance_engines</span><span class="o">.</span><span class="n">instance_engines</span><span class="p">[</span><span class="mi">0</span><span class="p">][</span><span class="s2">&quot;engine&quot;</span><span class="p">])</span>
</pre></div>
</div>
<dl class="field-list simple">
<dt class="field-odd">Parameters</dt>
<dd class="field-odd"><ul class="simple">
<li><p><strong>engine</strong> (<em>str</em>) – Database type. Options are <code class="docutils literal notranslate"><span class="pre">Redis</span></code>, <code class="docutils literal notranslate"><span class="pre">Memcache</span></code>. Default to <code class="docutils literal notranslate"><span class="pre">Redis</span></code>.</p></li>
<li><p><strong>engine_version</strong> (<em>str</em>) – <p>Database version required by the user. Value options of Redis can refer to the latest docs <a class="reference external" href="https://www.alibabacloud.com/help/doc-detail/60873.htm">detail info</a> <code class="docutils literal notranslate"><span class="pre">EngineVersion</span></code>. Value of Memcache should be empty.</p>
</p></li>
<li><p><strong>instance_charge_type</strong> (<em>str</em>) – Filter the results by charge type. Valid values: <code class="docutils literal notranslate"><span class="pre">PrePaid</span></code> and <code class="docutils literal notranslate"><span class="pre">PostPaid</span></code>. Default to <code class="docutils literal notranslate"><span class="pre">PrePaid</span></code>.</p></li>
<li><p><strong>zone_id</strong> (<em>str</em>) – The Zone to launch the KVStore instance.</p></li>
</ul>
</dd>
</dl>
</dd></dl>

<dl class="py function">
<dt id="pulumi_alicloud.kvstore.get_instances">
<code class="sig-prename descclassname">pulumi_alicloud.kvstore.</code><code class="sig-name descname">get_instances</code><span class="sig-paren">(</span><em class="sig-param"><span class="n">ids</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">instance_class</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">instance_type</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">name_regex</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">output_file</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">status</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">tags</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">vpc_id</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">vswitch_id</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">opts</span><span class="o">=</span><span class="default_value">None</span></em><span class="sig-paren">)</span><a class="headerlink" href="#pulumi_alicloud.kvstore.get_instances" title="Permalink to this definition">¶</a></dt>
<dd><p>The <code class="docutils literal notranslate"><span class="pre">kvstore.getInstances</span></code> data source provides a collection of kvstore instances available in Alicloud account.
Filters support regular expression for the instance name, searches by tags, and other filters which are listed below.</p>
<dl class="field-list simple">
<dt class="field-odd">Parameters</dt>
<dd class="field-odd"><ul class="simple">
<li><p><strong>ids</strong> (<em>list</em>) – A list of RKV instance IDs.</p></li>
<li><p><strong>instance_class</strong> (<em>str</em>) – <p>Type of the applied ApsaraDB for Redis instance.
For more information, see <a class="reference external" href="https://www.alibabacloud.com/help/doc-detail/61135.htm">Instance type table</a>.</p>
</p></li>
<li><p><strong>instance_type</strong> (<em>str</em>) – Database type. Options are <code class="docutils literal notranslate"><span class="pre">Memcache</span></code>, and <code class="docutils literal notranslate"><span class="pre">Redis</span></code>. If no value is specified, all types are returned.</p></li>
<li><p><strong>name_regex</strong> (<em>str</em>) – A regex string to apply to the instance name.</p></li>
<li><p><strong>status</strong> (<em>str</em>) – Status of the instance.</p></li>
<li><p><strong>tags</strong> (<em>dict</em>) – Query the instance bound to the tag. The format of the incoming value is <code class="docutils literal notranslate"><span class="pre">json</span></code> string, including <code class="docutils literal notranslate"><span class="pre">TagKey</span></code> and <code class="docutils literal notranslate"><span class="pre">TagValue</span></code>. <code class="docutils literal notranslate"><span class="pre">TagKey</span></code> cannot be null, and <code class="docutils literal notranslate"><span class="pre">TagValue</span></code> can be empty. Format example <code class="docutils literal notranslate"><span class="pre">{&quot;key1&quot;:&quot;value1&quot;}</span></code>.</p></li>
<li><p><strong>vpc_id</strong> (<em>str</em>) – Used to retrieve instances belong to specified VPC.</p></li>
<li><p><strong>vswitch_id</strong> (<em>str</em>) – Used to retrieve instances belong to specified <code class="docutils literal notranslate"><span class="pre">vswitch</span></code> resources.</p></li>
</ul>
</dd>
</dl>
</dd></dl>

<dl class="py function">
<dt id="pulumi_alicloud.kvstore.get_zones">
<code class="sig-prename descclassname">pulumi_alicloud.kvstore.</code><code class="sig-name descname">get_zones</code><span class="sig-paren">(</span><em class="sig-param"><span class="n">instance_charge_type</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">multi</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">output_file</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">opts</span><span class="o">=</span><span class="default_value">None</span></em><span class="sig-paren">)</span><a class="headerlink" href="#pulumi_alicloud.kvstore.get_zones" title="Permalink to this definition">¶</a></dt>
<dd><p>This data source provides availability zones for KVStore that can be accessed by an Alibaba Cloud account within the region configured in the provider.</p>
<blockquote>
<div><p><strong>NOTE:</strong> Available in v1.73.0+.</p>
</div></blockquote>
<div class="highlight-python notranslate"><div class="highlight"><pre><span></span><span class="kn">import</span> <span class="nn">pulumi</span>
<span class="kn">import</span> <span class="nn">pulumi_alicloud</span> <span class="k">as</span> <span class="nn">alicloud</span>

<span class="n">zones_ids</span> <span class="o">=</span> <span class="n">alicloud</span><span class="o">.</span><span class="n">kvstore</span><span class="o">.</span><span class="n">get_zones</span><span class="p">()</span>
<span class="c1"># Create an KVStore instance with the first matched zone</span>
<span class="n">kvstore</span> <span class="o">=</span> <span class="n">alicloud</span><span class="o">.</span><span class="n">kvstore</span><span class="o">.</span><span class="n">Instance</span><span class="p">(</span><span class="s2">&quot;kvstore&quot;</span><span class="p">,</span> <span class="n">availability_zone</span><span class="o">=</span><span class="n">zones_ids</span><span class="o">.</span><span class="n">zones</span><span class="p">[</span><span class="mi">0</span><span class="p">][</span><span class="s2">&quot;id&quot;</span><span class="p">])</span>
<span class="c1"># Other properties...</span>
</pre></div>
</div>
<dl class="field-list simple">
<dt class="field-odd">Parameters</dt>
<dd class="field-odd"><ul class="simple">
<li><p><strong>instance_charge_type</strong> (<em>str</em>) – Filter the results by a specific instance charge type. Valid values: <code class="docutils literal notranslate"><span class="pre">PrePaid</span></code> and <code class="docutils literal notranslate"><span class="pre">PostPaid</span></code>. Default to <code class="docutils literal notranslate"><span class="pre">PostPaid</span></code>.</p></li>
<li><p><strong>multi</strong> (<em>bool</em>) – Indicate whether the zones can be used in a multi AZ configuration. Default to <code class="docutils literal notranslate"><span class="pre">false</span></code>. Multi AZ is usually used to launch KVStore instances.</p></li>
</ul>
</dd>
</dl>
</dd></dl>

</div>
