# Aplikasi Daftar Pengguna

Aplikasi frontend sederhana untuk menampilkan dan mencari daftar pengguna menggunakan Vue.js dan Tailwind CSS.

## Fitur

- 📋 Menampilkan daftar pengguna dari API
- 🔍 Pencarian pengguna berdasarkan nama
- 👤 Detail lengkap pengguna dalam modal
- 💅 UI yang responsif dan modern
- ⚡ Performa yang optimal

## Teknologi yang Digunakan

- Vue.js 3
- Tailwind CSS
- Vite
- JSONPlaceholder API

## Struktur Kode
src/
├── components/ # Komponen Vue
│ ├── UserList.vue # Komponen untuk menampilkan daftar pengguna
│ ├── UserDetail.vue # Komponen modal detail pengguna
│ └── UserSearch.vue # Komponen pencarian
├── App.vue # Komponen utama
├── main.js # Entry point aplikasi
└── style.css # File CSS global

## Instalasi

1. Pastikan Anda telah menginstal Node.js dan npm.
2. Clone repositori ini ke komputer Anda.
3. Setup Tailwind CSS

```bash
git clone <url-repository>
cd <nama-folder>
npm install
npm install -D tailwindcss postcss autoprefixer
npx tailwindcss init -p
```

## Menjalankan Aplikasi

1. Jalankan aplikasi dalam mode development

```bash
npm run dev
```

2. Buka browser dan akses URL yang ditampilkan (biasanya http://localhost:5173)

## Build untuk Production
Untuk membuild aplikasi untuk production:

```bash
npm run build
```


File hasil build akan tersedia di folder `dist/`

## Komponen Utama

### App.vue
- Komponen utama yang mengelola state aplikasi
- Mengambil data dari API
- Menangani pencarian dan pemilihan pengguna

### UserList.vue
- Menampilkan daftar pengguna dalam grid
- Responsif untuk berbagai ukuran layar
- Menampilkan informasi dasar pengguna (nama, email, alamat)

### UserDetail.vue
- Modal yang menampilkan detail lengkap pengguna
- Informasi yang ditampilkan:
  - Data pribadi
  - Alamat lengkap
  - Informasi perusahaan

### UserSearch.vue
- Input pencarian dengan desain yang clean
- Fitur real-time search
- Pencarian case-insensitive

## API

Aplikasi menggunakan JSONPlaceholder API untuk data pengguna:
- Endpoint: https://jsonplaceholder.typicode.com/users
- Method: GET
- Response: Array of user objects

## Styling

Aplikasi menggunakan Tailwind CSS untuk styling dengan:
- Desain responsif
- Tema yang konsisten
- Transisi dan animasi yang smooth
- Custom scrollbar
- Font smoothing

## Browser Support

Aplikasi mendukung browser modern termasuk:
- Chrome (versi terbaru)
- Firefox (versi terbaru)
- Safari (versi terbaru)
- Edge (versi terbaru)

## Pengembangan Selanjutnya

Beberapa fitur yang bisa ditambahkan:
- Sorting pengguna
- Filter berdasarkan kriteria lain
- Pagination
- Mode gelap
- Export data
