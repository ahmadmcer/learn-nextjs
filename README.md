# BAB 3: Memperbarui UI dengan JavaScript

Dalam bab ini, kita akan mulai membangun proyek kita dengan menggunakan metode JavaScript dan DOM untuk menambahkan tag `h1` ke proyek anda.

Buka editor kode anda dan buat file `index.html` baru. Di dalam file HTML, tambahkan kode berikut:

```html
<html>
  <body>
    <div></div>
  </body>
</html>
```

Kemudian berikan `id` yang unik pada `div` sehingga anda dapat menargetkannya nanti.

```html
<html>
  <body>
    <div id="app"></div>
  </body>
</html>
```

Untuk menulis JavaScript di dalam file HTML anda, tambahkan tag `script`:

```html
<html>
  <body>
    <div id="app"></div>
    <script type="text/javascript"></script>
  </body>
</html>
```

Sekarang, di dalam tag `script`, anda dapat menggunakan metode DOM, [`getElementById()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/getElementById), untuk memilih elemen `<div>` berdasarkan `id`:

```html
<html>
  <body>
    <div id="app"></div>
    <script type="text/javascript">
      const app = document.getElementById('app');
    </script>
  </body>
</html>
```

Anda dapat terus menggunakan metode DOM untuk membuat elemen `<div>` baru:

```html
<html>
  <body>
    <div id="app"></div>
    <script type="text/javascript">
      // Pilih elemen div dengan id 'app'
      const app = document.getElementById('app');
 
      // Buat elemen H1 baru
      const header = document.createElement('h1');
 
      // Buat node teks baru untuk elemen H1
      const text = 'Develop. Preview. Ship.';
      const headerContent = document.createTextNode(text);
 
      // Tambahkan teks ke elemen H1
      header.appendChild(headerContent);
 
      // Tempatkan elemen H1 di dalam div
      app.appendChild(header);
    </script>
  </body>
</html>
```

Untuk memastikan semuanya berfungsi, buka file HTML anda di dalam browser pilihan anda. Anda akan melihat tag `h1` yang bertuliskan, 'Develop. Preview. Ship.'.

---

## HTML vs DOM

Jika anda melihat elemen DOM di dalam [browser developer tools](https://developer.mozilla.org/en-US/docs/Learn_web_development/Howto/Tools_and_setup/What_are_browser_developer_tools), anda akan melihat DOM menyertakan elemen `<h1>`. DOM halaman berbeda dari source code - atau dengan kata lain, file HTML asli yang anda buat.

![DOM and Source](https://nextjs.org/_next/image?url=https%3A%2F%2Fh8DxKfmAPhn8O0p3.public.blob.vercel-storage.com%2Flearn%2Fdark%2Flearn-dom-and-source.png&w=3840&q=75)

Hal ini karena HTML mewakili **konten halaman awal**, sedangkan DOM mewakili **konten halaman yang diperbarui** yang diubah oleh kode JavaScript yang anda tulis.

Memperbarui DOM dengan JavaScript biasa sangat kuat tetapi bertele-tele. Anda telah menulis semua kode ini untuk menambahkan elemen `<h1>` dengan beberapa teks:

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

Seiring bertambahnya ukuran aplikasi atau tim, membangun aplikasi dengan cara ini bisa menjadi semakin menantang.

Dengan pendekatan ini, pengembang menghabiskan banyak waktu menulis instruksi untuk memberi tahu komputer **bagaimana** ia harus melakukan sesuatu. Tapi bukankah lebih baik untuk menjelaskan **apa** yang ingin anda tunjukkan dan membiarkan komputer mencari tau **bagaimana** cara memperbarui DOM?

---

## Pemrograman imperatif vs deklaratif

Kode di atas adalah contoh yang baik dari pemrograman **imperatif**. Anda sedang menulis langkah-langkah tentang **bagaimana** antarmuka pengguna harus diperbarui. Tetapi ketiak datang untuk membangun antarmuka pengguna, pendekatan deklaratif sering disukai karena dapat mempercepat proses pengembangan. Alih-alih harus menulis metode DOM, akan sangat membantu jika pengembang dapat mendeklarasikan **apa** yang ingin mereka tampilkan (dalam hal ini, tag `h1` dengan beberapa teks).

Dengan kata lain, **pemrograman imperatif** seperti memberikan instruksi langkah demi langkah kepada koki tentang cara membuat pizza. **Pemrograman deklaratif** seperti memesan pizza tanpa khawatir tentang langkah-langkah yang diperlukan untuk membuat pizza. 🍕

[React](https://react.dev/) adalah library deklaratif populer yang dapat anda gunakan untuk membangun antarmuka pengguna (build user interface).

---

## React: Library UI deklaratif

Sebagai pengembang, anda dapat memberi tahu React apa yang anda inginkan terjadi pada antarmuka pengguna, dan React akan mencari tahu langkah-langkah **bagaimana memperbarui** DOM atas nama anda.

Di bab berikutnya, kita akan mengeksplorasi bagaimana anda dapat memulai dengan React.
