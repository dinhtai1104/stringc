---


---

<h1 id="string-trong-c">String trong C++</h1>
<p>Ở bài học trước, chúng ta đã được tìm hiểu về kiểu dữ liệu <strong>Vector</strong> trong ngôn ngữ <strong>C++</strong><br>
<strong>String</strong>  là một lớp chuẩn mô tả về về chuỗi kí tự, nó cung cấp khả năng lưu trữ chuỗi kí tự gọi là  <strong>standard container</strong>, và thêm vào đó một số chi tiết được thiết kế để xử lý chuỗi kí tự mà nó đang lưu trữ, hay có thể hiểu là <strong>vector</strong> của kiểu dữ liệu <strong>char</strong> ( hay có thể hiểu như <strong>vector&lt; char &gt;</strong>).</p>
<pre class=" language-cpp"><code class="prism  language-cpp">string s <span class="token operator">=</span> <span class="token string">"Lap trinh PTIT"</span><span class="token punctuation">;</span>
string name <span class="token operator">=</span> <span class="token string">"Nguyen Van A"</span><span class="token punctuation">;</span>
</code></pre>
<p>Ở đây chúng ta sẽ phân ra 2 kiểu dữ liệu chuỗi là <strong>Cpp-style-string</strong> và <strong>C-style-string</strong>.</p>
<h1 id="c-style-string">C-style-string</h1>
<p>Đây là kiểu chuỗi kí tự mà chúng ta sử dụng trong ngôn ngữ <strong>C</strong></p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token macro property">#<span class="token directive keyword">include</span> <span class="token string">&lt;stdio.h&gt;</span></span>
<span class="token keyword">int</span> <span class="token function">main</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
	<span class="token keyword">char</span> name<span class="token punctuation">[</span><span class="token number">20</span><span class="token punctuation">]</span><span class="token punctuation">;</span>
	<span class="token function">scanf</span><span class="token punctuation">(</span><span class="token string">"%s"</span><span class="token punctuation">,</span> name<span class="token punctuation">)</span><span class="token punctuation">;</span>
	<span class="token function">printf</span><span class="token punctuation">(</span><span class="token string">"%s"</span><span class="token punctuation">,</span> name<span class="token punctuation">)</span><span class="token punctuation">;</span>
	<span class="token keyword">return</span> <span class="token number">0</span><span class="token punctuation">;</span>
<span class="token punctuation">}</span>
</code></pre>
<p>Với thư viện <strong>&lt;string.h&gt;</strong> chúng ta có các hàm như:</p>
<ol>
<li><strong>strcat</strong> : nối chuỗi</li>
<li><strong>strspy</strong> : copy chuỗi</li>
<li><strong>strtok</strong> : tách chuỗi</li>
<li>…</li>
</ol>
<p>Tuy nhiên có rất nhiều bất tiện trong sử dụng mảng <strong>char</strong> nên ở <strong>C++</strong> đã cho ra đời lớp <strong>string</strong> để hỗ trợ việc xử lý chuỗi được dễ dàng hơn</p>
<h1 id="cpp-style-string">Cpp-style-string</h1>
<blockquote>
<p>Một ưu điểm mà lớp  <strong>string</strong>  đem lại cho chúng ta là  <strong>standard container</strong>  có thể tự thay đổi kích thước vùng nhớ cho phù hợp với yêu cầu về mặt lưu trữ chuỗi kí tự. Do đó, các bạn có thể tùy ý nối hoặc chèn thêm dữ liệu vào  <strong>standard container</strong>  cho đến khi dung lượng bộ nhớ không đủ để cung cấp nữa.</p>
</blockquote>
<h3 id="khai-báo-và-khởi-tạo">Khai báo và khởi tạo</h3>
<p>Tương tự như cách chúng ta khai báo biến thông thường, kiểu dữ liệu sẽ được dùng trong bài học này là  <strong>string</strong>  (Các bạn cần include thư viện  <strong>string</strong>  vào trước khi sử dụng).</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token macro property">#<span class="token directive keyword">include</span><span class="token string">&lt;iostream&gt;</span></span>
<span class="token macro property">#<span class="token directive keyword">include</span><span class="token string">&lt;string&gt;</span></span>
<span class="token keyword">using</span> <span class="token keyword">namespace</span> std<span class="token punctuation">;</span>
<span class="token punctuation">.</span><span class="token punctuation">.</span><span class="token punctuation">.</span>
string myClub <span class="token operator">=</span> <span class="token string">"Lap trinh PTIT"</span><span class="token punctuation">;</span>
</code></pre>
<p><strong>string</strong> cũng có thể được khai báo từ nhiều cách khác nhau:</p>
<pre class=" language-cpp"><code class="prism  language-cpp">string myName <span class="token operator">=</span> <span class="token string">"Nguyen Van A"</span><span class="token punctuation">;</span>
string myName2 <span class="token operator">=</span> myName<span class="token punctuation">;</span>
string myClass<span class="token punctuation">;</span>
myClass <span class="token operator">=</span> <span class="token string">"D18CN"</span><span class="token punctuation">;</span>
string <span class="token function">myClub</span><span class="token punctuation">(</span><span class="token string">"Lap trinh PTIT"</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
<span class="token comment">// Có thể đọc từ bàn phím như một biến thông thường</span>
string myPlanet<span class="token punctuation">;</span>
cin <span class="token operator">&gt;&gt;</span> myPlanet<span class="token punctuation">;</span>
cout <span class="token operator">&lt;&lt;</span> myPlanet<span class="token punctuation">;</span>
</code></pre>
<h3 id="nhập-xuất-khai-báo">Nhập xuất, khai báo</h3>
<p>Kiểu dữ liệu <strong>string</strong> nằm trong thư viện &lt; string &gt; và trong <strong>namespace std;</strong> nên nhớ khai báo trước khi sử dụng nhé.</p>
<p>Cách nhập một chuỗi string trong C++ có nhiều cách:</p>
<ol>
<li>Nhập các từ đơn lẻ: “Hello”, “PROPTIT”,… chỉ cần dùng</li>
</ol>
<pre class=" language-cpp"><code class="prism  language-cpp">string firstName<span class="token punctuation">;</span>
cin <span class="token operator">&gt;&gt;</span> firstName<span class="token punctuation">;</span>
</code></pre>
<ol start="2">
<li>Nhập một chuỗi nhiều từ (Đọc theo dòng)</li>
</ol>
<pre class=" language-cpp"><code class="prism  language-cpp">string myName<span class="token punctuation">;</span>
<span class="token function">getline</span><span class="token punctuation">(</span>cin<span class="token punctuation">,</span> myName<span class="token punctuation">)</span><span class="token punctuation">;</span>
</code></pre>
<ol start="3">
<li>Đọc cho tới khi gặp một kí tự nào đó</li>
</ol>
<pre class=" language-cpp"><code class="prism  language-cpp">string myName<span class="token punctuation">;</span>
<span class="token keyword">char</span> token <span class="token operator">=</span> <span class="token string">'t'</span><span class="token punctuation">;</span>
<span class="token function">getline</span><span class="token punctuation">(</span>cin<span class="token punctuation">,</span> myName<span class="token punctuation">,</span> token<span class="token punctuation">)</span><span class="token punctuation">;</span>
<span class="token operator">--</span><span class="token operator">--</span><span class="token operator">--</span><span class="token operator">--</span><span class="token operator">--</span><span class="token operator">--</span><span class="token operator">--</span><span class="token operator">--</span><span class="token operator">--</span><span class="token operator">--</span><span class="token operator">--</span><span class="token operator">--</span><span class="token operator">--</span><span class="token operator">--</span><span class="token operator">--</span>
Input<span class="token operator">:</span> my name is TaitDinh
Output<span class="token operator">:</span> my name is Tai
</code></pre>
<h3 id="sử-dụng">Sử dụng</h3>
<p>Do có nhiều lợi thế hơn nên <strong>string</strong> được cung cấp khá nhiều tiện ích:</p>
<ol>
<li>Nối chuỗi: Dùng toán tử cộng <strong>+</strong> để nối 2 string lại</li>
</ol>
<pre class=" language-cpp"><code class="prism  language-cpp">string university <span class="token operator">=</span> <span class="token string">"Hoc vien "</span> <span class="token operator">+</span> <span class="token string">"Cong nghe "</span> <span class="token operator">+</span> <span class="token string">"Buu chinh "</span> <span class="token operator">+</span> <span class="token string">"Vien thong"</span><span class="token punctuation">;</span>
string number <span class="token operator">=</span> <span class="token string">"2"</span> <span class="token operator">+</span> <span class="token string">"4"</span><span class="token punctuation">;</span> <span class="token comment">//kq = "24"</span>
</code></pre>
<ol start="2">
<li>So sánh 2 string:</li>
</ol>
<pre class=" language-cpp"><code class="prism  language-cpp">string A <span class="token operator">=</span> <span class="token string">"Nguyen Van A"</span><span class="token punctuation">;</span>
string B <span class="token operator">=</span> <span class="token string">"Nguyen Van B"</span><span class="token punctuation">;</span>
<span class="token keyword">if</span> <span class="token punctuation">(</span>A <span class="token operator">==</span> B<span class="token punctuation">)</span> <span class="token punctuation">{</span>
	cout <span class="token operator">&lt;&lt;</span> <span class="token string">"2 String giong nhau"</span><span class="token punctuation">;</span>
<span class="token punctuation">}</span>
<span class="token keyword">else</span> <span class="token punctuation">{</span>
	cout <span class="token operator">&lt;&lt;</span> <span class="token string">"2 String khac nhau"</span><span class="token punctuation">;</span>
<span class="token punctuation">}</span>
</code></pre>
<ol start="3">
<li>Lấy độ dài của chuỗi</li>
</ol>
<pre class=" language-cpp"><code class="prism  language-cpp">string testLength <span class="token operator">=</span> <span class="token string">"My boys"</span><span class="token punctuation">;</span>
<span class="token keyword">int</span> len <span class="token operator">=</span> testLength<span class="token punctuation">.</span><span class="token function">length</span><span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
cout <span class="token operator">&lt;&lt;</span> testLength <span class="token operator">&lt;&lt;</span> <span class="token string">" co do dai bang :"</span> <span class="token operator">&lt;&lt;</span> len<span class="token punctuation">;</span>
</code></pre>
<ol start="4">
<li>Đảo ngược chuỗi</li>
</ol>
<pre class=" language-cpp"><code class="prism  language-cpp">string s <span class="token operator">=</span> <span class="token string">"This is a chair"</span><span class="token punctuation">;</span>
s<span class="token punctuation">.</span><span class="token function">reserve</span><span class="token punctuation">(</span>s<span class="token punctuation">.</span><span class="token function">begin</span><span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">,</span> s<span class="token punctuation">.</span><span class="token function">end</span><span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
cout <span class="token operator">&lt;&lt;</span> s<span class="token punctuation">;</span>
<span class="token comment">// kq : riahc a si sihT</span>
</code></pre>
<p>Và do <strong>string</strong> cũng là một kiểu dữ liệu <strong>vector</strong> nên <strong>string</strong> cũng bao gồm tất cả các hàm có trong lớp <strong>vector</strong>.</p>
<h1 id="thank-you">Thank you</h1>

