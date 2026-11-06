# Security Hardening Scripts

Linux shell scripts that lock down permissions for common web apps and home directories — including SELinux-aware options where relevant.

Each tool lives in its own folder with a focused README. Point the script at your install root (or copy `settings.cfg`), then run it as root.

## Repository Structure

```text
security-hardening-scripts/
├── secure-homedir/
├── secure-mediawiki/
├── secure-phpbb/
└── secure-wordpress/
```

## Scripts

| Script | Description |
|--------|-------------|
| **secure-homedir** | Harden `/home/group/user` trees (and optional Apache `mod_userdir` `WWW` folders) with ownership and permission fixes |
| **secure-mediawiki** | Fix MediaWiki tree permissions; keeps `LocalSettings.php` locked down (`root:apache`, `640`) |
| **secure-phpbb** | Fix phpBB tree permissions; keeps `config.php` locked down (`root:apache`, `640`) |
| **secure-wordpress** | Fix WordPress tree permissions (secure / unsecure modes for updates); SELinux enforcing supported |

## Typical Use

1. Clone the repository (or copy the folder you need).
2. Edit the script (or `settings.cfg`) for your paths and options.
3. Run as root against the target hosts or directories.

WordPress includes both `secure-wp.sh` and `unsecure-wp.sh`: secure mode favors root-owned files; unsecure mode loosens ownership so core updates can run more easily.

## Author

**Adam Mallul (RaveMaker)**

- GitHub: https://github.com/RaveMaker
- Website: https://ravemaker.net
