# Nikto

*[Read in English](README.en.md)*

Nikto — veb-ilovalarni pentest qilishda recon (dastlabki tekshiruv) bosqichida ishlatiladigan veb-server skaner vositasi. U hech narsani o'zi ekspluatatsiya qilmaydi — saytni ma'lum muammolar bazasi bo'yicha tekshirib, qayerda qo'shimcha tekshiruv kerakligini ko'rsatadi.

## Nimalarni qidiradi

- Server konfiguratsiyasidagi xatolar
- Default va xavfli fayllar
- Insecure/ochiq fayllar
- Eski server yoki dastur versiyalari
- Ba'zi authentication bilan bog'liq muammolar
- CGI va boshqa web komponentlar
- Server/software haqida ma'lumot
- Ma'lum xavfli konfiguratsiyalar va fayllar

## Muhim eslatma

Nikto **aniqlovchi** vosita, ekspluatatsiya qiluvchi emas. Topilgan narsa "bu muammo bo'lishi mumkin, qo'lda tekshirib ko'rish kerak" degani, "bu aniq ekspluatatsiya qilinadi" degani emas. Har doim natijalarni qo'lda tasdiqlang.

## Asosiy flaglar

| Flag | Vazifasi |
|------|----------|
| `-h` / `-host` | Target IP/domen |
| `-p` / `-port` | Port ko'rsatish |
| `-ssl` | SSL/HTTPS majburlash |
| `-Tuning` | Qaysi turdagi testlarni bajarishini tanlash |
| `-o` / `-output` | Natijani faylga saqlash |
| `-Format` | Natija formatini tanlash |
| `-Display` | Ekranga qanday ma'lumot chiqarishni boshqarish |
| `-vhost` | Virtual Host berish |
| `-id` | HTTP authentication berish |
| `-root` | Barcha requestlarga boshlang'ich directory qo'shish |
| `-Plugins` | Faqat kerakli pluginlarni ishlatish |
| `-Pause` | Requestlar orasiga kutish qo'yish |
| `-timeout` | Request timeout |
| `-useragent` | User-Agent o'zgartirish |
| `-useproxy` | Proxy orqali yuborish |
| `-nolookup` | DNS lookup qilmaslik |
| `-nocookies` | Cookie ishlatmaslik |

## Misol

```bash
nikto -h 10.10.10.10 -Tuning 2
```

`-Tuning 2` skanerni faqat misconfiguration va default pagelarni tekshirish bilan cheklaydi — bu barcha tekshiruvlarni ishga tushirishdan tezroq va aniqroq natija beradi.
