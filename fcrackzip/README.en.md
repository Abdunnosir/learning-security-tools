# fcrackzip

*[O'zbekcha o'qish](README.uz.md)*

`fcrackzip` is a Kali Linux tool for recovering the password of a protected ZIP archive. It supports two attack modes: dictionary attack and brute force.

## Dictionary attack

```bash
fcrackzip -D -p <wordlist-file> <zip-file>
```

Example:

```bash
fcrackzip -D -p passwords.txt archive.zip
```

- `-D` — dictionary mode
- `-p` — path to the wordlist (or a single password to try)

## Brute force attack

```bash
fcrackzip -b -c a -l 4 archive.zip
```

- `-b` — switch to brute force mode
- `-c a` — character set to try (see table below)
- `-l` — password length to attempt

### Character set options for `-c`

| Flag | Character range |
|------|------------------|
| `a` | a-z |
| `A` | A-Z |
| `1` | 0-9 |
| `!` | special characters |

## Avoiding false positives

Because zip checksums can occasionally produce an incorrect match, it's worth confirming any "found" password before trusting it:

```bash
fcrackzip -D -p passwords.txt -u archive.zip
```

- `-u` — verifies each candidate by actually attempting to unzip the archive with it before reporting a match, filtering out false positives

## Useful flags summary

| Flag | Purpose |
|------|---------|
| `-D` | Dictionary attack |
| `-b` | Brute force attack |
| `-p` | Password list / starting password |
| `-c` | Character set (brute force) |
| `-l` | Password length (brute force) |
| `-u` | Verify match by actually unzipping |
| `-v` | Verbose output |
