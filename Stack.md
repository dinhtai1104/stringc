<!DOCTYPE html>
<html>

<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Stack</title>
  <link rel="stylesheet" href="https://stackedit.io/style.css" />
</head>

<body class="stackedit">
  <div class="stackedit__html"><h1 id="mục-lục">Mục lục</h1>
<hr>
<ul>
<li><a href="#gi%E1%BB%9Bi-thi%E1%BB%87u">Giới thiệu</a></li>
<li><a href="#%C4%91%E1%BB%8Bnh-ngh%C4%A9a">Định nghĩa</a></li>
<li><a href="#code">Code</a></li>
<li><a href="#%E1%BB%A9ng-d%E1%BB%A5ng">Ứng dụng</a></li>
<li><a href="#%C3%A1p-d%E1%BB%A5ng">Áp dụng</a></li>
</ul>
<h2 id="giới-thiệu">Giới thiệu</h2>
<hr>
<p>Tưởng tượng bạn có một giá sách thì khi cất sách thì cuốn đó được đặt lên trên cùng, và khi lấy ra thì phải lấy cuốn trên cùng, chứ không thể lấy ra hoặc cất lên từ vị trí khác. Đó chính là cách hoạt động của cấu trúc <strong>Stack</strong> (Ngăn xếp) theo kiểu <strong>LIFO</strong>(Last In First Out - Vào sau ra trước)<br>
<img src="https://images.pexels.com/photos/51342/books-education-school-literature-51342.jpeg?auto=compress&amp;cs=tinysrgb&amp;h=750&amp;w=1260b&amp;h=750&amp;w=1260%22%3E" alt="enter image description here"></p>
<h2 id="định-nghĩa">Định nghĩa</h2>
<hr>
<p>Một ngăn xếp là một cấu trúc dữ liệu dạng thùng chứa <strong>(container)</strong> của các phần tử (thường gọi là các nút <strong>(node)</strong>) và có hai phép toán cơ bản:</p>
<ul>
<li><strong>push</strong>: Bổ sung một phần tử vào đỉnh (top) của ngăn xếp, nghĩa là sau các phần tử đã có trong ngăn xếp.</li>
<li><strong>pop</strong>: Giải phóng và trả về phần tử đang đứng ở đỉnh của ngăn xếp.</li>
</ul>
<p>Trong stack, các đối tượng có thể được thêm vào stack bất kỳ lúc nào <em>nhưng chỉ có đối tượng thêm vào sau cùng mới được phép lấy ra khỏi stack.</em></p>
<h2 id="code">Code</h2>
<hr>
<p>Cấu trúc <strong>Stack</strong> được chứa trong thư viện <strong>stack</strong> vậy nên chúng ta cần <em>include&lt; stack &gt;</em><br>
Cách khai báo:</p>
<pre class=" language-cpp"><code class="prism  language-cpp">stack<span class="token operator">&lt;</span><span class="token keyword">int</span><span class="token operator">&gt;</span> nganXep1<span class="token punctuation">;</span> <span class="token comment">// stack có các phần tử kiểu int</span>
stack<span class="token operator">&lt;</span><span class="token keyword">char</span><span class="token operator">&gt;</span> nganXep2<span class="token punctuation">;</span> <span class="token comment">// kiểu char</span>
<span class="token punctuation">.</span><span class="token punctuation">.</span><span class="token punctuation">.</span>
</code></pre>
<pre class=" language-cpp"><code class="prism  language-cpp">stack<span class="token operator">&lt;</span><span class="token keyword">int</span><span class="token operator">&gt;</span> s<span class="token punctuation">;</span>
</code></pre>
<p>Với <strong>stack</strong>  <span class="katex--inline"><span class="katex"><span class="katex-mathml"><math><semantics><mrow><mi>s</mi></mrow><annotation encoding="application/x-tex">s</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="base"><span class="strut" style="height: 0.43056em; vertical-align: 0em;"></span><span class="mord mathdefault">s</span></span></span></span></span>, ta có các hàm:</p>
<ul>
<li>s.size(): Trả về số lượng các phần tử trong <strong>stack</strong></li>
<li>s.empty(): Trả về <strong>true</strong> nếu <strong>stack</strong> rỗng(size=0) ngược lại trả về <strong>false</strong></li>
<li>s.push(x): Đầy phần tử <span class="katex--inline"><span class="katex"><span class="katex-mathml"><math><semantics><mrow><mi>x</mi></mrow><annotation encoding="application/x-tex">x</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="base"><span class="strut" style="height: 0.43056em; vertical-align: 0em;"></span><span class="mord mathdefault">x</span></span></span></span></span> vào đỉnh <strong>stack</strong></li>
<li>s.pop(): Loại bỏ đỉnh của <strong>stack</strong></li>
<li>s.top(): Trả về phần tử đỉnh của <strong>stack</strong></li>
</ul>
<h3 id="ví-dụ">Ví dụ:</h3>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token macro property">#<span class="token directive keyword">include</span><span class="token string">&lt;iostream&gt;</span></span>
<span class="token macro property">#<span class="token directive keyword">include</span><span class="token string">&lt;stack&gt;</span></span>
<span class="token keyword">using</span> <span class="token keyword">namespace</span> std<span class="token punctuation">;</span>

stack<span class="token operator">&lt;</span><span class="token keyword">int</span><span class="token operator">&gt;</span> s<span class="token punctuation">;</span>

<span class="token keyword">int</span> <span class="token function">main</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
	<span class="token keyword">for</span> <span class="token punctuation">(</span><span class="token keyword">int</span> i<span class="token operator">=</span><span class="token number">0</span><span class="token punctuation">;</span>i<span class="token operator">&lt;</span><span class="token number">5</span><span class="token punctuation">;</span>i<span class="token operator">++</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
		s<span class="token punctuation">.</span><span class="token function">push</span><span class="token punctuation">(</span>i<span class="token punctuation">)</span><span class="token punctuation">;</span> <span class="token comment">// s = {1,2,3,4,5}</span>
	<span class="token punctuation">}</span>
	s<span class="token punctuation">.</span><span class="token function">push</span><span class="token punctuation">(</span><span class="token number">100</span><span class="token punctuation">)</span><span class="token punctuation">;</span> <span class="token comment">// s = {1,2,3,4,5,100}</span>
	cout<span class="token operator">&lt;&lt;</span>s<span class="token punctuation">.</span><span class="token function">top</span><span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token operator">&lt;&lt;</span>endl<span class="token punctuation">;</span> <span class="token comment">// in ra 100</span>
	s<span class="token punctuation">.</span><span class="token function">pop</span><span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">;</span> <span class="token comment">// s = {1,2,3,4,5}</span>
	<span class="token keyword">for</span><span class="token punctuation">(</span><span class="token keyword">int</span> i<span class="token operator">=</span><span class="token number">0</span><span class="token punctuation">;</span>i<span class="token operator">&lt;</span><span class="token number">5</span><span class="token punctuation">;</span>i<span class="token operator">++</span><span class="token punctuation">)</span><span class="token punctuation">{</span>
		cout<span class="token operator">&lt;&lt;</span>s<span class="token punctuation">.</span><span class="token function">top</span><span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token operator">&lt;&lt;</span><span class="token string">' '</span><span class="token punctuation">;</span>
		s<span class="token punctuation">.</span><span class="token function">pop</span><span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
	<span class="token punctuation">}</span>
	<span class="token comment">// in ra 5 4 3 2 1</span>
<span class="token punctuation">}</span>
</code></pre>
<h2 id="ứng-dụng">Ứng dụng</h2>
<hr>
<ul>
<li>Đảo ngược xâu: nhập từng kí tự xâu cho vào stack, sau đó lấy từng kí tự ra ta sẽ được 1 xâu đảo ngược.</li>
<li>Chuyển hệ cơ số 10 sang cơ số 2(cơ số bất kì): thực hiện liên tiếp phép chia dư n cho 2 rồi , n=n/2 và push kq phép chia dư vào stack, sau khi chia xong ta lấy các phần tử trong stack ra.</li>
<li>Tính biểu thức đại số, chuyển biểu thức đại số dạng trung sang hậu tố.</li>
<li>Khử đệ quy (trong duyệt đồ thị DFS)</li>
</ul>
<h2 id="áp-dụng">Áp dụng</h2>
<hr>
<p>PTIT123J - Dấu ngoặc đúng<br>
<a href="https://www.spoj.com/PTIT/problems/PTIT123J/">https://www.spoj.com/PTIT/problems/PTIT123J/</a></p>
<p>Ý tưởng:<br>
Có một stack lưu các kí tự “(” hoặc “[”, xét từ đầu xâu tới cuối:</p>
<ul>
<li>Nếu gặp dấu “(” hoặc “[” thì push vào stack</li>
<li>Nếu gặp dấu “)” mà đỉnh stack là dấu “(” thì pop ra ngược lại in ra <span class="katex--inline"><span class="katex"><span class="katex-mathml"><math><semantics><mrow><mi>N</mi><mi>O</mi></mrow><annotation encoding="application/x-tex">NO</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="base"><span class="strut" style="height: 0.68333em; vertical-align: 0em;"></span><span class="mord mathdefault" style="margin-right: 0.10903em;">N</span><span class="mord mathdefault" style="margin-right: 0.02778em;">O</span></span></span></span></span> vì đỉnh là “[” (không thể có loại “(…]”</li>
<li>Nếu gặp dấu “]” mà đỉnh stack là dấu “[” thì pop ra ngược lại in ra <span class="katex--inline"><span class="katex"><span class="katex-mathml"><math><semantics><mrow><mi>N</mi><mi>O</mi></mrow><annotation encoding="application/x-tex">NO</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="base"><span class="strut" style="height: 0.68333em; vertical-align: 0em;"></span><span class="mord mathdefault" style="margin-right: 0.10903em;">N</span><span class="mord mathdefault" style="margin-right: 0.02778em;">O</span></span></span></span></span> vì đỉnh là “(” (không thể có loại “[…)”</li>
<li>Sau khi xét đến cuối xâu kiếm tra nếu trong stack còn phần tử thì in ra <span class="katex--inline"><span class="katex"><span class="katex-mathml"><math><semantics><mrow><mi>N</mi><mi>O</mi></mrow><annotation encoding="application/x-tex">NO</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="base"><span class="strut" style="height: 0.68333em; vertical-align: 0em;"></span><span class="mord mathdefault" style="margin-right: 0.10903em;">N</span><span class="mord mathdefault" style="margin-right: 0.02778em;">O</span></span></span></span></span> ngược lại in ra <span class="katex--inline"><span class="katex"><span class="katex-mathml"><math><semantics><mrow><mi>Y</mi><mi>E</mi><mi>S</mi></mrow><annotation encoding="application/x-tex">YES</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="base"><span class="strut" style="height: 0.68333em; vertical-align: 0em;"></span><span class="mord mathdefault" style="margin-right: 0.22222em;">Y</span><span class="mord mathdefault" style="margin-right: 0.05764em;">E</span><span class="mord mathdefault" style="margin-right: 0.05764em;">S</span></span></span></span></span>.</li>
</ul>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token macro property">#<span class="token directive keyword">include</span><span class="token string">&lt;iostream&gt;</span></span>
<span class="token macro property">#<span class="token directive keyword">include</span><span class="token string">&lt;string&gt;</span></span>
<span class="token keyword">using</span> <span class="token keyword">namespace</span> std<span class="token punctuation">;</span>
<span class="token macro property">#<span class="token directive keyword">include</span><span class="token string">&lt;stack&gt;</span></span>
<span class="token keyword">int</span> <span class="token function">main</span><span class="token punctuation">(</span><span class="token punctuation">)</span>
<span class="token punctuation">{</span>
	<span class="token keyword">while</span><span class="token punctuation">(</span><span class="token number">1</span><span class="token punctuation">)</span>
	<span class="token punctuation">{</span>
		string s<span class="token punctuation">;</span>
		<span class="token function">getline</span><span class="token punctuation">(</span>cin<span class="token punctuation">,</span> s<span class="token punctuation">)</span><span class="token punctuation">;</span>
		<span class="token keyword">if</span> <span class="token punctuation">(</span>s<span class="token punctuation">[</span>s<span class="token punctuation">.</span><span class="token function">length</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token operator">-</span> <span class="token number">1</span><span class="token punctuation">]</span> <span class="token operator">==</span> <span class="token string">'.'</span> <span class="token operator">&amp;&amp;</span> s<span class="token punctuation">.</span><span class="token function">length</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token operator">==</span> <span class="token number">1</span><span class="token punctuation">)</span> <span class="token keyword">break</span><span class="token punctuation">;</span><span class="token punctuation">;</span>
		stack<span class="token operator">&lt;</span><span class="token keyword">char</span><span class="token operator">&gt;</span> stark<span class="token punctuation">;</span>
		<span class="token keyword">bool</span> flag <span class="token operator">=</span> <span class="token boolean">true</span><span class="token punctuation">;</span>
		<span class="token comment">//while(stark.size()) stark.pop();</span>
		<span class="token keyword">for</span> <span class="token punctuation">(</span><span class="token keyword">int</span> i <span class="token operator">=</span> <span class="token number">0</span><span class="token punctuation">;</span> s<span class="token punctuation">[</span>i<span class="token punctuation">]</span> <span class="token operator">!=</span> <span class="token string">'.'</span><span class="token punctuation">;</span> i<span class="token operator">++</span><span class="token punctuation">)</span> 
		<span class="token punctuation">{</span>
			<span class="token keyword">if</span> <span class="token punctuation">(</span>s<span class="token punctuation">[</span>i<span class="token punctuation">]</span> <span class="token operator">==</span> <span class="token string">'('</span><span class="token punctuation">)</span> stark<span class="token punctuation">.</span><span class="token function">push</span><span class="token punctuation">(</span>s<span class="token punctuation">[</span>i<span class="token punctuation">]</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
			<span class="token keyword">else</span> <span class="token keyword">if</span> <span class="token punctuation">(</span>s<span class="token punctuation">[</span>i<span class="token punctuation">]</span> <span class="token operator">==</span> <span class="token string">'['</span><span class="token punctuation">)</span> stark<span class="token punctuation">.</span><span class="token function">push</span><span class="token punctuation">(</span>s<span class="token punctuation">[</span>i<span class="token punctuation">]</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
			<span class="token keyword">else</span> 
			<span class="token punctuation">{</span>
				<span class="token keyword">if</span> <span class="token punctuation">(</span>s<span class="token punctuation">[</span>i<span class="token punctuation">]</span> <span class="token operator">==</span> <span class="token string">')'</span><span class="token punctuation">)</span> 
				<span class="token punctuation">{</span>
					<span class="token keyword">if</span> <span class="token punctuation">(</span>stark<span class="token punctuation">.</span><span class="token function">size</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token operator">==</span> <span class="token number">0</span> <span class="token operator">||</span> stark<span class="token punctuation">.</span><span class="token function">top</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token operator">!=</span> <span class="token string">'('</span><span class="token punctuation">)</span>
					<span class="token punctuation">{</span>
						flag <span class="token operator">=</span> <span class="token boolean">false</span><span class="token punctuation">;</span>
						<span class="token keyword">break</span><span class="token punctuation">;</span>
					<span class="token punctuation">}</span>
					<span class="token keyword">else</span> stark<span class="token punctuation">.</span><span class="token function">pop</span><span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
				<span class="token punctuation">}</span>
				<span class="token keyword">else</span> <span class="token keyword">if</span> <span class="token punctuation">(</span>s<span class="token punctuation">[</span>i<span class="token punctuation">]</span> <span class="token operator">==</span> <span class="token string">']'</span><span class="token punctuation">)</span>
				<span class="token punctuation">{</span>
					<span class="token keyword">if</span> <span class="token punctuation">(</span>stark<span class="token punctuation">.</span><span class="token function">size</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token operator">==</span> <span class="token number">0</span> <span class="token operator">||</span> stark<span class="token punctuation">.</span><span class="token function">top</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token operator">!=</span> <span class="token string">'['</span><span class="token punctuation">)</span>
					<span class="token punctuation">{</span>
						flag <span class="token operator">=</span> <span class="token boolean">false</span><span class="token punctuation">;</span>
						<span class="token keyword">break</span><span class="token punctuation">;</span>
					<span class="token punctuation">}</span>
					<span class="token keyword">else</span> stark<span class="token punctuation">.</span><span class="token function">pop</span><span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
				<span class="token punctuation">}</span>			
			<span class="token punctuation">}</span>
		<span class="token punctuation">}</span>
		<span class="token keyword">if</span> <span class="token punctuation">(</span>flag <span class="token operator">&amp;&amp;</span> stark<span class="token punctuation">.</span><span class="token function">size</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token operator">==</span> <span class="token number">0</span><span class="token punctuation">)</span> cout <span class="token operator">&lt;&lt;</span> <span class="token string">"yes"</span> <span class="token operator">&lt;&lt;</span> endl<span class="token punctuation">;</span>
		<span class="token keyword">else</span> cout <span class="token operator">&lt;&lt;</span> <span class="token string">"no"</span> <span class="token operator">&lt;&lt;</span> endl<span class="token punctuation">;</span>
	<span class="token punctuation">}</span>
	
	<span class="token keyword">return</span> <span class="token number">0</span><span class="token punctuation">;</span>
<span class="token punctuation">}</span>


</code></pre>
<p>Bài tập áp dụng:<br>
PTIT121E - Nguyên tố hóa học<br>
<a href="https://www.spoj.com/PTIT/problems/PTIT121E/">https://www.spoj.com/PTIT/problems/PTIT121E/</a></p>
<p>BCSTACK - Cấu trúc dữ liệu ngăn xếp (stack) (Cơ bản)<br>
<a href="https://www.spoj.com/PTIT/problems/BCSTACK/">https://www.spoj.com/PTIT/problems/BCSTACK/</a></p>
</div>
</body>

</html>
