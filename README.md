# 🚀 Crypto Tracker Pro - Firebase Edition

Aplikasi web untuk memantau Whale Wallets dan Potential Coins dengan integrasi Firebase Firestore.

## 📁 File Structure

```
crypto-tracker/
├── index.html          # Dashboard utama (View data)
├── entry-whale.html    # Form input Whale Wallet
├── entry-coin.html     # Form input Coin Potensial
├── firestore.rules     # Firebase Security Rules
└── README.md          # Dokumentasi ini
```

## 🔥 Setup Firebase

### 1. Update Firebase Rules

Buka Firebase Console:
1. Pergi ke **Firestore Database**
2. Klik tab **Rules**
3. Copy isi file `firestore.rules` dan paste ke editor rules
4. Klik **Publish**

**Isi Rules:**
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
  }
}
```

> ⚠️ **PENTING**: Rules ini mengizinkan akses publik. Untuk production, tambahkan authentication!

### 2. Struktur Database Firestore

Aplikasi akan otomatis membuat 2 collections:

#### Collection: `whales`
```javascript
{
  name: "Whale Alpha",
  address: "0x123...",
  chain: "BSC",
  notes: "Active trader",
  dateAdded: timestamp
}
```

#### Collection: `coins`
```javascript
{
  name: "n$PEPE",
  contract: "0xabc...",
  chain: "ETH",
  potential: "🔥 High",
  notes: "Strong community",
  dateAdded: timestamp
}
```

## 🎯 Fitur Aplikasi

### 📊 Dashboard (index.html)
- **Statistics Cards**: Total whales, coins, dan per blockchain
- **Tab Navigation**: Switch antara Whales dan Coins
- **Filter**: Filter coins berdasarkan blockchain
- **Actions**: Copy address, delete entry
- **Real-time**: Data langsung dari Firebase

### 🐋 Entry Whale (entry-whale.html)
- Form terpisah untuk input whale wallet
- Fields:
  - Nama wallet (custom)
  - Alamat wallet
  - Blockchain (BSC, ETH, Solana, Base)
  - Catatan opsional
- Auto-redirect ke dashboard setelah save

### 💰 Entry Coin (entry-coin.html)
- Form terpisah untuk input coin potensial
- Fields:
  - Nama coin (format: n$TOKEN)
  - Smart contract address
  - Blockchain (BSC, ETH, Solana, Base)
  - Level potensi (High/Medium/Low)
  - Analisis dan catatan
- Live preview nama coin
- Auto-redirect ke dashboard setelah save

## 🚀 Cara Menggunakan

### Setup Awal
1. Upload semua file HTML ke web hosting atau buka langsung di browser
2. Pastikan koneksi internet aktif (untuk Firebase)
3. Update Firebase rules seperti di atas

### Menambah Whale Wallet
1. Klik menu **Entry Whale** atau tombol floating **+**
2. Isi form:
   - Nama wallet (contoh: "Whale Binance")
   - Address wallet
   - Pilih blockchain
   - Tambah catatan (opsional)
3. Klik **Simpan Whale**
4. Otomatis redirect ke dashboard

### Menambah Coin Potensial
1. Klik menu **Entry Coin** atau tombol floating **+**
2. Isi form:
   - Nama coin dengan format **n$TOKEN** (contoh: n$SHIB)
   - Smart contract address
   - Pilih blockchain
   - Pilih level potensi
   - Tambah analisis (opsional)
3. Klik **Simpan Coin**
4. Otomatis redirect ke dashboard

### Melihat Data
1. Buka **Dashboard** (index.html)
2. Lihat statistik di bagian atas
3. Switch tab antara **Whales** dan **Coins**
4. Filter coins berdasarkan blockchain (dropdown)
5. Copy address dengan tombol clipboard
6. Delete entry dengan tombol trash

## 🎨 Desain Features

- ✅ Dark theme modern
- ✅ Bootstrap 5 responsive
- ✅ Gradient colors
- ✅ Bootstrap Icons
- ✅ Card animations
- ✅ Loading states
- ✅ Toast notifications
- ✅ Floating action button
- ✅ Live preview (coin name)
- ✅ Form validation

## 🔐 Security Notes

### Current Setup (Development)
```javascript
allow read, create, update, delete: if true;
```
✅ Cocok untuk development dan testing
❌ TIDAK aman untuk production

### Recommended for Production
```javascript
match /whales/{whaleId} {
  allow read: if request.auth != null;
  allow create: if request.auth != null;
  allow update, delete: if request.auth != null && 
                          request.auth.uid == resource.data.userId;
}
```

Tambahkan authentication:
- Firebase Authentication (Email/Password)
- Google Sign-In
- Save `userId` di setiap document

## 📱 Browser Support

- ✅ Chrome (Recommended)
- ✅ Firefox
- ✅ Edge
- ✅ Safari
- ⚠️ IE11 (Limited support)

## 🐛 Troubleshooting

### Data tidak muncul?
1. Cek Firebase Rules sudah di-publish
2. Cek console browser (F12) untuk error
3. Pastikan firebaseConfig sudah benar
4. Cek koneksi internet

### Error saat save?
1. Cek Firebase Rules
2. Cek form validation (semua field required terisi)
3. Cek console untuk error message

### Copy tidak berfungsi?
1. Pastikan browser support Clipboard API
2. Gunakan HTTPS (bukan HTTP)
3. Allow clipboard permission di browser

## 📊 Database Indexes

Jika ada warning tentang indexes, buat composite index:

**Collection: whales**
- `dateAdded` (Descending)

**Collection: coins**
- `dateAdded` (Descending)
- `chain` + `dateAdded` (Ascending + Descending)

## 🔄 Future Improvements

- [ ] User authentication
- [ ] Price tracking API integration
- [ ] Export to CSV/Excel
- [ ] Advanced filtering
- [ ] Search functionality
- [ ] Bulk operations
- [ ] Price alerts
- [ ] Portfolio tracking
- [ ] Mobile app version

## 📞 Support

Jika ada masalah atau pertanyaan:
1. Cek dokumentasi Firebase: https://firebase.google.com/docs
2. Cek console browser untuk error messages
3. Verify Firebase configuration

## 📝 License

Free to use and modify.

---

**Dibuat dengan ❤️ menggunakan:**
- HTML5 & CSS3
- Bootstrap 5
- Firebase Firestore
- Bootstrap Icons
