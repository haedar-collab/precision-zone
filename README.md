# Precision Zone · Spot Long Scanner v2.1 (Web App Gratis)

> 🇬🇧 **English:** a free, single-file Binance Spot **long-only** scanner based on the Precision Zone System (EMA 50/200 + supply & demand zones), with Binance execution tickets (Limit + OCO), watchlist and trading journal. The app is bilingual: use the **ID | EN** switch in the top-right corner. Deploy by uploading `index.html` to GitHub Pages (see section 1). The full English guide is in the app's **Guide** tab.

Scanner **khusus Spot Long** untuk Binance Spot (pair USDT) dengan kerangka **Precision Zone System**. Hanya sinyal BUY, supply zone dipakai sebagai target TP. Isinya: filter trend EMA 50/200, zona Supply & Demand, candle konfirmasi, konteks SMC (BOS/CHoCH/liquidity sweep), serta trading plan otomatis (Entry, SL, TP1, TP2, RR) dan kalkulator ukuran posisi.

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

## Fitur v2.0
- **Kartu peluang** dikelompokkan: Siap eksekusi → Siapkan limit → Pantau, masing-masing dengan ringkasan bahasa sederhana.
- **Banner kondisi pasar** (BTC trend + % pair uptrend) dengan saran sikap.
- **Tiket eksekusi Binance Spot**: Limit/Market Buy + OCO Sell (TP1/TP2 + stop-limit). Harga dan qty dibulatkan sesuai tick/step size pair dan dicek terhadap minimum order.
- **Rincian skor**, checklist, dan tabel **multi-timeframe** (15m/1H/4H/1D) di halaman detail.
- **Watchlist** (☆) dan **Jurnal trading** (R, win rate, P&L), plus backup/restore JSON.
- Tampilan responsif dengan navigasi bawah di HP.
- **Dua bahasa (Indonesia / English)**: tombol **ID | EN** di kanan atas. Semua teks, termasuk panduan, tiket, dan notifikasi Telegram, ikut berganti. Pilihan bahasa tersimpan otomatis.

## 2. Cara pakai singkat
1. Atur modal, metode ukuran posisi, dan pembagian TP di **Pengaturan**.
2. Pilih cakupan (Semua crypto / Pair pilihan / Watchlist) dan timeframe, lalu tekan **Scan**.
3. Cek banner **Kondisi pasar**.
4. Buka kartu **Siap eksekusi** atau **Siapkan limit**, lalu ikuti **Tiket eksekusi** (tombol salin di setiap angka).
5. Tekan **Simpan ke jurnal** untuk melacak hasilnya.

Panduan lengkap (aturan sistem, arti sinyal, komponen skor, manajemen posisi, Telegram, troubleshooting) ada di tab **Panduan** di dalam aplikasi.

---

## 3. Ringkasan aturan sistem
| Komponen | Aturan |
|---|---|
| Trend | UP: EMA50 > EMA200 dan harga > EMA200 (cari BUY) · DOWN: hindari beli · selain itu SIDEWAYS (tunggu) |
| Zona | Base 1–3 candle kecil, diikuti impulse dengan body ≥ 1,2×ATR. Proximal = body base, distal = ekstrem base |
| Status zona | Fresh → Tested 1× → Lemah (≥ 2×). Zona Broken (close melewati distal) dihapus |
| Siap eksekusi | Trend UP, HTF tidak DOWN, demand disentuh ≤ 3 candle terakhir, pin bar/engulfing bullish, harga ≤ 1 ATR dari zona |
| Siapkan limit | Trend UP, demand Fresh/Tested 1× dalam jarak ≤ 1,5 ATR |
| SL | Distal − 0,2×ATR |
| TP1 / TP2 | Supply zone terdekat di atas entry (kalau ≥ 1R), atau 2R · TP2 ≥ 3R |
| Eksekusi | Limit buy + OCO (TP & SL) di Binance Spot |

Semua angka bisa diubah di tab **Pengaturan**.

---

## 4. Batasan
- Auto-scan dan notifikasi hanya berjalan **selama tab terbuka**.
- Filter token saham (NVDAB, TSLAB, dll.) memakai daftar nama, bukan penanda resmi Binance. Pair yang lolos bisa dikecualikan manual.
- Aturan di aplikasi ini adalah terjemahan algoritmik dari konsep Precision Zone. Sesuaikan dengan cheat sheet Anda.

**Disclaimer:** alat bantu analisis, bukan nasihat keuangan.
