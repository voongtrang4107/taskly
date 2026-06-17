# Docs1 - Giải thích bài Task.ly

## 1. Một số thẻ HTML đã dùng

### `header`

Dùng cho phần đầu trang.

```html
<header class="header">
```

Trong `header` có logo, menu và nút `Get Started`.

### `nav`

Dùng cho menu điều hướng.

```html
<nav class="nav" aria-label="Menu chính">
```

`aria-label` giúp hỗ trợ accessibility cơ bản.

### `main`

Dùng để chứa nội dung chính.

```html
<main>
```

Trong `main` có hero, preview, about, features, plans và contact.

### `section`

Dùng để chia trang thành từng phần.

```html
<section class="hero" id="home">
```

Mỗi section là một khối nội dung riêng.

### `article`

Dùng cho card nhỏ.

```html
<article class="task-demo">
```

Trong bài, `article` dùng cho demo task và các feature card.

### `table`

Dùng để tạo bảng so sánh gói Free và Team.

```html
<table>
```

Trong bảng có:

- `caption`: tên bảng.
- `thead`: phần đầu bảng.
- `tbody`: phần nội dung.
- `th`: ô tiêu đề.
- `td`: ô dữ liệu.

### `form`

Dùng để tạo form đăng ký.

```html
<form action="#" method="post">
```

Form có:

- `label`
- `input`
- `select`
- `button`

Ví dụ:

```html
<label for="email">Email</label>
<input id="email" name="email" type="email" required>
```

`for` và `id` giống nhau để label liên kết đúng input.

## 2. Các CSS selector đã dùng

### Selector theo thẻ

```css
body {
  margin: 0;
}
```

Áp dụng cho thẻ `body`.

```css
h1 {
  font-size: 52px;
}
```

Áp dụng cho thẻ `h1`.

### Selector theo class

Class selector bắt đầu bằng dấu chấm.

```css
.hero {
  display: grid;
}
```

Một số class chính:

- `.header`: phần đầu trang.
- `.nav`: menu.
- `.hero`: phần mở đầu.
- `.task-demo`: card demo task.
- `.cards`: nhóm feature card.
- `.contact`: phần form.
- `.footer`: cuối trang.

### Selector lồng nhau

```css
.menu a:hover {
  color: #2563eb;
}
```

Nghĩa là khi hover vào thẻ `a` nằm trong `.menu`, chữ đổi màu xanh.

### Nhiều class trên một thẻ

Trong HTML có:

```html
<a class="btn btn-light">
```

Thẻ này có 2 class:

- `btn`: style chung của nút.
- `btn-light`: style riêng cho nút nền trắng.

### Pseudo-class `:focus`

```css
input:focus,
select:focus {
  outline: 2px solid #93c5fd;
}
```

Khi người dùng bấm vào input/select, viền sẽ rõ hơn.

### Pseudo-element `::after`

```css
.task-demo::after {
  content: "";
  position: absolute;
}
```

Dùng để tạo thanh xanh nhỏ ở góc card demo mà không cần thêm thẻ HTML.

## 3. Cách viết CSS responsive

Em viết giao diện desktop trước, sau đó dùng media query cho màn hình nhỏ.

### Desktop

Ở màn hình lớn, phần hero được căn giữa:

```css
.hero {
  max-width: 820px;
  margin: 0 auto;
  text-align: center;
}
```

Features chia 3 cột:

```css
.cards {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
}
```

Phần preview cũng dùng Grid để chia 2 cột: card task bên trái và dashboard tượng trưng bên phải.

```css
.preview {
  display: grid;
  grid-template-columns: 0.8fr 1.5fr;
}
```

### Tablet

Khi màn hình nhỏ hơn `800px`, các layout nhiều cột đổi thành 1 cột:

```css
@media (max-width: 800px) {
  .contact {
    grid-template-columns: 1fr;
  }

  .preview,
  .about {
    grid-template-columns: 1fr;
  }

  .cards {
    grid-template-columns: 1fr;
  }
}
```

Mục đích là để nội dung không bị chật.

### Mobile

Khi màn hình nhỏ hơn `480px`:

```css
@media (max-width: 480px) {
  .menu {
    display: none;
  }

  .actions {
    flex-direction: column;
  }
}
```

Trên mobile:

- Ẩn menu cho gọn.
- Hai nút trong hero xếp dọc.
- Trang chiếm hết chiều ngang.

## 4. Tóm tắt

Bài này có dùng:

- Semantic HTML: `header`, `nav`, `main`, `section`, `article`, `footer`.
- SEO cơ bản: `title`, `meta description`, `keywords`, `author`.
- Accessibility cơ bản: `aria-label`, `label` nối với `input`.
- Form: phần contact.
- Table: phần plans.
- CSS: box model, position, flexbox, grid, responsive, media query, animation.
