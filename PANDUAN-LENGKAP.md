# Panduan Lengkap Bubu's Little World (untuk pemula)

Kamu tidak perlu bisa coding. Kamu hanya perlu **mengunduh, mengunggah, dan menekan tombol**.

**Kata-kata yang akan muncul:**
- **GitHub** = tempat menyimpan file proyek di internet (seperti Google Drive untuk programmer).
- **Repository** (disingkat *repo*) = satu "folder" di GitHub untuk satu proyek.
- **Commit** = tombol "Simpan" di GitHub.
- **Vercel** = layanan yang mengubah file di GitHub menjadi website yang bisa dibuka siapa saja.
- **Deploy** = proses Vercel membuat websitenya.

> Tampilan GitHub dan Vercel kadang berubah sedikit. Kalau nama tombol agak berbeda, cari tombol yang artinya sama.

---

## Langkah 1: Mengunduh proyek
1. Unduh file **`bubus-little-world.zip`** dari Claude.
2. **Windows:** klik kanan file ZIP → **Extract All…** → **Extract**. **Mac:** klik 2 kali file ZIP. **HP:** sebaiknya pakai laptop/komputer untuk langkah 1-3.
3. Buka folder **`bubus-little-world`** hasil ekstrak. Di dalamnya harus ada:
   - folder `public`
   - file `build.js`, `package.json`, `vercel.json`
   - file `README.md`, `PANDUAN-LENGKAP.md`, `DAFTAR-SUARA.md`, `.gitignore`
4. Buka folder `public`. Harus ada: `index.html`, `style.css`, `minigames.js`, `platformer.js`, `favicon.svg`, dan folder `sounds`.
5. **Mau mencoba dulu di komputer?** Buka folder `public`, klik 2 kali `index.html`, pakai **Google Chrome**.

⚠️ Kalau ada file yang tidak terlihat (misalnya `.gitignore`), tidak apa-apa. File itu tidak wajib untuk game.

---

## Langkah 2: Mengunggah ke GitHub
1. Buka **github.com** → **Sign up** (buat akun gratis) atau **Sign in**.
2. Klik tanda **+** di kanan atas → **New repository**.
3. Isi **Repository name**: `bubus-little-world` (huruf kecil, tanpa spasi).
4. Pilih **Public**. Jangan centang apa pun lainnya. Klik **Create repository**.
5. Di halaman berikutnya, klik tulisan **uploading an existing file**.
6. Buka folder `bubus-little-world` di komputermu. Tekan **Ctrl+A** (Mac: **Cmd+A**) untuk memilih **semua isinya** (bukan folder luarnya), lalu **drag** ke kotak di halaman GitHub.
   - ⚠️ Yang di-drag adalah *isi* folder: `public`, `build.js`, `package.json`, `vercel.json`, dan seterusnya. `package.json` harus langsung terlihat di halaman depan repo nanti.
   - Gunakan **Chrome** atau **Edge**. Safari kadang gagal mengunggah folder.
7. Tunggu sampai semua file muncul di daftar. Di bagian bawah, klik tombol hijau **Commit changes** (artinya "simpan").
8. **Cek berhasil:** halaman depan repo harus menampilkan folder `public` dan file `package.json`, `vercel.json`, `build.js`. Klik `public` untuk memastikan ada `index.html`.

**Kalau gagal / ada file yang tidak ikut:** GitHub membatasi unggahan lewat website (maksimal 100 file sekali unggah, 25 MB per file). Proyek ini jauh di bawah batas itu. Kalau folder `public` tidak ikut, unggah dua kali: pertama file-file di luar, lalu klik **Add file → Upload files** lagi dan drag folder `public`. Alternatif termudah: aplikasi **GitHub Desktop** (desktop.github.com). Ia punya tombol **Add** dan **Publish repository**, tanpa perintah coding.

---

## Langkah 3: Deploy ke Vercel
1. Buka **vercel.com** → **Sign Up** → **Continue with GitHub** → izinkan (**Authorize**).
2. Klik **Add New…** → **Project**.
3. Cari repo `bubus-little-world` → klik **Import**. (Kalau belum muncul, klik **Adjust GitHub App Permissions** lalu izinkan repo itu.)
4. Periksa pengaturan. **Jangan diubah**, cukup cek:
   - **Framework Preset:** `Other`
   - **Build Command:** `npm run build`
   - **Output Directory:** `dist`
   - **Install Command:** biarkan kosong/bawaan
   - Tidak ada **Environment Variables** yang perlu diisi.
   (Pengaturan ini sudah otomatis terisi dari file `vercel.json`.)
5. Klik **Deploy**. Tunggu 30-60 detik.
6. Saat muncul **Congratulations!**, klik gambar websitenya atau tombol **Visit**. Alamatnya seperti `bubus-little-world.vercel.app`. **Itu link game-mu.** Bagikan ke HP atau tablet anak.

⚠️ Kalau Vercel meminta nama project, pakai huruf kecil tanpa spasi.

---

## Langkah 4: Memperbarui game
1. Buka repo di GitHub. Untuk **mengganti satu file**: klik folder `public` → **Add file → Upload files** → drag file barunya (nama harus **sama persis**) → **Commit changes**. File lama otomatis tertimpa.
2. Untuk **menambah suara MP3**: buka `public` → klik `sounds` → **Add file → Upload files** → drag MP3 → **Commit changes**. Nama file lihat `DAFTAR-SUARA.md`.
3. Untuk **mengubah tulisan kecil**: klik file (misalnya `platformer.js`) → ikon pensil ✏️ → ubah teks di antara tanda petik → **Commit changes**.
4. Vercel **otomatis** memperbarui website 1 menit setelah commit. Cek di vercel.com → project Anda → **Deployments**: tulisan **Ready** berarti selesai.

**Hindari kesalahan:**
- ⚠️ Jangan ganti nama file, dan jangan taruh file di folder yang salah. `index.html` harus tetap di dalam `public`.
- ⚠️ Jangan hapus `build.js`, `package.json`, `vercel.json`.
- ⚠️ Setelah update, buka website dengan **refresh keras** (Windows: Ctrl+Shift+R, Mac: Cmd+Shift+R; HP: tutup tab lalu buka lagi).
- Simpan cadangan: file ZIP asli jangan dihapus.

---

## Langkah 5: Mengatasi masalah
| Masalah | Solusi |
|---|---|
| **Halaman kosong** | Buka repo di GitHub: pastikan `public/index.html` ada. Lalu di Vercel buka **Deployments** → klik deployment terbaru → baca tulisan merah. Pastikan **Output Directory** = `dist`. |
| **Deployment gagal (Failed)** | Klik deployment-nya dan baca pesan error. Jika tertulis `FILE HILANG: public/...`, unggah lagi file yang disebut ke folder `public`. Jika `package.json` tidak ditemukan, berarti kamu mengunggah folder luarnya: pindahkan isinya ke depan repo. |
| **Gambar atau animasi tidak muncul** | Refresh keras. Pastikan `style.css` dan `platformer.js` ada di `public`. Gambar game digambar oleh kode, jadi tidak ada file gambar terpisah. |
| **Tombol tidak berfungsi** | Pastikan 4 file ada di `public` (`index.html`, `style.css`, `minigames.js`, `platformer.js`). Putar HP ke samping. Pakai Chrome. |
| **Audio tidak terdengar** | Pastikan HP tidak mode senyap dan tombol 🔊 di game hidup. Suara bergantung suara bawaan perangkat; paling stabil memakai MP3 (lihat `DAFTAR-SUARA.md`). Di iPhone, tambahkan suara Bahasa Indonesia di Pengaturan → Aksesibilitas → Konten Lisan. |
| **Tidak jalan di HP** | Buka lewat **Chrome** atau **Safari**, bukan lewat browser di dalam WhatsApp/Instagram. Putar layar ke samping. |
| **Perubahan di GitHub belum muncul** | Tunggu 1-2 menit. Cek **Deployments** di Vercel sampai **Ready**. Lalu refresh keras. Pastikan kamu menekan **Commit changes** di GitHub. |

Kalau masih bingung, foto atau salin pesan errornya dan kirim ke Claude.
