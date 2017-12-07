<div class="post_content" itemprop="articleBody"><h1 class="headline" itemprop="headline">PHP Form Validation Script</h1><p>It is very essential to have the input to your form validated before taking the form submission data for further processing. When there are many fields in the form, the PHP validation script becomes too complex. Moreover, since you are doing the same or similar validation for most of the forms that you make, just too much of duplicate effort is spent on form validations.<br><span id="more-331"></span></p><h2>About this generic PHP form validation script</h2><p>This generic PHP form validator script makes it very easy to add validations to your form.</p><p>We create and associate a set of “validation descriptors” with each element in the form. The “validation descriptor” is a string specifying the type of validation to be performed. For example, “req” means required, “alpha” means allow only alphabetic characters and so on.</p><p>Each field in the form can have zero, one or more validations. For example, the input should not be empty, should be less than 25 chars, should be alpha-numeric, etc</p><p>You can associate a set of validation descriptors for each input field in the form.</p><h2>Using the PHP form validation script</h2><ol><li>Include formvalidator.php in your form processing script</li><div id="highlighter_581344" class="syntaxhighlighter  "><div class="bar  "><div class="toolbar"><a href="#viewSource" title="view source" style="width: 16px; height: 16px;" class="item viewSource">view source</a><div class="item copyToClipboard"><embed id="highlighter_581344_clipboard" type="application/x-shockwave-flash" title="copy to clipboard" allowscriptaccess="always" wmode="transparent" flashvars="highlighterId=highlighter_581344" menu="false" src="http://form.guide/wp-content/plugins/syntaxhighlighter/syntaxhighlighter2/scripts/clipboard.swf" width="16" height="16"></div><a href="#printSource" title="print" style="width: 16px; height: 16px;" class="item printSource">print</a><a href="#about" title="?" style="width: 16px; height: 16px;" class="item about">?</a></div></div><div class="lines"><div class="line alt1"><table><tbody><tr><td class="number"><code>1</code></td><td class="content"><code class="keyword">require_once</code> <code class="string">"formvalidator.php"</code></td></tr></tbody></table></div></div></div><li>Create a FormValidator object and add the form validation descriptors.</li><div id="highlighter_409245" class="syntaxhighlighter  "><div class="bar           "><div class="toolbar"><a href="#viewSource" title="view source" style="width: 16px; height: 16px;" class="item viewSource">view source</a><div class="item copyToClipboard"><embed id="highlighter_409245_clipboard" type="application/x-shockwave-flash" title="copy to clipboard" allowscriptaccess="always" wmode="transparent" flashvars="highlighterId=highlighter_409245" menu="false" src="http://form.guide/wp-content/plugins/syntaxhighlighter/syntaxhighlighter2/scripts/clipboard.swf" width="16" height="16"></div><a href="#printSource" title="print" style="width: 16px; height: 16px;" class="item printSource">print</a><a href="#about" title="?" style="width: 16px; height: 16px;" class="item about">?</a></div></div><div class="lines"><div class="line alt1"><table><tbody><tr><td class="number"><code>1</code></td><td class="content"><code class="variable">$validator</code> <code class="plain">= </code><code class="keyword">new</code> <code class="plain">FormValidator();</code></td></tr></tbody></table></div><div class="line alt2"><table><tbody><tr><td class="number"><code>2</code></td><td class="content"><code class="variable">$validator</code><code class="plain">-&gt;addValidation(</code><code class="string">"Name"</code><code class="plain">,</code><code class="string">"req"</code><code class="plain">,</code><code class="string">"Please fill in Name"</code><code class="plain">);</code></td></tr></tbody></table></div><div class="line alt1"><table><tbody><tr><td class="number"><code>3</code></td><td class="content"><code class="variable">$validator</code><code class="plain">-&gt;addValidation(</code><code class="string">"Email"</code><code class="plain">,</code><code class="string">"email"</code><code class="plain">,</code></td></tr></tbody></table></div><div class="line alt2"><table><tbody><tr><td class="number"><code>4</code></td><td class="content"><code class="string">"The input for Email should be a valid email value"</code><code class="plain">);</code></td></tr></tbody></table></div><div class="line alt1"><table><tbody><tr><td class="number"><code>5</code></td><td class="content"><code class="variable">$validator</code><code class="plain">-&gt;addValidation(</code><code class="string">"Email"</code><code class="plain">,</code><code class="string">"req"</code><code class="plain">,</code><code class="string">"Please fill in Email"</code><code class="plain">); </code></td></tr></tbody></table></div></div></div><p>The first argument is the name of the input field in the form. The second argument is the validation descriptor that tells the type of the validation required. The third argument is the error message to be displayed if the validation fails.</p><li>Validate the form by calling ValidateForm() function</li><div id="highlighter_62351" class="syntaxhighlighter  "><div class="bar         "><div class="toolbar"><a href="#viewSource" title="view source" style="width: 16px; height: 16px;" class="item viewSource">view source</a><div class="item copyToClipboard"><embed id="highlighter_62351_clipboard" type="application/x-shockwave-flash" title="copy to clipboard" allowscriptaccess="always" wmode="transparent" flashvars="highlighterId=highlighter_62351" menu="false" src="http://form.guide/wp-content/plugins/syntaxhighlighter/syntaxhighlighter2/scripts/clipboard.swf" width="16" height="16"></div><a href="#printSource" title="print" style="width: 16px; height: 16px;" class="item printSource">print</a><a href="#about" title="?" style="width: 16px; height: 16px;" class="item about">?</a></div></div><div class="lines"><div class="line alt1"><table><tbody><tr><td class="number"><code>1</code></td><td class="content"><code class="keyword">if</code><code class="plain">(!</code><code class="variable">$validator</code><code class="plain">-&gt;ValidateForm())</code></td></tr></tbody></table></div><div class="line alt2"><table><tbody><tr><td class="number"><code>2</code></td><td class="content"><code class="plain">{</code></td></tr></tbody></table></div><div class="line alt1"><table><tbody><tr><td class="number"><code>3</code></td><td class="content"><code class="spaces">&nbsp;&nbsp;&nbsp;&nbsp;</code><code class="functions">echo</code> <code class="string">"&lt;B&gt;Validation Errors:&lt;/B&gt;"</code><code class="plain">;</code></td></tr></tbody></table></div><div class="line alt2"><table><tbody><tr><td class="number"><code>4</code></td><td class="content"><code class="spaces">&nbsp;&nbsp;&nbsp;&nbsp;</code><code class="variable">$error_hash</code> <code class="plain">= </code><code class="variable">$validator</code><code class="plain">-&gt;GetErrors();</code></td></tr></tbody></table></div><div class="line alt1"><table><tbody><tr><td class="number"><code>5</code></td><td class="content"><code class="spaces">&nbsp;&nbsp;&nbsp;&nbsp;</code><code class="keyword">foreach</code><code class="plain">(</code><code class="variable">$error_hash</code> <code class="keyword">as</code> <code class="variable">$inpname</code> <code class="plain">=&gt; </code><code class="variable">$inp_err</code><code class="plain">)</code></td></tr></tbody></table></div><div class="line alt2"><table><tbody><tr><td class="number"><code>6</code></td><td class="content"><code class="spaces">&nbsp;&nbsp;&nbsp;&nbsp;</code><code class="plain">{</code></td></tr></tbody></table></div><div class="line alt1"><table><tbody><tr><td class="number"><code>7</code></td><td class="content"><code class="spaces">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</code><code class="functions">echo</code> <code class="string">"&lt;p&gt;$inpname : $inp_err&lt;/p&gt;\n"</code><code class="plain">;</code></td></tr></tbody></table></div><div class="line alt2"><table><tbody><tr><td class="number"><code>8</code></td><td class="content"><code class="spaces">&nbsp;&nbsp;&nbsp;&nbsp;</code><code class="plain">}</code></td></tr></tbody></table></div><div class="line alt1"><table><tbody><tr><td class="number"><code>9</code></td><td class="content"><code class="plain">}</code></td></tr></tbody></table></div></div></div></ol><h2>Example</h2><p>The example below will make the idea clearer</p><div><div id="highlighter_955635" class="syntaxhighlighter  "><div class="bar        "><div class="toolbar"><a href="#viewSource" title="view source" style="width: 16px; height: 16px;" class="item viewSource">view source</a><div class="item copyToClipboard"><embed id="highlighter_955635_clipboard" type="application/x-shockwave-flash" title="copy to clipboard" allowscriptaccess="always" wmode="transparent" flashvars="highlighterId=highlighter_955635" menu="false" src="http://form.guide/wp-content/plugins/syntaxhighlighter/syntaxhighlighter2/scripts/clipboard.swf" width="16" height="16"></div><a href="#printSource" title="print" style="width: 16px; height: 16px;" class="item printSource">print</a><a href="#about" title="?" style="width: 16px; height: 16px;" class="item about">?</a></div></div><div class="lines"><div class="line alt1"><table><tbody><tr><td class="number"><code>1</code></td><td class="content"><code class="plain">&lt;?PHP</code></td></tr></tbody></table></div><div class="line alt2"><table><tbody><tr><td class="number"><code>2</code></td><td class="content"><code class="keyword">require_once</code> <code class="string">"formvalidator.php"</code><code class="plain">;</code></td></tr></tbody></table></div><div class="line alt1"><table><tbody><tr><td class="number"><code>3</code></td><td class="content"><code class="variable">$show_form</code><code class="plain">=true;</code></td></tr></tbody></table></div><div class="line alt2"><table><tbody><tr><td class="number"><code>4</code></td><td class="content"><code class="keyword">if</code><code class="plain">(isset(</code><code class="variable">$_POST</code><code class="plain">[</code><code class="string">'Submit'</code><code class="plain">]))</code></td></tr></tbody></table></div><div class="line alt1"><table><tbody><tr><td class="number"><code>5</code></td><td class="content"><code class="plain">{</code></td></tr></tbody></table></div><div class="line alt2"><table><tbody><tr><td class="number"><code>6</code></td><td class="content"><code class="spaces">&nbsp;&nbsp;&nbsp;&nbsp;</code><code class="variable">$validator</code> <code class="plain">= </code><code class="keyword">new</code> <code class="plain">FormValidator();</code></td></tr></tbody></table></div><div class="line alt1"><table><tbody><tr><td class="number"><code>7</code></td><td class="content"><code class="spaces">&nbsp;&nbsp;&nbsp;&nbsp;</code><code class="variable">$validator</code><code class="plain">-&gt;addValidation(</code><code class="string">"Name"</code><code class="plain">,</code><code class="string">"req"</code><code class="plain">,</code><code class="string">"Please fill in Name"</code><code class="plain">);</code></td></tr></tbody></table></div><div class="line alt2"><table><tbody><tr><td class="number"><code>8</code></td><td class="content"><code class="spaces">&nbsp;&nbsp;&nbsp;&nbsp;</code><code class="variable">$validator</code><code class="plain">-&gt;addValidation(</code><code class="string">"Email"</code><code class="plain">,</code><code class="string">"email"</code><code class="plain">,</code></td></tr></tbody></table></div><div class="line alt1"><table><tbody><tr><td class="number"><code>9</code></td><td class="content"><code class="string">"The input for Email should be a valid email value"</code><code class="plain">);</code></td></tr></tbody></table></div><div class="line alt2"><table><tbody><tr><td class="number"><code>10</code></td><td class="content"><code class="spaces">&nbsp;&nbsp;&nbsp;&nbsp;</code><code class="variable">$validator</code><code class="plain">-&gt;addValidation(</code><code class="string">"Email"</code><code class="plain">,</code><code class="string">"req"</code><code class="plain">,</code><code class="string">"Please fill in Email"</code><code class="plain">);</code></td></tr></tbody></table></div><div class="line alt1"><table><tbody><tr><td class="number"><code>11</code></td><td class="content"><code class="spaces">&nbsp;&nbsp;&nbsp;&nbsp;</code><code class="keyword">if</code><code class="plain">(</code><code class="variable">$validator</code><code class="plain">-&gt;ValidateForm())</code></td></tr></tbody></table></div><div class="line alt2"><table><tbody><tr><td class="number"><code>12</code></td><td class="content"><code class="spaces">&nbsp;&nbsp;&nbsp;&nbsp;</code><code class="plain">{</code></td></tr></tbody></table></div><div class="line alt1"><table><tbody><tr><td class="number"><code>13</code></td><td class="content"><code class="spaces">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</code><code class="functions">echo</code> <code class="string">"&lt;h2&gt;Validation Success!&lt;/h2&gt;"</code><code class="plain">;</code></td></tr></tbody></table></div><div class="line alt2"><table><tbody><tr><td class="number"><code>14</code></td><td class="content"><code class="spaces">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</code><code class="variable">$show_form</code><code class="plain">=false;</code></td></tr></tbody></table></div><div class="line alt1"><table><tbody><tr><td class="number"><code>15</code></td><td class="content"><code class="spaces">&nbsp;&nbsp;&nbsp;&nbsp;</code><code class="plain">}</code></td></tr></tbody></table></div><div class="line alt2"><table><tbody><tr><td class="number"><code>16</code></td><td class="content"><code class="spaces">&nbsp;&nbsp;&nbsp;&nbsp;</code><code class="keyword">else</code></td></tr></tbody></table></div><div class="line alt1"><table><tbody><tr><td class="number"><code>17</code></td><td class="content"><code class="spaces">&nbsp;&nbsp;&nbsp;&nbsp;</code><code class="plain">{</code></td></tr></tbody></table></div><div class="line alt2"><table><tbody><tr><td class="number"><code>18</code></td><td class="content"><code class="spaces">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</code><code class="functions">echo</code> <code class="string">"&lt;B&gt;Validation Errors:&lt;/B&gt;"</code><code class="plain">;</code></td></tr></tbody></table></div><div class="line alt1"><table><tbody><tr><td class="number"><code>19</code></td><td class="content">&nbsp;</td></tr></tbody></table></div><div class="line alt2"><table><tbody><tr><td class="number"><code>20</code></td><td class="content"><code class="spaces">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</code><code class="variable">$error_hash</code> <code class="plain">= </code><code class="variable">$validator</code><code class="plain">-&gt;GetErrors();</code></td></tr></tbody></table></div><div class="line alt1"><table><tbody><tr><td class="number"><code>21</code></td><td class="content"><code class="spaces">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</code><code class="keyword">foreach</code><code class="plain">(</code><code class="variable">$error_hash</code> <code class="keyword">as</code> <code class="variable">$inpname</code> <code class="plain">=&gt; </code><code class="variable">$inp_err</code><code class="plain">)</code></td></tr></tbody></table></div><div class="line alt2"><table><tbody><tr><td class="number"><code>22</code></td><td class="content"><code class="spaces">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</code><code class="plain">{</code></td></tr></tbody></table></div><div class="line alt1"><table><tbody><tr><td class="number"><code>23</code></td><td class="content"><code class="spaces">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</code><code class="functions">echo</code> <code class="string">"&lt;p&gt;$inpname : $inp_err&lt;/p&gt;\n"</code><code class="plain">;</code></td></tr></tbody></table></div><div class="line alt2"><table><tbody><tr><td class="number"><code>24</code></td><td class="content"><code class="spaces">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</code><code class="plain">}</code></td></tr></tbody></table></div><div class="line alt1"><table><tbody><tr><td class="number"><code>25</code></td><td class="content"><code class="spaces">&nbsp;&nbsp;&nbsp;&nbsp;</code><code class="plain">}</code></td></tr></tbody></table></div><div class="line alt2"><table><tbody><tr><td class="number"><code>26</code></td><td class="content"><code class="plain">}</code></td></tr></tbody></table></div><div class="line alt1"><table><tbody><tr><td class="number"><code>27</code></td><td class="content">&nbsp;</td></tr></tbody></table></div><div class="line alt2"><table><tbody><tr><td class="number"><code>28</code></td><td class="content"><code class="keyword">if</code><code class="plain">(true == </code><code class="variable">$show_form</code><code class="plain">)</code></td></tr></tbody></table></div><div class="line alt1"><table><tbody><tr><td class="number"><code>29</code></td><td class="content"><code class="plain">{</code></td></tr></tbody></table></div><div class="line alt2"><table><tbody><tr><td class="number"><code>30</code></td><td class="content"><code class="plain">?&gt;</code></td></tr></tbody></table></div></div></div></div><div><div id="highlighter_489705" class="syntaxhighlighter  "><div class="bar  "><div class="toolbar"><a href="#viewSource" title="view source" style="width: 16px; height: 16px;" class="item viewSource">view source</a><div class="item copyToClipboard"><embed id="highlighter_489705_clipboard" type="application/x-shockwave-flash" title="copy to clipboard" allowscriptaccess="always" wmode="transparent" flashvars="highlighterId=highlighter_489705" menu="false" src="http://form.guide/wp-content/plugins/syntaxhighlighter/syntaxhighlighter2/scripts/clipboard.swf" width="16" height="16"></div><a href="#printSource" title="print" style="width: 16px; height: 16px;" class="item printSource">print</a><a href="#about" title="?" style="width: 16px; height: 16px;" class="item about">?</a></div></div><div class="lines"><div class="line alt1"><table><tbody><tr><td class="number"><code>1</code></td><td class="content"><code class="plain">&lt;</code><code class="keyword">form</code> <code class="color1">name</code><code class="plain">=</code><code class="string">'test'</code> <code class="color1">method</code><code class="plain">=</code><code class="string">'POST'</code> <code class="color1">action</code><code class="plain">=</code><code class="string">''</code> <code class="color1">accept-charset</code><code class="plain">=</code><code class="string">'UTF-8'</code><code class="plain">&gt;</code></td></tr></tbody></table></div><div class="line alt2"><table><tbody><tr><td class="number"><code>2</code></td><td class="content"><code class="plain">Name: &lt;</code><code class="keyword">input</code> <code class="color1">type</code><code class="plain">=</code><code class="string">'text'</code> <code class="color1">name</code><code class="plain">=</code><code class="string">'Name'</code> <code class="color1">size</code><code class="plain">=</code><code class="string">'20'</code><code class="plain">&gt;</code></td></tr></tbody></table></div><div class="line alt1"><table><tbody><tr><td class="number"><code>3</code></td><td class="content"><code class="plain">Email: &lt;</code><code class="keyword">input</code> <code class="color1">type</code><code class="plain">=</code><code class="string">'text'</code> <code class="color1">name</code><code class="plain">=</code><code class="string">'Email'</code> <code class="color1">size</code><code class="plain">=</code><code class="string">'20'</code><code class="plain">&gt;</code></td></tr></tbody></table></div><div class="line alt2"><table><tbody><tr><td class="number"><code>4</code></td><td class="content"><code class="plain">&lt;</code><code class="keyword">input</code> <code class="color1">type</code><code class="plain">=</code><code class="string">'submit'</code> <code class="color1">name</code><code class="plain">=</code><code class="string">'Submit'</code> <code class="color1">value</code><code class="plain">=</code><code class="string">'Submit'</code><code class="plain">&gt;</code></td></tr></tbody></table></div><div class="line alt1"><table><tbody><tr><td class="number"><code>5</code></td><td class="content"><code class="plain">&lt;/</code><code class="keyword">form</code><code class="plain">&gt;</code></td></tr></tbody></table></div></div></div></div><div><div id="highlighter_207107" class="syntaxhighlighter  "><div class="bar "><div class="toolbar"><a href="#viewSource" title="view source" style="width: 16px; height: 16px;" class="item viewSource">view source</a><div class="item copyToClipboard"><embed id="highlighter_207107_clipboard" type="application/x-shockwave-flash" title="copy to clipboard" allowscriptaccess="always" wmode="transparent" flashvars="highlighterId=highlighter_207107" menu="false" src="http://form.guide/wp-content/plugins/syntaxhighlighter/syntaxhighlighter2/scripts/clipboard.swf" width="16" height="16"></div><a href="#printSource" title="print" style="width: 16px; height: 16px;" class="item printSource">print</a><a href="#about" title="?" style="width: 16px; height: 16px;" class="item about">?</a></div></div><div class="lines"><div class="line alt1"><table><tbody><tr><td class="number"><code>1</code></td><td class="content"><code class="plain">&lt;?PHP</code></td></tr></tbody></table></div><div class="line alt2"><table><tbody><tr><td class="number"><code>2</code></td><td class="content"><code class="plain">}</code><code class="comments">//true == $show_form</code></td></tr></tbody></table></div><div class="line alt1"><table><tbody><tr><td class="number"><code>3</code></td><td class="content"><code class="plain">?&gt;</code></td></tr></tbody></table></div></div></div></div><h2>Adding Custom Validation</h2><p>If you want to add a custom validation, which is not provided by the validation descriptors, you can do so. Here are the steps:</p><ol><li>Create a class for the custom validation and override the DoValidate() function</li><div><div id="highlighter_146717" class="syntaxhighlighter  "><div class="bar              "><div class="toolbar"><a href="#viewSource" title="view source" style="width: 16px; height: 16px;" class="item viewSource">view source</a><div class="item copyToClipboard"><embed id="highlighter_146717_clipboard" type="application/x-shockwave-flash" title="copy to clipboard" allowscriptaccess="always" wmode="transparent" flashvars="highlighterId=highlighter_146717" menu="false" src="http://form.guide/wp-content/plugins/syntaxhighlighter/syntaxhighlighter2/scripts/clipboard.swf" width="16" height="16"></div><a href="#printSource" title="print" style="width: 16px; height: 16px;" class="item printSource">print</a><a href="#about" title="?" style="width: 16px; height: 16px;" class="item about">?</a></div></div><div class="lines"><div class="line alt1"><table><tbody><tr><td class="number"><code>1</code></td><td class="content"><code class="keyword">class</code> <code class="plain">MyValidator </code><code class="keyword">extends</code> <code class="plain">CustomValidator</code></td></tr></tbody></table></div><div class="line alt2"><table><tbody><tr><td class="number"><code>2</code></td><td class="content"><code class="plain">{</code></td></tr></tbody></table></div><div class="line alt1"><table><tbody><tr><td class="number"><code>3</code></td><td class="content"><code class="spaces">&nbsp;&nbsp;&nbsp;&nbsp;</code><code class="keyword">function</code> <code class="plain">DoValidate(&amp;</code><code class="variable">$formars</code><code class="plain">,&amp;</code><code class="variable">$error_hash</code><code class="plain">)</code></td></tr></tbody></table></div><div class="line alt2"><table><tbody><tr><td class="number"><code>4</code></td><td class="content"><code class="spaces">&nbsp;&nbsp;&nbsp;&nbsp;</code><code class="plain">{</code></td></tr></tbody></table></div><div class="line alt1"><table><tbody><tr><td class="number"><code>5</code></td><td class="content"><code class="spaces">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</code><code class="keyword">if</code><code class="plain">(</code><code class="functions">stristr</code><code class="plain">(</code><code class="variable">$formars</code><code class="plain">[</code><code class="string">'Comments'</code><code class="plain">],</code><code class="string">'<a href="http://">http://</a>'</code><code class="plain">))</code></td></tr></tbody></table></div><div class="line alt2"><table><tbody><tr><td class="number"><code>6</code></td><td class="content"><code class="spaces">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</code><code class="plain">{</code></td></tr></tbody></table></div><div class="line alt1"><table><tbody><tr><td class="number"><code>7</code></td><td class="content"><code class="spaces">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</code><code class="variable">$error_hash</code><code class="plain">[</code><code class="string">'Comments'</code><code class="plain">]=</code><code class="string">"No URLs allowed in comments"</code><code class="plain">;</code></td></tr></tbody></table></div><div class="line alt2"><table><tbody><tr><td class="number"><code>8</code></td><td class="content"><code class="spaces">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</code><code class="keyword">return</code> <code class="plain">false;</code></td></tr></tbody></table></div><div class="line alt1"><table><tbody><tr><td class="number"><code>9</code></td><td class="content"><code class="spaces">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</code><code class="plain">}</code></td></tr></tbody></table></div><div class="line alt2"><table><tbody><tr><td class="number"><code>10</code></td><td class="content"><code class="spaces">&nbsp;&nbsp;&nbsp;&nbsp;</code><code class="keyword">return</code> <code class="plain">true;</code></td></tr></tbody></table></div><div class="line alt1"><table><tbody><tr><td class="number"><code>11</code></td><td class="content"><code class="spaces">&nbsp;&nbsp;&nbsp;&nbsp;</code><code class="plain">}</code></td></tr></tbody></table></div><div class="line alt2"><table><tbody><tr><td class="number"><code>12</code></td><td class="content"><code class="plain">}</code></td></tr></tbody></table></div></div></div></div><li>Add the custom validation object</li><div><div id="highlighter_490640" class="syntaxhighlighter  "><div class="bar                 "><div class="toolbar"><a href="#viewSource" title="view source" style="width: 16px; height: 16px;" class="item viewSource">view source</a><div class="item copyToClipboard"><embed id="highlighter_490640_clipboard" type="application/x-shockwave-flash" title="copy to clipboard" allowscriptaccess="always" wmode="transparent" flashvars="highlighterId=highlighter_490640" menu="false" src="http://form.guide/wp-content/plugins/syntaxhighlighter/syntaxhighlighter2/scripts/clipboard.swf" width="16" height="16"></div><a href="#printSource" title="print" style="width: 16px; height: 16px;" class="item printSource">print</a><a href="#about" title="?" style="width: 16px; height: 16px;" class="item about">?</a></div></div><div class="lines"><div class="line alt1"><table><tbody><tr><td class="number"><code>1</code></td><td class="content"><code class="variable">$validator</code> <code class="plain">= </code><code class="keyword">new</code> <code class="plain">FormValidator();</code></td></tr></tbody></table></div><div class="line alt2"><table><tbody><tr><td class="number"><code>2</code></td><td class="content"><code class="variable">$validator</code><code class="plain">-&gt;addValidation(</code><code class="string">"Name"</code><code class="plain">,</code><code class="string">"req"</code><code class="plain">,</code><code class="string">"Please fill in Name"</code><code class="plain">);</code></td></tr></tbody></table></div><div class="line alt1"><table><tbody><tr><td class="number"><code>3</code></td><td class="content"><code class="variable">$validator</code><code class="plain">-&gt;addValidation(</code><code class="string">"Email"</code><code class="plain">,</code><code class="string">"email"</code><code class="plain">,</code></td></tr></tbody></table></div><div class="line alt2"><table><tbody><tr><td class="number"><code>4</code></td><td class="content"><code class="spaces">&nbsp;</code><code class="string">"The input for Email should be a valid email value"</code><code class="plain">);</code></td></tr></tbody></table></div><div class="line alt1"><table><tbody><tr><td class="number"><code>5</code></td><td class="content"><code class="variable">$validator</code><code class="plain">-&gt;addValidation(</code><code class="string">"Email"</code><code class="plain">,</code><code class="string">"req"</code><code class="plain">,</code><code class="string">"Please fill in Email"</code><code class="plain">);</code></td></tr></tbody></table></div><div class="line alt2"><table><tbody><tr><td class="number"><code>6</code></td><td class="content"><code class="variable">$custom_validator</code> <code class="plain">= </code><code class="keyword">new</code> <code class="plain">MyValidator();</code></td></tr></tbody></table></div><div class="line alt1"><table><tbody><tr><td class="number"><code>7</code></td><td class="content"><code class="variable">$validator</code><code class="plain">-&gt;AddCustomValidator(</code><code class="variable">$custom_validator</code><code class="plain">);</code></td></tr></tbody></table></div></div></div></div></ol><p>The custom validation function will be called automatically after other validations.</p><h2>Table of Validation Descriptors</h2><p>Here is the list of all validation descriptors:</p><table class="datatable" cellspacing="0"><thead><tr><td>Validation Descriptor</td><td>Usage</td></tr></thead><tbody><tr><td>req</td><td>The field should not be empty</td></tr><tr><td>maxlen=???</td><td>checks the length entered data to the maximum. For example, if the maximum size permitted is 25, give the validation descriptor as “maxlen=25”</td></tr><tr><td>minlen=???</td><td>checks the length of the entered string to the required minimum. example “minlen=5”</td></tr><tr><td>alnum</td><td>Check the data if it contains any other characters other than alphabetic or numeric characters</td></tr><tr><td>alnum_s</td><td>Allows only alphabetic, numeric and space characters</td></tr><tr><td>num</td><td>Check numeric data</td></tr><tr><td>alpha</td><td>Check alphabetic data.</td></tr><tr><td>alpha_s</td><td>Check alphabetic data and allow spaces.</td></tr><tr><td>email</td><td>The field is an email field and verify the validity of the data.</td></tr><tr><td>lt=???<br>
lessthan=???</td><td>Verify the data to be less than the value passed. Valid only for numeric fields.<br>
example: if the value should be less than 1000 give validation description as “lt=1000”</td></tr><tr><td>gt=???<br>
greaterthan=???</td><td>Verify the data to be greater than the value passed. Valid only for numeric fields.<br>
example: if the value should be greater than 10 give validation description as “gt=10”</td></tr><tr><td>regexp=???</td><td>Check with a regular expression the value should match the regular expression.<br>
example: “regexp=^[A-Za-z]{1,20}$” allow up to 20 alphabetic characters.</td></tr><tr><td>dontselect=??</td><td>This validation descriptor is for select input items (lists) Normally, the select list boxes will have one item saying ‘Select One’. The user should select an option other than this option. If the&nbsp;<strong>value</strong> of this option is ‘Select One’, the validation description should be “dontselect=Select One”</td></tr><tr><td>dontselectchk</td><td>This validation descriptor is for check boxes. The user should not select the given check box. Provide the&nbsp;<strong>value</strong> of the check box instead of ??<br>
For example, dontselectchk=on</td></tr><tr><td>shouldselchk</td><td>This validation descriptor is for check boxes. The user should select the given check box. Provide the value of the check box instead of ??<br>
For example, shouldselchk=on</td></tr><tr><td>dontselectradio</td><td>This validation descriptor is for radio buttons. The user should not select the given radio button. Provide the value of the radio button instead of ??<br>
For example, dontselectradio=NO</td></tr><tr><td>selectradio</td><td>This validation descriptor is for radio buttons. The user should select the given radio button. Provide the value of the radio button instead of ??<br>
For example, selectradio=yes</td></tr><tr><td>selmin=??</td><td>Select atleast&nbsp;n number of check boxes from a check box group.<br>
For example: selmin=3</td></tr><tr><td>selone</td><td>Makes a radio group mandatory. The user should select atleast one item from the radio group.</td></tr><tr><td>eqelmnt=???</td><td>compare two elements in the form and make sure the values are the same For example, ‘password’ and ‘confirm password’. Replace the ??? with the name of the other input element.<br>
For example: eqelmnt=confirm_pwd</td></tr></tbody></table></div>
