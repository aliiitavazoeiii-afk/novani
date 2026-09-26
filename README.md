# Novani Wholesale

نسخه اولیه سایت عمده‌فروشی نووانی با تمرکز روی کاتالوگ محدود، موجودی انبار، روند تولید، پیشنهاد ویژه و تماس مستقیم.

## ساختار صفحه اصلی

هر بخش شناسه ثابت دارد تا در تغییرات بعدی دقیقاً قابل اشاره باشد:

- `hero` — هیرو و CTA اصلی
- `availability` — موجود در انبار / در روند تولید
- `products` — پنج محصول اصلی
- `special-offer` — انبارتکانی / پیشنهاد ویژه عمده
- `benefits` — چرا نووانی
- `order-guide` — روند ثبت سفارش
- `contact` — تماس مستقیم، آدرس و نقشه
- `footer` — فوتر

در HTML علاوه بر `id`، برای بخش‌های اصلی `data-section` هم وجود دارد.

## فایل‌ها

- `index.html` — ساختار و محتوای صفحه
- `styles.css` — تمام طراحی و responsive behavior
- `app.js` — منوی موبایل و رفتارهای سبک رابط کاربری
- `Dockerfile` — اجرای production با nginx
- `docker-compose.yml` — اجرای سریع روی VPS
- `nginx.conf` — تنظیمات nginx و cache فایل‌های static

## اجرای محلی

می‌توان `index.html` را مستقیم باز کرد، یا با Python:

```bash
python3 -m http.server 8080
```

سپس:

```text
http://localhost:8080
```

## اجرای روی سرور با Docker

```bash
git clone https://github.com/aliiitavazoeiii-afk/novani.git /opt/novani
cd /opt/novani
docker compose up -d --build
```

پورت پیش‌فرض:

```text
8088
```

یعنی در reverse proxy باید دامنه به `127.0.0.1:8088` متصل شود.

## جایگزینی تصاویر

در نسخه اول عمداً هیچ تصویر واقعی قرار نگرفته است. Placeholderها با متن‌های زیر مشخص‌اند:

- عکس هیرو
- عکس موجودی انبار
- عکس روند تولید
- عکس محصول 01 تا 05
- عکس محصول ویژه
- Google Map

## تصمیم‌های طراحی فعلی

- سبک بصری الهام‌گرفته از Sober: مینیمال، editorial، فضای سفید زیاد
- فارسی و RTL
- mobile-first responsive behavior
- بدون framework سنگین
- مسیر خرید فعلی: مشاهده → وضعیت موجودی → محصول → تماس / ثبت سفارش
- فروش ویژه به جای Shop Page عمومی

## موارد مرحله بعد

1. لوگوی واقعی Novani
2. Hero image واقعی
3. نام و مشخصات ۵ محصول
4. قیمت‌های عمده
5. رنگ/سایز/تعداد و فرم سفارش واقعی
6. تلفن، واتساپ و آدرس
7. Google Map
8. اتصال به backend برای مدیریت موجودی و سفارش‌ها
9. صفحات اختصاصی محصول و SEO schema
