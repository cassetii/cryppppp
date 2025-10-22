# 💰 Portfolio Tracking Feature

## ✨ Fitur Baru: Portfolio Asset Tracker

Sekarang Anda bisa tracking investasi crypto Anda dengan lengkap! Monitor berapa dollar yang diinvest, jumlah coin yang dibeli, harga beli, harga sekarang, dan profit/loss secara real-time.

## 🎯 Fitur Utama

### 1. **Portfolio Dashboard** (portfolio.html)
Halaman utama untuk melihat semua aset crypto Anda

#### Portfolio Summary
- 💰 **Total Investment**: Total uang yang sudah Anda investasikan
- 💵 **Current Value**: Nilai portfolio saat ini
- 📈 **Total P/L**: Total Profit/Loss (jumlah & persentase)
- 🎯 **Best Performer**: Coin dengan performa terbaik

#### Statistics Cards
- Total Assets (semua chain)
- BSC Assets
- ETH Assets
- SOL Assets
- BASE Assets

#### Filter & Sort
- **Filter by Blockchain**: BSC, ETH, Solana, Base
- **Sort by**: Date, Highest Value, Highest P/L

### 2. **Entry Portfolio** (entry-portfolio.html)
Form untuk menambah aset baru ke portfolio

#### Field Input:
1. **Nama Coin** - Nama token yang dibeli (Bitcoin, n$PEPE, dll)
2. **Blockchain** - Chain tempat token berada
3. **Jumlah Investment (USD)** - Berapa dollar yang diinvest
4. **Harga Beli per Coin** - Price per coin saat beli
5. **Jumlah Coin** - Auto calculate atau input manual
6. **Harga Sekarang** (Opsional) - Update untuk tracking P/L
7. **Smart Contract** (Opsional) - Alamat contract
8. **Catatan** (Opsional) - Strategy, notes, target

## 📊 Cara Menggunakan

### Menambah Asset ke Portfolio:

#### Scenario 1: Anda masuk coin baru
```
Nama Coin: n$MEMECAT
Blockchain: BSC
Investment: $100
Harga Beli: $0.0001
Jumlah Coin: 1,000,000 (auto calculated)
Catatan: Entry at support level, target 10x
```

**Hasil Auto Calculate:**
- Investment: $100
- Buy Price: $0.0001
- Coin Amount: 1,000,000 tokens

#### Scenario 2: Update harga current untuk tracking
```
(Edit asset yang sudah ada)
Harga Sekarang: $0.00015

Portfolio akan show:
- Current Value: $150
- Profit: +$50 (+50%)
```

### Melihat Portfolio:

1. **Buka** portfolio.html
2. **Lihat Summary** - Total investment, value, P/L
3. **Filter** by blockchain jika perlu
4. **Sort** by value atau P/L
5. **Monitor** setiap asset detail

## 💡 Detail Informasi Per Asset

Setiap asset card menampilkan:

### Investment Info
- 💵 **Investment**: Total dollar yang diinvest
- 🪙 **Amount**: Jumlah coin yang dibeli
- 💰 **Buy Price**: Harga beli per coin

### Current Performance (jika Current Price diisi)
- 📊 **Current Price**: Harga coin sekarang
- 💎 **Current Value**: Nilai portfolio saat ini
- 📈 **Profit/Loss**: 
  - Jumlah dollar (hijau jika profit, merah jika loss)
  - Persentase keuntungan/kerugian

### Additional Info
- 📝 Notes (jika ada)
- 📅 Date Added
- 🔗 Blockchain badge

## 🎨 Visual Features

### Color Indicators
- **Green** (#14F195): Profit, positive performance
- **Red** (#ff4757): Loss, negative performance
- **Purple** (#9945FF): Primary actions, highlights
- **Gold** (#f3ba2f): BSC chain
- **Blue** (#627eea): ETH chain

### Interactive Elements
- ✏️ **Edit Button**: Update asset info
- 🗑️ **Delete Button**: Remove from portfolio
- 📋 **Auto Calculate**: Investment ÷ Buy Price
- 📊 **Live Preview**: Calculate P/L real-time

## 🧮 Calculation Logic

### Coin Amount Calculation
```javascript
Coin Amount = Investment Amount ÷ Buy Price

Example:
$100 ÷ $0.0001 = 1,000,000 coins
```

### Current Value Calculation
```javascript
Current Value = Coin Amount × Current Price

Example:
1,000,000 × $0.00015 = $150
```

### Profit/Loss Calculation
```javascript
P/L Amount = Current Value - Investment
P/L Percentage = (P/L Amount ÷ Investment) × 100%

Example:
P/L = $150 - $100 = +$50
P/L% = ($50 ÷ $100) × 100% = +50%
```

## 📝 Use Cases

### Use Case 1: Entry Baru
```
Situation: Beli coin potensial baru
Action: 
1. Klik "Tambah Asset"
2. Input nama coin, chain, investment, buy price
3. Coin amount auto calculate
4. Save

Result: Asset masuk portfolio, bisa tracking nanti
```

### Use Case 2: Update Progress
```
Situation: Harga coin naik, mau cek profit
Action:
1. Edit asset
2. Update "Harga Sekarang"
3. Save

Result: Otomatis calculate P/L, show profit percentage
```

### Use Case 3: Monitor Portfolio
```
Situation: Daily check portfolio performance
Action:
1. Buka portfolio.html
2. Lihat summary - total value & P/L
3. Check best performer
4. Update current price per asset

Result: Full visibility portfolio performance
```

### Use Case 4: Multi-Chain Tracking
```
Situation: Invest di berbagai chain
Portfolio:
- BSC: 3 coins
- ETH: 2 coins  
- Solana: 5 coins

Action: Filter by chain untuk focus analysis
Result: Clear view per blockchain
```

## 🎯 Best Practices

### When Adding Assets:
1. ✅ **Always** input nama coin yang jelas
2. ✅ **Always** pilih blockchain yang benar
3. ✅ **Always** input investment amount akurat
4. ✅ **Always** input buy price yang tepat
5. ✅ **Optional** tapi recommended: add notes strategy

### When Updating:
1. 🔄 Update current price secara berkala (daily/weekly)
2. 📝 Update notes jika ada perubahan strategy
3. 🎯 Review best/worst performer
4. 📊 Monitor total P/L trend

### Portfolio Management:
1. 🗂️ Organize by chain untuk clarity
2. 📈 Track performance per blockchain
3. 💰 Monitor total exposure per chain
4. 🎯 Set alerts untuk target price (manual notes)

## 🚀 Advanced Features (Manual)

### Target Setting
```
Notes field:
Entry: $0.0001
Target 1: $0.0005 (5x) ✅
Target 2: $0.001 (10x) 🎯
Stop Loss: $0.00005
```

### Strategy Notes
```
Notes field:
- Fundamental: Strong community
- Technical: Support at $0.0001
- Catalysts: CEX listing planned
- Exit plan: Scale out 50% at 5x, hold rest
```

## 📱 Responsive Design

- **Desktop**: Full grid view, all stats visible
- **Tablet**: 2-column layout
- **Mobile**: Stack layout, scroll untuk detail

## 🔥 Tips & Tricks

### Tip 1: Auto Calculate
Isi Investment dan Buy Price dulu, Coin Amount otomatis calculate!

### Tip 2: Quick Entry
Bisa skip current price dulu, update nanti saat mau cek P/L

### Tip 3: Multi-Entry
Beli coin sama di harga berbeda? Add as separate entries untuk tracking detail

### Tip 4: Best Performer
Check summary box untuk tau coin mana yang paling profit

### Tip 5: Portfolio Rebalancing
Review setiap minggu, decide mana yang di-hold atau take profit

## 🎓 Example Portfolio

### Memecoin Hunter Portfolio
```
Asset 1:
- Coin: n$PEPE
- Chain: ETH
- Investment: $200
- Buy: $0.00001
- Current: $0.00002
- P/L: +$200 (+100%) ✅

Asset 2:
- Coin: n$SHIB
- Chain: ETH  
- Investment: $150
- Buy: $0.00002
- Current: $0.000015
- P/L: -$37.5 (-25%) ❌

Asset 3:
- Coin: n$BONK
- Chain: Solana
- Investment: $100
- Buy: $0.000001
- Current: $0.0000015
- P/L: +$50 (+50%) ✅

Portfolio Summary:
- Total Investment: $450
- Current Value: $662.5
- Total P/L: +$212.5 (+47.2%)
- Best Performer: n$PEPE (+100%)
```

## 🔐 Data Storage

- Semua data tersimpan di **Firebase Firestore**
- Collection: `portfolio`
- Real-time sync across devices
- Secure dan scalable

## 🎨 Color Palette

Menggunakan Solana theme:
- Purple (#9945FF): Primary
- Green (#14F195): Success/Profit
- Red (#ff4757): Loss
- Black (#000000): Background

## ✅ Benefits

✅ **Complete Tracking**: Investment, amount, price, P/L  
✅ **Multi-Chain**: BSC, ETH, SOL, BASE  
✅ **Auto Calculate**: Coin amount & P/L otomatis  
✅ **Visual Indicators**: Green profit, red loss  
✅ **Portfolio Summary**: Total overview  
✅ **Best Performer**: Identify winner  
✅ **Notes & Strategy**: Document your plan  
✅ **Filter & Sort**: Easy navigation  

## 🚀 Next Steps

Sekarang Anda bisa:
1. ✅ Track semua crypto investment
2. ✅ Monitor profit/loss real-time
3. ✅ Manage multi-chain portfolio
4. ✅ Make data-driven decisions

**Start tracking your portfolio now! 💰🚀**
