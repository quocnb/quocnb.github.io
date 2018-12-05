
Đôi khi bạn muốn tạo 1 trang web cá nhân cho riêng mình, để show một vài thứ hay ho, chia sẻ 1 vài điều thầm kín ... nhưng lại ngại vì không biết lập trình web, không có tiền mua tên miền, thuê server ... Thế nên ước mơ đành giang dở ...

Bỗng 1 ngày đẹp trời, bạn phát hiện ra trang `Github` mà bạn vẫn dùng mỗi ngày có thể giúp bạn biến ước mơ đơn giản đó thành hiện thực mà không tốn xu nào. Cùng khám phá thôi

## 1. [Github Pages](https://pages.github.com/)

`Github Pages` chính là công cụ giúp bạn thực hiện ước mơ. Nói đơn giản thì Github pages cho phép bạn tạo ra 1 website riêng với những thứ mà bạn vẫn sử dụng hàng ngày khi làm việc trên github.



![](/resources/2018-12-05-github-pages-logo.jpeg)

>Websites for you and your projects.
>
>Hosted directly from your GitHub repository. Just edit, push, and your changes are live.

## 2. Hello world, Github Pages

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

## NOTE

1. Việc đặt tên theo 1 cú pháp định sẵn (ở step 1) cũng đồng nghĩa với việc bạn chỉ có thể tạo 1 page duy nhất với mỗi account github. Tuy nhiên đó chỉ là page cá nhân, còn mỗi project, mỗi organization bạn có thể tạo ra các page tương ứng

2. Source code của page sẽ được quản lý tại `https://github.com/username/username.github.io`, cũng có nghĩa là nếu bạn để repo của bạn là public thì tất cả mọi người sẽ đọc được source code của bạn ^^

3. Page của bạn sẽ được (tự động) tạo với tên miền https://username.github.io
