# 📁 Crypto Tracker Pro - Struktur File & Setup Guide

## 🗂️ Struktur File Aplikasi

```
crypto-tracker-pro/
│
├── 📄 index.html                    # Dashboard utama (Whales & Coins)
├── 📄 entry-whale.html              # Form tambah Whale Wallet
├── 📄 entry-coin.html               # Form tambah Coin Potensial
├── 📄 portfolio.html                # Portfolio Tracker Dashboard
├── 📄 entry-portfolio.html          # Form tambah Asset ke Portfolio
│
├── 📄 firestore.rules               # Firebase Security Rules
│
├── 📄 README.md                     # Dokumentasi utama
├── 📄 SOLANA-COLORS.md             # Dokumentasi color palette
├── 📄 DETAILED-COIN-STATS.md       # Dokumentasi fitur coin stats
├── 📄 PORTFOLIO-TRACKING.md        # Dokumentasi fitur portfolio
└── 📄 PROJECT-STRUCTURE.md         # File ini
```

## 📋 Deskripsi File

### 🌐 Halaman Web (HTML)

#### 1. **index.html** - Dashboard Utama
**Fungsi:**
- Halaman pertama yang dibuka
- Menampilkan semua Whale Wallets
- Menampilkan semua Coins Potensial dengan stats lengkap
- Statistics cards (total whales, coins, per chain)
- Tab navigation antara Whales & Coins
- Filter coins by blockchain
- Copy address & delete functionality

**Fitur:**
- ✅ Real-time data dari Firebase
- ✅ Detailed coin stats display
- ✅ Responsive design
- ✅ Solana color theme

#### 2. **entry-whale.html** - Form Entry Whale
**Fungsi:**
- Form untuk menambah whale wallet baru
- Input: nama, address, chain, notes
- Auto-redirect ke dashboard setelah save

**Fitur:**
- ✅ Form validation
- ✅ Auto-save ke Firebase
- ✅ Success notification

#### 3. **entry-coin.html** - Form Entry Coin
**Fungsi:**
- Form untuk menambah coin potensial
- Input: nama (n$), contract, chain, potential, stats, notes
- Live preview nama coin

**Fitur:**
- ✅ Format n$ otomatis
- ✅ Stats section lengkap (price, MC, volume, dll)
- ✅ Live coin name preview
- ✅ Auto-save ke Firebase

#### 4. **portfolio.html** - Portfolio Dashboard
**Fungsi:**
- Menampilkan semua aset crypto
- Portfolio summary (total investment, value, P/L)
- Statistics per blockchain
- Filter & sort functionality

**Fitur:**
- ✅ Total portfolio value
- ✅ Profit/Loss tracking
- ✅ Best performer indicator
- ✅ Multi-chain support
- ✅ Edit & delete assets

#### 5. **entry-portfolio.html** - Form Entry Portfolio
**Fungsi:**
- Form untuk menambah aset ke portfolio
- Input: coin name, chain, investment, buy price, amount
- Auto calculate coin amount
- Live preview calculations

**Fitur:**
- ✅ Auto calculate: Investment ÷ Buy Price
- ✅ P/L calculator dengan current price
- ✅ Live calculation preview
- ✅ Auto-save ke Firebase

### 🔧 Konfigurasi

#### **firestore.rules** - Firebase Security Rules
**Fungsi:**
- Mengatur akses ke Firestore database
- Allow read/write untuk collections:
  - `whales`
  - `coins`
  - `portfolio`

**⚠️ PENTING:**
- File ini harus di-copy ke Firebase Console
- Rules harus di-publish agar aplikasi bisa akses database

### 📚 Dokumentasi

#### **README.md** - Dokumentasi Utama
- Overview aplikasi
- Setup Firebase
- Cara menggunakan
- Troubleshooting

#### **SOLANA-COLORS.md** - Color Palette Guide
- Daftar warna Solana theme
- Gradient combinations
- Usage guide

#### **DETAILED-COIN-STATS.md** - Coin Stats Feature
- Cara input stats coin
- Format data yang benar
- Visual examples

#### **PORTFOLIO-TRACKING.md** - Portfolio Feature
- Cara tracking investasi
- Calculation logic
- Use cases & examples

## 🚀 Cara Setup & Deploy

### Option 1: Local Testing (Termudah)

1. **Download semua file** ke satu folder
2. **Buka Firebase Console**:
   - Go to Firestore Database → Rules
   - Copy isi `firestore.rules`
   - Paste & Publish
3. **Buka `index.html`** dengan browser
4. **Selesai!** Aplikasi siap digunakan

```
Struktur folder lokal:
D:/crypto-tracker/
├── index.html
├── entry-whale.html
├── entry-coin.html
├── portfolio.html
└── entry-portfolio.html
```

### Option 2: Web Hosting (Recommended)

#### A. Menggunakan Firebase Hosting (Gratis)

1. **Install Firebase CLI**:
```bash
npm install -g firebase-tools
```

2. **Login Firebase**:
```bash
firebase login
```

3. **Init Firebase Hosting**:
```bash
firebase init hosting
```

4. **Deploy**:
```bash
firebase deploy
```

**URL Aplikasi:** https://cryptt-3f364.web.app

#### B. Menggunakan Netlify (Gratis)

1. Buka https://netlify.com
2. Drag & drop folder ke Netlify
3. Done! Auto dapat URL

#### C. Menggunakan Vercel (Gratis)

1. Buka https://vercel.com
2. Import project dari folder
3. Deploy otomatis

#### D. Menggunakan GitHub Pages (Gratis)

1. Upload file ke GitHub repository
2. Settings → Pages → Enable
3. URL: https://username.github.io/repo-name

### Option 3: Upload ke Hosting Sendiri

Upload semua file HTML ke:
- cPanel File Manager
- FTP (FileZilla)
- Cloud storage (Google Drive → Public)

## 🔥 Setup Firebase (WAJIB)

### 1. Update Firestore Rules

**Buka Firebase Console:**
https://console.firebase.google.com

**Steps:**
1. Pilih project: `cryptt-3f364`
2. Klik **Firestore Database**
3. Tab **Rules**
4. Copy & paste dari `firestore.rules`:

```javascript
rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    match /whales/{whaleId} {
      allow read, create, update, delete: if true;
    }
    match /coins/{coinId} {
      allow read, create, update, delete: if true;
    }
    match /portfolio/{portfolioId} {
      allow read, create, update, delete: if true;
    }
  }
}
```

5. Klik **Publish**

### 2. Verifikasi Firebase Config

Cek di setiap file HTML, pastikan config ini sama:

```javascript
const firebaseConfig = {
  apiKey: "AIzaSyDb0XCzx13LR_lQ_W9zUGHdl4OCt5RmL0s",
  authDomain: "cryptt-3f364.firebaseapp.com",
  projectId: "cryptt-3f364",
  storageBucket: "cryptt-3f364.firebasestorage.app",
  messagingSenderId: "333311322801",
  appId: "1:333311322801:web:7f02896dd29487a2fa5090",
  measurementId: "G-KT5YB5E5PN"
};
```

## 📊 Collections di Firestore

Aplikasi menggunakan 3 collections:

### 1. Collection: `whales`
```javascript
{
  name: "Whale Alpha",
  address: "0x123...",
  chain: "BSC",
  notes: "Active trader",
  dateAdded: timestamp
}
```

### 2. Collection: `coins`
```javascript
{
  name: "n$PEPE",
  contract: "0xabc...",
  chain: "ETH",
  potential: "🔥 High",
  notes: "Strong community",
  stats: {
    price: "0.0001235",
    priceChange: 31,
    marketCap: "123.6K",
    volume: "653.3K",
    liquidity: "22.2K",
    supply: "1B/1B",
    holders: "1K",
    ath: "531.6K",
    athChange: "-77% / 16m"
  },
  age: "2h",
  dateAdded: timestamp
}
```

### 3. Collection: `portfolio`
```javascript
{
  coinName: "n$SHIB",
  chain: "ETH",
  investmentAmount: "100",
  buyPrice: "0.00001",
  coinAmount: "10000000",
  currentPrice: "0.00002",
  contract: "0x...",
  notes: "Hold until 10x",
  dateAdded: timestamp
}
```

## 🎯 Navigation Flow

```
index.html (Landing Page)
    ├── Tab: Whales Wallet
    │   └── Button: Add Whale → entry-whale.html
    │
    ├── Tab: Potential Coins
    │   └── Button: Add Coin → entry-coin.html
    │
    └── Menu: Portfolio → portfolio.html
        └── Button: Add Asset → entry-portfolio.html
```

## 📱 Akses Aplikasi

### Desktop
1. Buka browser (Chrome/Firefox/Edge)
2. Buka `index.html` atau URL hosting
3. Navigate menggunakan menu navbar

### Mobile
1. Buka browser mobile
2. Akses URL aplikasi
3. Responsive design otomatis adjust
4. Dapat save to home screen

### Tablet
- Full support untuk iPad, Android tablets
- Landscape & portrait mode

## ⚡ Tips Deploy

### Jika Pakai Local:
✅ **Pro:** Gratis, cepat, offline
❌ **Con:** Hanya bisa akses dari PC sendiri

### Jika Pakai Hosting:
✅ **Pro:** Akses dari mana saja, share ke orang lain
✅ **Pro:** URL permanent
❌ **Con:** Perlu setup (tapi mudah!)

## 🔐 Security Notes

### Current Setup (Development):
```javascript
allow read, create, update, delete: if true;
```
✅ Cocok untuk: Personal use, testing
❌ **TIDAK** untuk: Public/production

### Production Setup (Recommended):
Tambahkan Firebase Authentication:
```javascript
allow read, write: if request.auth != null;
```

## 📞 Support & Updates

### Jika Ada Error:
1. Cek browser console (F12)
2. Verify Firebase rules published
3. Check internet connection
4. Verify firebaseConfig benar

### Update Aplikasi:
1. Edit file HTML yang diperlukan
2. Re-upload ke hosting (jika pakai hosting)
3. Clear browser cache
4. Refresh page

## 🎨 Customization

### Ganti Warna:
Edit CSS variables di setiap file HTML:
```css
:root {
  --primary-gradient: linear-gradient(...);
  --dark-bg: #000000;
  --card-bg: #0B0B0F;
  --border-color: #1A1A24;
}
```

### Tambah Blockchain:
Di setiap `<select>` untuk chain, tambah:
```html
<option value="NAMACHAIN">Nama Chain</option>
```

### Tambah Field:
1. Edit form HTML
2. Update Firebase save function
3. Update display/render function

## ✅ Checklist Setup

- [ ] Download semua 5 file HTML
- [ ] Setup Firebase rules
- [ ] Test buka index.html
- [ ] Test tambah whale
- [ ] Test tambah coin
- [ ] Test tambah portfolio
- [ ] (Optional) Deploy ke hosting
- [ ] Share URL (jika hosting)

## 🚀 Quick Start

**Paling Cepat (5 menit):**
1. Download semua file
2. Update Firebase rules
3. Buka index.html
4. Done! 🎉

**Rekomendasi:**
File di folder ini sudah siap pakai langsung!
```
crypto-tracker/
├── index.html ← BUKA INI DULU
├── entry-whale.html
├── entry-coin.html
├── portfolio.html
└── entry-portfolio.html
```

**Selamat menggunakan Crypto Tracker Pro! 🚀💰**
