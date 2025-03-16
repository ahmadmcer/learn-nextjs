# BAB 2: Merender Antarmuka Pengguna (UI)

Untuk memahami cara kerja React, pertama-tama kita membutuhkan pemahaman dasar tentang bagaimana browser menafsirkan kode anda untuk membuat (atau merender) antarmuka pengguna (UI).

Saat pengguna mengunjungi halaman web, server mengembalikan file HTML ke browser yang mungkin terlihat seperti ini:

![HTML and DOM](https://nextjs.org/_next/image?url=https%3A%2F%2Fh8DxKfmAPhn8O0p3.public.blob.vercel-storage.com%2Flearn%2Fdark%2Flearn-html-and-dom.png&w=3840&q=75)

Browser kemudian membaca HTML dan membangun Document Object Model (DOM).

## Apa itu DOM?

DOM adalah representasi objek dari elemen HTML. Ini bertindak sebagai jembatan antara kode anda dan antarmuka pengguna, dan memiliki struktur seperti pohon dengan hubungan induk dan anak.

![DOM and UI](https://nextjs.org/_next/image?url=https%3A%2F%2Fh8DxKfmAPhn8O0p3.public.blob.vercel-storage.com%2Flearn%2Fdark%2Flearn-dom-and-ui.png&w=3840&q=75)

Anda dapat menggunakan metode DOM dan JavaScript, untuk mendengarkan peristiwa pengguna dan [memanipulasi DOM](https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Scripting/DOM_scripting) dengan memilih, menambahkan, meperbarui, dan menghapus elemen tertentu di antarmuka pengguna. Manipulasi DOM memungkinkan anda untuk tidak hanya menargetkan elemen tertentu, tetapi juga mengubah gaya dan kontennya.

Di bagian berikutnya anda akan belajar cara menggunakan metode JavaScript dan DOM.
