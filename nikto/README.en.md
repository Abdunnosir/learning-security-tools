# Nikto

*[O'zbekcha o'qish](README.uz.md)*

Nikto is a web server scanner used during the recon phase of web application penetration testing. It doesn't exploit anything itself — it checks a target against a large database of known issues and flags what might be worth investigating further.

## What it looks for

- Server misconfigurations
- Default or dangerous files left on the server
- Insecure or publicly exposed files
- Outdated server or software versions
- Certain authentication-related issues
- CGI scripts and other web components
- Information disclosure about the server/software
- Known dangerous configurations and files

## Important note

Nikto is a **detection** tool, not an exploitation tool. A finding means "this might be an issue, worth checking manually" — not "this is confirmed exploitable." Always verify findings before relying on them.

## Common flags

| Flag | Purpose |
|------|---------|
| `-h` / `-host` | Target IP or domain |
| `-p` / `-port` | Specify port |
| `-ssl` | Force SSL/HTTPS |
| `-Tuning` | Choose which categories of tests to run |
| `-o` / `-output` | Save results to a file |
| `-Format` | Choose output format |
| `-Display` | Control what's shown on screen |
| `-vhost` | Specify a virtual host |
| `-id` | Provide HTTP authentication credentials |
| `-root` | Prepend a base directory to all requests |
| `-Plugins` | Run only specific plugins |
| `-Pause` | Add a delay between requests |
| `-timeout` | Set request timeout |
| `-useragent` | Change the User-Agent string |
| `-useproxy` | Route requests through a proxy |
| `-nolookup` | Skip DNS lookups |
| `-nocookies` | Don't use cookies |

## Example

```bash
nikto -h 10.10.10.10 -Tuning 2
```

`-Tuning 2` limits the scan to checks for misconfigurations and default pages, which keeps the scan faster and more focused than running every check available.
