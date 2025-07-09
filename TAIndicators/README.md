This library offers a comprehensive suite of enhanced **technical indicator** functions, building upon TradingView's built-in indicators. The primary advantage of this library is its expanded flexibility, allowing you to select from a wider range of _moving average types_ for _calculations_ and _smoothing_ across various indicators.  
  
The core difference between these functions and TradingView's standard ones is the ability to specify different moving average types beyond the default. While a standard **ta.rsi()** is fixed, the **rsi()** in this library, for example, can be smoothed by an 'SMMA (RMA)', 'WMA', 'VWMA', or others, giving you greater control over your analysis.  
  
█ **FEATURES**  
  
This library provides enhanced versions of the following popular indicators:  

* **Moving Average (ma):** A versatile MA function that includes optional secondary smoothing and Bollinger Bands.  

* **RSI (rsi):** Calculate RSI with an optional smoothed signal line using various MA types, plus built-in divergence detection.  

* **MACD (macd):** A MACD function where you can define the MA type for both the main calculation and the signal line.  

* **ATR (atr):** An ATR function that allows for different smoothing types.  

* **VWAP (vwap):** A comprehensive anchored VWAP with multiple configurable bands.  

* **ADX (adx):** A standard ADX calculation.  

* **Cumulative Volume Delta (cvd):** Provides CVD data based on a lower timeframe.  

* **Bollinger Bands (bb):** Create Bollinger Bands with a customizable MA type for the basis line.  

* **Keltner Channels (kc):** Keltner Channels with selectable MA types and band styles.  

* **On-Balance Volume (obv):** An OBV indicator with an optional smoothed signal line using various MA types.  

* **... and more to come!** This library will be actively maintained, with new useful indicator functions added over time.  

█ **HOW TO USE**  
  
To use this library in your scripts, import it using its publishing link. You can then call the functions directly.  
  
For example, to calculate a _Weighted Moving Average (WMA)_ and then smooth it with a _Simple Moving Average (SMA)_:  

```pinescript
import ActiveQuants/TAIndicators/1 as tai  
  
// Calculate a 20-period WMA of the close  
// Then, smooth the result with a 10-period SMA  
[myWma, smoothedWma] = tai.ma("WMA", close, 20, "SMA", 10)  
  
plot(myWma, color = color.blue)  
plot(smoothedWma, color = color.orange)
```

█ **Why Choose This Library?**  
  
If you're looking for more control and customization than what's offered by the standard built-in functions, this library is for you. By allowing for a variety of smoothing methods across multiple indicators, it enables a more nuanced and personalized approach to technical analysis. Fine-tune your indicators to better fit your trading style and strategies.

🔗 [View on TradingView ↗](https://www.tradingview.com/script/6GEomWSW-TAIndicators/)
