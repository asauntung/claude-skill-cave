# cave — mode caveman untuk Claude

Skill yang memaksa Claude menjawab dalam gaya caveman: padat dan tanpa basa-basi. Tujuannya menghemat token supaya limit percakapan tidak cepat habis.

> **English:** A Claude Agent Skill that forces Claude to answer in caveman style: dense, no small talk. The point is to spend fewer tokens so your conversation limit lasts longer. Works in claude.ai, Claude Desktop, and Claude Code.

## Kenapa dipakai

Sebagian besar token output habis untuk hal yang tidak Anda butuhkan: banyak pengantar, sering mengulang pertanyaan, kalimat penutup yang menawarkan bantuan lanjutan, dan jargon-jargon. Skill ini memangkas semuanya, namun dan menyisakan isi.

Contoh perbedaannya:

**Tanpa cave**

> Pertanyaan bagus! Ada beberapa cara untuk mengatasi masalah ini. Salah satu pendekatan yang umum digunakan adalah dengan menambahkan indeks pada kolom tersebut, karena hal ini secara umum dapat mempercepat proses query secara signifikan. Namun perlu diingat bahwa ini juga punya trade-off...

**Dengan cave**

> Query lambat karena full table scan. Tambah indeks di kolom `user_id`. Trade-off: insert jadi sedikit lebih lambat.

## Yang tetap

Kompresi hanya menyentuh gaya bahasa saja tanpa menyentuh isi. Sementara fakta, angka, kode, dan teks error tetap ditulis persis. Skill juga otomatis keluar dari gaya caveman untuk peringatan keselamatan, tindakan yang tidak bisa dibatalkan, dan langkah yang bisa salah kalau dijelaskan setengah-setengah. Setelah ia akan kembali ke mode cave.

## Instalasi

### claude.ai, Claude Desktop, dan aplikasi mobile

1. Unduh repo ini (tombol **Code** > **Download ZIP**), lalu ekstrak.
2. Kompres folder `cave/` menjadi `cave.zip`. Yang di-zip harus foldernya, bukan isinya.
3. Buka **Settings > Capabilities** dan pastikan *Code execution and file creation* aktif.
4. Buka **Customize > Skills**, pilih tambah skill, unggah `cave.zip`.
5. Aktifkan togglenya.

Skills tersedia untuk paket Free, Pro, Max, Team, dan Enterprise. Di paket Team dan Enterprise, admin perlu mengaktifkan Skills lebih dulu di Organization settings. Panduan resminya: <https://support.claude.com/en/articles/12512180>

### Claude Code

```bash
git clone https://github.com/asauntung/claude-skill-cave.git
cp -r claude-skill-cave/cave ~/.claude/skills/
```

Atau pakai symlink supaya pembaruan ikut tersalin otomatis:

```bash
ln -s "$(pwd)/claude-skill-cave/cave" ~/.claude/skills/cave
```

## Cara pakai

Ketik salah satu pemicu, mode langsung aktif tanpa konfirmasi:

`caveman mode` · `cave mode` · `/cave` · `jawab singkat` · `singkat saja` · `ringkas` · `hemat token` · `be brief` · `fewer tokens`

Mematikannya: `stop caveman`, `normal mode`, atau `mode normal`.

Bahasa mengikuti Anda. Kalau Anda menulis bahasa Indonesia, jawabannya caveman berbahasa Indonesia.

### Level

Ada tiga level: `lite`, `full`, `ultra`. Default `full`. Level hanya berubah kalau Anda menyebutnya sendiri, misalnya `cave ultra`.

## Struktur repo

```
.
├── README.md
├── LICENSE
└── cave/
    └── SKILL.md   # seluruh isi skill
```

Seluruh skill ada di satu file. Silakan baca dulu sebelum dipasang, isinya cuma 30-an baris saja

## Lisensi

MIT. Bebas dipakai, dimodifikasi, dan disebarkan. Kalau Anda bikin turunan yang lebih bagus, kabari lewat issue, ya.
