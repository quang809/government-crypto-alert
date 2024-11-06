### README

---

# Government Crypto Wallet Transaction Monitor

## Overview

The **Government Crypto Wallet Transaction Monitor** is a Python tool designed to monitor specific wallet addresses for transaction activity. When a transaction is detected, the bot sends an alert via email, making it useful for tracking high-profile wallet movements.

### Features

- **Monitors Wallet Transactions**: Checks the latest transaction for specified wallet addresses on the Ethereum blockchain.
- **Email Alerts**: Sends an email alert with transaction details if a new transaction is detected.
- **Periodic Checks**: Runs periodically, ensuring timely alerts without excessive API calls.

### Prerequisites

To use this script, you’ll need:

1. Python 3.x
2. Required libraries: `requests`, `smtplib` (built-in), and `email` (built-in)
3. An [Etherscan API key](https://etherscan.io/apis)
4. An email provider for SMTP (e.g., Gmail)

Install the required libraries with:

```bash
pip install requests
```

### Usage

#### Step 1: Update the API Key and Wallet Addresses

- **api_key**: Replace with your Etherscan API key.
- **addresses**: Add the wallet addresses you want to monitor in the `addresses` list.

#### Step 2: Configure Email Alerts

In `email_config`, add:

- **from_email**: Email address from which alerts are sent.
- **to_email**: Recipient’s email address.
- **smtp_server** and **smtp_port**: Email provider’s SMTP server and port (e.g., `smtp.gmail.com` for Gmail).
- **password**: Password for the `from_email` account.

Ensure that **two-factor authentication** is disabled or set up an **app-specific password** if using Gmail or another secure email provider.

#### Step 3: Run the Script

Run the script using:

```bash
py gov_wallet_monitor.py
```

The script will check each wallet address periodically (default: every 10 minutes) and send an alert email if a new transaction is detected.

### Example

To monitor wallet addresses `0xAddress1`, `0xAddress2`, and `0xAddress3`, set them in the `addresses` list:

```python
addresses = [
    "0xAddress1",
    "0xAddress2",
    "0xAddress3"
]
```

Then run:

```bash
py gov_wallet_monitor.py
```

### Important Notes

- **API Rate Limits**: Etherscan enforces rate limits on their API. Be mindful of check frequency to avoid being blocked.
- **Email Security**: Use a secure email account and follow email provider recommendations for app-specific passwords or two-factor authentication.

### Limitations

- **Platform-Specific**: This script is designed for Ethereum and Etherscan. To monitor other blockchains, consider alternative APIs and adjust the code accordingly.
- **Time Delay**: The script checks transactions periodically; transactions may go unreported if they occur and are finalized between intervals.

### Future Enhancements

- **Multi-Platform Support**: Extend support for other blockchains by integrating additional APIs.
- **Alternative Notification Methods**: Add support for SMS or Telegram alerts as alternatives to email.
- **Historical Data Analysis**: Log past transactions for long-term monitoring and analysis.

--- 

This script provides a straightforward way to track and alert on wallet activity for specific addresses. Let me know if you need additional customization or support for other blockchain networks!print('rksujiosnh')