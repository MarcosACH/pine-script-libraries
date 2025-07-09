# ActiveQuants Pine Script Libraries

A comprehensive collection of enhanced Pine Script libraries for TradingView, designed to provide advanced technical analysis tools with greater flexibility and customization options than standard built-in functions.

![Pine Script](https://img.shields.io/badge/Pine%20Script-v6-blue)
![TradingView](https://img.shields.io/badge/TradingView-Compatible-green)

## 🎯 Overview

This repository contains a suite of Pine Script libraries that extend TradingView's capabilities with enhanced technical indicators, candlestick analysis tools, market structure functions, and utility helpers. Each library is designed to be modular, well-documented, and easy to integrate into your scripts.

## 📚 Library Collection

| Library | Description | Key Features | TradingView Link |
|---------|-------------|--------------|------------------|
| [**TAIndicators**](./TAIndicators/) | Enhanced technical indicators with customizable moving average types | RSI, MACD, ATR, VWAP, Bollinger Bands, Keltner Channels with flexible smoothing options | [View →](https://www.tradingview.com/script/6GEomWSW-TAIndicators/) |
| [**CandleAnalysis**](./CandleAnalysis/) | Comprehensive candlestick pattern recognition and analysis | Pattern detection (Hammer, Doji, Shooting Star), body/wick measurements, directional analysis | [View →](https://www.tradingview.com/script/8FfhF3Iz-CandleAnalysis/) |
| [**MarketAnalysis**](./MarketAnalysis/) | Fibonacci-based market structure analysis | Fibonacci retracements and extensions for bullish/bearish scenarios | [View →](https://www.tradingview.com/script/TTqKBRT9-MarketAnalysis/) |
| [**Objects**](./Objects/) | Pine Script object and variable type utilities | Dynamic type detection and object management for debugging and validation | [View →](https://www.tradingview.com/script/1gEuhX73-Objects/) |

## 🚀 Quick Start

### 1. Import a Library

To use any library in your Pine Script, import it using the TradingView publishing link:

```pinescript
//@version=6
indicator("My Indicator", overlay=true)

// Import the TAIndicators library
import ActiveQuants/TAIndicators/2 as tai

// Use enhanced RSI with EMA smoothing
[rsiValue, smoothedRsi, _, _, bullDiv, bearDiv] = tai.rsi(close, 14, "EMA", 10)

plot(rsiValue, color=color.blue, title="RSI")
plot(smoothedRsi, color=color.orange, title="Smoothed RSI")
```

### 2. Explore Examples

Each library folder contains:

- **README.md** - Detailed documentation and usage examples
- **Source Code** - Complete Pine Script implementation
- **CHANGELOG.md** - Version history and breaking changes (where applicable)

## ✨ Key Advantages

### **Enhanced Flexibility**

- **Customizable Moving Averages**: Choose from SMA, EMA, WMA, VWMA, SMMA, and more for calculations and smoothing
- **Modular Design**: Use only the functions you need without bloating your script
- **Consistent APIs**: Standardized function signatures across all libraries

### **Advanced Features**

- **Built-in Divergence Detection**: Automatic bullish/bearish divergence identification
- **Multiple Timeframe Support**: Functions designed to work across different timeframes
- **Comprehensive Pattern Recognition**: Beyond basic patterns with customizable thresholds

### **Developer-Friendly**

- **Well-Documented**: Clear examples and parameter explanations
- **Type Safety**: Robust error handling and input validation
- **Performance Optimized**: Efficient algorithms that don't slow down your charts

## 📖 Documentation

### TAIndicators Library

Enhanced technical indicators with flexible moving average options:

```pinescript
import ActiveQuants/TAIndicators/2 as tai

// Calculate 20-period WMA, then smooth with 10-period SMA
[wma, smoothedWma] = tai.ma("WMA", close, 20, "SMA", 10)

// RSI with custom smoothing and divergence detection
[rsi, smoothRsi, _, _, bullDiv, bearDiv] = tai.rsi(close, 14, "EMA", 10)
```

### CandleAnalysis Library

Comprehensive candlestick analysis tools:

```pinescript
import MarcosACH/CandleAnalysis/1 as candle

// Basic candle direction
isBull = candle.isBullish()
isBear = candle.isBearish()

// Pattern recognition
isHammer = candle.isHammer(0.1, 2.0)  // 10% body, 2x wick ratio
isDoji = candle.isDoji(0.05)          // 5% body threshold
```

### MarketAnalysis Library

Fibonacci-based market structure analysis:

```pinescript
import MarcosACH/MarketAnalysis/1 as market

// Calculate Fibonacci retracement levels
fib618 = market.bullFibRet(low[20], high[0], 0.618)
fib382 = market.bullFibRet(low[20], high[0], 0.382)
```

## 🤝 Contributing

We welcome contributions! Please:

1. **Fork** the repository
2. **Create** a feature branch (`git checkout -b feature/amazing-feature`)
3. **Test** your changes thoroughly
4. **Commit** your changes (`git commit -m 'Add amazing feature'`)
5. **Push** to the branch (`git push origin feature/amazing-feature`)
6. **Open** a Pull Request

### Contribution Guidelines

- Follow existing code style and conventions
- Add comprehensive documentation for new functions
- Include usage examples in README files
- Test with multiple timeframes and instruments

## ⭐ Show Your Support

If these libraries help your trading analysis, please:

- ⭐ **Star** this repository
- 🔄 **Share** with the Pine Script community
- 💬 **Leave feedback** on TradingView script pages
