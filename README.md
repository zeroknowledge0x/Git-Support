# Git-Support

GitHub Actions bot for issue/PR triage and security.

## What it does

- Auto-comments on every new issue and pull request with a triage message.
- Detects sensitive information (wallet addresses, emails, private keys, seed phrases) and warns the author.
- Labels issues containing sensitive data with `contains-sensitive-info` and `needs-triage`.
- Directs security concerns to GitHub's private vulnerability reporting.

## Security

This workflow warns users when they accidentally share:
- Cryptocurrency wallet addresses (BTC, ETH, TRON/TRC20)
- Private keys or seed phrases
- Personal email addresses in public issues

**Never share private keys, seed phrases, or wallet credentials in public issues.**
