---


---

<h2 id="giới-thiệu-bài-toán">Giới thiệu bài toán</h2>
<p>Trong thực tế nhiều trường hợp, chúng ta luôn phải sắp xếp, tìm kiếm theo một chuẩn nào đó. Ví dụ như:</p>
<ul>
<li>Trong lớp có duy nhất một bạn được 9 điểm, hãy tìm bạn đó? Hay là một dãy sinh viên trong lớp tìm một sinh viên bất kì?</li>
</ul>
<p>Với những bài toán như vậy chúng ta sẽ phải đi tìm kiếm trên một tập nào đó, ví dụ như tìm kiếm tên sinh viên trên tập sinh viên trong lớp…</p>
<h2 id="truyền-thốnglinear-search">Truyền thống(Linear Search)</h2>
<p>Tất cả chúng ta đều biết rằng, muốn tìm kiếm một sinh viên nào đó trên bảng danh sách thì cách đơn giản nhất đó là : “Đi từng sinh viên từ đầu, kiểm tra xem đó có phải sinh viên cần tìm không, không thì next”.<br>
Ví dụ chúng ta có mảng A[] = {1, 2, 3, 4, 5, 6, 7, 8, 9} với Key = 7<br>
Theo đúng cách trên thì ta có cách duyệt từ đầu đến cuối. Nếu giá trị mình cần tìm là Key thì sẽ in ra vị trí xuất hiện đó</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token macro property">#<span class="token directive keyword">include</span> <span class="token string">&lt;iostream&gt;</span></span>
<span class="token keyword">using</span> <span class="token keyword">namespace</span> std<span class="token punctuation">;</span>
<span class="token keyword">int</span> <span class="token function">timKiem</span><span class="token punctuation">(</span><span class="token keyword">int</span> Arr<span class="token punctuation">[</span><span class="token punctuation">]</span><span class="token punctuation">,</span> <span class="token keyword">int</span> n<span class="token punctuation">,</span> <span class="token keyword">int</span> Key<span class="token punctuation">)</span> <span class="token punctuation">{</span>
	<span class="token keyword">for</span> <span class="token punctuation">(</span><span class="token keyword">int</span> i <span class="token operator">=</span> <span class="token number">0</span><span class="token punctuation">;</span> i <span class="token operator">&lt;</span> n<span class="token punctuation">;</span> i<span class="token operator">++</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
		<span class="token keyword">if</span> <span class="token punctuation">(</span>Arr<span class="token punctuation">[</span>i<span class="token punctuation">]</span> <span class="token operator">==</span> Key<span class="token punctuation">)</span> <span class="token punctuation">{</span>
			<span class="token keyword">return</span> i<span class="token punctuation">;</span> <span class="token comment">// tìm thấy thì sẽ kết thúc luôn</span>
		<span class="token punctuation">}</span>
	<span class="token punctuation">}</span>
	<span class="token keyword">return</span> <span class="token operator">-</span><span class="token number">1</span><span class="token punctuation">;</span><span class="token comment">//tức không tìm thấy</span>
<span class="token punctuation">}</span>
<span class="token keyword">int</span> <span class="token function">main</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
	<span class="token keyword">int</span> A<span class="token punctuation">[</span><span class="token punctuation">]</span> <span class="token operator">=</span> <span class="token punctuation">{</span><span class="token number">1</span><span class="token punctuation">,</span> <span class="token number">2</span><span class="token punctuation">,</span> <span class="token number">3</span><span class="token punctuation">,</span> <span class="token number">4</span><span class="token punctuation">,</span> <span class="token number">5</span><span class="token punctuation">,</span> <span class="token number">6</span><span class="token punctuation">,</span> <span class="token number">7</span><span class="token punctuation">,</span> <span class="token number">8</span><span class="token punctuation">,</span> <span class="token number">9</span><span class="token punctuation">}</span><span class="token punctuation">;</span>
	<span class="token keyword">int</span> n <span class="token operator">=</span> <span class="token keyword">sizeof</span><span class="token punctuation">(</span>A<span class="token punctuation">)</span><span class="token operator">/</span><span class="token keyword">sizeof</span><span class="token punctuation">(</span><span class="token keyword">int</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
	<span class="token keyword">if</span> <span class="token punctuation">(</span><span class="token function">timKiem</span><span class="token punctuation">(</span>A<span class="token punctuation">,</span> n<span class="token punctuation">,</span> <span class="token number">7</span><span class="token punctuation">)</span> <span class="token operator">!=</span> <span class="token operator">-</span><span class="token number">1</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
		cout <span class="token operator">&lt;&lt;</span> <span class="token string">"Tim thay 7 o vi tri "</span> <span class="token operator">&lt;&lt;</span> <span class="token function">timKiem</span><span class="token punctuation">(</span>A<span class="token punctuation">,</span> n<span class="token punctuation">,</span> <span class="token number">7</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
	<span class="token punctuation">}</span>
	<span class="token keyword">if</span> <span class="token punctuation">(</span><span class="token function">timKiem</span><span class="token punctuation">(</span>A<span class="token punctuation">,</span> n<span class="token punctuation">,</span> <span class="token number">10</span><span class="token punctuation">)</span> <span class="token operator">!=</span> <span class="token operator">-</span><span class="token number">1</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
		cout <span class="token operator">&lt;&lt;</span> <span class="token string">"Tim thay 7 o vi tri "</span> <span class="token operator">&lt;&lt;</span> <span class="token function">timKiem</span><span class="token punctuation">(</span>A<span class="token punctuation">,</span> n<span class="token punctuation">,</span> <span class="token number">7</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
	<span class="token punctuation">}</span> <span class="token keyword">else</span> <span class="token punctuation">{</span>
		cout <span class="token operator">&lt;&lt;</span> <span class="token string">"Trong mang khong ton tai so 10"</span><span class="token punctuation">;</span>
	<span class="token punctuation">}</span>
<span class="token punctuation">}</span>
</code></pre>
<p>Nhìn sơ qua thì thuật toán này khá là tốt để tiếp cận bởi nó tuyến tính, dễ hiểu, dễ code. Nhưng nếu theo con mắt của một người ưu tiên về giải thuật hay với công việc sau này, cách giải quyết này không thể được áp dụng bởi độ phức tạp của nó quá lớn O(n) giả sử n = <span class="katex--inline"><span class="katex"><span class="katex-mathml"><math><semantics><mrow><mn>1</mn><msup><mn>0</mn><mn>10</mn></msup></mrow><annotation encoding="application/x-tex">10^{10}</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="base"><span class="strut" style="height: 0.814108em; vertical-align: 0em;"></span><span class="mord">1</span><span class="mord"><span class="mord">0</span><span class="msupsub"><span class="vlist-t"><span class="vlist-r"><span class="vlist" style="height: 0.814108em;"><span class="" style="top: -3.063em; margin-right: 0.05em;"><span class="pstrut" style="height: 2.7em;"></span><span class="sizing reset-size6 size3 mtight"><span class="mord mtight"><span class="mord mtight">1</span><span class="mord mtight">0</span></span></span></span></span></span></span></span></span></span></span></span></span> thì toang.</p>
<h2 id="cách-tối-ưu">Cách tối ưu</h2>
<p>Về thuật toán tối ưu sự tìm kiếm thì có một thuật toán kiểu : “À mày không phải cái ta tìm kiếm thì chắc nó ở nửa sau hoặc nửa đầu rồi” - Chính là Binary Search (Tìm kiếm nhị phân)<br>
Khi sử dụng cách này thì phải đảm bảo điều kiện là dữ liệu của chúng ta đã được sắp xếp (theo bất kì kiểu gì)<br>
Tư tưởng thuật toán này đi từ phần tử giữa của dữ liệu hiện tại. Khi mảng hiện tại được chia làm hai thì chỉ có 3 khả năng duy nhất:</p>
<ul>
<li>Phần tử tìm kiếm là ở vị trí giữa</li>
<li>Nếu không phải ở giữa thì nếu A[giữa] &gt; Key tức là từ giữa-&gt;cuối đều &gt; Key nên ta sẽ chỉ thao tác với mảng bên trái.</li>
<li>Tương tự với mảng bên phải</li>
</ul>
<p>Ví dụ: A[] = {1, 2, 3, 4, 5, 6, 7, 8, 9}; // Điều kiện đã được sắp xêp<br>
Key = 1</p>
<p>Các bước thuật toán như sau:</p>
<ul>
<li>Khởi tạo Left=0, Right = n;</li>
<li>Nếu Left &lt;= Right thì tiếp tục thuật toán</li>
<li>Lấy vị trí giữa là (10 - 0)/2 = 5 | A[mid] = 6</li>
<li>So sánh thấy 1 &lt; 6 nên sẽ thao tác với mảng bên trái. Lúc này Right của mảng sẽ là Right = mid - 1;</li>
<li>Lấy lại mid = (Right-Left)/2 = 2 | A[mid] = 3</li>
<li>So sánh thấy 1 &lt; 3 nên sẽ thao tác với mảng bên trái. Right mới Right = mid-1 = 2</li>
<li>Lấy lại mid = (Right-Left)/2 = 1 | A[mid] = 2</li>
<li>So sánh thấy 1 &lt; 2 nên sẽ thao tác với mảng bên trái. Right mới Right = mid-1 = 0</li>
<li>Lấy lại mid = (Right-Left)/2 = 0 | A[mid] = 1</li>
<li>Thấy Key == A[mid] ==1 nên sẽ dừng thuật toán =&gt; mid là vị trí cần tìm (0)</li>
</ul>
<p>So sánh thấy BinarySearch mất 4 bước để so sánh thì Linear Search mất 9 bước so sánh, con số này không khác biệt với <span class="katex--inline"><span class="katex"><span class="katex-mathml"><math><semantics><mrow><mi>n</mi></mrow><annotation encoding="application/x-tex">n</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="base"><span class="strut" style="height: 0.43056em; vertical-align: 0em;"></span><span class="mord mathdefault">n</span></span></span></span></span> nhỏ. Tuy nhiên với <span class="katex--inline"><span class="katex"><span class="katex-mathml"><math><semantics><mrow><mi>n</mi><mo>=</mo><mn>1</mn><msup><mn>0</mn><mn>10</mn></msup></mrow><annotation encoding="application/x-tex">n = 10^{10}</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="base"><span class="strut" style="height: 0.43056em; vertical-align: 0em;"></span><span class="mord mathdefault">n</span><span class="mspace" style="margin-right: 0.277778em;"></span><span class="mrel">=</span><span class="mspace" style="margin-right: 0.277778em;"></span></span><span class="base"><span class="strut" style="height: 0.814108em; vertical-align: 0em;"></span><span class="mord">1</span><span class="mord"><span class="mord">0</span><span class="msupsub"><span class="vlist-t"><span class="vlist-r"><span class="vlist" style="height: 0.814108em;"><span class="" style="top: -3.063em; margin-right: 0.05em;"><span class="pstrut" style="height: 2.7em;"></span><span class="sizing reset-size6 size3 mtight"><span class="mord mtight"><span class="mord mtight">1</span><span class="mord mtight">0</span></span></span></span></span></span></span></span></span></span></span></span></span> thì LinearS sẽ mất <span class="katex--inline"><span class="katex"><span class="katex-mathml"><math><semantics><mrow><mn>1</mn><msup><mn>0</mn><mn>10</mn></msup></mrow><annotation encoding="application/x-tex">10^{10}</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="base"><span class="strut" style="height: 0.814108em; vertical-align: 0em;"></span><span class="mord">1</span><span class="mord"><span class="mord">0</span><span class="msupsub"><span class="vlist-t"><span class="vlist-r"><span class="vlist" style="height: 0.814108em;"><span class="" style="top: -3.063em; margin-right: 0.05em;"><span class="pstrut" style="height: 2.7em;"></span><span class="sizing reset-size6 size3 mtight"><span class="mord mtight"><span class="mord mtight">1</span><span class="mord mtight">0</span></span></span></span></span></span></span></span></span></span></span></span></span> bước thì BinaryS mất <span class="katex--inline"><span class="katex"><span class="katex-mathml"><math><semantics><mrow><mi>l</mi><mi>o</mi><msub><mi>g</mi><mn>2</mn></msub><mo stretchy="false">(</mo><mn>1</mn><msup><mn>0</mn><mn>10</mn></msup><mo stretchy="false">)</mo><mo>=</mo><mn>30</mn></mrow><annotation encoding="application/x-tex">log_{2}(10^{10}) = 30</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="base"><span class="strut" style="height: 1.06411em; vertical-align: -0.25em;"></span><span class="mord mathdefault" style="margin-right: 0.01968em;">l</span><span class="mord mathdefault">o</span><span class="mord"><span class="mord mathdefault" style="margin-right: 0.03588em;">g</span><span class="msupsub"><span class="vlist-t vlist-t2"><span class="vlist-r"><span class="vlist" style="height: 0.301108em;"><span class="" style="top: -2.55em; margin-left: -0.03588em; margin-right: 0.05em;"><span class="pstrut" style="height: 2.7em;"></span><span class="sizing reset-size6 size3 mtight"><span class="mord mtight"><span class="mord mtight">2</span></span></span></span></span><span class="vlist-s">​</span></span><span class="vlist-r"><span class="vlist" style="height: 0.15em;"><span class=""></span></span></span></span></span></span><span class="mopen">(</span><span class="mord">1</span><span class="mord"><span class="mord">0</span><span class="msupsub"><span class="vlist-t"><span class="vlist-r"><span class="vlist" style="height: 0.814108em;"><span class="" style="top: -3.063em; margin-right: 0.05em;"><span class="pstrut" style="height: 2.7em;"></span><span class="sizing reset-size6 size3 mtight"><span class="mord mtight"><span class="mord mtight">1</span><span class="mord mtight">0</span></span></span></span></span></span></span></span></span><span class="mclose">)</span><span class="mspace" style="margin-right: 0.277778em;"></span><span class="mrel">=</span><span class="mspace" style="margin-right: 0.277778em;"></span></span><span class="base"><span class="strut" style="height: 0.64444em; vertical-align: 0em;"></span><span class="mord">3</span><span class="mord">0</span></span></span></span></span> (Rất nhỏ đúng không)</p>
<p>Code:</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token macro property">#<span class="token directive keyword">include</span> <span class="token string">&lt;iostream&gt;</span></span>
<span class="token keyword">using</span> <span class="token keyword">namespace</span> std<span class="token punctuation">;</span>

<span class="token keyword">int</span> <span class="token function">timKiem</span><span class="token punctuation">(</span><span class="token keyword">int</span> Arr<span class="token punctuation">[</span><span class="token punctuation">]</span><span class="token punctuation">,</span> <span class="token keyword">int</span> n<span class="token punctuation">,</span> <span class="token keyword">int</span> Key<span class="token punctuation">)</span> <span class="token punctuation">{</span>
	<span class="token keyword">int</span> left <span class="token operator">=</span> <span class="token number">0</span><span class="token punctuation">,</span> right <span class="token operator">=</span> n<span class="token punctuation">;</span> <span class="token comment">// Khởi tạo đầu đuôi</span>
	<span class="token keyword">while</span><span class="token punctuation">(</span>left<span class="token operator">&lt;=</span>right<span class="token punctuation">)</span> <span class="token punctuation">{</span>
		<span class="token keyword">int</span> mid <span class="token operator">=</span> <span class="token punctuation">(</span>right <span class="token operator">-</span> left<span class="token punctuation">)</span><span class="token operator">/</span><span class="token number">2</span><span class="token punctuation">;</span> <span class="token comment">// Khởi tạo vị trí giữa</span>
		<span class="token keyword">if</span> <span class="token punctuation">(</span>Arr<span class="token punctuation">[</span>mid<span class="token punctuation">]</span> <span class="token operator">==</span> Key<span class="token punctuation">)</span> <span class="token punctuation">{</span>
			<span class="token keyword">return</span> mid<span class="token punctuation">;</span> <span class="token comment">// Trả về vị trí tìm thấy key</span>
		<span class="token punctuation">}</span> <span class="token keyword">else</span> <span class="token keyword">if</span> <span class="token punctuation">(</span>Arr<span class="token punctuation">[</span>mid<span class="token punctuation">]</span> <span class="token operator">&gt;</span> Key<span class="token punctuation">)</span> <span class="token punctuation">{</span>
			right <span class="token operator">=</span> mid<span class="token number">-1</span><span class="token punctuation">;</span> <span class="token comment">// Tìm kiếm bên trái</span>
		<span class="token punctuation">}</span> <span class="token keyword">else</span> <span class="token keyword">if</span> <span class="token punctuation">(</span>Arr<span class="token punctuation">[</span>mid<span class="token punctuation">]</span> <span class="token operator">&lt;</span> Key<span class="token punctuation">)</span> <span class="token punctuation">{</span>
			left <span class="token operator">=</span> mid<span class="token operator">+</span><span class="token number">1</span><span class="token punctuation">;</span><span class="token comment">//Tìm kiếm bên phải</span>
		<span class="token punctuation">}</span>
	<span class="token punctuation">}</span>
	<span class="token keyword">return</span> <span class="token operator">-</span><span class="token number">1</span><span class="token punctuation">;</span> <span class="token comment">//Nếu không tìm thấy</span>
<span class="token punctuation">}</span>

<span class="token keyword">int</span> <span class="token function">main</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
	<span class="token keyword">int</span> A<span class="token punctuation">[</span><span class="token punctuation">]</span> <span class="token operator">=</span> <span class="token punctuation">{</span><span class="token number">1</span><span class="token punctuation">,</span> <span class="token number">2</span><span class="token punctuation">,</span> <span class="token number">3</span><span class="token punctuation">,</span> <span class="token number">4</span><span class="token punctuation">,</span> <span class="token number">5</span><span class="token punctuation">,</span> <span class="token number">6</span><span class="token punctuation">,</span> <span class="token number">7</span><span class="token punctuation">,</span> <span class="token number">8</span><span class="token punctuation">,</span> <span class="token number">9</span><span class="token punctuation">}</span><span class="token punctuation">;</span>
	<span class="token keyword">int</span> n <span class="token operator">=</span> <span class="token keyword">sizeof</span><span class="token punctuation">(</span>A<span class="token punctuation">)</span><span class="token operator">/</span><span class="token keyword">sizeof</span><span class="token punctuation">(</span><span class="token keyword">int</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
	<span class="token keyword">if</span> <span class="token punctuation">(</span><span class="token function">timKiem</span><span class="token punctuation">(</span>A<span class="token punctuation">,</span> n<span class="token punctuation">,</span> <span class="token number">7</span><span class="token punctuation">)</span> <span class="token operator">!=</span> <span class="token operator">-</span><span class="token number">1</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
		cout <span class="token operator">&lt;&lt;</span> <span class="token string">"Tim thay 7 o vi tri "</span> <span class="token operator">&lt;&lt;</span> <span class="token function">timKiem</span><span class="token punctuation">(</span>A<span class="token punctuation">,</span> n<span class="token punctuation">,</span> <span class="token number">7</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
	<span class="token punctuation">}</span> <span class="token keyword">else</span> <span class="token punctuation">{</span>
		cout <span class="token operator">&lt;&lt;</span> <span class="token string">"Trong mang khong ton tai so 7"</span><span class="token punctuation">;</span>
	<span class="token punctuation">}</span>
	<span class="token keyword">if</span> <span class="token punctuation">(</span><span class="token function">timKiem</span><span class="token punctuation">(</span>A<span class="token punctuation">,</span> n<span class="token punctuation">,</span> <span class="token number">10</span><span class="token punctuation">)</span> <span class="token operator">!=</span> <span class="token operator">-</span><span class="token number">1</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
		cout <span class="token operator">&lt;&lt;</span> <span class="token string">"Tim thay 7 o vi tri "</span> <span class="token operator">&lt;&lt;</span> <span class="token function">timKiem</span><span class="token punctuation">(</span>A<span class="token punctuation">,</span> n<span class="token punctuation">,</span> <span class="token number">7</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
	<span class="token punctuation">}</span> <span class="token keyword">else</span> <span class="token punctuation">{</span>
		cout <span class="token operator">&lt;&lt;</span> <span class="token string">"Trong mang khong ton tai so 10"</span><span class="token punctuation">;</span>
	<span class="token punctuation">}</span>
<span class="token punctuation">}</span>

</code></pre>
