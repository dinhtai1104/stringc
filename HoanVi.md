---


---

<h1 id="mục-lục">Mục lục</h1>
<hr>
<p><a href="#gi%E1%BB%9Bi-thi%E1%BB%87u">Giới thiệu</a><br>
<a href="#gi%E1%BB%9Bi-thi%E1%BB%87u-thu%E1%BA%ADt-to%C3%A1n">Giới thiệu thuật toán</a><br>
<a href="#thu%E1%BA%ADt-to%C3%A1n-kh%C3%A1c">Thuật toán khác</a></p>
<h2 id="giới-thiệu">Giới thiệu</h2>
<hr>
<p>Một hoán vị trong toán học là một dãy gồm <span class="katex--inline"><span class="katex"><span class="katex-mathml"><math><semantics><mrow><mi>n</mi></mrow><annotation encoding="application/x-tex">n</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="base"><span class="strut" style="height: 0.43056em; vertical-align: 0em;"></span><span class="mord mathdefault">n</span></span></span></span></span> kí tự với các kí tự từ 1…9 xuất hiện duy nhất và chỉ một lần: 123, 321, 1234, …</p>
<h2 id="giới-thiệu-thuật-toán">Giới thiệu thuật toán</h2>
<hr>
<p>Thuật toán sinh hoán vị kế tiếp là một thuật toán được dùng trong tin học máy tính rất nhiều, và thường được thấy ở một số bài toán giải thuật  áp dụng.</p>
<p>Giống với “Sinh Nhị Phân”, sinh hoán vị cũng là thuật toán được áp dụng với các bài toán mang tính “Lựa chọn” có thứ tự.<br>
Ví dụ: Các cách sắp xếp các số từ 1 đến 3 có thể là: 123, 321, 132, 231, 213, 312</p>
<h3 id="thuật-toán-được-phát-biểu-như-sau">Thuật toán được phát biểu như sau:</h3>
<ul>
<li>Từ phải qua trái tìm chỉ số đầu tiên xuất hiện trước dãy giảm dần:
<ul>
<li>Ví dụ: 6543<strong>721</strong> thì vị trí cần tìm là i = 4 với A[i] = 3</li>
</ul>
</li>
<li>Trong đoạn giảm dần ở vị trí có phần tử nhỏ nhất vẫn lớn hơn A[i]:
<ul>
<li>Như trên thì chỉ só cần tìm là j = 5 A[j] = 7</li>
</ul>
</li>
<li>Đổi chỗ A[i] và A[j]</li>
<li>Sau đó đảo ngược đoạn từ i + 1 -&gt; cuối dãy</li>
</ul>
<p>Code:</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token macro property">#<span class="token directive keyword">include</span> <span class="token string">&lt;iostream&gt;</span></span>
<span class="token keyword">using</span> <span class="token keyword">namespace</span> std<span class="token punctuation">;</span>
<span class="token keyword">int</span> a<span class="token punctuation">[</span><span class="token number">20</span><span class="token punctuation">]</span><span class="token punctuation">,</span> n<span class="token punctuation">;</span>
<span class="token keyword">void</span> <span class="token function">Init</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
	cin<span class="token operator">&gt;&gt;</span>n<span class="token punctuation">;</span>
	<span class="token keyword">for</span> <span class="token punctuation">(</span><span class="token keyword">int</span> i <span class="token operator">=</span> <span class="token number">1</span><span class="token punctuation">;</span> i <span class="token operator">&lt;=</span> n<span class="token punctuation">;</span> i<span class="token operator">++</span><span class="token punctuation">)</span>
		a<span class="token punctuation">[</span>i<span class="token punctuation">]</span> <span class="token operator">=</span> i<span class="token punctuation">;</span>
<span class="token punctuation">}</span>
<span class="token keyword">void</span> <span class="token function">InDay</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
	<span class="token keyword">for</span> <span class="token punctuation">(</span><span class="token keyword">int</span> i <span class="token operator">=</span> <span class="token number">1</span><span class="token punctuation">;</span> i <span class="token operator">&lt;=</span> n<span class="token punctuation">;</span> i<span class="token operator">++</span><span class="token punctuation">)</span>
		cout <span class="token operator">&lt;&lt;</span> a<span class="token punctuation">[</span>i<span class="token punctuation">]</span><span class="token punctuation">;</span>
	cout<span class="token operator">&lt;&lt;</span>endl<span class="token punctuation">;</span>
<span class="token punctuation">}</span>
<span class="token keyword">void</span> <span class="token function">Swap</span><span class="token punctuation">(</span><span class="token keyword">int</span> <span class="token operator">&amp;</span>a<span class="token punctuation">,</span> <span class="token keyword">int</span> <span class="token operator">&amp;</span>b<span class="token punctuation">)</span> <span class="token punctuation">{</span>
	<span class="token keyword">int</span> tmp <span class="token operator">=</span> a<span class="token punctuation">;</span>
	a <span class="token operator">=</span> b<span class="token punctuation">;</span>
	b <span class="token operator">=</span> tmp<span class="token punctuation">;</span>
<span class="token punctuation">}</span>
<span class="token keyword">void</span> <span class="token function">Sinh</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
	<span class="token keyword">while</span><span class="token punctuation">(</span><span class="token number">1</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
		<span class="token function">InDay</span><span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
		<span class="token keyword">int</span> i <span class="token operator">=</span> n <span class="token operator">-</span> <span class="token number">1</span><span class="token punctuation">;</span>
		<span class="token keyword">while</span><span class="token punctuation">(</span>i <span class="token operator">&gt;</span> <span class="token number">0</span> <span class="token operator">&amp;&amp;</span> a<span class="token punctuation">[</span>i<span class="token punctuation">]</span> <span class="token operator">&gt;</span> a<span class="token punctuation">[</span>i <span class="token operator">+</span> <span class="token number">1</span><span class="token punctuation">]</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
			i<span class="token operator">--</span><span class="token punctuation">;</span>
		<span class="token punctuation">}</span>
		<span class="token keyword">if</span> <span class="token punctuation">(</span>i <span class="token operator">&lt;</span> <span class="token number">1</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
			<span class="token keyword">break</span><span class="token punctuation">;</span>
		<span class="token punctuation">}</span>
		<span class="token keyword">int</span> k <span class="token operator">=</span> n<span class="token punctuation">;</span>
		<span class="token keyword">while</span><span class="token punctuation">(</span>k <span class="token operator">&gt;</span> i <span class="token operator">&amp;&amp;</span> a<span class="token punctuation">[</span>k<span class="token punctuation">]</span> <span class="token operator">&lt;</span> a<span class="token punctuation">[</span>i<span class="token punctuation">]</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
			k<span class="token operator">--</span><span class="token punctuation">;</span>
		<span class="token punctuation">}</span>
		<span class="token function">Swap</span><span class="token punctuation">(</span>a<span class="token punctuation">[</span>i<span class="token punctuation">]</span><span class="token punctuation">,</span> a<span class="token punctuation">[</span>k<span class="token punctuation">]</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
		<span class="token keyword">int</span> ptr1 <span class="token operator">=</span> i <span class="token operator">+</span> <span class="token number">1</span><span class="token punctuation">,</span> ptr2 <span class="token operator">=</span> n<span class="token punctuation">;</span>
		<span class="token keyword">while</span><span class="token punctuation">(</span>ptr1 <span class="token operator">&lt;=</span> ptr2<span class="token punctuation">)</span> <span class="token punctuation">{</span>
			<span class="token function">Swap</span><span class="token punctuation">(</span>a<span class="token punctuation">[</span>ptr1<span class="token punctuation">]</span><span class="token punctuation">,</span> a<span class="token punctuation">[</span>ptr2<span class="token punctuation">]</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
			ptr1<span class="token operator">++</span><span class="token punctuation">;</span>
			ptr2<span class="token operator">--</span><span class="token punctuation">;</span>
		<span class="token punctuation">}</span>
	<span class="token punctuation">}</span>
<span class="token punctuation">}</span>
<span class="token keyword">int</span> <span class="token function">main</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
	<span class="token function">Init</span><span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
	<span class="token function">Sinh</span><span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
<span class="token punctuation">}</span>
</code></pre>
<h2 id="thuật-toán-khác">Thuật toán khác</h2>
<hr>
<p>Bên cạnh việc sinh hoán vị bằng pp bên trên thì chúng ta cũng có thể sinh hoán vị bằng cách dùng pp Quay Lui được trình bày ở các bài trước.</p>
<p>Chúng ta sẽ dùng một mảng A[n+1] lưu các hoán vị, khi đó các hoán vị sẽ được biểu diễn như sau:</p>
<p>A[1], A[2], A[3], …,A[n].</p>
<p>Trong đó A[i] ≠ A[j] Với mọi i,j ∈ [1,n] và i ≠ j.</p>
<p>Để xác nhận một phần tử chỉ được dùng một lần ta sẽ dùng mảng Bool để lưu đánh dấu. Nếu phần tử chưa sử dụng thì sẽ có giá trị là 0 ngược lại sẽ có giá trị là 1. Ban đầu ta khởi tạo tất cả các phần tử trong mảng đều có giá trị là 0.</p>
<p>Ý tưởng của phương pháp quay lui là chúng ta sẽ chọn ra một phần tử chưa sử dụng. Lưu phần tử đó vào một cấu hình tổ hợp, sau đó đánh dấu nó đã sử dụng. Ta sẽ lặp lại công việc như trên đến khi đủ cấu hình cho một tổ hợp thì sẽ xuất ra màn hình. Sau khi xuất ra ta lại quay trở lại bước trước đó để đánh dấu là nó chưa được chọn.</p>
<p>Ta có thể hình dung bài toán như hình vẽ sau: Với n=3 thì bài toán trở thành liệt kê các hoán vị của các phần tử 1, 2, 3. Các hoán vị được liệt kê theo thứ tự từ điển tăng dần như hình vẽ sau:<br>
<img src="https://nguyenvanhieu.vn/wp-content/uploads/2018/11/hoan-vi.png" alt="enter image description here"></p>
<p>Code:</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token macro property">#<span class="token directive keyword">include</span> <span class="token string">&lt;iostream&gt;</span></span>
<span class="token keyword">using</span> <span class="token keyword">namespace</span> std<span class="token punctuation">;</span>
<span class="token keyword">int</span> a<span class="token punctuation">[</span><span class="token number">20</span><span class="token punctuation">]</span><span class="token punctuation">,</span> n<span class="token punctuation">,</span> danhdau<span class="token punctuation">[</span><span class="token number">20</span><span class="token punctuation">]</span> <span class="token operator">=</span> <span class="token punctuation">{</span><span class="token punctuation">}</span><span class="token punctuation">;</span>
<span class="token keyword">void</span> <span class="token function">Init</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
	cin<span class="token operator">&gt;&gt;</span>n<span class="token punctuation">;</span>
	<span class="token keyword">for</span> <span class="token punctuation">(</span><span class="token keyword">int</span> i <span class="token operator">=</span> <span class="token number">1</span><span class="token punctuation">;</span> i <span class="token operator">&lt;=</span> n<span class="token punctuation">;</span> i<span class="token operator">++</span><span class="token punctuation">)</span>
		a<span class="token punctuation">[</span>i<span class="token punctuation">]</span> <span class="token operator">=</span> i<span class="token punctuation">;</span>
<span class="token punctuation">}</span>
<span class="token keyword">void</span> <span class="token function">InDay</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
	<span class="token keyword">for</span> <span class="token punctuation">(</span><span class="token keyword">int</span> i <span class="token operator">=</span> <span class="token number">1</span><span class="token punctuation">;</span> i <span class="token operator">&lt;=</span> n<span class="token punctuation">;</span> i<span class="token operator">++</span><span class="token punctuation">)</span>
		cout <span class="token operator">&lt;&lt;</span> a<span class="token punctuation">[</span>i<span class="token punctuation">]</span><span class="token punctuation">;</span>
	cout<span class="token operator">&lt;&lt;</span>endl<span class="token punctuation">;</span>
<span class="token punctuation">}</span>
<span class="token keyword">void</span> <span class="token function">Swap</span><span class="token punctuation">(</span><span class="token keyword">int</span> <span class="token operator">&amp;</span>a<span class="token punctuation">,</span> <span class="token keyword">int</span> <span class="token operator">&amp;</span>b<span class="token punctuation">)</span> <span class="token punctuation">{</span>
	<span class="token keyword">int</span> tmp <span class="token operator">=</span> a<span class="token punctuation">;</span>
	a <span class="token operator">=</span> b<span class="token punctuation">;</span>
	b <span class="token operator">=</span> tmp<span class="token punctuation">;</span>
<span class="token punctuation">}</span>
<span class="token keyword">void</span> <span class="token function">Try</span><span class="token punctuation">(</span><span class="token keyword">int</span> i<span class="token punctuation">)</span> <span class="token punctuation">{</span>
	<span class="token keyword">for</span> <span class="token punctuation">(</span><span class="token keyword">int</span> j <span class="token operator">=</span> <span class="token number">1</span><span class="token punctuation">;</span> j <span class="token operator">&lt;=</span> n<span class="token punctuation">;</span> j<span class="token operator">++</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
		<span class="token keyword">if</span> <span class="token punctuation">(</span>danhdau<span class="token punctuation">[</span>j<span class="token punctuation">]</span> <span class="token operator">==</span> <span class="token number">0</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
			danhdau<span class="token punctuation">[</span>j<span class="token punctuation">]</span> <span class="token operator">=</span> <span class="token number">1</span><span class="token punctuation">;</span>
			a<span class="token punctuation">[</span>i<span class="token punctuation">]</span> <span class="token operator">=</span> j<span class="token punctuation">;</span>
			<span class="token keyword">if</span> <span class="token punctuation">(</span>i <span class="token operator">==</span> n<span class="token punctuation">)</span> <span class="token punctuation">{</span>
				<span class="token function">InDay</span><span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
			<span class="token punctuation">}</span> <span class="token keyword">else</span> <span class="token punctuation">{</span>
				<span class="token function">Try</span><span class="token punctuation">(</span>i <span class="token operator">+</span> <span class="token number">1</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
			<span class="token punctuation">}</span>
			danhdau<span class="token punctuation">[</span>j<span class="token punctuation">]</span> <span class="token operator">=</span> <span class="token number">0</span><span class="token punctuation">;</span>
		<span class="token punctuation">}</span>
	<span class="token punctuation">}</span>
<span class="token punctuation">}</span>
<span class="token keyword">int</span> <span class="token function">main</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
	<span class="token function">Init</span><span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
	<span class="token function">Try</span><span class="token punctuation">(</span><span class="token number">1</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
<span class="token punctuation">}</span>

</code></pre>
<blockquote>
<p>Khi chúng ta dùng sinh hoán vị bằng pp sinh kế tiếp ta có thể bắt đầu từ bất kì cấu hình nào. Còn dùng sinh hoán vị theo pp Quay lui nhất định ta phải bắt đầu từ cấu hình đầu tiên là 1…n</p>
</blockquote>
<p>Bài tập luyện tập:<br>
<a href="https://www.spoj.com/PTIT/problems/BCPERMU/">https://www.spoj.com/PTIT/problems/BCPERMU/</a><br>
<a href="https://www.spoj.com/PTIT/problems/BCNEPER/">https://www.spoj.com/PTIT/problems/BCNEPER/</a></p>

