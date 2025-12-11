# ⚡ SN Cowboy Credits / Sats Market Dept Tracker

A real-time order book visualization for Cowboy Credits (CC) trading on Stacker News. This interactive chart displays buy and sell orders, market depth, and current pricing for the CC/sats market.

## 🎯 Features

- **Market Depth Chart**: Visual representation of buy and sell orders with cumulative volume
- **Order Book Display**: Real-time listings of all active bids and asks
- **Market Statistics**: Best bid, best ask, actual price (midpoint), and spread
- **Direct Links**: Click usernames to view Stacker News profiles, click 🔗 to see original posts
- **Stacker News Themed**: Dark mode design matching the Stacker News brand

## 📊 How It Works

The market depth chart visualizes:
- **Buy Orders (Green)**: Cumulative volume of buyers at each price point
- **Sell Orders (Red)**: Cumulative volume of sellers at each price point
- **Actual Price**: Midpoint between best bid and best ask (shown in yellow)

### Price Calculation

Each order contains:
- `cc`: Number of Cowboy Credits
- `sats`: Number of Bitcoin Satoshis
- `rate`: Automatically calculated as `sats / cc` (price per CC)

## 🤝 How to Submit New Offers

### Option 1: GitHub Pull Request (Recommended)

1. **Fork the repository** or clone it locally
2. **Edit the `index.html` file**
3. **Add your order** to the `orders` array around line 145:

```javascript
var orders = [
    // ... existing orders ...
    { user: '@YourUsername', type: 'buy', cc: 10, sats: 5, postId: 'POSTID' },
];
```

4. **Submit a Pull Request** with:
   - Title: "Add order: @YourUsername"
   - Description: Details of your offer (e.g., "Buying 10 CC for 5 sats")

### Option 2: Submit via Issue

If you're not familiar with Git:

1. **[Create a new GitHub Issue](https://github.com/4G0R4/cc-sat/issues/new)**
2. **Use the title**: "New Market Order: @YourUsername"
3. **Include in the description**:
   - Your Stacker News username (with @)
   - Type: `buy` or `sell`
   - Amount of CC you're offering/requesting
   - Amount of sats you're offering/requesting
   - Link to your Stacker News post announcing the offer

**Example Issue**:
```
Title: New Market Order: @alice

I'm buying 50 CC for 30 sats
- Username: @alice
- Type: buy
- CC: 50
- Sats: 30
- Post: https://stacker.news/items/1234567
```

### Option 3: Post on Stacker News

1. [**Create a post**]() on Stacker News announcing your offer
2. **Tag** one of the repository maintainers
3. **Include**: Amount of CC, amount of sats, buy/sell direction
4. **Someone will add** your order to the chart

## 📝 Order Data Format

Each order follows this structure:

```javascript
{
    user: '@username',        // Stacker News username with @
    type: 'buy' | 'sell',    // Order direction
    cc: number,              // Amount of Cowboy Credits
    sats: number,            // Amount of satoshis
    postId: 'string'         // Stacker News post ID (optional)
}
```

### Finding Your Post ID

Your Stacker News post ID is in the URL:
- URL: `https://stacker.news/items/1323640/r/AGORA`
- Post ID: `1323640`

## 🛠️ Contributing to Development

We welcome contributions! Here's how to help improve the chart:

### Setting Up

1. **Clone the repository**
```bash
git clone [repository-url]
cd cowboy-credits-market
```

2. **Open `index.html` in your browser**
   - No build process needed! It's a single HTML file
   - Uses Chart.js from CDN

### Ways to Contribute

#### 1. Add New Features
- Enhanced chart visualizations
- Additional market statistics
- Price history tracking
- Trading volume indicators
- Export functionality

#### 2. Improve UI/UX
- Better mobile responsiveness
- Accessibility improvements
- Animation enhancements
- Dark/light mode toggle

#### 3. Fix Bugs
- Check the Issues tab for known bugs
- Test edge cases (empty orders, extreme values)
- Improve error handling

#### 4. Documentation
- Improve this README
- Add code comments
- Create usage examples
- Write tutorials

**Questions?** 

There's an open discussion on this SN thread

## ⚠️ Disclaimer
This is an unofficial community tool. Always verify offers directly on Stacker News before trading. The maintainers are not responsible for any trades or disputes.
