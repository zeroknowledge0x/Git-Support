# Git-Support

GitHub Actions bot for issue/PR triage and security.

## What it does

- Auto-comments on every new issue and pull request with a triage message.
- **Scans comments on issues** for sensitive information and phishing links — not just the issue body.
- Detects sensitive information (wallet addresses, emails, private keys, seed phrases) and warns the author with **specific category details** (e.g., "BTC wallet address", "personal email address").
- Detects phishing and scam links in issue bodies **and comments** and warns contributors not to follow unofficial support channels.
- Labels issues containing sensitive data with `contains-sensitive-info` and `needs-triage`.
- Labels issues with suspected scam links with `possible-scam` and `needs-triage`.
- **Auto-locks issues** containing sensitive information to prevent further data exposure by other commenters.
- **Auto-locks issues** when scam links are detected in comments.
- Directs security concerns to GitHub's private vulnerability reporting.

## Security

This workflow warns users when they accidentally share:
- Cryptocurrency wallet addresses (BTC, ETH, TRON/TRC20)
- Private keys or seed phrases
- Personal email addresses in public issues or comments

When sensitive info is detected in an **issue body**, the bot:
1. Posts a warning listing exactly what was found (category-level, no value echoed)
2. Labels the issue for maintainer attention
3. Auto-locks the issue to prevent additional exposure

When sensitive info or scam links are detected in a **comment**, the bot:
1. Posts a warning on the issue listing the detected categories
2. Labels the issue for maintainer attention
3. Auto-locks the issue to prevent further phishing attempts

**Never share private keys, seed phrases, wallet credentials, or personal contact info in public issues or comments.**

## Scam detection

The bot detects known phishing patterns in both issue bodies and comments, including:
- Unofficial "support page" links (e.g., `officialgittechpage.web.app`)
- Suspicious email addresses (e.g., `gitactivebox@gmail.com`)
- "Live chat page" or "contact agent" lures

When detected, the issue is labeled `possible-scam` and locked.
