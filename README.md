# BAB 4: Memulai dengan React

Untuk menggunakan React dalam proyek yang baru dibuat, muat dua skrip React dari situs web eksternal bernama [unpkg.com](https://unpkg.com/):

- **react** adalah pustaka inti React.
- **react-dom** menyediakan metode khusus DOM yang memungkinkan anda untuk menggunakan React dengan DOM.

```html
<html>
  <body>
    <div id="app"></div>
    <script src="https://unpkg.com/react@18/umd/react.development.js"></script>
    <script src="https://unpkg.com/react-dom@18/umd/react-dom.development.js"></script>
    <script type="text/javascript">
      const app = document.getElementById('app');
      const header = document.createElement('h1');
      const text = 'Develop. Preview. Ship.';
      const headerContext = document.createTextNode(text);
      header.appendChild(headerContext);
      app.appendChild(header);
    </script>
  </body>
</html>
```

Alih-alih secara langsung memanipulasi DOM dengan JavaScript biasa, hapus metode DOM yang telah anda tambahkan sebelumnya, dan tambahkan [`ReactDOM.createRoot()`](https://react.dev/reference/react-dom/client/createRoot) untuk menargetkan elemen DOM tertentu dan membuat root untuk menampilkan Komponen React anda. Kemudian, tambahkan metode [`root.render()`](https://react.dev/reference/react-dom/client/hydrateRoot#root-render) untuk merender kode React anda ke DOM.

Ini akan memberi tahu React untuk merender judul `<h1>` kita di dalam elemen `#app` kita.

```html
<html>
  <body>
    <div id="app"></div>
    <script src="https://unpkg.com/react@18/umd/react.development.js"></script>
    <script src="https://unpkg.com/react-dom@18/umd/react-dom.development.js"></script>
    <script>
      const app = document.getElementById('app');
      const root = ReactDOM.createRoot(app);
      root.render(<h1>Develop. Preview. Ship.</h1>);
    </script>
  </body>
</html>
```

Jika anda mencoba menjalankan kode ini di browser, anda akan mendapatkan kesalahan sintaksis:

```batch
Uncaught SyntaxError: expected expression, got '<'
```

Ini karena `<h1>...</h1>` bukan Javascript yang valid. Bagian kode ini adalah **JSX**.

---

## Apa itu JSX?

JSX adalah ekstensi sintaks untuk JavaScript yang memungkinkan anda mendeskripsikan UI anda dalam sintaks seperti HTML yang sudah dikenal. Hal yang menyenangkan tentang JSX adalah selain mengikuti [tiga aturan JSX](https://react.dev/learn/writing-markup-with-jsx#the-rules-of-jsx), anda tidak perlu mempelajari simbol atau sintaks baru di luar HTML dan JavaScript.

Tetapi browser tidak memahami JSX secara tidak langsung, jadi anda memerlukan kompiler JavaScript, seperti [Babel](https://babeljs.io/), untuk mengubah kode JSX anda menjadi JavaScript biasa.

---

## Menambahkan Babel ke Proyek Anda

Untuk menambahkan Babel ke proyek anda, salin dan tempel skrip berikut di file `index.html` anda:

```html
<script src="https://unpkg.com/@babel/standalone/babel.min.js"></script>
```

Selain itu, anda perlu memberi tahu Babel kode apa yang akan diubah dengan mengubah jenis skript menjadi `type=text/jsx`.

```html
<html>
  <body>
    <div id="app"></div>
    <script src="https://unpkg.com/react@18/umd/react.development.js"></script>
    <script src="https://unpkg.com/react-dom@18/umd/react-dom.development.js"></script>
    <!-- Babel Script -->
    <script src="https://unpkg.com/@babel/standalone/babel.min.js"></script>
    <script type="text/jsx">
      const domNode = document.getElementById('app');
      const root = ReactDOM.createRoot(domNode);
      root.render(<h1>Develop. Preview. Ship.</h1>);
    </script>
  </body>
</html>
```

Untuk mengonfirmasi bahwa file tersebut berfungsi dengan benar, buka file HTML anda di browser.

Membandingkan kode React **deklaratif** yang baru saja anda tulis:

```jsx
<script type="text/jsx">
  const domNode = document.getElementById("app")
  const root = ReactDOM.createRoot(domNode);
  root.render(<h1>Develop. Preview. Ship.</h1>);
</script>
```

ke kode JavaScript **imperatif** yang anda tulis di bagian sebelumnya:

```html
<script type="text/javascript">
  const app = document.getElementById('app');
  const header = document.createElement('h1');
  const text = 'Develop. Preview. Ship.';
  const headerContent = document.createTextNode(text);
  header.appendChild(headerContent);
  app.appendChild(header);
</script>
```

Anda dapat mulai melihat bagaimana menggunakan React memungkinkan anda untuk mengurangi banyak kode berulang.

Dan inilah yang dilakukan React, ini adalah pustaka yang berisi cuplikan kode yang dapat digunakan kembali yang melakukan tugas atas nama anda - dalam hal ini, memperbarui UI.

---

## JavaScript Penting untuk React

Meskipun anda dapat mempelajari JavaScript dan React secara bersamaan, membiasakan diri dengan JavaScript dapat membuat proses belajar React lebih mudah.

Di bagian selanjutnya, anda akan diperkenalkan dengan beberapa konsep inti React dari perspektif JavaScript. Berikut ringkasan topik JavaScript yang akan disebutkan:

- [Functions](https://developer.mozilla.org/docs/Web/JavaScript/Guide/Functions) dan [Arrow Functions](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Functions/Arrow_functions)
- [Objects](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Object)
- [Arrays dan Array Methods](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Array)
- [Destructuring](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Operators/Destructuring_assignment)
- [Template Literals](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Template_literals)
- [Ternary Operators](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Operators/Conditional_Operator)
- [ES Modules dan Import / Export Syntax](https://developer.mozilla.org/docs/Web/JavaScript/Guide/Modules)

Meskipun kursus ini tidak menyelami JavaScript, praktik yang baik adalah tetap up to date dengan versi terbaru JavaScript. Tetapi jika anda belum merasa mahir dalam JavaScript, jangan biarkan ini menghalangi anda untuk mulai membangun dengan React!
