# UTAITEREC

A place to find your new favorite Utaite.

---

## Deskripsi Website

UTAITEREC adalah website rekomendasi dan database Utaite (Japanese cover artists) yang membantu pengguna menemukan penyanyi Jepang berdasarkan tipe suara, genre, dan popularitas. Website ini dirancang untuk memudahkan penggemar musik Jepang mengeksplorasi dan menemukan Utaite baru yang sesuai dengan preferensi mereka.

---

## Target Pengguna

- Penggemar musik Jepang yang ingin menemukan Utaite baru
- Pengguna yang mencari rekomendasi berdasarkan karakteristik suara (High Voice, Deep Voice, Breathy, Powerful, Versatile, Unique)
- Fans yang ingin mengeksplorasi profil dan informasi tentang Utaite favorit mereka
- Pengguna yang mengakses website melalui desktop, tablet, maupun mobile

---

## Prinsip UI/UX yang Diterapkan

### Konsistensi Desain

Website menggunakan CSS Custom Properties untuk seluruh design token seperti warna, spacing, dan typography. Komponen-komponen UI dibuat reusable dengan naming convention BEM (Block Element Modifier) sehingga konsisten di seluruh halaman. Contoh komponen yang digunakan meliputi artist-card-sm, artist-card-md, artist-card-lg, tag-pill, dan social-icon.

### Navigasi yang Jelas

Navigasi utama menggunakan sticky navigation bar yang selalu terlihat saat scroll. Setiap menu memiliki active state indicator berupa underline animasi. Untuk mobile, tersedia hamburger menu yang menggunakan CSS-only checkbox hack sehingga tidak memerlukan JavaScript. Tersedia juga skip link untuk aksesibilitas keyboard yang memungkinkan pengguna langsung menuju konten utama tanpa harus melewati seluruh navigasi.

### Tata Letak yang Rapi

Layout halaman menggunakan CSS Grid untuk struktur besar dan Flexbox untuk alignment komponen. Sistem container dengan max-width memastikan konten tetap terbaca di layar besar. Setiap halaman memiliki section-based structure yang jelas dengan padding dan margin yang konsisten.

### Pemilihan Warna dan Tipografi

Paleta warna menggunakan gradasi biru-muda yang memberikan kesan profesional dan nyaman di mata. Warna utama (accent) adalah #2A6B87 dengan variasi light dan dark. Font stack menggunakan system fonts (Segoe UI, Tahoma, Geneva, Verdana, sans-serif) untuk loading yang cepat. Hierarki tipografi dibangun dari font-size-xs (0.75rem) hingga font-size-4xl (4rem) dengan weight yang bervariasi untuk membedakan heading, body, dan caption.

### Responsivitas

Website menggunakan mobile-first approach dengan dua breakpoint utama: 576px untuk mobile dan 768px untuk tablet. Layout grid menyesuaikan dari 1 kolom di mobile, 2 kolom di tablet, hingga 3 kolom di desktop. Font size menggunakan clamp() untuk fluid typography yang responsif tanpa media query tambahan. Mobile menu toggle menggunakan CSS checkbox hack sehingga berfungsi tanpa JavaScript.

### Aksesibilitas

Semantic HTML5 elements digunakan di seluruh halaman untuk struktur yang bermakna. Setiap ikon dan navigasi dilengkapi ARIA labels. Semua gambar memiliki alt text yang deskriptif. Focus-visible states diterapkan pada semua interactive elements. Tersedia dukungan untuk reduced motion preference dan high contrast mode.

---

## Fitur Website

Homepage menampilkan photo collage artist dengan efek polaroid dan musical staff navigation yang mengarahkan ke halaman recommendation berdasarkan kategori suara.

Recommendation Page menyajikan 6 kategori suara (High Voice, Deep Voice, Breathy, Powerful, Versatile, Unique) dengan artist cards yang berisi ranking, nama, deskripsi singkat, dan link ke detail page.

Database Page menyediakan daftar lengkap 22 artist dengan dua ranking list (Popular Now dan Underrated), search box, filter alfabet A-Z, dan daftar artist yang dikelompokkan berdasarkan huruf awal.

Detail Page menampilkan profil lengkap setiap artist termasuk foto, nama, genre tags, voice category tags, type tags, deskripsi lengkap, informasi grup dan proyek, ikon sosial media, dan rekomendasi artist serupa (similar artists).

---

## Teknologi

Frontend dibangun menggunakan HTML5 dan CSS3 tanpa framework JavaScript. Styling menggunakan CSS Custom Properties, CSS Grid, dan Flexbox. Animasi menggunakan CSS Keyframes dan Transitions. Mobile menu menggunakan CSS-only checkbox hack. Data artist disimpan dalam file JSON (artists_data.json). Templating HTML menggunakan Python Jinja2 untuk generate halaman dari data.

---

## Struktur Folder

    /
    |-- index.html              # Homepage
    |-- recommendation.html     # Voice category recommendations
    |-- database.html           # Artist database
    |-- css/
    |   -- style.css            # All styles
    |-- assets/
    |   -- artists/             # Artist portraits (22 images)
    |-- detail/
    |   -- 96neko.html
    |   -- ado.html
    |   -- akugetsu.html
    |   -- amatsuki.html
    |   -- araki.html
    |   -- chogakusei.html
    |   -- dongdang.html
    |   -- eve.html
    |   -- gero.html
    |   -- luz.html
    |   -- mafumafu.html
    |   -- meychan.html
    |   -- nqrse.html
    |   -- reol.html
    |   -- sakata.html
    |   -- senra.html
    |   -- shima.html
    |   -- soraru.html
    |   -- sou.html
    |   -- tuki.html
    |   -- urata.html
    |-- artists_data.json       # Data source
    |-- README.md

---

## Cara Menjalankan

Clone repository:

    git clone https://github.com/username/utaiterec.git
    cd utaiterec

Buka file index.html di browser, atau gunakan live server:

    npx live-server

---

## Deployment

Website dihosting menggunakan GitHub Pages. Pengaturan dilakukan melalui Settings -> Pages -> Source: Deploy from branch -> main -> root. URL hasil deployment: https://username.github.io/utaiterec/

---

## Data Sources

Data artist dikompilasi dari sumber publik meliputi YouTube subscriber counts, social media profiles, official websites, dan fan databases. Data mencakup 22 Utaite dengan informasi genre, tipe suara, popularitas score, dan similarity ranking.

---

## Lisensi

Data compiled from public sources for educational purposes. Website dibuat untuk tugas mata kuliah Desain Antarmuka Pengguna (UI/UX) Semester Genap 2025-2026.
