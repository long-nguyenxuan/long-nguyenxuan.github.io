---


---

<hr>
<p>layout: post<br>
title: Tâm tư chuyện Viết blog<br>
date: ‘2019-11-06T00:04:00.000+07:00’<br>
author: LongNX<br>
tags:</p>
<ul>
<li>vụn</li>
</ul>
<hr>
<p>Nhiều lúc ngồi nhìn mấy cái blog của người ta lại thèm viết blog của mình, cơ mà bắt tay vào viết lại quá tập trung vào cái “blog engine” thay vì “blog content”.<br>
Hồi bữa thấy giới thiệu cái Github pages, thấy hay hay, xong rồi mày mò qua <code>jeklly</code> với lại <code>hexo</code> cũng thú vị, hôm nay mày mò chỗ thằng <code>jekyll-import</code>, wow, export cái file, nhấn enter một phát là nó kéo hết được bài viết từ bên chỗ blogspot về, lướt lại mấy dòng thời ngây ngô cũng vui :D.<br>
Note lại đây coi như 1 đoạn thú vị hôm nay:</p>
<ol>
<li>phi vào trong blogspot --&gt; Settings --&gt; Other chọn <code>Backup Content</code>, nó sẽ generate ra 1 file xml có dạng <code>blog-MM-DD-YYYY.xml</code>, save nó về 1 folder</li>
<li>Vào <a href="%5Bhttps://import.jekyllrb.com/docs/blogger/%5D(https://import.jekyllrb.com/docs/blogger/)">đây</a> để đọc hướng dẫn export data, hoặc chép đoạn code dưới vào 1 file tên <code>import.rb</code> chẳng hạn</li>
</ol>
<pre class=" language-ruby"><code class="prism  language-ruby"><span class="token keyword">require</span> <span class="token string">"jekyll-import"</span><span class="token punctuation">;</span>
<span class="token constant">JekyllImport</span><span class="token punctuation">:</span><span class="token symbol">:Importers</span><span class="token punctuation">:</span><span class="token symbol">:Blogger</span><span class="token punctuation">.</span><span class="token function">run</span><span class="token punctuation">(</span><span class="token punctuation">{</span>
  <span class="token string">"source"</span>                <span class="token operator">=</span><span class="token operator">&gt;</span> <span class="token string">"blog-11-06-2019.xml"</span><span class="token punctuation">,</span>
  <span class="token string">"no-blogger-info"</span>       <span class="token operator">=</span><span class="token operator">&gt;</span> <span class="token keyword">false</span><span class="token punctuation">,</span> <span class="token comment"># not to leave blogger-URL info (id and old URL) in the front matter</span>
  <span class="token string">"replace-internal-link"</span> <span class="token operator">=</span><span class="token operator">&gt;</span> <span class="token keyword">false</span><span class="token punctuation">,</span> <span class="token comment"># replace internal links using the post_url liquid tag.</span>
<span class="token punctuation">}</span><span class="token punctuation">)</span>
</code></pre>
<ol start="3">
<li>mở cmd ở folder có chứa cái file <code>import.rb</code> đấy chạy lệnh <code>ruby import.rb</code> vậy là ruby sẽ gọi cái <code>gem</code> <code>jekyll-import</code> kia lên, truyền tham số là file xml của ta, để kéo hết đống bài viết trên blogger về, ở định dạng html, kèm theo cái header của jekyll (chả biết phải không, đoán thế :D )</li>
</ol>
<pre><code>---
layout: post
title: Tùy chỉnh Firefox không đóng cửa sổ khi close tab cuối
date: '2011-01-08T00:04:00.000+07:00'
author: LongNX
tags:
- Tips
modified_time: '2012-10-07T00:41:16.815+07:00'
blogger_id: tag:blogger.com,1999:blog-7002884210363940340.post-822816716037176474
blogger_orig_url: https://longtth.blogspot.com/2011/01/tuy-chinh-firefox-khong-ong-cua-so-khi.html
---
</code></pre>
<ol start="4">
<li>Rồi hết chuyện “blog engine” lại đến chuyện editor, như cái bài này thì viết bằng stackedit, 1 cái markdown editor cực mạnh, cơ mà web-based :D trong khi việc chuyển blogger sang chỗ jekyll là để quản lý tất cả đống post này bằng <code>local file</code> rồi đồng bộ bằng github này kia.</li>
</ol>
<blockquote>
<p>Written with <a href="https://stackedit.io/">StackEdit</a>.</p>
</blockquote>

