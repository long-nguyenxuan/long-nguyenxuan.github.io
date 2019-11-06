---
layout: post
title: Tâm tư chuyện Viết blog
date: '2019-11-06T00:04:00.000+07:00'
author: LongNX
tags:
- vụn
---
Nhiều lúc ngồi nhìn mấy cái blog của người ta lại thèm viết blog của mình, cơ mà bắt tay vào viết lại quá tập trung vào cái "blog engine" thay vì "blog content". 
Hồi bữa thấy giới thiệu cái Github pages, thấy hay hay, xong rồi mày mò qua `jeklly` với lại `hexo` cũng thú vị, hôm nay mày mò chỗ thằng `jekyll-import`, wow, export cái file, nhấn enter một phát là nó kéo hết được bài viết từ bên chỗ blogspot về, lướt lại mấy dòng thời ngây ngô cũng vui :D. 
Note lại đây coi như 1 đoạn thú vị hôm nay: 
1. phi vào trong blogspot --> Settings --> Other chọn `Backup Content`, nó sẽ generate ra 1 file xml có dạng `blog-MM-DD-YYYY.xml`, save nó về 1 folder 
2. Vào [đây]([https://import.jekyllrb.com/docs/blogger/](https://import.jekyllrb.com/docs/blogger/)) để đọc hướng dẫn export data, hoặc chép đoạn code dưới vào 1 file tên `import.rb` chẳng hạn
```ruby
require "jekyll-import";
JekyllImport::Importers::Blogger.run({
  "source"                => "blog-11-06-2019.xml",
  "no-blogger-info"       => false, # not to leave blogger-URL info (id and old URL) in the front matter
  "replace-internal-link" => false, # replace internal links using the post_url liquid tag.
})
```
3. mở cmd ở folder có chứa cái file `import.rb` đấy chạy lệnh `ruby import.rb` vậy là ruby sẽ gọi cái `gem` `jekyll-import` kia lên, truyền tham số là file xml của ta, để kéo hết đống bài viết trên blogger về, ở định dạng html, kèm theo cái header của jekyll (chả biết phải không, đoán thế :D ) 
```yaml
---
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
```
4. Rồi hết chuyện "blog engine" lại đến chuyện editor, như cái bài này thì viết bằng stackedit, 1 cái markdown editor cực mạnh, cơ mà web-based :D trong khi việc chuyển blogger sang chỗ jekyll là để quản lý tất cả đống post này bằng `local file` rồi đồng bộ bằng github này kia. 
5. ok5, bạn stackedit thực ra chỉ cho mình viết và save markdown trên máy bạn ấy và cái workspace (Google Drive v.v.) chứ khi publish thì bạn ấy sẽ generate nó thành html và đẩy qua. Hình như có thể set workspace vào trong `github/user/repo/_posts` được nhưng mà nãy giờ cứ xà quần nên quất luôn. Cơ mà khi sync cái stackedit workspace vào trong `repo/_posts` thì nó kẹp theo cái `.stackedit-trash`, thôi nghỉ. 😒


> Written with [StackEdit](https://stackedit.io/).