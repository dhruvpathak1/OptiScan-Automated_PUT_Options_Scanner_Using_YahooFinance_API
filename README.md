# Options API Filter

[![Python Version](https://img.shields.io/badge/python-3.8%2B-blue.svg)](https://www.python.org/downloads/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

A specialized tool for options traders that fetches PUT options data from Yahoo Finance and filters them based on specific validation criteria. The application includes an automated scheduler and desktop notifications for Windows users.

## 📌 Overview

This project aims to simplify the process of finding specific PUT options that fit a predefined strategy. By automating the fetching and filtering process, it saves time for traders who are looking for options within a certain timeframe and price range.

### Key Features

- **Automated Data Fetching**: Retrieves real-time options data from Yahoo Finance API.
- **Smart Filtering**:
  - Filters for expiration dates between 35 to 50 days from the current date.
  - Filters strike prices within 70% to 110% of the current stock price.
- **Periodic Scheduling**: Runs automatically every hour to provide updated data.
- **Desktop Notifications**: Sends a Windows toast notification upon completion of each execution cycle.
- **Clean Output**: Pretty prints relevant data including Strike Price, Bid, Ask, and Expiration Date.

## 🛠 Technical Information

### Architecture

1. **API Integration**: Uses `urllib.request` to communicate with the Yahoo Finance v7 API.
2. **Data Processing**: Parses JSON responses to identify expiration dates and filter PUT options.
3. **Task Scheduling**: Employs the `schedule` library to manage recurring execution.
4. **Notifications**: Utilizes `win10toast` for desktop alerts (compatible with Windows 10/11).

### Dependencies

The project is designed to be lightweight with minimal external dependencies:

- `schedule`: For job scheduling.
- `win10toast`: For Windows desktop notifications (Optional, only installed on Windows).
- *Built-in modules*: `pprint`, `datetime`, `json`, `math`, `time`, `os`, `urllib.request`.

## 🚀 Getting Started

### Prerequisites

- Python 3.8 or higher.

### Installation

1. **Clone the repository**:
   ```bash
   git clone https://github.com/yourusername/options_api.git
   cd options_api
   ```

2. **Install dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

### Running the Application

To start the scheduler:
```bash
python index.py
```
The script will run immediately and then continue to run once every hour.

## 📊 How it Works

1. **Step 1**: The script identifies expiration dates falling in the 35-50 day range.
2. **Step 2**: For each valid expiration date, it fetches all PUT options.
3. **Step 3**: It filters these options based on the strike price (70% - 110% of current price).
4. **Step 4**: Relevant details (Strike, Bid, Ask, etc.) are printed to the console.
5. **Step 5**: A Windows notification is triggered (if on Windows).

## 📁 Project Structure

```text
options_api/
├── assets/             # Images and icons
│   └── bull.ico        # Notification icon
├── index.py            # Main application script
├── requirements.txt    # Project dependencies
├── runtime.txt         # Python runtime version
└── README.md           # Documentation
```

## ⚠️ Disclaimer

This tool is for **educational and informational purposes only**. It does not constitute financial advice. Options trading involves significant risk. Always perform your own due diligence before making any investment decisions.

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

---
*Developed as an individual project to explore Financial APIs and Automation.*
