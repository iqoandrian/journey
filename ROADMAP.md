# Roadmap JavaScript: Dari Nol sampai Deploy (Era AI)

Tujuan: paham JavaScript sampai bisa nulis, baca, debug, dan deploy sendiri. Bukan sekadar copy-paste hasil AI.

Estimasi: sekitar 12 minggu kalau 1-2 jam per hari. Anggap ini perkiraan kasar. Pindah fase kalau udah lulus checkpoint-nya, bukan karena kalender.

---

## Aturan Main (baca dulu, ini yang bikin lo beneran belajar)

### Loop belajar harian: PRAJE
1. **Prediksi**: sebelum run kode, tulis di komentar apa yang bakal keluar.
2. **Run**: jalanin, cocokin sama prediksi lo.
3. **Acak-acak**: sengaja rusakin kodenya. Ganti tipe data, hapus satu baris, bikin error. Catat apa yang terjadi.
4. **Jelasin**: tulis ulang konsepnya pakai kata-kata lo sendiri di `notes.md` folder fasenya.
5. **Ketik ulang dari kosong**: besoknya, bikin ulang tanpa lihat contoh.

### Aturan pakai AI
- Boleh: minta AI jadi tutor, jelasin error, bikin soal latihan, review kode lo.
- Jangan: minta AI nulis solusi sebelum lo coba sendiri minimal 20 menit.
- Kalau AI ngasih kode, lo wajib bisa jelasin tiap barisnya. Kalau nggak bisa, itu belum "milik lo".
- Prompt yang bagus buat belajar: "Jangan kasih jawabannya. Kasih hint aja." atau "Kuis gue 5 soal tentang closure."

### Aturan "Gate" per fase
Tiap fase punya checkpoint: hal yang harus bisa lo lakuin **tanpa AI dan tanpa contekan**. Belum bisa, ulangi fase itu.

---

## Struktur Repo GitHub

Repo: `journey`

```
journey/
├── README.md            # progress + link ke tiap fase
├── ROADMAP.md           # file ini
├── journal/             # 1 file per hari: 2026-11-28.md
├── 00-setup/
├── 01-basics/
├── 02-functions/
├── 03-data/
├── 04-debugging/
├── 05-async/
├── 06-tooling/
├── 07-browser/
├── 08-server/
└── 09-capstone/
```

Isi tiap folder fase (pola yang sama, jadi gampang diingat):

```
02-functions/
├── README.md        # apa yang dipelajari + Gate fase ini
├── notes.md         # penjelasan pakai kata-kata lo sendiri
└── exercises/
    ├── counter.js   # 1 file = 1 latihan, nama sesuai fungsinya
    └── debounce.js
```

Aturan rapi:
- Nama folder dan file: huruf kecil, pakai tanda `-`, tanpa spasi (`make-counter.js`, bukan `Latihan Final 2 (baru).js`).
- Nama file menjelaskan isinya. Dilarang `test.js`, `coba.js`, `final-final.js`.
- Satu latihan, satu file. Kalau salah, edit file itu dan commit. Git yang nyimpen versi lamanya, bukan folder `backup`.
- Kode yang berasal dari AI atau contekan: tandai di komentar paling atas (`// dibantu AI: bagian X`), lalu tulis ulang sendiri sampai nggak perlu lihat.
- Jangan commit `node_modules/` dan `.env`. Bikin `.gitignore` dari awal.

### Template jurnal harian (`journal/YYYY-MM-DD.md`)
```
## Hari ini gue pelajari
## Prediksi gue yang salah (dan kenapa)
## Yang gue rusakin sengaja & hasilnya
## Yang masih bingung
## Besok
```

Kebiasaan commit: satu commit per unit kerja, pesan jelas, misalnya `feat(02-functions): closure counter + notes`. Commit tiap hari biar kelihatan jejak belajarnya.

---

## Fase 0: Setup (2-3 hari)

**Belajar:** Node.js LTS, VS Code, Git, akun GitHub, terminal dasar (`cd`, `ls`, `mkdir`), jalanin `node file.js`.

**Kenapa penting di era AI:** hampir semua tool AI, SDK, dan API lo bakal jalan lewat terminal dan Node.

**Latihan:** bikin repo, clone, bikin `hello.js`, jalanin, commit, push.

**Gate:** lo bisa bikin file, jalanin pakai Node, commit, dan push tanpa lihat panduan.

---

## Fase 1: Dasar Bahasa (1.5 minggu)

**Belajar:**
- `const` vs `let` (dan kenapa `var` dihindari)
- Tipe data: string, number, boolean, `null`, `undefined`
- Operator, `==` vs `===`, type coercion (sumber bug klasik)
- Template literal
- `if/else`, `switch`, ternary
- Loop: `for`, `while`, `for...of`

**Latihan (tanpa copy-paste):**
- FizzBuzz
- Kalkulator tip + split bill
- Tebak angka (pakai `process.argv` atau `readline`)
- Prediksi hasil dari: `"5" + 3`, `"5" - 3`, `[] + {}`, `0.1 + 0.2`

**Gate:** jelasin kenapa `0.1 + 0.2 !== 0.3` dan kapan `==` bisa menipu lo.

---

## Fase 2: Fungsi & Scope (1.5 minggu)

**Belajar:**
- Function declaration vs arrow function
- Parameter, default value, return
- Scope, hoisting, **closure**
- Pure function vs side effect
- Callback (fungsi sebagai nilai)

**Kenapa penting di era AI:** kode hasil AI isinya fungsi kecil yang dirantai. Kalau lo nggak ngerti closure dan scope, lo nggak bisa review.

**Latihan:**
- Bikin `makeCounter()` pakai closure
- Bikin `debounce` sederhana
- Bikin mini util library: `capitalize`, `sum`, `unique`, `chunk`

**Gate:** gambar di kertas apa yang terjadi di memori pas closure kepanggil, tanpa bantuan.

---

## Fase 3: Data (2 minggu)

**Belajar:**
- Array dan method-nya: `map`, `filter`, `reduce`, `find`, `some`, `every`, `sort`
- Object, destructuring, spread/rest, optional chaining (`?.`), `??`
- `Map` dan `Set`
- **JSON**: `JSON.parse`, `JSON.stringify`
- Immutability: copy vs reference

**Kenapa penting di era AI:** API LLM berkomunikasi lewat JSON. Lo bakal sering ngolah array of objects, memotong data, dan merapikan respons.

**Latihan:**
- Ambil data dummy JSON (daftar transaksi), hitung total per kategori pakai `reduce`
- Bikin fungsi `groupBy` dari nol
- Tulis ulang satu loop `for` jadi `map/filter` dan sebaliknya

**Gate:** dari array of objects, lo bisa bikin laporan ringkas (total, rata-rata, top 3) tanpa bantuan.

---

## Fase 4: Debugging & Testing (1 minggu)

**Belajar:**
- Baca error message dan stack trace
- `console.log` yang efektif, `console.table`
- Debugger VS Code (breakpoint, step over/into, watch)
- `try/catch`, melempar error sendiri
- Testing pakai test runner bawaan Node (`node --test`)

**Kenapa penting di era AI:** AI bakal ngasih lo kode yang kelihatan benar tapi salah. Tes dan debugging adalah cara lo memverifikasi, bukan percaya buta.

**Latihan:**
- Ambil fungsi dari Fase 2 dan 3, tulis 5 tes buat tiap fungsi (termasuk edge case: input kosong, `null`, angka negatif)
- Minta AI bikin sebuah fungsi, lalu tulis tes yang membuktikan fungsi itu salah di satu kasus

**Gate:** lo bisa nemuin bug dengan breakpoint, bukan nebak-nebak.

---

## Fase 5: Asynchronous (2 minggu)

**Belajar:**
- Event loop: kenapa `setTimeout(..., 0)` nggak langsung jalan
- Callback, **Promise**, `async/await`
- `Promise.all`, `Promise.allSettled`
- `fetch` dan HTTP dasar (method, status code, header, body)
- Error handling di kode async

**Kenapa penting di era AI:** setiap panggilan ke LLM atau API itu async. Ini fase paling krusial buat membangun apa pun yang pakai AI.

**Latihan:**
- Script yang fetch API publik (cuaca, kurs, dsb), tampilkan hasil rapi
- Jalankan 3 request paralel pakai `Promise.all`, bandingkan waktunya dengan berurutan
- Tambahin retry sederhana kalau request gagal
- Prediksi urutan output dari kode campuran `console.log`, `setTimeout`, dan Promise

**Gate:** jelasin urutan eksekusi dari potongan kode async campuran, tanpa run.

---

## Fase 6: Module & Tooling (1 minggu)

**Belajar:**
- ES Modules (`import`/`export`)
- npm, `package.json`, `node_modules`, semver
- Environment variable dan `.env` (jangan pernah commit API key)
- `.gitignore`
- ESLint dan Prettier

**Latihan:**
- Pecah util library lo jadi beberapa modul
- Pasang satu package dari npm, baca dokumentasinya, pakai
- Bikin script yang baca API key dari `.env`

**Gate:** lo paham kenapa `.env` harus masuk `.gitignore`, dan bisa ngecek repo lo nggak membocorkan secret.

---

## Fase 7: Browser & DOM (2 minggu)

**Belajar:**
- HTML dan CSS secukupnya
- DOM: `querySelector`, bikin dan ubah elemen
- Event: `click`, `input`, `submit`, event delegation
- `localStorage`
- `fetch` dari browser, CORS (kenapa kadang diblok)

**Latihan:**
- Todo list dengan simpan ke `localStorage`
- Aplikasi quiz kecil
- Halaman yang ambil data dari API dan render hasilnya

**Gate:** bikin satu aplikasi web kecil dari file kosong, tanpa framework.

---

## Fase 8: Server dengan Node (1.5 minggu)

**Belajar:**
- HTTP server dasar, lalu Express (atau Hono)
- Routing, middleware, kirim dan terima JSON
- Validasi input
- **Kenapa API key LLM nggak boleh ada di frontend**, dan cara pakai server sebagai perantara (proxy)

**Latihan:**
- REST API kecil (CRUD catatan)
- Endpoint yang manggil API eksternal dan mengembalikan hasilnya

**Gate:** jelasin alur request dari browser sampai server dan balik, termasuk di mana secret disimpan.

---

## Fase 9: Deploy + Capstone (2 minggu)

**Belajar:**
- Deploy frontend statis (GitHub Pages, Netlify, atau Cloudflare Pages)
- Deploy backend Node (Render, Railway, Fly.io, dsb)
- Environment variable di platform hosting
- Dasar GitHub Actions (jalankan tes tiap push)
- Baca log produksi

**Capstone:** bikin aplikasi yang bermanfaat buat lo sendiri dan memakai AI sebagai fitur, misalnya peringkas teks, asisten catatan, atau pengkategori pengeluaran. Syaratnya:
- Frontend (Fase 7) + backend (Fase 8)
- API key aman di server
- Ada tes
- Ada README yang jelas
- Ter-deploy dengan URL publik

**Gate:** orang lain bisa buka link-nya dan pakai.

---

## Setelah Ini (opsional)

- **TypeScript**: bikin kode AI lebih aman dan gampang direview
- Framework (React, dll): baru masuk setelah dasar bener-bener kuat
- Pelajari cara kerja SDK LLM, streaming respons, tool calling

---

## Checklist Progress

- [ ] Fase 0: Setup
- [ ] Fase 1: Dasar bahasa
- [ ] Fase 2: Fungsi & scope
- [ ] Fase 3: Data
- [ ] Fase 4: Debugging & testing
- [ ] Fase 5: Async
- [ ] Fase 6: Module & tooling
- [ ] Fase 7: Browser & DOM
- [ ] Fase 8: Server
- [ ] Fase 9: Deploy + capstone
