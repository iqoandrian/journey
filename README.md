# Journey

Catatan perjalanan gue belajar JavaScript dari nol sampai bisa deploy aplikasi sendiri, dengan fokus ke hal-hal yang paling berguna di era AI.

Tujuannya bukan nyalin kode, tapi paham sampai bisa nulis, baca, debug, dan jelasin sendiri.

Rencana lengkap ada di [ROADMAP.md](ROADMAP.md).

## Cara gue belajar

Setiap hari pakai loop **PRAJE**:

1. **Prediksi**: tulis dulu apa yang gue kira bakal keluar.
2. **Run**: jalanin, cocokin sama prediksi.
3. **Acak-acak**: sengaja rusakin kodenya dan catat hasilnya.
4. **Jelasin**: tulis ulang konsepnya pakai kata-kata sendiri di `notes.md`.
5. **Ketik ulang**: besoknya bikin lagi dari kosong tanpa lihat contoh.

Aturan pakai AI: AI boleh jadi tutor, reviewer, dan pembuat soal. Solusi baru diminta setelah gue coba sendiri. Kode dari AI selalu ditandai di komentar dan harus bisa gue jelasin per baris.

## Progress

| Fase | Topik | Status |
|------|-------|--------|
| 00 | [Setup](00-setup/) | ⬜ |
| 01 | [Basics](01-basics/) | ⬜ |
| 02 | [Functions](02-functions/) | ⬜ |
| 03 | [Data](03-data/) | ⬜ |
| 04 | [Debugging](04-debugging/) | ⬜ |
| 05 | [Async](05-async/) | ⬜ |
| 06 | [Tooling](06-tooling/) | ⬜ |
| 07 | [Browser](07-browser/) | ⬜ |
| 08 | [Server](08-server/) | ⬜ |
| 09 | [Capstone](09-capstone/) | ⬜ |

Legenda: ⬜ belum mulai · 🟨 sedang jalan · ✅ lulus Gate

## Struktur

```
journey/
├── README.md
├── ROADMAP.md
├── journal/         # catatan harian: 2026-11-28.md
├── 00-setup/
├── 01-basics/
│   ├── README.md    # yang dipelajari + Gate
│   ├── notes.md     # penjelasan versi gue
│   └── exercises/   # 1 file = 1 latihan
└── ...
```

## Menjalankan kode

Butuh [Node.js](https://nodejs.org/) (LTS). Dari root repo:

```bash
node 00-setup/hello.js
```

## Jurnal

Catatan harian ada di [`journal/`](journal/).