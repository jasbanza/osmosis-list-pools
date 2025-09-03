# 🌊 Osmosis Pool List Fetcher

A simple web application to fetch and display liquidity pools from the Osmosis blockchain using the LCD API.

## 🚀 Live Demo

**[View Live Application](https://jasbanza.github.io/osmosis-list-pools/)**

## 📋 Features

- **Pool Data Fetching**: Retrieves pool information from Osmosis poolmanager API
- **Multiple Pool Types**: Supports Standard AMM, Concentrated Liquidity, and CosmWasm pools
- **Sorting Options**: Sort pools by newest or oldest first (by Pool ID)
- **Configurable Results**: Set maximum number of pools to fetch (1-100)
- **Pool Information Display**:
  - Pool ID and type
  - Swap and exit fees
  - Asset information and amounts
  - Pool-specific data based on type
- **Responsive Design**: Clean, modern interface that works on all devices
- **Real-time API Integration**: Direct connection to Osmosis LCD endpoints

## 🛠️ Technical Details

### API Endpoints
- **Primary**: `https://lcd.osmosis.zone/osmosis/poolmanager/v1beta1/all-pools`
- **Protocol**: REST API with pagination support
- **Data Format**: JSON response with pool arrays

### Pool Types Supported
1. **Standard AMM Pools** (`/osmosis.gamm.v1beta1.Pool`)
2. **Concentrated Liquidity Pools** (`/osmosis.concentratedliquidity.v1beta1.Pool`)
3. **CosmWasm Pools** (`/osmosis.cosmwasmpool.v1beta1.CosmWasmPool`)

### Features
- Pagination support with reverse ordering
- Error handling and fallback mechanisms
- Responsive grid layout
- Number formatting for large amounts
- Percentage formatting for fees

## 🏃‍♂️ Quick Start

### Option 1: Use the Live Demo
Simply visit the [live application](https://jasbanza.github.io/osmosis-list-pools/) in your browser.

### Option 2: Run Locally
1. Clone the repository:
   ```bash
   git clone https://github.com/jasbanza/osmosis-list-pools.git
   cd osmosis-list-pools
   ```

2. Open the application:
   ```bash
   # Simply open public/index.html in your browser
   # Or serve it with a local server:
   npx serve public
   # Or with Python:
   python -m http.server 8000 --directory public
   ```

3. Navigate to `http://localhost:8000` (if using a server) or directly open `public/index.html`

## 📖 Usage

1. **Set Pool Limit**: Choose how many pools you want to fetch (default: 10)
2. **Choose Sort Order**: Select newest first or oldest first
3. **Fetch Pools**: Click the "Fetch Pools" button
4. **View Results**: Browse through the pool cards showing detailed information

### Understanding Pool Information

- **Pool ID**: Unique identifier for each pool
- **Type**: The specific pool implementation (AMM, Concentrated Liquidity, etc.)
- **Swap Fee**: Fee charged for token swaps (as percentage)
- **Exit Fee**: Fee for exiting the pool (if applicable)
- **Assets**: Number and details of tokens in the pool

## 🔧 Configuration

The application uses these default settings:
- **Default Pool Limit**: 10 pools
- **Default Sort**: Newest first
- **API Timeout**: Browser default (usually 30 seconds)
- **Pagination**: Enabled with reverse ordering for newest pools

## 🌐 API Reference

### Osmosis LCD API
- **Base URL**: `https://lcd.osmosis.zone`
- **Endpoint**: `/osmosis/poolmanager/v1beta1/all-pools`
- **Parameters**:
  - `pagination.limit`: Number of pools to return
  - `pagination.reverse`: Boolean for reverse ordering
  - `pagination.key`: Pagination key for subsequent requests

### Response Format
```json
{
  "pools": [
    {
      "@type": "/osmosis.gamm.v1beta1.Pool",
      "id": "1",
      "pool_params": {
        "swap_fee": "0.002000000000000000",
        "exit_fee": "0.000000000000000000"
      },
      "pool_assets": [...],
      "total_shares": {...}
    }
  ],
  "pagination": {
    "next_key": "...",
    "total": "0"
  }
}
```

## 🔗 Links

- **Live Application**: [https://jasbanza.github.io/osmosis-list-pools/](https://jasbanza.github.io/osmosis-list-pools/)
- **GitHub Repository**: [https://github.com/jasbanza/osmosis-list-pools](https://github.com/jasbanza/osmosis-list-pools)
- **Osmosis Official**: [https://osmosis.zone](https://osmosis.zone)
- **Osmosis LCD API**: [https://lcd.osmosis.zone](https://lcd.osmosis.zone)

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- [Osmosis](https://osmosis.zone) for providing the excellent LCD API
- The Cosmos ecosystem for the robust blockchain infrastructure
- The open-source community for inspiration and tools

---

**Made with ❤️ for the Osmosis community**
