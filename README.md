<h1 align="center">📈 ICT Everything + MA Ribbon Add-On</h1>
<p align="center">A combined TradingView indicator for Smart Money Concepts + customizable Moving Average Ribbon</p>

---

<p align="center">
  <b>Author:</b> starditt<br>
  <b>Version:</b> 1.0<br>
  <b>Platform:</b> TradingView (Pine Script v5)
</p>

---

## ✨ Overview

This repository provides a **merged version** of:

### 1️⃣ ICT Everything  
A full-featured Smart Money Concepts indicator including:
- Killzones  
- Session ranges  
- FVGs  
- Liquidity tools  
- Market structure (BOS/CHOCH)  
- Mitigation blocks  
- PD Arrays  
- Previous Day / Week / Month levels  
- Volume analysis  
- SMC premium/discount zones  
…and much more.

### 2️⃣ MA Ribbon Add-On  
A lightweight 4-MA ribbon with complete customization:
- MA type  
- Length  
- Color  
- Visibility toggle  
- Global ON/OFF  

Designed to work **inside the same script**, perfect for **non-premium TradingView users** who need multiple indicators combined.

---

## 🎨 Features

### 🔹 1. ICT Everything (Full Engine)
All features from the original ICT Everything remain untouched and fully functional.  
Nothing is removed or modified — the module is injected safely at the bottom of the script.

---

### 🔸 2. MA Ribbon (Fully Customizable)

#### 🎛 Ribbon Controls
- Show/Hide entire ribbon  
- Enable/disable each MA (1–4) individually  
- Choose MA type:
  - SMA
  - EMA
  - SMMA (RMA)
  - WMA
  - VWMA  
- Change length  
- Change color  

#### 🚀 Default Behavior
All MA lines are **enabled by default** but can be toggled at any time.

---

## 🧠 Logic Behind the Ribbon

A single general-purpose function handles all MA types:

```pine
ma_func(src, len, type) =>
    switch type
        "SMA"        => ta.sma(src, len)
        "EMA"        => ta.ema(src, len)
        "SMMA (RMA)" => ta.rma(src, len)
        "WMA"        => ta.wma(src, len)
        "VWMA"       => ta.vwma(src, len)

Each MA is only calculated when:
Show Ribbon == true
AND
That MA is enabled

If not, the value becomes na, meaning TradingView will not plot it.

This keeps the script light even when combined with the heavy ICT logic.

🛠 Installation

Open Pine Editor on TradingView

Paste the entire ICT Everything script

At the very bottom, paste the MA Ribbon Add-On block

Click Add to chart

No original ICT code needs to be changed.

🖥 Overlay Mode

The indicator runs with:
overlay = true
This means:

ICT tools appear on chart

MA Ribbon also appears directly on chart

No extra panel is used

Perfect for clean charting.

⚠️ Technical Notes

ICT Everything is extremely large (thousands of lines + many visual objects).
Because of TradingView’s internal limits:

Avoid adding too many heavy features

Keep objects (labels, lines) under TV’s threshold

The Ribbon module is optimized to be very light

🌱 Future Enhancements

Potential upgrades available:

Gradient ribbon shading

MA clouds (MA1 vs MA2)

Trend detection based on slope

MA Cross alerts

Extended ribbon (8–12 MAs, Guppy-style)

Request if needed — these can be added easily.

⭐ Credits

Created by starditt
Built for traders who need a clean, optimized, all-in-one indicator.
