# M4DI_UciH4_SmartPanel_PRO v2.00

<div align="center">

![MQL5](https://img.shields.io/badge/MQL5-MetaTrader%205-blue?style=for-the-badge&logo=data:image/png;base64,)
![Version](https://img.shields.io/badge/Version-2.00-brightgreen?style=for-the-badge)
![License](https://img.shields.io/badge/License-MIT-yellow?style=for-the-badge)
![Platform](https://img.shields.io/badge/Platform-MetaTrader%205-orange?style=for-the-badge)

**Ultimate Semi-Auto Trade Manager dengan Panel Interaktif & Smart Entry**

*By M4DI~UciH4 | [GitHub](https://github.com/RizkyEvory)*

</div>

---

## 📖 Deskripsi

**M4DI_UciH4_SmartPanel_PRO** adalah Expert Advisor (EA) MetaTrader 5 berfitur lengkap yang dirancang sebagai **Trade Manager semi-otomatis** tingkat profesional. EA ini dilengkapi dengan panel kontrol interaktif langsung di chart, sistem analisis sinyal multi-layer, serta berbagai alat manajemen risiko canggih — cocok untuk trader yang ingin kontrol penuh namun tetap dibantu otomasi cerdas.

> ⚡ Lebih dari sekadar EA biasa — ini adalah **command center trading** di layar MT5 kamu.

---

## ✨ Fitur Utama

### 🖥️ Interactive Smart Panel
- Panel kontrol visual langsung di chart MT5
- Tombol **BUY / SELL** one-click trading
- Toggle realtime untuk SL, TP, Trailing, Breakeven, Auto Entry, Layer, Recovery, Partial Close
- Input lot size & risk% langsung dari panel (editable)
- Display: Equity, Daily P&L, Posisi aktif, Signal, Trend, MTF, Pattern, RSI, Strength indicator

### 📊 Multi-Indicator Signal Engine
| Indikator | Fungsi |
|---|---|
| **EMA Cross** (9/21/5) | Primary entry signal |
| **RSI** (14) | Filter overbought/oversold + divergence |
| **MACD** (12/26/9) | Konfirmasi momentum |
| **ADX** (14) | Filter kekuatan trend |
| **Bollinger Bands** (20) | Filter volatilitas & breakout |
| **Stochastic** (14/3/3) | Filter entry timing |
| **ATR** (14) | Dynamic SL/TP & trailing |
| **Volume MA** | Konfirmasi volume spike |

### 🕯️ Candle Pattern Recognition
Deteksi otomatis 10 pattern candlestick:
- **Engulfing** (Bullish & Bearish)
- **Pin Bar** (Bullish & Bearish) — dengan rasio wick/body yang bisa dikonfigurasi
- **Inside Bar**
- **Morning Star & Evening Star**
- **Doji**
- **Hammer & Shooting Star**

### 💡 Smart Money Concepts (SMC)
- **Order Blocks** — Deteksi zona institusional
- **Fair Value Gaps (FVG)** — Identifikasi imbalance harga
- **Liquidity Sweeps** — Deteksi perburuan stop loss
- **Break of Structure (BOS)** — Konfirmasi perubahan struktur market
- Visualisasi zona SMC langsung di chart

### 📈 Multi-Timeframe Analysis (MTF)
- Filter konfirmasi dari 2 timeframe berbeda (default H1 & H4)
- Mode: Require All TF alignment atau partial
- Trend direction label di panel

### 🛡️ Risk Management System
- **Auto SL/TP** — Fixed atau berbasis ATR
- **Hidden SL/TP (Stealth)** — SL/TP tidak terlihat di broker
- **Breakeven** — Otomatis geser SL ke entry + offset
- **Partial Close** — 2 level partial (% lot & trigger points yang bisa dikonfigurasi)
- **Trailing Stop** — 4 mode: Fixed, ATR-based, Parabolic SAR, Chandelier Exit
- **Equity Protection** — Auto close semua posisi jika drawdown/profit mencapai % tertentu
- **Daily Loss/Profit Limit** — Berhenti trading otomatis jika target harian tercapai

### 🔄 Recovery & Grid System
- **Recovery Mode** — 4 strategi: Martingale, Anti-Martingale, Fibonacci, Fixed Add
- **Layer / Grid System** — ATR-based atau fixed distance, max 5 layer
- Reset lot otomatis setelah profit

### 📅 Session & Time Filter
- Filter sesi: London, New York, Asian, London-NY Overlap, atau Custom
- Avoid Monday / Friday trading
- Auto close semua posisi sebelum weekend (Friday close hour)
- Batas jumlah trade per hari
- Mode: hanya satu trade aktif dalam satu waktu

### 🔔 Notification System
- **Push Notification** ke HP via MT5 mobile app
- **Email Alert**
- **Telegram Bot** — kirim alert trade & sinyal ke chat/group Telegram kamu
- Auto screenshot on trade (opsional)
- Export **Trade Journal ke CSV**

---

## 🚀 Cara Instalasi

1. **Download** file `M4DI_UciH4_SmartPanel_PRO.mq5`
2. Copy ke folder MQL5 kamu:
   ```
   [MT5 Data Folder] → MQL5 → Experts
   ```
   > Cara cepat: Di MT5, klik **File → Open Data Folder → MQL5 → Experts**
3. **Compile** di MetaEditor (tekan `F7`)
4. Drag & drop EA ke chart yang diinginkan
5. Pastikan **"Allow Algo Trading"** aktif di MT5
6. Panel akan muncul otomatis di pojok kiri atas chart

---

## ⚙️ Parameter Input

### Lot Management
| Parameter | Default | Deskripsi |
|---|---|---|
| `InpLotSize` | 0.05 | Fixed lot size |
| `InpAutoLot` | false | Auto lot berdasarkan % risiko |
| `InpRiskPercent` | 1.0 | Risiko per trade (%) |
| `InpMaxLotSize` | 10.0 | Maksimum lot |
| `InpUseCompounding` | false | Compound growth dari balance |

### SL/TP Settings
| Parameter | Default | Deskripsi |
|---|---|---|
| `InpSL_Points` | 300 | Fixed SL dalam points |
| `InpTP_Points` | 500 | Fixed TP dalam points |
| `InpATR_SLTP` | false | Gunakan ATR untuk SL/TP dinamis |
| `InpATR_MultiplierSL` | 1.5 | Multiplier ATR untuk SL |
| `InpATR_MultiplierTP` | 2.5 | Multiplier ATR untuk TP |
| `InpUseHiddenSLTP` | false | Hidden/Stealth SL/TP |

### Trailing Stop
| Parameter | Default | Deskripsi |
|---|---|---|
| `InpUseTrailing` | false | Aktifkan trailing stop |
| `InpTrailingPoints` | 200 | Fixed trailing distance |
| `InpUseSmartTrailing` | false | ATR-based trailing |
| `InpUseParabolicTrailing` | false | Trailing via Parabolic SAR |
| `InpUseChandelierExit` | false | Chandelier exit |

### Equity Protection
| Parameter | Default | Deskripsi |
|---|---|---|
| `InpMaxLossPercent` | 5.0 | Max drawdown % (close all) |
| `InpMaxProfitPercent` | 3.0 | Max profit % (take all) |
| `InpDailyMaxLoss` | 0 | Daily max loss $ (0=disabled) |
| `InpDailyMaxProfit` | 0 | Daily profit target $ (0=disabled) |

### Recovery Mode
| Parameter | Default | Deskripsi |
|---|---|---|
| `InpRecoveryType` | MARTINGALE | Tipe recovery (4 pilihan) |
| `InpRecoveryMultiplier` | 1.5 | Lot multiplier setelah loss |
| `InpMaxRecoveryTrades` | 5 | Maksimum recovery trades |

### Telegram Notifications
| Parameter | Default | Deskripsi |
|---|---|---|
| `InpUseTelegram` | false | Aktifkan Telegram |
| `InpTelegramBotToken` | "" | Token dari @BotFather |
| `InpTelegramChatID` | "" | Chat ID tujuan |

---

## 📱 Setup Telegram Alert

1. Buat bot baru via **@BotFather** di Telegram → copy **Bot Token**
2. Dapatkan **Chat ID** kamu via `https://api.telegram.org/bot<TOKEN>/getUpdates`
3. Isi `InpTelegramBotToken` dan `InpTelegramChatID` di parameter EA
4. Set `InpUseTelegram = true`
5. EA akan otomatis kirim notif setiap ada trade terbuka/tertutup dan deteksi sinyal

---

## 🎛️ Panel Control Guide

```
┌─────────────────────────────────┐
│  M4DI~UciH4 SmartPanel PRO      │
│  github.com/RizkyEvory          │
├─────────────────────────────────┤
│  Symbol: XAUUSD   Equity: $1000 │
│  Signal: EMA Bull Cross 🟢      │
│  Trend: ↑ BULLISH | MTF: ✓      │
│  Pattern: Engulfing | RSI: 45.3 │
│  Strength: ●●●○ Strong          │
├─────────────────────────────────┤
│  Lot: [0.05]   Risk: [1.0%]     │
│  [   BUY   ]   [   SELL   ]     │
│  [Close Buy]   [Close Sell]     │
│  [Close Profit] [Close Loss]    │
│        [ Close ALL ]            │
├─────────────────────────────────┤
│ [SL✓] [TP✓] [Trail] [BE✓]      │
│ [Auto] [Layer] [Recov] [Part]   │
├─────────────────────────────────┤
│  Daily P&L: +$25.40             │
│  Trades: 3 | Win: 2 | Loss: 1   │
└─────────────────────────────────┘
```

**Toggle Buttons:**
- 🟢 **[SL]** / **[TP]** — Toggle Auto Stop Loss / Take Profit
- 🔵 **[Trail]** — Toggle Trailing Stop
- 🟡 **[BE]** — Toggle Breakeven
- 🟣 **[Auto]** — Toggle Auto Entry mode
- 🔴 **[Layer]** — Toggle Grid/Layering system
- ⚪ **[Recov]** — Toggle Recovery Mode
- 🟠 **[Part]** — Toggle Partial Close

---

## 📊 Signal Strength Levels

| Level | Deskripsi |
|---|---|
| ⬜ **NONE** | Tidak ada sinyal |
| 🟡 **WEAK** | Sinyal lemah — tidak dieksekusi |
| 🟠 **MODERATE** | Minimal untuk auto entry |
| 🟢 **STRONG** | Sinyal kuat dengan konfirmasi |
| 💚 **VERY STRONG** | Semua filter align |

> Auto Entry hanya akan membuka posisi jika signal strength minimal **MODERATE**

---

## 🧪 Backtesting & Optimasi

EA ini dilengkapi custom **OnTester()** criterion untuk optimasi:

```
Criterion = (ProfitFactor × WinRate) / (1 + MaxDrawdown%)
```

**Filter otomatis dalam backtesting:**
- Minimum 20 trades
- Max drawdown tidak boleh melebihi 30%

**Rekomendasi setting tester:**
- Mode: **Every Tick** atau **Real Ticks**
- Tick generation: OHLC data lebih cepat, real ticks lebih akurat
- Optimasi: gunakan "Genetic Algorithm" untuk parameter banyak

---

## ⚠️ Disclaimer

> **PERINGATAN RISIKO:** Trading forex dan instrumen keuangan mengandung risiko tinggi kehilangan modal. EA ini adalah alat bantu, **bukan jaminan profit**. Selalu uji di akun demo terlebih dahulu sebelum live. Developer tidak bertanggung jawab atas kerugian finansial apapun.

---

## 🛠️ Requirements

- **Platform:** MetaTrader 5 (Build 2700+)
- **Akun:** Semua jenis (Standard, ECN, Raw Spread)
- **Simbol:** Semua instrumen (Forex, Gold, Indeks, Crypto)
- **Timeframe:** Semua TF (disarankan M15 ke atas)
- **VPS:** Sangat direkomendasikan untuk performa optimal

---

## 📂 Struktur File

```
M4DI_UciH4_SmartPanel_PRO/
├── M4DI_UciH4_SmartPanel_PRO.mq5   # Source code utama
└── README.md                         # Dokumentasi ini
```

---

## 🤝 Kontribusi

Pull request, bug report, dan saran fitur sangat disambut!

1. Fork repository ini
2. Buat branch baru: `git checkout -b fitur-baru`
3. Commit: `git commit -m 'Tambah fitur X'`
4. Push: `git push origin fitur-baru`
5. Buat Pull Request

---

## 📄 License

MIT License — bebas digunakan, dimodifikasi, dan didistribusikan dengan tetap mencantumkan kredit.

---

<div align="center">

Made with ❤️ by **M4DI~UciH4**

⭐ Kalau EA ini berguna, jangan lupa kasih **Star** di GitHub ya!

[![GitHub](https://img.shields.io/badge/GitHub-RizkyEvory-black?style=for-the-badge&logo=github)](https://github.com/RizkyEvory)

</div>
