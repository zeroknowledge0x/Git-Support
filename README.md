# Git-Support

GitHub Actions bot for issue/PR triage and security.

## What it does

- Auto-comments on every new issue and pull request with a triage message.
- Detects sensitive information (wallet addresses, emails, private keys, seed phrases) and warns the author with **specific category details** (e.g., "BTC wallet address", "personal email address").
- Detects phishing and scam links in issue bodies and warns contributors not to follow unofficial support channels.
- Labels issues containing sensitive data with `contains-sensitive-info` and `needs-triage`.
- Labels issues with suspected scam links with `possible-scam` and `needs-triage`.
- **Auto-locks issues** containing sensitive information to prevent further data exposure by other commenters.
- Directs security concerns to GitHub's private vulnerability reporting.

## Security

This workflow warns users when they accidentally share:
- Cryptocurrency wallet addresses (BTC, ETH, TRON/TRC20)
- Private keys or seed phrases
- Personal email addresses in public issues

When sensitive info is detected, the bot:
1. Posts a warning listing exactly what was found (category-level, no value echoed)
2. Labels the issue for maintainer attention
3. Auto-locks the issue to prevent additional exposure

**Never share private keys, seed phrases, or wallet credentials in public issues.**
