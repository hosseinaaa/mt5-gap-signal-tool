# MT5 Gap Signal Generator (Free Arbitrage Tool)

![MT5 Gap Signal Tool](screenshot.png)

A free Windows tool that connects to your MetaTrader 5 (MT5) via gRPC and generates **BUY/SELL signals** based on price gaps.  
It is designed for arbitrage traders who want a simple external signal file that can be read by EAs, scripts, or other tools.

---

## Features

- Subscribes to a single symbol (e.g., XAUUSD).
- Calculates the average price `(Bid + Ask) / 2`.
- Detects gaps larger than a user-defined threshold.
- Writes a simple text signal (`buy` / `sell`) into a file (e.g. `trade_signal.txt`).
- Clean UI, easy to configure and monitor.

---

## How to use the tool

1. **Download**
   - Download the latest `MT5GapSignal.exe` from this repository.

2. **Run the EXE**
   - Double-click `MT5GapSignal.exe`.
   - Fill in:
     - **User (Login)** – your MT5 account login.
     - **Password** – your MT5 account password.
     - **MT5 Host** – the server host of your broker.
     - **MT5 Port** – the server port of your broker.
     - **Symbol** – for example: `XAUUSD`.
     - **Threshold (points)** – e.g. `10.0`.
     - **Signal file path** – where the `buy/sell` text file should be created.

3. Click **Start** to begin receiving quotes and generating signals.  
4. Your EA or external script can read the signal from the file and open/close trades.

---

## How to find your MT5 server host & port

There are a few ways to find the host/IP and port of your MT5 trading server.

### Method 1 – From inside MetaTrader 5 (recommended)

1. Open **MetaTrader 5**.
2. Go to:  
   **File → Login to Trade Account** or **File → Open an Account**.
3. In the server list, look for the server your broker gave you  
   (for example: `BrokerName-Demo`, `BrokerName-Live`).
4. In many cases, your broker will provide the server **address** and **port** in their documentation or in the MT5 "server" field.
5. Copy that host and port and paste them into the app fields:
   - **MT5 Host**
   - **MT5 Port**


### Method 2 – Using NetLimiter to inspect connections (advanced users)

If your broker does not clearly show host/port, you can inspect the MT5 terminal connections on your own computer.

> **Important:** Use this only on your own machine and with your own broker account.  
> Do not share your IP/port or login details with anyone.

1. Download and install **NetLimiter** on your PC.
2. Run MetaTrader 5 and log in to your trading account.
3. Open NetLimiter and find the process:
   - `terminal.exe` (the MT5 terminal).
4. Check the active connections of `terminal.exe`:
   - You will see one or more **remote IP addresses** and **ports**.
   - The remote IP is the trading server IP.
   - The remote port is the server port.
5. Use that IP and port as **MT5 Host** and **MT5 Port** in this app.
![photo_2025-11-12_09-18-59](https://github.com/user-attachments/assets/076d028a-9814-4f80-9bd1-16bf58229ac0)

---

## Requirements

- Windows OS
- MetaTrader 5 terminal (installed and logged in)
- .NET / Visual C++ runtimes if required by your broker’s bridge (depending on their installer)

---

## Disclaimer

This tool is provided **for free** and **as-is**.  
Trading and arbitrage involve risk. Always test on a demo account before using on live accounts.

---

## Contact / Custom development

If you need **custom tools** for MT4/MT5, arbitrage utilities, or integrations:

- **Telegram:** [@hosseinaaa](https://t.me/hosseinaaa)
- Author: *Hossein Ahmadi*
