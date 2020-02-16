---


---

<h1 id="mục-lục">Mục lục</h1>
<hr>
<p><a href="#gi%E1%BB%9Bi-thi%E1%BB%87u">Giới thiệu</a><br>
<a href="#gi%E1%BB%9Bi-thi%E1%BB%87u-thu%E1%BA%ADt-to%C3%A1n">Giới thiệu thuật toán</a><br>
<a href="#quay-lui-nh%E1%BB%8B-ph%C3%A2n">Quay lui nhị phân</a><br>
<a href="#%C3%A1p-d%E1%BB%A5ng-gi%E1%BA%A3i-thu%E1%BA%ADt">Áp dụng giải thuật</a></p>
<h2 id="giới-thiệu">Giới thiệu</h2>
<p>Nhị phân là một chuỗi kí tự gồm [0,1] thường được dùng để biểu diễn các tín hiệu số trong môn Điện tử số(Kỹ thuật số PTIT), và được sử dụng bởi chính chiếc máy tính của chúng ta, những thao tác cực kì phức tạp cũng được biểu diễn bởi những dãy nhị phân. Vd: 001, 111, 111100110,…<br>
Tất nhiên dãy nhị phân có quy luật cả đấy. Bây giờ chúng ta sẽ đi tìm cách để xây dựng bộ mã nhị phân nhé!</p>
<h2 id="giới-thiệu-thuật-toán">Giới thiệu thuật toán</h2>
<hr>
<p>Ví dụ:</p>
<ul>
<li>Một dãy nhị phân cấp 3: 000, 001, 010, 011, 100, 101, 110, 111</li>
<li>Dãy nhị phân cấp 2: 00, 01, 10, 11</li>
<li>Dãy nhị phân cấp n: sẽ có <span class="katex--inline"><span class="katex"><span class="katex-mathml"><math><semantics><mrow><msup><mn>2</mn><mi>n</mi></msup></mrow><annotation encoding="application/x-tex">2^n</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="base"><span class="strut" style="height: 0.664392em; vertical-align: 0em;"></span><span class="mord"><span class="mord">2</span><span class="msupsub"><span class="vlist-t"><span class="vlist-r"><span class="vlist" style="height: 0.664392em;"><span class="" style="top: -3.063em; margin-right: 0.05em;"><span class="pstrut" style="height: 2.7em;"></span><span class="sizing reset-size6 size3 mtight"><span class="mord mathdefault mtight">n</span></span></span></span></span></span></span></span></span></span></span></span> dãy</li>
</ul>
<h4 id="thuật-toán-chúng-ta-dùng-ở-đây-mình-sẽ-không-chứng-minh-lại-mà-áp-dụng-kết-quả-luôn-các-bạn-có-thể-tự-suy-nghĩ-từ-các-dãy-quy-luật-rất-đơn-giản">Thuật toán chúng ta dùng ở đây mình sẽ không chứng minh lại mà áp dụng kết quả luôn, các bạn có thể tự suy nghĩ từ các dãy, quy luật rất đơn giản</h4>
<p>Thuật toán được phát biểu như sau:</p>
<ul>
<li>Bước khởi tạo: Khởi tạo tất cả các giá trị bằng 0</li>
<li>Bước một: Duyệt từ cuối về đầu gặp số 0 đầu tiên thì đánh đấu là 1</li>
<li>Bước hai: Đặt tất cả các số ở sau thành 0</li>
<li>Bước ba: Lặp lại đến khi không tìm được số 0 nào nữa</li>
</ul>
<p>Minh họa thuật toán:<br>
Giả sử n = 3<br>
Cấu hình đầu tiên: a = 000<br>
Bước 1: thấy vị trí i=3 với a[i]=0 chuyển a[i]=1<br>
Bước 2: từ 3+1=4 -&gt; 3 chuyển về 0-&gt; cấu hình tiếp 001<br>
Lặp lại:<br>
Bước 1: 001 thấy vị trí i=2 với a[i]=0 chuyển a[i]=1-&gt; 011<br>
Bước 2: từ vị trí i=2+1-&gt;3 chuyển về 0-&gt; 010<br>
Lặp lại:<br>
…</p>
<p>Code:</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token macro property">#<span class="token directive keyword">include</span> <span class="token string">&lt;iostream&gt;</span></span>
<span class="token keyword">using</span> <span class="token keyword">namespace</span> std<span class="token punctuation">;</span>
<span class="token keyword">int</span> a<span class="token punctuation">[</span><span class="token number">20</span><span class="token punctuation">]</span><span class="token punctuation">,</span>n<span class="token punctuation">;</span>
<span class="token keyword">void</span> <span class="token function">Init</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
	cin<span class="token operator">&gt;&gt;</span>n<span class="token punctuation">;</span>
	<span class="token keyword">for</span><span class="token punctuation">(</span><span class="token keyword">int</span> i <span class="token operator">=</span> <span class="token number">1</span><span class="token punctuation">;</span> i <span class="token operator">&lt;=</span> n<span class="token punctuation">;</span> i<span class="token operator">++</span><span class="token punctuation">)</span> 
		a<span class="token punctuation">[</span>i<span class="token punctuation">]</span> <span class="token operator">=</span> <span class="token number">0</span><span class="token punctuation">;</span>
<span class="token punctuation">}</span>
<span class="token keyword">void</span> <span class="token function">InCauHinh</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
	<span class="token keyword">for</span> <span class="token punctuation">(</span><span class="token keyword">int</span> i <span class="token operator">=</span> <span class="token number">1</span><span class="token punctuation">;</span> i <span class="token operator">&lt;=</span> n<span class="token punctuation">;</span> i<span class="token operator">++</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
		cout <span class="token operator">&lt;&lt;</span> a<span class="token punctuation">[</span>i<span class="token punctuation">]</span><span class="token punctuation">;</span>
	<span class="token punctuation">}</span>
	cout <span class="token operator">&lt;&lt;</span> endl<span class="token punctuation">;</span>
<span class="token punctuation">}</span>
<span class="token keyword">void</span> <span class="token function">SinhNhiPhan</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
	<span class="token keyword">while</span><span class="token punctuation">(</span><span class="token number">1</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
		<span class="token function">InCauHinh</span><span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
		<span class="token keyword">int</span> i <span class="token operator">=</span> n<span class="token punctuation">;</span>
		<span class="token keyword">while</span><span class="token punctuation">(</span>i <span class="token operator">&gt;=</span> <span class="token number">1</span> <span class="token operator">&amp;&amp;</span> a<span class="token punctuation">[</span>i<span class="token punctuation">]</span> <span class="token operator">!=</span> <span class="token number">0</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
			i<span class="token operator">--</span><span class="token punctuation">;</span>
		<span class="token punctuation">}</span>
		<span class="token keyword">if</span> <span class="token punctuation">(</span>i <span class="token operator">&lt;</span> <span class="token number">1</span><span class="token punctuation">)</span> <span class="token punctuation">{</span> <span class="token comment">// tức dãy hiện tại là 111..11</span>
			<span class="token keyword">break</span><span class="token punctuation">;</span> <span class="token comment">// kết thúc</span>
		<span class="token punctuation">}</span>
		a<span class="token punctuation">[</span>i<span class="token punctuation">]</span> <span class="token operator">=</span> <span class="token number">1</span><span class="token punctuation">;</span> <span class="token comment">// đánh dấu lại thành 1, sau đó chuyển nửa bên kia =0</span>
		<span class="token keyword">for</span> <span class="token punctuation">(</span><span class="token keyword">int</span> j <span class="token operator">=</span> i <span class="token operator">+</span> <span class="token number">1</span><span class="token punctuation">;</span> j <span class="token operator">&lt;=</span> n<span class="token punctuation">;</span> j<span class="token operator">++</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
			a<span class="token punctuation">[</span>j<span class="token punctuation">]</span> <span class="token operator">=</span> <span class="token number">0</span><span class="token punctuation">;</span>
		<span class="token punctuation">}</span>
	<span class="token punctuation">}</span>
<span class="token punctuation">}</span>
<span class="token keyword">int</span> <span class="token function">main</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
	<span class="token function">Init</span><span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
	<span class="token function">SinhNhiPhan</span><span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
<span class="token punctuation">}</span>
</code></pre>
<p>Độ phức tạp: O(<span class="katex--inline"><span class="katex"><span class="katex-mathml"><math><semantics><mrow><msup><mn>2</mn><mi>n</mi></msup><mo stretchy="false">)</mo></mrow><annotation encoding="application/x-tex">2^n)</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="base"><span class="strut" style="height: 1em; vertical-align: -0.25em;"></span><span class="mord"><span class="mord">2</span><span class="msupsub"><span class="vlist-t"><span class="vlist-r"><span class="vlist" style="height: 0.664392em;"><span class="" style="top: -3.063em; margin-right: 0.05em;"><span class="pstrut" style="height: 2.7em;"></span><span class="sizing reset-size6 size3 mtight"><span class="mord mathdefault mtight">n</span></span></span></span></span></span></span></span><span class="mclose">)</span></span></span></span></span> - vậy nên sinh tối đa chỉ đến khoảng 20-22 thôi nhé :v</p>
<p>Thuật toán trên khá là dài phải không, khó nhớ nữa :’(. Tuy nhiên chúng ta có cách ngắn hơn mà dễ hiểu chạy cũng ngang cái trên thôi :v</p>
<h2 id="quay-lui-sinh-nhị-phân">Quay lui sinh nhị phân</h2>
<hr>
<blockquote>
<p>Ở các kỳ trước, chúng ta đã học về Backtracking(Quay lui). Vậy nên ta sẽ áp dụng nó vào thuật toán này! (Thực ra có rất nhiều thuật toán liên quan tới Quay lui đó)</p>
</blockquote>
<p>Lướt lại tý nhé:<br>
0 0<br>
0 1<br>
1 0<br>
1 1<br>
Thấy từng phần tử nó lặp theo quy luật là cứ 0 rồi sẽ thành 1 và ngược lại. Xem trên là vị trí 2 thì chu kì lặp là 1 đơn vị, vị trí 1 là 2 đơn vị.</p>
<p>Code:</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token macro property">#<span class="token directive keyword">include</span> <span class="token string">&lt;iostream&gt;</span></span>
<span class="token keyword">using</span> <span class="token keyword">namespace</span> std<span class="token punctuation">;</span>
<span class="token keyword">int</span> a<span class="token punctuation">[</span><span class="token number">20</span><span class="token punctuation">]</span><span class="token punctuation">,</span>n<span class="token punctuation">;</span>
<span class="token keyword">void</span> <span class="token function">Init</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
	cin<span class="token operator">&gt;&gt;</span>n<span class="token punctuation">;</span>
	<span class="token keyword">for</span><span class="token punctuation">(</span><span class="token keyword">int</span> i <span class="token operator">=</span> <span class="token number">1</span><span class="token punctuation">;</span> i <span class="token operator">&lt;=</span> n<span class="token punctuation">;</span> i<span class="token operator">++</span><span class="token punctuation">)</span> 
		a<span class="token punctuation">[</span>i<span class="token punctuation">]</span> <span class="token operator">=</span> <span class="token number">0</span><span class="token punctuation">;</span>
<span class="token punctuation">}</span>
<span class="token keyword">void</span> <span class="token function">InCauHinh</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
	<span class="token keyword">for</span> <span class="token punctuation">(</span><span class="token keyword">int</span> i <span class="token operator">=</span> <span class="token number">1</span><span class="token punctuation">;</span> i <span class="token operator">&lt;=</span> n<span class="token punctuation">;</span> i<span class="token operator">++</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
		cout <span class="token operator">&lt;&lt;</span> a<span class="token punctuation">[</span>i<span class="token punctuation">]</span><span class="token punctuation">;</span>
	<span class="token punctuation">}</span>
	cout <span class="token operator">&lt;&lt;</span> endl<span class="token punctuation">;</span>
<span class="token punctuation">}</span>
<span class="token keyword">void</span> <span class="token function">Try</span><span class="token punctuation">(</span><span class="token keyword">int</span> i<span class="token punctuation">)</span> <span class="token punctuation">{</span> <span class="token comment">// Xác định vị trí i là 0 hay là 1</span>
	<span class="token keyword">for</span> <span class="token punctuation">(</span><span class="token keyword">int</span> j <span class="token operator">=</span> <span class="token number">0</span><span class="token punctuation">;</span> j <span class="token operator">&lt;</span> <span class="token number">2</span><span class="token punctuation">;</span> j<span class="token operator">++</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
		a<span class="token punctuation">[</span>i<span class="token punctuation">]</span> <span class="token operator">=</span> j<span class="token punctuation">;</span> <span class="token comment">// Tại vị trí i chỉ có thể thay thế bằng 0 hoặc 1</span>
		<span class="token keyword">if</span> <span class="token punctuation">(</span>i <span class="token operator">==</span> n<span class="token punctuation">)</span> <span class="token punctuation">{</span>
			<span class="token function">InCauHinh</span><span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">;</span> <span class="token comment">// Nếu đạt đủ độ dài dãy thì in ra</span>
		<span class="token punctuation">}</span> <span class="token keyword">else</span> <span class="token punctuation">{</span>
			<span class="token function">Try</span><span class="token punctuation">(</span>i <span class="token operator">+</span> <span class="token number">1</span><span class="token punctuation">)</span><span class="token punctuation">;</span> <span class="token comment">// Ngược lại xác định vị trí i + 1</span>
		<span class="token punctuation">}</span>
	<span class="token punctuation">}</span>
<span class="token punctuation">}</span>
<span class="token keyword">int</span> <span class="token function">main</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
	<span class="token function">Init</span><span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
	<span class="token function">Try</span><span class="token punctuation">(</span><span class="token number">1</span><span class="token punctuation">)</span><span class="token punctuation">;</span> <span class="token comment">// Bắt đầu từ vị trí 1</span>
<span class="token punctuation">}</span>
</code></pre>
<h2 id="áp-dụng-giải-thuật">Áp dụng giải thuật</h2>
<hr>
<p>Sinh nhị phân áp dụng với rất nhiều bài tập mang tính “chọn lựa” - tức là có thể chọn hoặc không chọn.<br>
Thôi thì nói nhiều lí thuyết quá, nhảy vào bài tập luôn cho nó đỡ buồn ngủ.<br>
Link: <a href="https://www.spoj.com/PTIT/problems/BCCOW/">https://www.spoj.com/PTIT/problems/BCCOW/</a><br>
Tóm tắt đề bài cho ngắn: Cho n con bò với n cân nặng cho trước, chọn ra các con bò sao cho trọng lượng lớn nhất và không vượt quá M.</p>
<p>Phân tích bài toán:</p>
<ul>
<li>Bài này thuộc dạng sinh nhị phân</li>
<li>Vậy mình có thể áp dụng như sau, nếu chọn con bò thứ i thì đánh dấu 1, không thì đánh dấu là 0</li>
<li>Sau đó tính tổng các con được đánh dấu là 1 rồi tìm Max.</li>
<li>Tức sẽ sinh nhị phân một dãy cấp n:</li>
<li>Giả sử dãy mình đang xét là: 0001 thì tức là chỉ chọn con bò thứ 4 thôi.</li>
</ul>
<p>Code:</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token macro property">#<span class="token directive keyword">include</span> <span class="token string">&lt;iostream&gt;</span></span>
<span class="token keyword">using</span> <span class="token keyword">namespace</span> std<span class="token punctuation">;</span>
<span class="token keyword">int</span> a<span class="token punctuation">[</span><span class="token number">20</span><span class="token punctuation">]</span><span class="token punctuation">,</span> n<span class="token punctuation">,</span> w<span class="token punctuation">;</span>
<span class="token keyword">int</span> result <span class="token operator">=</span> <span class="token number">0</span><span class="token punctuation">;</span>
<span class="token keyword">int</span> danhdau<span class="token punctuation">[</span><span class="token number">20</span><span class="token punctuation">]</span><span class="token punctuation">;</span>
<span class="token keyword">void</span> <span class="token function">Init</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
	cin<span class="token operator">&gt;&gt;</span>w<span class="token operator">&gt;&gt;</span>n<span class="token punctuation">;</span>
	<span class="token keyword">for</span> <span class="token punctuation">(</span><span class="token keyword">int</span> i <span class="token operator">=</span> <span class="token number">1</span><span class="token punctuation">;</span> i <span class="token operator">&lt;=</span> n<span class="token punctuation">;</span> i<span class="token operator">++</span><span class="token punctuation">)</span> 
		cin <span class="token operator">&gt;&gt;</span> a<span class="token punctuation">[</span>i<span class="token punctuation">]</span><span class="token punctuation">;</span>
	<span class="token keyword">for</span> <span class="token punctuation">(</span><span class="token keyword">int</span> i <span class="token operator">=</span> <span class="token number">1</span><span class="token punctuation">;</span> i <span class="token operator">&lt;=</span> n<span class="token punctuation">;</span> i<span class="token operator">++</span><span class="token punctuation">)</span> 
		danhdau<span class="token punctuation">[</span>i<span class="token punctuation">]</span> <span class="token operator">=</span> <span class="token number">0</span><span class="token punctuation">;</span>
<span class="token punctuation">}</span>
<span class="token keyword">void</span> <span class="token function">Update</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
	<span class="token keyword">int</span> Sum<span class="token operator">=</span><span class="token number">0</span><span class="token punctuation">;</span>
	<span class="token keyword">for</span><span class="token punctuation">(</span><span class="token keyword">int</span> i <span class="token operator">=</span> <span class="token number">1</span><span class="token punctuation">;</span> i <span class="token operator">&lt;=</span> n<span class="token punctuation">;</span> i<span class="token operator">++</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
		<span class="token keyword">if</span> <span class="token punctuation">(</span>danhdau<span class="token punctuation">[</span>i<span class="token punctuation">]</span><span class="token operator">==</span><span class="token number">1</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
			Sum <span class="token operator">+</span><span class="token operator">=</span> a<span class="token punctuation">[</span>i<span class="token punctuation">]</span><span class="token punctuation">;</span>
		<span class="token punctuation">}</span>
	<span class="token punctuation">}</span>
	<span class="token keyword">if</span> <span class="token punctuation">(</span>Sum <span class="token operator">&lt;</span> w<span class="token punctuation">)</span> <span class="token punctuation">{</span>
		<span class="token keyword">if</span> <span class="token punctuation">(</span>Sum <span class="token operator">&gt;</span> result<span class="token punctuation">)</span>
			result <span class="token operator">=</span> Sum<span class="token punctuation">;</span> <span class="token comment">// Nếu thỏa mãn yêu cầu thì cập nhật két quả</span>
	<span class="token punctuation">}</span>
<span class="token punctuation">}</span>
<span class="token keyword">void</span> <span class="token function">SinhNhiPhan</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
	<span class="token keyword">while</span><span class="token punctuation">(</span><span class="token number">1</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
		<span class="token function">Update</span><span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
		<span class="token keyword">int</span> i <span class="token operator">=</span> n<span class="token punctuation">;</span>
		<span class="token keyword">while</span><span class="token punctuation">(</span>i <span class="token operator">&gt;=</span> <span class="token number">1</span> <span class="token operator">&amp;&amp;</span> danhdau<span class="token punctuation">[</span>i<span class="token punctuation">]</span> <span class="token operator">!=</span> <span class="token number">0</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
			i<span class="token operator">--</span><span class="token punctuation">;</span>
		<span class="token punctuation">}</span>
		<span class="token keyword">if</span> <span class="token punctuation">(</span>i <span class="token operator">&lt;</span> <span class="token number">1</span><span class="token punctuation">)</span> <span class="token punctuation">{</span> <span class="token comment">// tức dãy hiện tại là 111..11</span>
			<span class="token keyword">break</span><span class="token punctuation">;</span> <span class="token comment">// kết thúc</span>
		<span class="token punctuation">}</span>
		danhdau<span class="token punctuation">[</span>i<span class="token punctuation">]</span> <span class="token operator">=</span> <span class="token number">1</span><span class="token punctuation">;</span> <span class="token comment">// đánh dấu lại thành 1, sau đó chuyển nửa bên kia =0</span>
		<span class="token keyword">for</span> <span class="token punctuation">(</span><span class="token keyword">int</span> j <span class="token operator">=</span> i <span class="token operator">+</span> <span class="token number">1</span><span class="token punctuation">;</span> j <span class="token operator">&lt;=</span> n<span class="token punctuation">;</span> j<span class="token operator">++</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
			danhdau<span class="token punctuation">[</span>j<span class="token punctuation">]</span> <span class="token operator">=</span> <span class="token number">0</span><span class="token punctuation">;</span>
		<span class="token punctuation">}</span>
	<span class="token punctuation">}</span>
<span class="token punctuation">}</span>
<span class="token keyword">int</span> <span class="token function">main</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
	<span class="token function">Init</span><span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
	<span class="token function">SinhNhiPhan</span><span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
	cout <span class="token operator">&lt;&lt;</span> result<span class="token punctuation">;</span>
<span class="token punctuation">}</span>
</code></pre>
<p>Luyện tập thêm nhiều bài tập nữa nhé!</p>
<h2 id="thank-you">Thank you</h2>

