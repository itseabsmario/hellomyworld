# A Little Surprise For You ♡

Halaman kejutan satu file (`surprise-website.html`): amplop yang dikunci password, surat di dalamnya, dan lagu latar. Tidak butuh build atau library tambahan.

## Fitur

- **Amplop interaktif** — klik amplop atau tombol "Buka suratnya" untuk membuka surat.
- **Password** — surat hanya terbuka kalau password benar (tidak peduli huruf besar/kecil).
- **Lagu latar** — memutar file audio lokal mulai dari detik tertentu dengan fade in, diulang terus.
- **Autoplay** — mencoba langsung memutar lagu saat halaman dibuka; kalau diblokir browser, lagu mulai di klik/sentuhan pertama.
- **Background bunga** — pola ember kecil berisi bunga (SVG di dalam CSS, tanpa gambar eksternal).
- **Tombol "More love!"** — hati beterbangan.
- **Responsif** — isi halaman berada di tengah layar HP.

## Struktur folder

```
surprise/
├── surprise-website.html   # seluruh halaman (HTML + CSS + JS)
├── backsound.mp3           # file lagu (siapkan sendiri, lihat di bawah)
└── README.md
```

## Cara menjalankan

Taruh folder di `W:\wamp\www\surprise\`, nyalakan WAMP, lalu buka:

```
http://localhost/surprise/surprise-website.html
```

Sebaiknya dibuka lewat `http://localhost`, bukan klik dua kali file-nya (`file:///`), supaya audio berjalan normal di semua browser.

## Pengaturan

Semua ada di bagian `<script>` pada `surprise-website.html`.

| Pengaturan | Fungsi |
| --- | --- |
| `PASSWORD` | Password untuk membuka amplop |
| `MUSIC_FILE` | Nama file lagu (default `backsound.mp3`) |
| `START_AT` | Detik awal lagu diputar (default `38`) |
| `FADE_MS` | Lama fade in dalam milidetik (default `3000`) |
| `MAX_VOL` | Volume maksimum, 0 sampai 1 (default `0.8`) |

Isi surat ada di bagian `<article class="letter">`. Teks judul, subjudul, dan tanda tangan bisa diubah langsung di HTML.

## Menyiapkan lagu

1. Siapkan file audio milikmu sendiri (mp3).
2. Taruh di folder yang sama dengan `surprise-website.html`.
3. Samakan namanya dengan `MUSIC_FILE`.

Kalau file tidak ditemukan, tombol musik menampilkan pesan bahwa file lagu tidak ada. Pastikan kamu punya hak untuk memakai lagu tersebut.

## Catatan

- **Autoplay:** Brave, Chrome, dan Safari memblokir audio otomatis sebelum pengunjung berinteraksi. Itu aturan browser, jadi di banyak perangkat lagu baru mulai setelah klik atau sentuhan pertama.
- **Keamanan password:** Password tertulis di kode halaman, jadi orang yang melihat source bisa menemukannya. Cukup untuk kejutan, tapi jangan dipakai untuk hal yang benar-benar rahasia, dan jangan pakai password yang kamu pakai di tempat lain.
