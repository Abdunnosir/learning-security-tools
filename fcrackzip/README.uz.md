# fcrackzip

*[Read in English](README.en.md)*

`fcrackzip` — Kali Linux'dagi parol bilan himoyalangan ZIP fayllarning parolini topish uchun ishlatiladigan vosita. U 2 xil hujum turini qo'llab-quvvatlaydi: dictionary attack va brute force.

## Dictionary attack

```bash
fcrackzip -D -p <parollar-fayli> <zip-fayl>
```

Misol:

```bash
fcrackzip -D -p passwords.txt archive.zip
```

- `-D` — dictionary rejimi
- `-p` — parollar ro'yxati fayli (yoki bitta parol)

## Brute force attack

```bash
fcrackzip -b -c a -l 4 archive.zip
```

- `-b` — brute force rejimiga o'tqizish
- `-c a` — qaysi belgilar to'plamidan foydalanish (pastdagi jadvalga qarang)
- `-l` — sinab ko'riladigan parol uzunligi

### `-c` uchun belgilar to'plami

| Flag | Belgilar diapazoni |
|------|---------------------|
| `a` | a-z |
| `A` | A-Z |
| `1` | 0-9 |
| `!` | maxsus belgilar |

## Xato natijalardan qochish

Zip fayl checksumi ba'zida noto'g'ri moslikni ko'rsatishi mumkin, shuning uchun topilgan parolni tasdiqlab olish kerak:

```bash
fcrackzip -D -p passwords.txt -u archive.zip
```

- `-u` — har bir nomzod parolni haqiqatan ham arxivni ochish orqali tekshiradi, shu bilan xato natijalarni filtrlab tashlaydi

## Foydali flaglar

| Flag | Vazifasi |
|------|----------|
| `-D` | Dictionary attack |
| `-b` | Brute force attack |
| `-p` | Parollar ro'yxati / boshlang'ich parol |
| `-c` | Belgilar to'plami (brute force uchun) |
| `-l` | Parol uzunligi (brute force uchun) |
| `-u` | Natijani unzip qilib tekshirish |
| `-v` | Batafsil chiqish (verbose) |
