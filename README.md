MarketPulse

MarketPulse is a PHP-based stock market analysis platform that connects to the Upstox API to fetch real-time NSE (National Stock Exchange) data. It provides live market insights, OHLC tracking, and pattern-based scanning tools that help traders and analysts monitor stock performance effectively.
Designed as a lightweight web application, it combines secure authentication with automated data processing for quick market evaluation.

Features

Upstox API Integration: Connects to the official Upstox API for real-time and historical NSE data.

Live OHLC Data: Displays Open, High, Low, and Close values for various instruments.

Market Scanners: Automated scripts analyze patterns like Open = Low or Open = High to identify potential bullish or bearish signals.

Instrument Management: Fetches and lists available NSE instruments with symbol and token mapping.

Real-Time Updates: Data refreshes automatically at set intervals using optimized API calls.

User Authentication: Login and register system to manage user access securely.

Data Caching: Reduces API load by temporarily storing recent responses locally.

Simple UI: A responsive and minimalistic interface for ease of navigation.

Working

User Access and Authentication
Users begin by logging in or registering via a secure PHP session system (login.php, register.php, auth_guard.php). This ensures only authorized users can access the data dashboard.

API Connection Setup
The system uses an Upstox access token configured in the backend (config.php) to authenticate and fetch market data. API endpoints are used to retrieve instruments, OHLC data, and other relevant details.

Data Retrieval and Processing

PHP scripts like ohlc.php, scan_o_equal_lh.php, and nifty_open_0915.php request data from Upstox in JSON format.

Data is parsed, formatted, and filtered based on user queries or predefined logic (for example, filtering stocks where Open = Low or Open = High).

Processed results are either displayed directly on the frontend or stored temporarily in cache files.

Frontend Visualization
The HTML pages (index.html, front.html) load real-time results fetched from PHP scripts. Data is formatted in tables or simple visual elements for better readability. Users can refresh or navigate between market scans and OHLC dashboards.

Performance Optimization
To minimize repeated API calls, the system implements a lightweight caching mechanism in the /api/.cache directory. Cached data automatically updates after a short interval, ensuring performance and real-time accuracy.

Result Analysis
Users can view lists of stocks meeting specific conditions or download the data for further offline analysis. The system aims to provide actionable insights for intraday or short-term trading.

Main Functionalities

Login/Register	Secure user access with session handling
Fetch OHLC Data	Retrieves open, high, low, close values for symbols
Market Scan – O=H/O=L	Identifies bullish or bearish setups based on price patterns
Nifty 9:15 Snapshot	Displays early morning market condition at 9:15 AM
Instrument List Fetch	Loads complete NSE instrument data from Upstox
Data Caching	Reduces redundant API requests to speed up response
Auth Guard	Restricts access to API endpoints for unauthorized users
Technologies Used

Frontend: HTML, CSS, JavaScript

Backend: PHP

API Provider: Upstox API

Database: MySQL (for user and access management)

Environment: XAMPP / Apache

Installation Guide

Clone or download this repository.

git clone https://github.com/yourusername/marketpulse.git


Move the folder to your XAMPP htdocs directory.

Import the SQL file (if included) into phpMyAdmin to create required tables.

Configure your Upstox API access token and endpoints inside config.php.

Start Apache and MySQL from XAMPP Control Panel.

Open your browser and visit:

http://localhost/marketpulse/
