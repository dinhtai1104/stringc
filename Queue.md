---


---

<h1 id="mục-lục">Mục lục</h1>
<ul>
<li>[QUEUE]</li>
<li>[Priority_QUEUE]</li>
</ul>
<hr>
<h2 id="giới-thiệu-queue">Giới thiệu QUEUE</h2>
<p>Chắc hẳn các bạn đã từng xếp hàng rồi chứ nhỉ? Khi mua đồ, khi mua vé xem phim, hay xếp hàng ra về. Mọi lần xếp hàng sẽ bắt đầu từ người đứng đầu tiên rồi tới các bạn phía sau, và tất nhiên người nào đến sớm hơn thì sẽ được ra về sớm hơn. Đó cũng chính là minh họa cho Cấu trúc QUEUE mà mình muốn hướng tới ngày hôm nay.<br>
QUEUE-tạm dịch là hàng đợi, là cấu trúc song hành với STACK nhưng hoạt động theo chuẩn LILO(Last In Last Out) hoặc FIFO(Fist In First Out). Hiểu một cách đơn giản là Vào Trước Ra Trước.<br>
Trong QUEUE, có hai vị trí quan trọng là vị trí đầu danh sách (front), nơi phần tử được lấy ra, và vị trí cuối danh sách (back), nơi phần tử cuối cùng được thêm vào</p>
<h2 id="code">Code</h2>
<p>Việc thêm phần tử vào cuối queue gọi là enqueue.<br>
Việc xóa phần tử đầu gọi là dequeue</p>
<h3 id="khai-báo">Khai báo</h3>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token macro property">#<span class="token directive keyword">include</span><span class="token string">&lt;queue&gt;</span></span>
<span class="token comment">//Ví dụ khai báo queue kiểu int  </span>
queue <span class="token operator">&lt;</span><span class="token keyword">int</span><span class="token operator">&gt;</span> s<span class="token punctuation">;</span>  
s<span class="token punctuation">.</span><span class="token function">size</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token operator">:</span> trả về kích thước hiện tại của queue<span class="token punctuation">.</span>  
s<span class="token punctuation">.</span><span class="token function">empty</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token operator">:</span> <span class="token boolean">true</span> nếu queue rỗng<span class="token punctuation">,</span> và ngược lại  
s<span class="token punctuation">.</span><span class="token function">push</span><span class="token punctuation">(</span>x<span class="token punctuation">)</span> <span class="token operator">:</span> đẩy x vào cuối queue<span class="token punctuation">.</span>  
s<span class="token punctuation">.</span><span class="token function">pop</span><span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token operator">:</span> loại bỏ phần tử <span class="token punctuation">(</span>ở đầu<span class="token punctuation">)</span><span class="token punctuation">.</span>  
s<span class="token punctuation">.</span><span class="token function">front</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token operator">:</span> trả về phần tử ở đầu  
s<span class="token punctuation">.</span><span class="token function">back</span><span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token operator">:</span> trả về phần tử ở cuối
</code></pre>
<h3 id="ứng-dụng">Ứng dụng</h3>
<ul>
<li>khử đệ quy</li>
<li>tổ chức lưu vết các quá trình tìm kiếm theo chiều rộng (BFS) và quay  lui, vét cạn</li>
<li>tổ chức quản lý và phân phốitiến trình trong các hệ điều hành, tổ chức bộ  đệm bàn phím.</li>
</ul>
<h2 id="priority_queuehàng-đợi-ưu-tiên">Priority_QUEUE(Hàng đợi ưu tiên)</h2>
<h3 id="khái-niệm">Khái niệm</h3>
<p>Nhắc tới khái niệm “Ưu tiên” chắc hẳn chúng ta đã biết tính chất của loại hàng đợi này. Đây chính là ví dụ của sự bất công trong xã hội, khi chỉ vì một yếu tố nào đó mà người tới trước chưa chắc đã nhận được thứ mình muốn đầu tiên, hay nói thẳng ra thì người nào có điều kiện tốt nhất thì sẽ được ưu tiên hơn.</p>
<p>Ví dụ: Các thành phần trong hàng đợi được ưu tiên theo độ lớn giảm dần, thì giữa 1 và 5, dù 1 có vào trước nhưng khi đến 5 vào vẫn phải nhường chỗ cho nó.</p>
<h3 id="code-1">Code</h3>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token macro property">#<span class="token directive keyword">include</span><span class="token string">&lt;queue&gt;</span></span>
priority_queue<span class="token operator">&lt;</span><span class="token keyword">int</span><span class="token punctuation">,</span> vector<span class="token operator">&lt;</span><span class="token keyword">int</span><span class="token operator">&gt;</span><span class="token punctuation">,</span> chuẩn ưu tiê<span class="token function">n</span><span class="token punctuation">(</span>nếu bỏ trống mặc định vào theo thứ tự giảm dần<span class="token punctuation">)</span><span class="token operator">&gt;</span> q<span class="token punctuation">;</span>
q<span class="token punctuation">.</span><span class="token function">push</span><span class="token punctuation">(</span><span class="token number">1</span><span class="token punctuation">)</span><span class="token punctuation">;</span><span class="token comment">// độ phức tạp log(n)</span>
q<span class="token punctuation">.</span><span class="token function">push</span><span class="token punctuation">(</span><span class="token number">2</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
q<span class="token punctuation">.</span><span class="token function">push</span><span class="token punctuation">(</span><span class="token number">3</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
<span class="token keyword">while</span><span class="token punctuation">(</span><span class="token operator">!</span>q<span class="token punctuation">.</span><span class="token function">empty</span><span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
	<span class="token keyword">int</span> x<span class="token operator">=</span>q<span class="token punctuation">.</span><span class="token function">front</span><span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
	cout<span class="token operator">&lt;&lt;</span>x<span class="token operator">&lt;&lt;</span><span class="token string">' '</span><span class="token punctuation">;</span>
	q<span class="token punctuation">.</span><span class="token function">pop</span><span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
<span class="token punctuation">}</span>
<span class="token comment">// kq: 3 2 1</span>
</code></pre>
<h3 id="ứng-dụng-1">Ứng dụng</h3>
<ul>
<li>Có nhiều ứng dụng nhưng có thể dùng nó để sắp xếp cũng khá tốt.</li>
</ul>
<p>Để hiểu rõ cách hoạt động của priority_queue các bạn nên tìm hiểu thêm cấu trúc Heap(google, có thể tôi sẽ thêm vào các bài sau)</p>
<p>Luyện tập:<br>
<a href="https://www.spoj.com/PTIT/problems/P175SUME/">https://www.spoj.com/PTIT/problems/P175SUME/</a><br>
Luyện tập thêm tại SPOJ/PTIT</p>

