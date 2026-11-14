# MODUL-THESIS

Modul bimbingan mandiri untuk tesis **Analisis dan Peningkatan Hosting Capacity
Jaringan Distribusi 20 kV terhadap Penetrasi Simultan EV Charging dan PLTS Atap**.

Edward Paulus Saputra Panjaitan — Program Magister Teknik Elektro,
Institut Teknologi Sepuluh Nopember.

> **Versi anonim.** Nama gardu diganti kode G01–G13 dan penyulangnya disebut
> "Penyulang A", mengikuti versi makalah. Repositori ini tidak memuat nama
> gardu, nama gardu induk, maupun nama unit pelaksana yang sebenarnya.

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
| Hasil | Angka akhir dan urutan efektivitas strategi |
| Hitung tangan | Penetapan hosting capacity dengan kalkulator, tiga iterasi |
| Latihan soal | Soal acak sepuluh persamaan; angkanya berganti setiap jawaban benar |

Setiap persamaan disajikan dengan pola tetap: **cara membaca**, **fungsinya**,
**contoh matematis** dengan angka nyata, dan **sumbernya**.

## Kunci akses

Halaman terkunci frasa sandi. Isinya tidak tersimpan apa adanya di berkas —
yang ada hanya sandi-teks AES-256-GCM, dengan kunci diturunkan memakai PBKDF2
SHA-256 310.000 putaran. Tanpa frasa sandi yang benar, `index.html` hanya
berisi deretan karakter acak.

Frasa sandinya tidak ditulis di repositori ini.

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

Model OpenDSS dan berkas keluarannya tidak disertakan di repositori ini.

## Metode singkat

Quasi-static time series 48 interval 30 menit pada tiga hari tipikal. Hosting
capacity ditetapkan sebagai penetrasi maksimum yang memenuhi empat indikator
kinerja pada seluruh interval: batas tegangan, pembebanan penghantar,
pembebanan transformator, dan tidak ada aliran daya balik di gardu induk.
Verifikasi silang tiga lapis antara PowerFactory dan OpenDSS.
