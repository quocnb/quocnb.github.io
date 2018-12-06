---
title:  "Tạo website cá nhân đơn giản với Github Pages"
---

Đôi khi bạn muốn tạo 1 trang web cá nhân cho riêng mình, để show một vài thứ hay ho, chia sẻ 1 vài điều thầm kín ... nhưng lại ngại vì không biết lập trình web, không có tiền mua tên miền, thuê server ... Thế nên ước mơ đành giang dở ...

Bỗng 1 ngày đẹp trời, bạn phát hiện ra trang `Github` mà bạn vẫn dùng mỗi ngày có thể giúp bạn biến ước mơ đơn giản đó thành hiện thực mà không tốn xu nào. Cùng khám phá thôi

# 1. [Github Pages](https://pages.github.com/)

`Github Pages` chính là công cụ giúp bạn thực hiện ước mơ. Nói đơn giản thì Github pages cho phép bạn tạo ra 1 website riêng với những thứ mà bạn vẫn sử dụng hàng ngày khi làm việc trên github.



![](/resources/2018-12-05-github-pages-logo.jpeg)

>Websites for you and your projects.
>
>Hosted directly from your GitHub repository. Just edit, push, and your changes are live.

# 2. Hello world, Github Pages

Thật bất ngờ là những việc bạn cần làm để tạo 1 trang Github Pages cũng chính là việc mà bạn vẫn làm mỗi khi bạn muốn tạo 1 project trên Github

**Step 1: [Tạo repository](https://github.com/new)**

![](/resources/2018-12-05-create-repo.png)

Có 1 điểm khác biệt duy nhất và cũng là điểm quan trọng nhất, chính là tên repository của bạn. Để tạo 1 `Github Pages` tên repo của bạn bắt buộc phải được đặt theo cú pháp

```
username.github.io
```

với `username` chính là username github của bạn.

**Step 2: Clone repository**

Việc này chắc ai làm việc với `git` cũng đã thông thạo

```
git clone https://github.com/username/username.github.io
```

với `username` chính là username github của bạn.

**Step 3: Tạo màn hình chính cho website**

Tất cả những gì bạn cần làm là tạo 1 file `index.html` hoặc `index.md`, `Github Pages` sẽ tự động load trang này lên làm trang chủ cho page của bạn.

Việc lựa chọn file html hay markdown (.md) tùy thuộc vào sở thích của bạn.

![](/resources/2018-12-05-page-hello-world.png)

**NOTE**

1. Việc đặt tên theo 1 cú pháp định sẵn (ở step 1) cũng đồng nghĩa với việc bạn chỉ có thể tạo 1 page duy nhất với mỗi account github. Tuy nhiên đó chỉ là page cá nhân, còn mỗi project, mỗi organization bạn có thể tạo ra các page tương ứng

2. Source code của page sẽ được quản lý tại `https://github.com/username/username.github.io`, cũng có nghĩa là nếu bạn để repo của bạn là public thì tất cả mọi người sẽ đọc được source code của bạn ^^

3. Page của bạn sẽ được (tự động) tạo với tên miền https://username.github.io

# 3. Jekyll

Bạn đã có thể tạo ra 1 website cá nhân một cách vô cùng đơn giản. Tuy vậy, chỉ có 1 vấn đề là chính cái page đó lại đơn giản đến mức nhàm chán.

![](/resources/2018-12-06-jekyll.png)

Nếu bạn để ý, thì ngay phía dưới phần giới thiệu của `Github Pages` đã có giới thiệu cho chúng ta giải pháp cho vấn đề này. Đó chính là

>Jekyll is a blog-aware static site generator in Ruby https://jekyllrb.com

![](/resources/2018-12-06-jekyll-logo.png)

Nếu bạn để ý thì trong phần Setting ở repo github pages của bạn, Github cũng đã support việc này một cách vô cùng tận tình. Những gì bạn cần làm chỉ là click chọn 1 trong các theme mặc định của jekyll mà mình  thích. Việc còn lại cứ để Github lo.
<p float="left">
  <img src="/resources/2018-12-06-github-pages-setting-theme.png" width="45%" hspace="10"/>
  <img src="/resources/2018-12-06-github-pages-choose-theme.png" width="45%" hspace="10"/>
</p>

Nếu những theme mặc định vẫn chưa thể thỏa mãn nhu cầu của bạn, hãy thử custom một thứ gì đó hay hơn xem.

# 4. Minimal Mistake

[https://github.com/mmistakes/minimal-mistakes](https://github.com/mmistakes/minimal-mistakes)

> 📐 A flexible two-column Jekyll theme perfect for building personal sites, blogs, and portfolios.

`Minimal Mistakes` cho phép bạn custom giao diện page của bạn một cách dễ dàng nhất. Bạn sẽ không cần phải code, cũng không cần phải học HTML, CSS ..., những gì bạn cần làm chỉ đơn giản là thêm vào vài dòng config

## 4.1. Cài đặt

Có tới tận 3 cách cài đặt Mininal Mistakes
- Gem-based method
- Remote theme method
- forking/directly copying theme file

Riêng cá nhân mình lựa chọn cách số 2 khi push lên github, và cách số 1 để test trên máy local. Lý do đơn giản là vì khi sử dụng cách số 1, github không nhận custom theme =))

**Step 1:**

Add `github-pages` vào `Gemfile`

```
source "https://rubygems.org"

gem "github-pages", group: :jekyll_plugins
```

**Step 2:**

Thêm `jekyll-include-cache` vào `plugins` trong file `_config.yml`.

```
plugins:
  - jekyll-include-cache
```

**Step 3:**

Fetch, update bundled gems với [Bundler](https://bundler.io/)
```
bundle
```
**Step 4:**

Add remote theme vào `_config.yml`.

```
remote_theme: "mmistakes/minimal-mistakes@4.14.1"
```

Chú ý xóa (hoặc comment) các `theme:` hoặc `remote_theme:` khác.

Đến đây, bạn đã có thể `commit` + `push` code lên github và tận hưởng thành quả. Tuy vậy, để có 1 page thực sự vừa ý, bạn cần nhiều hơn thế.

## 4.2. Config theme

Có rất nhiều thứ bạn có thể thay đổi để custom page của bạn, mình chỉ nêu ra 1 số config cơ bản, phần còn lại hãy tự mình khám phá và sáng tạo nhé. Tất cả tài liệu bạn cần đều có ở đây.

[https://mmistakes.github.io/minimal-mistakes/docs/quick-start-guide/](https://mmistakes.github.io/minimal-mistakes/docs/quick-start-guide/)

*Page này cũng được tạo trên Github page và được custom bằng chính Mininal Mistake này luôn nhé =))*

>TIP: Một cách config đơn giản nhất chính là copy file [`_config.yml` từ chính repo của `Minimal Mistake`](https://github.com/mmistakes/minimal-mistakes/blob/master/_config.yml)

# 5. Kết

`Github Pages`, `Jekyll+Minimal Mistake` đã cung cấp cho bạn tất cả những gì thiết yếu nhất để tạo nên 1 page cá nhân của riêng bạn. Hãy sáng tạo nó theo cách riêng của  bạn nhé.

P/s:

>Demo : Chính trang này =))
>
>Source code: Cũng chính repo của trang này luôn =))
