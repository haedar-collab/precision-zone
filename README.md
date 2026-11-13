# Precision Zone Crypto — Scanner (Web App Gratis)

Scanner untuk Binance Spot (pair USDT) dengan kerangka **Precision Zone System**: filter trend EMA 50/200, zona Supply & Demand, candle konfirmasi, konteks SMC (BOS/CHoCH/liquidity sweep), serta trading plan otomatis (Entry, SL, TP1, TP2, RR) dan kalkulator ukuran posisi.

- **Biaya: Rp0.** Cukup satu file `index.html`, tanpa server, database, maupun API key.
- **Data:** Binance Public API (`data-api.binance.vision`, cadangan `api.binance.com`).
- **Privasi:** semua perhitungan dan pengaturan (termasuk token Telegram) tersimpan di browser Anda sendiri.

---

## 1. Deploy gratis

### Opsi A — GitHub Pages (disarankan)
1. Login ke https://github.com lalu klik **+ → New repository**.
2. Nama repo: `precision-zone`, pilih **Public**, lalu **Create repository**.
3. Klik **Add file → Upload files**, unggah `index.html` dan `README.md`, lalu **Commit changes**.
4. Buka **Settings → Pages**. Di *Build and deployment*: Source **Deploy from a branch**, Branch **main**, folder **/ (root)**, lalu **Save**.
5. Tunggu 1–3 menit, lalu buka `https://USERNAME.github.io/precision-zone/`.
6. Untuk update: unggah ulang `index.html` versi baru (file lama akan tertimpa).

### Opsi B — Cloudflare Pages
1. Buka dash.cloudflare.com, lalu **Workers & Pages → Create → Pages → Upload assets**.
2. Isi nama project, unggah folder berisi `index.html`, lalu **Deploy**. Aplikasi tersedia di `https://NAMA.pages.dev`.

### Opsi C — Netlify Drop
1. Buka https://app.netlify.com/drop lalu seret folder berisi `index.html`.
2. Daftar akun gratis supaya situsnya permanen.

### Pasang di HP
- **Android (Chrome):** menu ⋮, lalu **Add to Home screen**.
- **iPhone (Safari):** Share, lalu **Add to Home Screen**.

> Tanpa deploy pun, `index.html` bisa langsung dibuka di browser laptop.

---

## 2. Cara pakai singkat
1. Pilih **Semua Crypto** (top N berdasarkan volume) atau **Pair Pilihan** (mis. `BTC, ETH, SOL`).
2. Pilih timeframe (4H untuk swing, 1H untuk intraday) dan aktifkan **Filter HTF**.
3. Tekan **▶ Scan**, lalu saring dengan *BUY Confirmed*, *Zona Fresh*, atau *Grade A/B*.
4. Ketuk sebuah pair untuk melihat chart dengan zona, trading plan, checklist, dan kalkulator posisi.
5. Validasi di TradingView sebelum eksekusi.

Panduan lengkap (aturan sistem, arti sinyal, komponen skor, manajemen posisi, Telegram, troubleshooting) ada di tab **Panduan** di dalam aplikasi.

---

## 3. Ringkasan aturan sistem
| Komponen | Aturan |
|---|---|
| Trend | UP: EMA50 > EMA200 dan harga > EMA200 · DOWN: kebalikannya · selain itu SIDEWAYS |
| Zona | Base 1–3 candle kecil, diikuti impulse dengan body ≥ 1,2×ATR. Proximal = body base, distal = ekstrem base |
| Status zona | Fresh → Tested 1× → Lemah (≥ 2×). Zona Broken (close melewati distal) dihapus |
| BUY CONFIRMED | Trend UP, HTF tidak DOWN, demand disentuh ≤ 3 candle terakhir, pin bar/engulfing bullish, harga ≤ 1 ATR dari zona |
| BUY SETUP | Trend UP, demand Fresh/Tested 1× dalam jarak ≤ 1,5 ATR |
| SL | Distal − 0,2×ATR |
| TP1 / TP2 | Zona lawan terdekat (kalau ≥ 1R), atau 2R · TP2 ≥ 3R |

Semua angka bisa diubah di tab **Pengaturan**.

---

## 4. Batasan
- Auto-scan dan notifikasi hanya berjalan **selama tab terbuka**.
- Filter token saham (NVDAB, TSLAB, dll.) memakai daftar nama, bukan penanda resmi Binance. Pair yang lolos bisa dikecualikan manual.
- Aturan di aplikasi ini adalah terjemahan algoritmik dari konsep Precision Zone. Sesuaikan dengan cheat sheet Anda.

**Disclaimer:** alat bantu analisis, bukan nasihat keuangan.
