# Sinolife — karyera (HR) landingi

Call-markaz sotuvchisi vakansiyasi. Statik sahifa, GitHub Pages: `main` ga push = deploy.
Jonli: https://hr.sinolife.uz/ (eski https://forwork7002.github.io/sinolife-karyera/ unga 301 bilan yo'naltiradi)

> Repo PUBLIC: token, webhook, xodim ismi/telefoni, ichki maosh jadvali — bu yerga yozilmaydi.

## Tuzilishi
- `index.html` — butun sahifa (CSS/JS ichida), uz + ru (`?lang=ru`), 5 savolli mini-test.
- `img/jamoa-720.webp`, `img/jamoa-1280.webp`, `img/jamoa-1280.jpg` — jamoa rasmi (lazy, og:image).

## Sozlamalar (`index.html` → `<script>` boshida)
| O'zgaruvchi | Hozir | Nima qiladi |
|---|---|---|
| `BOT` | `sinolifeuz_hrbot` | Barcha CTA shu botga olib boradi |
| `DEEP_LINK` | `false` | `true` bo'lsa havolalar `?start=l_<manba>_<blok>` bilan. Faqat bot `/start` parametrini saqlashni o'rgangach yoqiladi |
| `PIXEL_ID` | `''` | HR Meta pixel ID. Bo'sh — pixel yuklanmaydi. To'ldirilsa: PageView, Contact (CTA bosish), QuizStart/QuizComplete |
| `PAY` | `null` | Tasdiqlangan maosh qoidasi (`{foiz, chek}`) bo'lsa daromad kalkulyatori ko'rinadi |

Hodisalar har doim `window.dataLayer` ga ham yoziladi (`View`, `Contact`, `CtaTest`, `QuizStart`, `QuizComplete`, `Lang`).

## Domen: hr.sinolife.uz (19.11.2026 dan)
- DNS (DigitalOcean, `sinolife.uz` zonasi): `CNAME hr → forwork7002.github.io.` — egasining ruxsati bilan qo'shilgan.
- Repo ildizidagi `CNAME` fayli (`hr.sinolife.uz`) va GitHub Pages custom domain shu manzilga; «Enforce HTTPS» yoqilgan.
- `index.html`: `canonical`, `og:url`, `og:image` — `https://hr.sinolife.uz/`. Ichki yo'llar nisbiy (`img/...`).
- `CNAME` faylini o'chirish yoki DNS yozuvini olib tashlash saytni buzadi — avval ikkinchisini qaytaring.
