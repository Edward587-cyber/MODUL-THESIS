# MODUL-THESIS

Modul bimbingan mandiri untuk tesis **Analisis dan Peningkatan Hosting Capacity
Jaringan Distribusi 20 kV terhadap Penetrasi Simultan EV Charging dan PLTS Atap**.

Edward Paulus Saputra Panjaitan — Program Magister Teknik Elektro,
Institut Teknologi Sepuluh Nopember.

> **Isi terenkripsi.** Modul ini memuat nama gardu, nama penyulang, dan angka
> hasil yang sebenarnya. Seluruhnya berada di dalam sandi-teks AES-256-GCM,
> sehingga `index.html` yang terbaca publik di GitHub tidak memuat satu pun
> nama tersebut dalam bentuk terbaca. Tanpa frasa sandi, berkas ini hanya
> deretan karakter acak.

## Isi

`index.html` — panel satu berkas, tanpa pustaka luar. Bilah menu di kiri, satu
panel isi di kanan. Tab pertama adalah bagan alir metodologi.

| Bagian | Isi |
|---|---|
| Bagan alir | Dua bagan metodologi lengkap dengan enam titik keputusan |
| Peta | Pertanyaan penelitian, tiga tujuan, rantai pengolahan data |
| Tahap 1 | Dari register meter ke profil beban — Pers. (3.1) – (3.5) |
| Tahap 2 | Model jaringan dan aliran daya — Pers. (2.3) – (2.16) |
| Tahap 2b | Newton-Raphson dikerjakan tangan, parameter saluran asli, dicocokkan dengan model penuh |
| Tahap 3 | Validasi terhadap kenyataan — Pers. (3.6) – (3.10) |
| Tahap 4 | Model beban kendaraan listrik — Pers. (3.11) – (3.15) |
| Tahap 5 | Model PLTS atap — Pers. (3.16) – (3.18) |
| Tahap 6 | Penetapan hosting capacity — Pers. (2.28) – (2.30), (3.19) |
| Tahap 7 | Partial smart charging — Pers. (3.20) – (3.23) |
| Tahap 8 | Realokasi adopsi per gardu — Pers. (3.26) – (3.29) |
| Hasil | **Angka akhir lengkap**: 9 uji, 18 tabel, 8 grafik, penanda poin penting, dan penelusuran tiap angka ke lembar Excel serta berkas CSV sumbernya |
| Kamus persamaan | Seluruh 61 persamaan naskah — Pers. (2.1) – (2.31), (3.1) – (3.29), (4.1) — dengan fungsi, arti notasi, dan sumber |
| Modul Python · DIgSILENT | `cereme_hc.py` dibedah delapan lapis: konfigurasi, data, jembatan API, mesin run, penilai, sapuan, 24 fase, pengaman |
| OpenDSS | Sembilan berkas masukan `.dss` baris demi baris, dan `studi_CEREME.py` dengan delapan fasenya |
| Hitung tangan | Penetapan hosting capacity dengan kalkulator, tiga iterasi |
| Latihan soal | Soal acak sepuluh persamaan; angkanya berganti setiap jawaban benar |

Setiap persamaan disajikan dengan pola tetap: **cara membaca**, **fungsinya**,
**contoh matematis** dengan angka nyata, dan **sumbernya**.

## Kunci akses

Halaman terkunci frasa sandi. Isinya tidak tersimpan apa adanya di berkas —
yang ada hanya sandi-teks AES-256-GCM, dengan kunci diturunkan memakai PBKDF2
SHA-256 310.000 putaran. Tanpa frasa sandi yang benar, `index.html` hanya
berisi deretan karakter acak.

Frasa sandinya tidak ditulis di repositori ini. Karena isinya memuat nama dan
angka yang sebenarnya, kekuatan frasa sandi itulah satu-satunya yang melindungi
— bukan sifat repositori yang publik atau privat.

Setelah terbuka, panel tetap terbuka selama tab peramban belum ditutup.
Tombol **Keluar dari panel** di kaki bilah menu menghapus sesi itu dan
mengembalikan halaman ke layar kunci.

## Cara membuka

Aktifkan GitHub Pages di Settings → Pages, sumber `main` / root. Halaman akan
terbit di `https://edward587-cyber.github.io/MODUL-THESIS/`.

Atau unduh `index.html` dan buka dengan peramban mana pun — tidak perlu server.

## Asal angka

- Naskah tesis Bab 1 – 4, untuk hasil DIgSILENT PowerFactory.
- Penjalanan skrip sapuan OpenDSS pada 13 November 2026, untuk hasil pembanding.
- Tab **Hasil** mengambil angkanya langsung dari berkas keluaran simulasi
  (`hasil_*.csv`, `validasi_*.csv`) dan dari 17 tabel olahan `buat_grafik.py`.
  Grafiknya digambar ulang sebagai SVG dari berkas yang sama, bukan disalin
  sebagai gambar, sehingga tetap tajam pada ukuran berapa pun.

Model OpenDSS dan berkas keluarannya tidak disertakan di repositori ini.

## Metode singkat

Quasi-static time series 48 interval 30 menit pada tiga hari tipikal. Hosting
capacity ditetapkan sebagai penetrasi maksimum yang memenuhi empat indikator
kinerja pada seluruh interval: batas tegangan, pembebanan penghantar,
pembebanan transformator, dan tidak ada aliran daya balik di gardu induk.
Verifikasi silang tiga lapis antara PowerFactory dan OpenDSS.
