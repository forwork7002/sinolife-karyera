# Sinolife — karyera (HR) landingi

Call-markaz sotuvchisi vakansiyasi. Statik sahifa, GitHub Pages: `main` ga push = deploy.
Jonli: https://forwork7002.github.io/sinolife-karyera/

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

## hr.sinolife.uz ga ulash (tayyor, hali yoqilmagan)
`CNAME` fayli ataylab YO'Q: u DNS'dan oldin qo'shilsa, github.io manzili ishlamay qolgan domenga yo'naltiriladi.
1. DNS (DigitalOcean, `sinolife.uz` zonasi): `CNAME  hr  →  forwork7002.github.io.` (TTL 3600). Egasining ruxsati bilan.
2. `dig +short hr.sinolife.uz` → `forwork7002.github.io.` qaytgach: repo ildiziga `CNAME` fayli (bitta qator `hr.sinolife.uz`) → push.
3. GitHub → Settings → Pages: sertifikat chiqqach «Enforce HTTPS».
4. Tekshiruv: `curl -sI https://hr.sinolife.uz/` → 200; eski manzil 301 bilan yangi domenga o'tadi.
5. `index.html` dagi `og:image` manzilini `https://hr.sinolife.uz/img/jamoa-1280.jpg` ga almashtirish.
Sahifadagi yo'llar nisbiy (`img/...`), shuning uchun ikkala manzilda ham ishlaydi.
