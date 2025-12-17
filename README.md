<img width="1407" height="241" alt="↯ Stacker.News CC/SAT Exchange Order Book" src="https://github.com/user-attachments/assets/979070a4-fe32-4de6-9324-cbe75922765f" />

A decentralized peer-to-peer order book for trading Cowboy Credits (CC) and Satoshis (SAT) on Stacker.News, powered by GitHub Gists.

**Live Order Book:** [https://4g0r4.github.io/cc-sat/](https://4g0r4.github.io/cc-sat/)

**Read the SN announcement** [https://stacker.news/items/1349267](https://stacker.news/items/1349267/r/AGORA)

## 🌟 Features

### 📊 Real-Time Market Data
- **Live Order Book** - See all active buy (bids) and sell (asks) orders
- **Market Depth Chart** - Visual representation of cumulative order volume
- **KPI Dashboard** - Track Best Bid, Best Ask, Actual Price (mid-market), and Spread
- **Automatic Updates** - Orders load instantly from GitHub Gist

### 💰 Smart Trading Tools
- **Dual Volume Input** - Enter either CC volume, SAT volume, or both
- **Automatic Price Calculation** - Fill in 2 of 3 fields (Price/CC/SAT) and the third calculates automatically
- **Sybil Fee Calculator** - See the 30% sybil fee impact on every order with red badges
- **Live Fee Preview** - Real-time calculation showing total, fees, and net amounts

### 🔗 Smart Contact Linking
- **Stacker.News usernames** - Automatically links to user profiles (@username or username)
- **Nostr npubs** - Links to njump.me for nostr public keys
- **Info tooltips** - Hover over ℹ️ to see order notes and details

### 🔐 Decentralized & Open
- **No login required** to view orders
- **GitHub Gist storage** - All data is public and verifiable
- **Community maintained** - Anyone can submit orders via GitHub or Stacker.News
- **Open source** - Full transparency, fork and modify as needed

## 🚀 Quick Start

### View Orders (No Setup Required)
Simply visit [https://4g0r4.github.io/cc-sat/](https://4g0r4.github.io/cc-sat/) to see all active orders.

### Submit Orders via Stacker.News
Comment on the [announcement post](https://stacker.news/items/1329607/r/AGORA) with your order details:
- Order type (BUY/SELL)
- Price (CC/SAT rate)
- Volume (in CCs)
- Contact info
- Any notes about fees, territory founder status, etc.

### Submit Orders via GitHub

1. **Get a GitHub Personal Access Token**
   - Go to [github.com/settings/tokens](https://github.com/settings/tokens)
   - Click "Generate new token (classic)"
   - Select the `gist` scope
   - Generate and copy your token

2. **Configure the Order Book**
   - Click `[⚙] Settings` on the order book
   - Paste your GitHub token
   - Save configuration

3. **Submit Your Order**
   - Click `[✎] Submit Order`
   - Fill in order details
   - Submit (automatically saved to the shared Gist)

## 📖 How It Works

### Order Book Structure
Orders are stored in a public GitHub Gist (`a52699d9f7209a225ae6d10d77d53eca`) as JSON:

```json
{
  "asks": [
    {
      "id": "1734450123456",
      "price": 0.85,
      "volume": 10000,
      "contact": "@stackernaut",
      "notes": "Territory founder - fees included",
      "timestamp": "2024-12-17T12:00:00.000Z"
    }
  ],
  "bids": [
    {
      "id": "1734450234567",
      "price": 0.82,
      "volume": 15000,
      "contact": "npub1abc...",
      "notes": "Bulk purchase - DM for details",
      "timestamp": "2024-12-17T13:00:00.000Z"
    }
  ]
}
```

### Understanding Sybil Fees
Stacker.News currently implements a 30% sybil fee on all transactions:
- **When buying CCs**: You pay 1.3 sats per CC (30% fee included)
- **Territory founders**: Receive 21% back on their territories
- **The order book**: Shows the effective price AND the fee amount separately

Example:
- Order: 10,000 CC @ 0.85 sats/CC
- Total: 8,500 sats
- 30% Sybil Fee: 2,550 sats (shown in red badge)
- Net to seller: 5,950 sats

## 🎯 Order Types

### BIDs (Buy Orders)
- You want to **buy CC** with sats
- Listed in **green** with highest price first
- Higher prices = better for sellers

### ASKs (Sell Orders)
- You want to **sell CC** for sats
- Listed in **red** with lowest price first
- Lower prices = better for buyers

## 🔧 Technical Details

### Built With
- **Pure HTML/CSS/JavaScript** - No build process, runs entirely in browser
- **Chart.js** - For market depth visualization
- **GitHub Gist API** - For decentralized data storage
- **Google Sans Font** - Matching Stacker.News aesthetics

### Browser Storage
Uses localStorage to remember your GitHub token (stored locally, never transmitted except to GitHub API).

### Data Storage
All orders are stored in GitHub Gist `a52699d9f7209a225ae6d10d77d53eca`:
- [View the Gist](https://gist.github.com/4G0R4/a52699d9f7209a225ae6d10d77d53eca)
- Public and auditable
- Can be forked for private order books

## 🤝 Contributing

### Report Issues
Found a bug or have a feature request? [Open an issue](https://github.com/4G0R4/cc-sat/issues/new)

### Submit Pull Requests
1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

### Maintain Orders
Help keep the order book clean:
- Remove completed/expired orders (click × button)
- Update your own orders when prices change
- Add detailed notes to help others understand your offer

## 📊 Market Data Examples

### Current Market (Example)
```
Best Bid:  0.8200 CC/SAT (buying CCs)
Best Ask:  0.8500 CC/SAT (selling CCs)
Mid Price: 0.8350 CC/SAT
Spread:    0.0300 CC/SAT
```

### Reading the Order Book

**ASKS (Selling CC for sats)**
```
Price    Volume      Contact         Fee
0.8500   10,000 CC   @seller1        -2,550 sats
0.8700   5,000 CC    @seller2        -1,305 sats
```

**BIDS (Buying CC with sats)**
```
Price    Volume      Contact         Fee
0.8200   15,000 CC   @buyer1         -3,690 sats
0.8000   20,000 CC   @buyer2         -4,800 sats
```

## ⚠️ Important Notes

### Sybil Fees
- The order book displays the **effective CC/SAT rate** after considering fees
- Red badges show the exact sybil fee amount for each order
- Territory founders can offer better rates (they receive 21% back)

### Trust & Safety
- This is a **peer-to-peer marketplace** - conduct your own due diligence
- Verify contact information before trading
- Use escrow or trusted intermediaries for large trades
- The order book is a **discovery tool**, not an escrow service

### Data Accuracy
- Orders are community-maintained
- Some orders may be outdated - always verify before trading
- Remove your orders when completed (click × button)

## 📜 License

🄯 Copyleft - This project is open source and free to use, modify, and distribute.

## 🔗 Links

- **Live Order Book**: [https://4g0r4.github.io/cc-sat/](https://4g0r4.github.io/cc-sat/)
- **GitHub Repository**: [https://github.com/4G0R4/cc-sat](https://github.com/4G0R4/cc-sat)
- **Announcement Post**: [Stacker.News](https://stacker.news/items/1349267/r/AGORA)
- **Issue Tracker**: [GitHub Issues](https://github.com/4G0R4/cc-sat/issues)
- **Order Data (Gist)**: [View Raw Data](https://gist.github.com/4G0R4/a52699d9f7209a225ae6d10d77d53eca)

## 💡 Tips

### For Buyers
- Sort by lowest ask price for best deals
- Check territory founder status in notes
- Verify sybil fees are included in the quoted price
- Contact sellers directly via their SN profile or nostr

### For Sellers
- Be clear about whether sybil fees are included
- Mention territory founder status for better rates
- Update or remove orders when volumes change
- Respond promptly to interested buyers

### For Territory Founders
- You receive 21% back on transactions in your territory
- This allows you to offer fairer rates around 0.91-0.93 sats/CC profitably
- Mention this in your order notes to attract buyers

## 🙏 Acknowledgments

Special thanks to:
- **[@harrym](https://stacker.news/harrym/r/AGORA)** for valuable feedback on order matching and market mechanics
- The **Stacker.News community** for early adoption and testing [#1329607](https://stacker.news/items/1329607/r/AGORA)
- Everyone contributing orders and helping build liquidity

---

**Start trading today at [https://4g0r4.github.io/cc-sat/](https://4g0r4.github.io/cc-sat/)**
