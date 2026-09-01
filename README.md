# ProjectPemweb-ARRay-
Web platform for reusing and exchanging second-hand items through a drop point system.
# [Nama Website] — Platform Reuse Barang Bekas

## Anggota Kelompok
- Akmal Anerol Husen
- Muhammad Rama Naradya
- Rangga Rasya Raditya

## Fungsi
Website ini berfungsi sebagai platform digital yang mempertemukan pemilik barang bekas layak pakai dengan orang yang membutuhkannya, dengan dua jalur utama: **tukar barang (barter)** sebagai prioritas, dan **ambil bebas dari drop point** sebagai fallback ketika tidak ada partner tukar yang cocok. Sebelum bisa mengambil barang (baik lewat tukar maupun bebas), pengguna wajib melewati gerbang edukasi berupa artikel dan kuis singkat sebagai bentuk pencegahan (prevention) timbulan sampah dari sisi kebiasaan pengguna.

## Tujuan
Proyek ini bertujuan untuk mendukung pencapaian **SDG 12: Ensure Sustainable Consumption and Production Patterns**, khususnya:

- **Target 12.5** — By 2030, substantially reduce waste generation through prevention, reduction, recycling and reuse. Website ini mendorong praktik *reuse* lewat dua jalur: barter langsung antar pengguna (memperpanjang usia pakai barang tanpa menambah peredaran barang di ruang publik) dan drop point terpusat sebagai jaring pengaman agar barang tidak berakhir menjadi sampah. Unsur **prevention** dalam target ini juga didukung lewat gerbang edukasi: sebelum mengklaim barang, pengguna wajib membaca materi dan menjawab kuis singkat terkait pengelolaan barang bekas, sehingga timbulan sampah dicegah bukan hanya lewat reuse barangnya, tapi juga lewat perubahan kebiasaan penggunanya.

## Target Pengguna
- Individu/rumah tangga yang memiliki barang bekas layak pakai namun tidak lagi digunakan
- Individu yang membutuhkan barang bekas namun memiliki keterbatasan biaya
- Komunitas atau organisasi lingkungan yang ingin mengelola drop point barang bekas
- (opsional) UMKM/toko yang ingin menyalurkan stok barang berlebih

## Alur Sistem

**Saat posting barang**, pengguna memilih salah satu:
1. **Tukar saja** — barang tetap di mode tukar tanpa batas waktu, murni menunggu ada pengguna lain yang cocok
2. **Tukar + fallback 30 hari** — dicarikan partner tukar dulu; jika lewat 30 hari belum ada yang cocok, barang otomatis berpindah ke pool bebas di drop point

**Saat mencari barang**, sistem selalu memprioritaskan menampilkan opsi tukar (barter) terlebih dahulu. Opsi barang di pool bebas tetap bisa diakses, namun ditampilkan setelah opsi tukar, supaya mode tukar tetap menjadi jalur utama dan tidak ditinggalkan pengguna.

**Sebelum klaim/ambil barang final** (baik dari hasil tukar maupun pool bebas), pengguna wajib membaca artikel edukasi dan menjawab 3 pertanyaan kuis terkait. Setelah lolos, kode klaim/alamat drop point baru terbuka.

```
Posting barang
   └─ pilih mode: tukar saja / tukar + fallback 30 hari
         │
         ├─ ada partner tukar cocok → tukar disetujui
         └─ (jika fallback) 30 hari tanpa partner → masuk pool bebas → diklaim user lain
                                                                              │
                                                    Edukasi + kuis (3 soal) ◄─┘
                                                              │
                                                  Ambil/antar di drop point
                                                              │
                                                          Selesai
```

## Mockup Kasar Sederhana
Alur halaman utama:

```
[Landing Page]
   ├─ Hero: penjelasan singkat + CTA "Mulai Sekarang"
   ├─ Highlight dampak (statistik jumlah barang terselamatkan)
   └─ Section edukasi singkat

[Halaman Login/Register]

[Halaman Beranda (setelah login)]
   ├─ Hasil pencarian: opsi tukar ditampilkan lebih dulu, opsi bebas di bawahnya
   └─ Tombol "Tambah Barang"

[Halaman Detail Barang]
   ├─ Foto, deskripsi, kondisi, mode (tukar/fallback), lokasi pickup
   └─ Tombol "Ajukan Tukar" / "Klaim Barang"

[Halaman Tambah Barang]
   └─ Form: nama barang, kategori, kondisi, foto, deskripsi, barang yang diinginkan (opsional), pilihan fallback 30 hari

[Halaman Edukasi + Kuis]
   ├─ Artikel singkat
   └─ 3 pertanyaan kuis → membuka kode klaim/alamat drop point

[Halaman Titik Donasi/Drop Point]
   └─ Peta/list lokasi fisik

[Halaman Profil]
   ├─ Barang yang diposting & statusnya
   ├─ Barang yang ditukar/diklaim
   └─ Statistik kontribusi personal
