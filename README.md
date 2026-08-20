oracrouter vs opencode vs 9router vs omnirouter

## جدول مقایسه‌ای

| ویژگی | 9router | OmniRoute | OpenCode | OpenCode + OmniRoute |
| :--- | :--- | :--- | :--- | :--- |
| **نقش اصلی** | روتر محلی برای اتصال ابزارهای کدنویسی به ۴۰+ سرویس‌دهنده  | روتر محلی با بیش از ۵۰۰ مدل از ۲۹۰ سرویس‌دهنده (حدود ۹۰ مورد رایگان)  | عامل کدنویسی متن‌باز در ترمینال  | ترکیب عامل کدنویسی با روتر برای دسترسی به مدل‌های رایگان و مدیریت بهتر محدودیت‌ها  |
| **نحوه کار** | از لاگین‌های شما (Claude, Codex, GitHub, Copilot) استفاده می‌کند و در صورت محدودیت، به مدل‌های رایگان یا ارزان‌تر سقوط می‌کند  | درخواست را به بهترین مدل بر اساس کیفیت و هزینه مسیریابی می‌کند  | خود کدنویسی را انجام می‌دهد، حلقه‌های عامل را اجرا می‌کند و خطاها را برطرف می‌سازد  | OpenCode کار کدنویسی را انجام می‌دهد و OmniRoute مدل مناسب را انتخاب می‌کند  |
| **مزایا** | **ذخیره‌سازی توکن RTK** (۲۰-۴۰٪ صرفه‌جویی)، سقوط خودکار به لایه‌های رایگان، پشتیبانی از حساب‌های متعدد  | **کنترل هزینه و عملکرد بهینه**، انتخاب هوشمند مدل بر اساس پیچیدگی سوال، عملکرد بهتر در شرایط محدودیت همزمانی  | کارآمدی بالا در مصرف توکن، متن‌باز، دارای مدل‌های رایگان داخلی  | ترکیب قدرت کدنویسی OpenCode با صرفه‌جویی و انعطاف‌پذیری OmniRoute  |
| **معایب و ریسک‌ها** | **دارای آسیب‌پذیری‌های امنیتی متعدد**: خروجی کلیدهای API، اجرای کد از راه دور بدون احراز هویت، دورزدن قفل ورود، کلید JWT پیش‌فرض  | نیاز به راه‌اندازی جداگانه دارد و برای کار به یک عامل کدنویسی نیازمند است  | مدل‌های رایگان داخلی به محدودیت نرخ برخورد می‌کنند  | پیچیدگی بیشتر در راه‌اندازی اولیه |
| **موارد استفاده** | کاربرانی که اشتراک‌های پولی دارند و می‌خواهند از آنها بهینه‌تر استفاده کنند  | کاربرانی که به دنبال کدنویسی رایگان با قابلیت Failover خودکار هستند  | کدنویسی مستقل با هزینه کمتر نسبت به مدل‌های گران‌قیمت  | راه‌اندازی ایده‌آل برای کدنویسی رایگان و بدون وقفه  |

---

## توضیحات تکمیلی

**9router** بیشتر یک روتر است که ابزارهای شما را به سرویس‌دهندگان متصل می‌کند، اما وجود آسیب‌پذیری‌های امنیتی بحرانی یک نگرانی جدی است . طبق گزارشات، این روتر امکان خروجی کلیدهای API و اجرای کد از راه دور را بدون احراز هویت فراهم می‌کند .

**OmniRoute** از نظر علمی عملکرد بهتری در بهینه‌سازی هزینه و کیفیت دارد . اما باید توجه داشت که **OpenCode و OmniRoute رقیب یکدیگر نیستند**؛ بلکه دو لایه مختلف هستند که می‌توانند مکمل هم کار کنند .

**OpenCode** خود یک عامل کدنویسی کامل است که با مدل‌های رایگان داخلی کار می‌کند، اما محدودیت نرخ دارد. ترکیب OpenCode با OmniRoute راه‌حل رایجی است که مشکل محدودیت را حل می‌کند .

**توصیه نهایی**:
- اگر قصد استفاده از 9router را دارید، **حتماً** نسخه‌های به‌روز را بررسی و اقدامات امنیتی را جدی بگیرید .
- برای یک راه‌حل پایدارتر و کم‌ریسک‌تر، ترکیب **OpenCode + OmniRoute** گزینه مناسب‌تری به نظر می‌رسد .

- هوش مصنوعی پینوکیو پدرژپتو رایگان
- ## OrcaRouter چیست؟

**OrcaRouter** یک دروازه (Gateway) API کاملاً سازگار با پروتکل OpenAI است که نقش یک روتر هوشمند را برای درخواست‌های مدل‌های زبانی بزرگ ایفا می‌کند. به زبان ساده‌تر، شما با یک کلید API و یک آدرس endpoint، به بیش از ۲۰۰ مدل از سرویس‌دهندگان مختلف دسترسی پیدا می‌کنید و OrcaRouter تصمیم می‌گیرد که هر درخواست را به کدام مدل ارسال کند.

### تفاوت کلیدی OrcaRouter با 9router و OmniRoute

برخلاف 9router و OmniRoute که روی **دستگاه خود شما** اجرا می‌شوند و از حساب‌های کاربری (OAuth) خودتان برای اتصال به سرویس‌دهندگان استفاده می‌کنند، OrcaRouter یک **سرویس ابری (یا خودمیزبان)** است.

| ویژگی | 9router / OmniRoute | OrcaRouter |
| :--- | :--- | :--- |
| **نحوه اجرا** | روی دستگاه محلی شما | سرویس ابری (یا خودمیزبان با نسخه Lite) |
| **نحوه احراز هویت** | استفاده از حساب‌های OAuth و کلیدهای API شخصی شما (BYOK) | استفاده از کلید API خود OrcaRouter و کلیدهای API شما (BYOK) |
| **هزینه** | رایگان (شما هزینه سرویس‌دهندگان را می‌پردازید) | **بدون مارک‌آپ روی توکن‌ها** (هزینه سرویس‌دهندگان + طرح‌های اختیاری برای امکانات تیمی) |
| **امنیت** | ریسک‌های امنیتی بالقوه (مشکل 9router) | مدیریت متمرکز و امن‌تر کلیدها در فضای ابری |

---

## ویژگی‌های کلیدی OrcaRouter

### ۱. مسیریابی هوشمند بدون مارک‌آپ
OrcaRouter با افتخار اعلام می‌کند که **هیچ سودی روی قیمت توکن‌ها نمی‌گیرد**. شما دقیقاً همان قیمتی را می‌پردازید که سرویس‌دهنده اصلی اعلام کرده است. درآمد OrcaRouter از طرح‌های اشتراکی برای امکانات پیشرفته‌تر (مثل مدیریت تیم) تأمین می‌شود، نه از گران‌تر فروختن توکن‌ها.

### ۲. استراتژی‌های مسیریابی متنوع
شما می‌توانید استراتژی مسیریابی را انتخاب کنید. OrcaRouter استراتژی‌های مختلفی ارائه می‌دهد که مهم‌ترین آنها عبارتند از:

*   **Cheapest (ارزان‌ترین):** ارزان‌ترین مدل زنده را انتخاب می‌کند. این حالت پیش‌فرض روتر `orcarouter/auto` است.
*   **Quality (بالاترین کیفیت):** بهترین مدل را از نظر کیفیت انتخاب می‌کند، بدون توجه به قیمت.
*   **Balanced (متوازن):** گزینه‌ای با قیمت مناسب که کیفیت قابل قبولی دارد را انتخاب می‌کند. این حالت پیش‌فرض برای روترهای جدید است.
*   **Adaptive (انطباق‌پذیر):** یک روش پیشرفته که از **یادگیری ماشین (LinUCB contextual bandit)** برای یادگیری از ترافیک واقعی شما استفاده می‌کند و بین کیفیت، هزینه، تأخیر و قابلیت اطمینان تعادل برقرار می‌کند. این استراتژی دو زیرحالت دارد:
    *   **Standard:** همه مدل‌های مجاز را برای هر درخواست در نظر می‌گیرد.
    *   **Gated:** درخواست‌ها را به دو دسته ساده (mundane) و سخت (hard) تقسیم کرده و از مدل‌های متفاوتی برای هر کدام استفاده می‌کند.

### ۳. قابلیت Failover و کش کردن
اگر مدلی پاسخ ندهد یا به محدودیت نرخ (Rate Limit) برخورد کند، OrcaRouter به‌طور خودکار درخواست را به مدل دیگری **در کمتر از ۵۰ میلی‌ثانیه** هدایت می‌کند (mid-stream failover). همچنین درخواست‌های تکراری را در حافظه‌ی کش (Redis یا LRU داخلی) ذخیره می‌کند تا پاسخ‌ها با هزینه صفر و با سرعت بالا برگردانده شوند.

### ۴. نصب و راه‌اندازی آسان
استفاده از OrcaRouter به‌سادگی تغییر چند خط کد در پروژه‌هایی است که از کتابخانه‌های OpenAI استفاده می‌کنند:

```python
from openai import OpenAI

client = OpenAI(
    base_url="https://api.orcarouter.ai/v1",
    api_key="YOUR_ORCAROUTER_API_KEY",
)

response = client.chat.completions.create(
    model="orcarouter/auto",  # OrcaRouter خودش بهترین مدل را انتخاب می‌کند
    messages=[{"role": "user", "content": "سلام!"}],
)
```

## نسخه OrcaRouter-Lite (خودمیزبان)

اگر به دنبال راه‌اندازی محلی و حفظ حریم خصوصی بیشتر هستید، پروژه **OrcaRouter-Lite** یک نسخه رایگان و متن‌باز از OrcaRouter است که می‌توانید آن را روی سرور خود اجرا کنید. این نسخه ویژگی‌های اصلی مانند مسیریابی با استراتژی‌های `balanced`, `cheapest`, `fastest`, `quality` و کش کردن را دارد، اما برای امکانات پیشرفته‌تر مانند Adaptive Routing باید از نسخه ابری استفاده کنید.

## جمع‌بندی و توصیه نهایی

**OrcaRouter** یک راه‌حل حرفه‌ای، امن و با هزینه‌ی شفاف برای مسیریابی هوشمند درخواست‌های مدل‌های زبانی است.

*   اگر به دنبال یک راه‌حل **ساده، امن و آماده به کار** هستید که نیازی به مدیریت کلیدهای API متعدد روی دستگاه خود نداشته باشید، **OrcaRouter ابری** انتخاب عالی است.
*   اگر به **دسترسی محلی و کنترل کامل** روی داده‌ها و سرور خود نیاز دارید، نسخه **OrcaRouter-Lite** گزینه‌ی مناسبی است.

با توجه به ریسک‌های امنیتی مطرح‌شده برای 9router و ماهیت سرویس ابری OrcaRouter، به نظر می‌رسد OrcaRouter گزینه‌ای مطمئن‌تر و کم‌دردسرتر برای تیم‌های توسعه‌دهنده باشد.
-
-
-
-
-
-
-
- The user is asking "چه شکل استفاده میشود" (How is it used / In what form is it used). They're asking about how to actually use the personal DoH endpoint from Gateway - i.e., how to configure it in a browser or system.

Let me provide practical instructions on how to use the DoH endpoint from Cloudflare Gateway in browsers and operating systems.

Agent
نحوه استفاده از DoH شخصی Gateway
وقتی تو Zero Trust یک DNS Location ساختید و DoH endpoint دریافت کردید (مثلاً abcdefg.cloudflare-gateway.com)، می‌تونید این‌طوری ازش استفاده کنید:

1. در مرورگر Firefox
Settings → Privacy & Security → DNS over HTTPS → Max Protection

روی Choose Provider کلیک کنید
Custom رو انتخاب کنید
این URL رو وارد کنید:
https://abcdefg.cloudflare-gateway.com/dns-query
ذخیره کنید
2. در Chrome / Edge / Brave
فعلاً DoH سفارشی فقط با providerهای شناخته‌شده کار می‌کنه (مثل Cloudflare 1.1.1.1). DoH اختصاصی Gateway به‌طور مستقیم پشتیبانی نمی‌شه. برای استفاده باید از Cloudflare One Client (WARP) استفاده کنید:

Cloudflare One Client رو نصب کنید
تنظیمات رو روی حالت WARP یا DoH only بذارید
Gateway به‌صورت خودکار کوئری‌های DNS رو از طریق endpoint شما ارسال می‌کنه
3. در سیستم‌عامل (Windows 11 / macOS / Linux)
Windows 11:
Settings → Network & Internet → DNS server assignment → Edit
DoH رو روشن کنید
این آدرس رو وارد کنید:
https://abcdefg.cloudflare-gateway.com/dns-query
macOS:
System Settings → Network → Wi-Fi → Details → DNS
DoH endpoint رو به‌صورت URL وارد کنید
Linux:
از systemd-resolved یا dnscrypt-proxy استفاده کنید:

# systemd-resolved
sudo systemctl edit systemd-resolved
[Resolve]
DNS=abcdefg.cloudflare-gateway.com
DNSOverTLS=yes
4. با Cloudflare One Client (ساده‌ترین روش)
این روش پیشنهادیه چون خودش DoH رو مدیریت می‌کنه:

Cloudflare One Client رو از داشبورد Zero Trust دانلود کنید
با اکانت Zero Trust خودتون لاگین کنید
Client به‌صورت خودکار از DoH endpoint شما استفاده می‌کنه
policyهای Gateway (فیلترینگ، بلاک دامنه و غیره) به‌صورت خودکار اعمال می‌شن
نکته مهم
DoH endpoint شما فقط زمانی کار می‌کنه که دستگاه به اکانت Zero Trust شما متصل باشه (یا از طریق WARP یا با token احراز هویت)
بدون احراز هویت، endpoint DoH Gateway به کوئری‌های ناشناس جواب نمی‌ده
کدوم روش رو می‌خواید استفاده کنید؟ اگر Cloudflare One Client رو می‌خواید، می‌تونم کمکتون کنم نصبش کنید.

هردو


See reasoning
→
Ran Retrieve existing Gateway DNS locations to ch...
→
Running Create a new DNS location named "Personal DoH......
Agent
شما قبلاً یک Default Location در Gateway دارید که DoH endpoint فعاله. نیازی به ساخت location جدید نیست — می‌تونید از همین استفاده کنید.

DoH endpoint شما
https://xxxx.cloudflare-gateway.com/dns-query
این endpoint آماده‌ست و می‌تونید هم در مرورگر و هم در Cloudflare One Client ازش استفاده کنید.

۱. تنظیم در مرورگر Firefox
Settings → Privacy & Security
اسکرول کنید به پایین، بخش DNS over HTTPS
Max Protection رو انتخاب کنید
روی Choose Provider کلیک کنید → Custom
این آدرس رو وارد کنید:
https://xxxx.cloudflare-gateway.com/dns-query
OK → ذخیره کنید
۲. نصب و تنظیم Cloudflare One Client (WARP)
به صفحه Zero Trust برید
به My Team → Devices → Device settings برید
یک Device profile بسازید (یا Default رو ویرایش کنید)
مطمئن بشید WARP mode روی DNS یا WARP تنظیم شده
Cloudflare One Client رو از این صفحه دانلود کنید (Windows / macOS / Linux / iOS / Android)
بعد از نصب، با ایمیل @gmail.com لاگین کنید
Client به‌صورت خودکار از DoH endpoint شما استفاده می‌کنه
تنظیم WARP روی حالت DNS-only (فقط DoH)
اگر می‌خواید فقط DNS از طریق Gateway بره و بقیه ترافیک مستقیم باشه:

روی آیکون Cloudflare Client کلیک کنید
Settings → Advanced → Connection options
WARP mode رو روی DNS only بذارید
این‌طوری فقط کوئری‌های DNS از طریق Gateway و DoH شما عبور می‌کنه و ترافیک عادی مستقیم می‌ره.

می‌خواید کمکتون کنم policyهای Gateway (مثل بلاک‌کردن دامنه‌های خاص یا فیلترینگ) رو هم تنظیم کنید؟


۷ گیگابایت ۷ روزه

حجم بسته
۷ گیگابایت
نوع بسته
۷ روزه
کد تائیدیه سازمان تنظیم مقررات: 
۵۳۳۵۰۴

۴۷,۴۳۰ تومان

خرید آنلاین
۱۴ گیگابایت ۷ روزه

حجم بسته
۱۴ گیگابایت
نوع بسته
۷ روزه
کد تائیدیه سازمان تنظیم مقررات: 
۵۳۳۵۰۴

۸۳,۵۴۰ تومان

خرید آنلاین
۱۰ گیگابایت ۳۰ روزه

حجم بسته
۱۰ گیگابایت
نوع بسته
۳۰ روزه
کد تائیدیه سازمان تنظیم مقررات: 
۵۳۳۵۰۴

۵۸,۹۰۰ تومان

خرید آنلاین
۱۵ گیگابایت ۳۰ روزه

حجم بسته
۱۵ گیگابایت
نوع بسته
۳۰ روزه
کد تائیدیه سازمان تنظیم مقررات: 
۵۳۳۵۰۴

۷۷,۸۸۰ تومان

خرید آنلاین
۳۰ گیگابایت ۳۰ روزه

حجم بسته
۳۰ گیگابایت
نوع بسته
۳۰ روزه
کد تائیدیه سازمان تنظیم مقررات: 
۵۳۳۵۰۴

۱۲۳,۱۹۰ تومان

خرید آنلاین
۵۰گیگابایت ۳۰ روزه

حجم بسته
۵۰ گیگابایت
نوع بسته
۳۰ روزه
کد تائیدیه سازمان تنظیم مقررات: 
۵۳۳۵۰۴

۱۶۷,۰۸۰ تومان

خرید آنلاین
۹۰گیگابایت ۳۰ روزه

حجم بسته
۹۰ گیگابایت
نوع بسته
۳۰ روزه
کد تائیدیه سازمان تنظیم مقررات: 
۵۳۳۵۰۴

۲۵۹,۱۲۰ تومان

خرید آنلاین
۱۰۰گیگابایت ۲ تا ۷ صبح ۳۰ روزه

حجم بسته
۱۰۰ گیگابایت
نوع بسته
۳۰ روزه
کد تائیدیه سازمان تنظیم مقررات: 
۵۳۳۵۰۴

۹۴,۸۷۰ تومان

خرید آنلاین
۲۰۰ گیگابایت ۲تا۷ صبح ۳۰ روزه

حجم بسته
۲۰۰ گیگابایت
نوع بسته
۳۰ روزه
کد تائیدیه سازمان تنظیم مقررات: 
۵۳۳۵۰۴

۱۶۱,۴۲۰ تومان

خرید آنلاین
۳۰۰گیگابایت ۲تا۷ صبح ۳۰ روزه

حجم بسته
۳۰۰ گیگابایت
نوع بسته
۳۰ روزه
کد تائیدیه سازمان تنظیم مقررات: 
۵۳۳۵۰۴

۲۲۷,۹۷۰ تومان

خرید آنلاین
۲ مگابیت اقتصادی ۳۰ روزه

حجم بسته
-
نوع بسته
۳۰ روزه
بسته تا ۲ مگابیت بر ثانیه ۳۰ روزه ۶۰ گیگابایت

کد تائیدیه سازمان تنظیم مقررات: 
۵۳۳۵۰۴

۱۵۲,۹۲۰ تومان

خرید آنلاین
۴ مگابیت اقتصادی ۳۰ روزه

حجم بسته
-
نوع بسته
۳۰ روزه
بسته تا ۴ مگابیت بر ثانیه ۳۰ روزه ۸۰ گیگابایت

کد تائیدیه سازمان تنظیم مقررات: 
۵۳۳۵۰۴

۱۸۹,۷۴۰ تومان

خرید آنلاین
۸ مگابیت اقتصادی ۳۰ روزه

حجم بسته
-
نوع بسته
۳۰ روزه
بسته تا ۸ مگابیت بر ثانیه ۳۰ روزه ۱۰۰ گیگابایت

کد تائیدیه سازمان تنظیم مقررات: 
۵۳۳۵۰۴

۲۲۷,۹۷۰ تومان

خرید آنلاین
۱۲۰ گیگابایت ۹۰ روزه

حجم بسته
۱۲۰ گیگابایت
نوع بسته
۹۰ روزه
کد تائیدیه سازمان تنظیم مقررات: 
۵۳۳۵۰۴

۴۱۷,۷۲۰ تومان

خرید آنلاین
۲۴۰ گیگابایت ۹۰ روزه

حجم بسته
۲۴۰ گیگابایت
نوع بسته
۹۰ روزه
کد تائیدیه سازمان تنظیم مقررات: 
۵۳۳۵۰۴

۷۳۰,۶۵۰ تومان

خرید آنلاین
۶۰ گیگابایت ۹۰ روزه

حجم بسته
۶۰ گیگابایت
نوع بسته
۹۰ روزه
کد تائیدیه سازمان تنظیم مقررات: 
۵۳۳۵۰۴

۲۴۳,۵۵۰ تومان

خرید آنلاین
۱۰۰ گیگابایت ۱۸۰ روزه

حجم بسته
۱۰۰ گیگابایت
نوع بسته
۱۸۰ روزه
کد تائیدیه سازمان تنظیم مقررات: 
۵۳۳۵۰۴

۳۷۹,۴۸۰ تومان

خرید آنلاین
۱۵۰ گیگابایت ۱۸۰ روزه

حجم بسته
۱۵۰ گیگابایت
نوع بسته
۱۸۰ روزه
کد تائیدیه سازمان تنظیم مقررات: 
۵۳۳۵۰۴

۵۱۲,۵۹۰ تومان

خرید آنلاین
۳۰۰ گیگابایت ۱۸۰ روزه

حجم بسته
۳۰۰ گیگابایت
نوع بسته
۱۸۰ روزه
کد تائیدیه سازمان تنظیم مقررات: 
۵۳۳۵۰۴

۸۵۳,۸۴۰ تومان

خرید آنلاین
۵۰۰ گیگابایت ۱۸۰ روزه

حجم بسته
۵۰۰ گیگابایت
نوع بسته
۱۸۰ روزه
کد تائیدیه سازمان تنظیم مقررات: 
۵۳۳۵۰۴

۱,۳۰۹,۸۰۰ تومان

خرید آنلاین
۲۰۰گیگابایت ۳۶۵ روزه

حجم بسته
۲۰۰ گیگابایت
نوع بسته
۳۶۵ روزه
کد تائیدیه سازمان تنظیم مقررات: 
۵۳۳۵۰۴

۷۵۰,۴۸۰ تومان

خرید آنلاین
۴۰۰ گیگابایت ۳۶۵ روزه

حجم بسته
۴۰۰ گیگابایت
نوع بسته
۳۶۵ روزه
کد تائیدیه سازمان تنظیم مقررات: 
۵۳۳۵۰۴

۱,۲۸۱,۴۸۰ تومان

خرید آنلاین
۶۰۰ گیگابایت ۳۶۵ روزه

حجم بسته
۶۰۰ گیگابایت
نوع بسته
۳۶۵ روزه
کد تائیدیه سازمان تنظیم مقررات:
۵۳۳۵۰۴

۱,۶۵۱,۰۵۰ تومان

خرید آنلاین





















## نتیجه: فیبر نوری به‌مراتب به‌صرفه‌تر است — حدود ۴ تا ۵ برابر ارزان‌تر به ازای هر گیگابایت

یک نکته مهم ابتدا: قیمت‌های بخش **فیبر نوری به تومان** هستند، ولی بقیه بخش‌ها **به ریال** (۱ تومان = ۱۰ ریال). پس همه را به «تومان بر گیگابایت» تبدیل کردم تا مقایسه منصفانه باشد.

| نوع اینترنت | بهترین بسته از نظر ارزش | هزینه مؤثر |
|---|---|---|
| فیبر (بهترین کل لیست) | ۳۶۵ روزه، ۸۵۰۰ گیگ @ ۱۲,۷۵۰,۰۰۰ تومان | **~۱,۵۰۰ تومان/گیگ** |
| فیبر (بهترین کوتاه‌مدت) | ۳۰ روزه، ۸۰۰ گیگ @ ۱,۳۲۰,۰۰۰ تومان | ~۱,۶۵۰ تومان/گیگ |
| موبایل (بهترین معمولی) | ۳۶۵ روزه، ۱۵۰ گیگ یا ۴۰۰ گیگ | **~۷,۰۰۰ تومان/گیگ** |
| موبایل (۳۰ روزه معمولی) | بسته‌های ۴/۸/۱۰/۲۰ گیگ | ~۱۰,۵۰۰ تومان/گیگ |

یعنی ارزان‌ترین اینترنت موبایلِ این لیست هنوز **حدود ۴.۵ برابر گران‌تر** از بدترین بسته فیبر است و نزدیک ۷ برابر گران‌تر از بهترین بسته فیبر. اگر فیبر در محل شما فعال است، از نظر هزینه هر گیگ، هیچ بسته موبایلی رقیب فیبر نیست.

## بهترین انتخاب‌ها در هر دسته

**فیبر نوری:**
- ۳۰ روزه: ۸۰۰ گیگ @ ۱,۳۲۰,۰۰۰ تومان (۱,۶۵۰ ت/گیگ) — بسته ۷۵۰ گیگی @ ۱,۳۹۰,۰۰۰ تومان گران‌تر است و حجم کمتری هم دارد؛ نخرید.
- ۹۰ روزه: ۲۵۰۰ گیگ @ ۴,۰۰۰,۰۰۰ تومان (۱,۶۰۰ ت/گیگ) — همین بسته دو بار با قیمت ۴,۲۵۰,۰۰۰ هم آمده؛ ارزان‌ترش را بگیرید.
- ۱۸۰ روزه: ۵۰۰۰ گیگ @ ۷,۷۵۰,۰۰۰ تومان (۱,۵۵۰ ت/گیگ).
- ۳۶۵ روزه: ۸۵۰۰ گیگ @ ۱۲,۷۵۰,۰۰۰ تومان (۱,۵۰۰ ت/گیگ) — **بهترین ارزش کل این فایل**.

**موبایل:**
- بهترین ارزش معمولی: ۳۶۵ روزه ۱۵۰ گیگ @ ۱۰,۵۰۰,۰۰۰ ریال یا ۴۰۰ گیگ @ ۲۸,۰۰۰,۰۰۰ ریال (هر دو ~۷,۰۰۰ ت/گیگ). هرچه مدت بلندتر، ارزان‌تر: ۳۰ روزه ~۱۰,۵۰۰ → ۹۰/۱۸۰ روزه ~۷,۸۰۰ → ۲۷۰ روزه ~۷,۵۰۰ → سالانه ~۷,۰۰۰ ت/گیگ.
- بسته‌های شبانه: ۳۰ روزه ۱۴ گیگ @ ۷۰۰,۰۰۰ ریال می‌شود ~۵,۰۰۰ ت/گیگ — ارزان‌ترین اینترنت موبایل لیست، ولی فقط ساعات شب قابل استفاده است.
- بسته‌های روبیکا (~۵,۷۰۰ ت/گیگ) ارزان‌اند ولی فقط داخل همان اپ کار می‌کنند.
- «نامحدود ۲ بامداد تا ۷ صبح» ۳۰ روزه @ ۳۷۷,۴۰۰ ریال فقط وقتی عالیه که بتوانید دانلودهای سنگین را در آن ۵ ساعت بگذارید.

## دام‌های قیمت‌گذاری در همین لیست

- فیبر ۳۰ روزه ۶۰ گیگ (۳,۹۱۷ ت/گیگ) از بسته کوچک‌ترِ ۵۵ گیگ (۳,۶۰۰ ت/گیگ) بدتر است.
- فیبر ۹۰ روزه ۷۵۰ گیگ و فیبر ۳۶۵ روزه ۲۱۰۰ گیگِ ۴,۵۰۰,۰۰۰ تومانی، هر دو توسط بسته‌های بزرگ‌تر/هم‌حجم قیمتی پایین‌تر زیرمی‌روند — بسته ۲۱۰۰ گیگی دو بار با قیمت ۳,۸۹۰,۰۰۰ و ۴,۵۰۰,۰۰۰ تومان آمده.
- بسته‌های روزانه/هفتگی کوچک موبایل (۱ گیگ با ۱۱,۵۰۰ تا ۱۲,۰۰۰ ت/گیگ) بدترین ارزش لیست‌اند — فقط برای شرایط اضطراری.

**یک هشدار:** محاسبه «تومان بر گیگ» فرض می‌کند کل حجم را قبل از انقضا مصرف می‌کنید. بسته سالانه ۸۵۰۰ گیگی فیبر یعنی به‌طور متوسط ~۲۳ گیگ در روز؛ اگر مصرف واقعی شما خیلی کمتر است، بسته کوچک‌تر با نرخ کمی بالاتر باز هم خریدار عاقلانه‌تری است. جمع‌بندی: مصرف سنگین خانگی → بسته‌های سالانه فیبر؛ موبایل فقط به‌عنوان جایگزین یا جایی که فیبر نمی‌رسد.
 

Looking at this, you've actually got four separate package groups here — a fiber-optic (FTTH) plan list priced in Toman, and three mobile/wireless data plan lists priced in Rial. Here's the value breakdown (cost per GB):
1. Fiber optic (FTTH) — priced in Toman This is clearly the best value tier overall. Larger, longer-term bundles get cheap fast:
365 days / 8500GB → 12,750,000 T = ~1,500 T/GB
180 days / 5000GB → 7,750,000 T = ~1,550 T/GB
90 days / 2500GB → 4,000,000 T = ~1,600 T/GB
Smaller/short packages are worse: 30-day 55GB is ~3,600 T/GB — over 2x pricier per GB than the big bundles.
Rule of thumb for fiber: the bigger and longer the package, the cheaper per GB. Anything 2500GB+ on the 90/180/365-day tiers is where the real value is.
2. Mobile packages (the 533685/534063 list, in Rial) Converting to Toman for a fair comparison, this tier is far more expensive per GB than fiber:
365 days / 400GB or 150GB → ~7,000 T/GB
Short packages (1–30 days) → 10,000–12,000+ T/GB So even the cheapest mobile option here (~7,000 T/GB) costs roughly 4–5x more per GB than the cheapest fiber option.
3. نذرآب (charity) packages ~8,500–8,700 T/GB — similar to standard mobile pricing, no real value edge (you're paying a premium that partly funds the stated charity cause).
4. شبانه (night) packages ~4,950–5,000 T/GB — better than daytime mobile packages, worst than fiber, but a reasonable middle ground if you mainly need data at night.
5. Last list (Rubika-specific, morning packages, new-subscriber specials) Mixed bag, but two standouts:
The morning package (12GB/30 days, 6am–12pm only) → ~1,580 T/GB — exceptional value, rivaling fiber, but only usable in that time window.
Rubika-specific packages (e.g., 22GB/30 days) → ~5,700–6,400 T/GB — decent if you mainly use Rubika.
Everything else in tiny/short packages (1–7 day, sub-1GB) is brutal: 15,000–40,000+ T/GB — the worst value in the whole document by far.
Bottom line
If you have a choice, fiber-optic large/long bundles (2500GB+, 90–365 days) give the best cost per gigabyte by a wide margin — roughly 1,500–1,700 T/GB.
Among mobile options, avoid tiny short-duration packages (1–7 days, <2GB) — they're 10–25x more expensive per GB than large fiber bundles.
The time-restricted morning package is a hidden gem if that window works for your usage pattern.
Want me to build this into a sortable table/spreadsheet so you can filter by duration or price?


برای تعیین اینکه کدام بسته **بیشترین ارزش خرید (Value for Money)** را دارد، من تمام بسته‌های لیست شده را بر اساس **«هزینه به ازای هر گیگابایت»** محاسبه و مقایسه کرده‌ام. 

نکته مهم: در متن شما، قیمت بسته‌های فیبر نوری به **تومان** و قیمت سایر بسته‌ها به **ریال** درج شده است. برای مقایسه عادلانه، تمام قیمت‌ها به **تومان** تبدیل شده‌اند (هر ۱۰,۰۰۰ ریال = ۱ تومان).

در ادامه، بهترین گزینه‌ها بر اساس نیازهای مختلف دسته‌بندی شده‌اند:

---

### 🥇 ۱. بهترین ارزش خرید مطلق (بیشترین حجم، کمترین هزینه به ازای هر گیگ)
اگر اتصال فیبر نوری (FTTH) دارید و مصرف بالایی دارید، بسته‌های فیبر نوری با اختلاف زیاد به‌صرفه‌ترین گزینه‌ها هستند:

1. **بسته ۳۶۵ روزه ۸۵۰۰ گیگابایتی (تا ۱۰۰ مگابیت)**: 
   - قیمت: ۱۲,۷۵۰,۰۰۰ تومان 
   - هزینه هر گیگ: **۱,۵۰۰ تومان** (ارزان‌ترین نرخ در کل لیست برای اینترنت کامل)
2. **بسته ۱۸۰ روزه ۵۰۰۰ گیگابایتی (تا ۱۰۰ مگابیت)**: 
   - قیمت: ۷,۷۵۰,۰۰۰ تومان 
   - هزینه هر گیگ: **۱,۵۵۰ تومان**
3. **بسته ۳۶۵ روزه ۸۸۰۰ گیگابایتی (تا ۱۰۰۰ مگابیت)**: 
   - قیمت: ۱۴,۰۰۰,۰۰۰ تومان 
   - هزینه هر گیگ: **۱,۵۹۰ تومان** (بهترین گزینه برای ترکیب سرعت گیگابیتی و حجم بسیار بالا)
4. **بسته ۹۰ روزه ۲۵۰۰ گیگابایتی (تا ۱۰۰ مگابیت)**: 
   - قیمت: ۴,۰۰۰,۰۰۰ تومان 
   - هزینه هر گیگ: **۱,۶۰۰ تومان** (بهترین گزینه میان‌مدت)

---

### 🥈 ۲. بهترین ارزش خرید برای مصرف‌کنندگان عادی (بسته‌های ۳۰ روزه فیبر)
اگر نمی‌خواهید مبلغ زیادی را یکجا پرداخت کنید، بسته‌های ماهانه فیبر نوری همچنان ارزش خرید فوق‌العاده‌ای دارند:

1. **بسته ۳۰ روزه ۸۰۰ گیگابایتی (تا ۱۰۰ مگابیت)**: 
   - قیمت: ۱,۳۲۰,۰۰۰ تومان 
   - هزینه هر گیگ: **۱,۶۵۰ تومان**
2. **بسته ۳۰ روزه ۷۵۰ گیگابایتی (تا ۱۰۰۰ مگابیت)**: 
   - قیمت: ۱,۳۹۰,۰۰۰ تومان 
   - هزینه هر گیگ: **۱,۸۵۳ تومان**

---

### 🥉 ۳. بهترین گزینه‌ها برای بودجه محدود یا مشترکین جدید (غیر فیبر)
اگر اتصال فیبر نوری ندارید یا به حجم کمی نیاز دارید، این بسته‌ها کمترین هزینه را به ازای هر گیگابایت دارند:

1. **بسته ۳۰ روزه ۷ گیگابایتی (ویژه مشترکین جدید)**: 
   - قیمت: ۳۴,۹۰۰ تومان 
   - هزینه هر گیگ: **۴,۹۸۵ تومان** (بسیار مقرون‌به‌صرفه برای تست سرویس)
2. **بسته ۳۰ روزه ۵ گیگابایتی (ویژه مشترکین جدید)**: 
   - قیمت: ۲۹,۲۰۰ تومان 
   - هزینه هر گیگ: **۵,۸۴۰ تومان**

---

### ⏰ ۴. بهترین گزینه‌ها برای مصرف خاص (زمان‌دار یا برنامه‌محور)
این بسته‌ها ارزان هستند اما محدودیت زمانی یا برنامه‌ای دارند:

1. **بسته صبحانت ۳۰ روزه ۱۲ گیگابایتی (ساعت ۶ صبح تا ۱۲ ظهر)**: 
   - قیمت: ۱۸,۹۷۰ تومان 
   - هزینه هر گیگ: **۱,۵۸۰ تومان** (از نظر ریاضی ارزان‌ترین است، اما فقط صبح‌ها قابل استفاده است).
2. **بسته شبانه ۳۰ روزه ۲۰ گیگابایتی**: 
   - قیمت: ۹۹,۰۰۰ تومان 
   - هزینه هر گیگ: **۴,۹۵۰ تومان** (مناسب برای دانلودهای سنگین در شب).
3. **بسته ۳۰ روزه ۲۲ گیگابایتی ویژه روبیکا**: 
   - قیمت: ۱۲۵,۴۰۰ تومان 
   - هزینه هر گیگ: **۵,۷۰۰ تومان** (فقط برای ترافیک داخلی برنامه روبیکا).

---

### 💡 جمع‌بندی و توصیه نهایی:
- **اگر فیبر نوری دارید:** بدون شک بسته **۳۶۵ روزه ۸۵۰۰ گیگابایتی (۱۰۰ مگابیت)** یا **۱۸۰ روزه ۵۰۰۰ گیگابایتی** را انتخاب کنید. هیچ بسته دیگری در این لیست (و حتی اکثر سرویس‌دهنده‌های دیگر) نمی‌تواند با نرخ ~۱,۵۰۰ تومان به ازای هر گیگابایت رقابت کند.
- **اگر فیبر نوری ندارید و مصرفتان کم است:** بسته **۳۰ روزه ۷ گیگابایتی ویژه مشترکین جدید** با قیمت ۳۴,۹۰۰ تومان، منطقی‌ترین انتخاب برای شروع است.
- **اگر فقط دانلود شبانه دارید:** بسته **شبانه ۳۰ روزه ۲۰ گیگابایتی** با ۹۹,۰۰۰ تومان بهترین انتخاب است.

*توجه: برای خرید بسته‌های فیبر نوری، حتماً باید «شماره سرویس فیبر نوری یا FTTH ID» را داشته باشید، در غیر این صورت سیستم اجازه خرید نمی‌دهد.*



Fiber optic (FTTH) packages offer by far the best value for money. The mobile/short-term packages (priced in Rials) are much more expensive per GB.
Quick comparison method
I calculated approximate price per GB (in Tomans).
1 Toman ≈ 10 Rials, so the later packages were converted.
Lower price/GB = better value.
Longer/higher-volume packages are usually cheaper per GB.
Fiber also gives much higher speeds (100 Mbps–1 Gbps) vs typical mobile speeds.
These are volume-capped packages (not truly unlimited).
Fiber FTTH packages (best value overall)
These start around 1,600–3,600 Toman/GB and improve with higher volume/longer duration.
Best value examples (lowest price/GB):
Duration
Volume
Speed
Price (Toman)
≈ Price/GB
Notes
90-day
2,500 GB
100 Mbps
4,000,000
1,600
Excellent
90-day
2,500 GB
1 Gbps
4,250,000
1,700
Excellent
30-day
800 GB
100 Mbps
1,320,000
1,650
Strong short-term
180-day
5,000 GB
100 Mbps
7,750,000
1,550
Very strong
365-day
8,500 GB
100 Mbps
12,750,000
1,500
Best long-term
365-day
8,800 GB
1 Gbps
14,000,000
1,590
Best long-term high-speed

Other solid options:
30-day 320 GB (100 Mbps) → ~1,953 T/GB
90-day 750 GB (100 Mbps) → ~1,960 T/GB
180-day 1,200 GB (100 Mbps) → ~1,900 T/GB
Smaller fiber packages (e.g. 55–180 GB / 30 days) cost 2,500–3,900 T/GB — still decent but worse value than the high-volume ones.
Mobile / short-term packages (much worse value)
These are typically 5,000–15,000+ Toman/GB (or higher for daily/weekly).
Examples:
1-day 1 GB → 11,500 T/GB
30-day 3–10 GB range → often 8,000–12,000+ T/GB
30-day 20 GB → ~10,500 T/GB
Night / Nazr-Ab / Rubika specials → still several times more expensive per GB than fiber
Long mobile ones (e.g. 365-day 150–400 GB) improve a bit but remain far above fiber rates (often 4,000–7,000+ T/GB)
Even the “best” mobile packages in the list cost several times more per GB than mid-to-high fiber packages, and they have lower speeds and more restrictions.
Summary – What has the most value for money?
Highest value: Large long-duration fiber packages
365-day ~8,500–8,800 GB or 180-day 5,000 GB (around 1,500–1,600 Toman/GB)
90-day 2,500 GB packages are also excellent if you don’t want a full year commitment.
Good short-term fiber: 30-day 800 GB or 320 GB packages.
Avoid for value: Almost all the Rial-priced mobile/daily/weekly/night packages unless you specifically need mobile data or have no fiber access. They are 3–10× more expensive per GB.
Recommendation: If you have (or can get) FTTH service, go for one of the high-volume fiber packages (especially 90+ days and 2,000+ GB). They give dramatically better price-per-GB and much higher speeds. The mobile packages only make sense for occasional/on-the-go use.
Prices and availability can change, and actual usable volume sometimes differs between domestic/international traffic depending on the operator. Check the exact terms on the provider’s site before buying.
Here’s the breakdown:

🏆 Best Value for Money (Overall)
The absolute best value in this list is:
بسته ۱۸۰ روزه ۵۰۰۰ گیگابایتی فیبرنوری
(180-day, 5000 GB package – 100 Mbps)
Price: 7,750,000 تومان
Price per GB: 1,550 تومان/GB
Price per day: 43,055 تومان/day
Speed: up to 100 Mbps
This gives you the lowest cost per gigabyte and a very reasonable daily cost for a huge amount of data over 6 months.

🥈 Second Best Value
بسته ۱۸۰ روزه ۳۷۰۰ گیگابایتی فیبرنوری
(180-day, 3700 GB – 1 Gbps)
Price: 6,400,000 تومان
Price per GB: 1,730 تومان/GB
Price per day: 35,555 تومان/day
Speed: up to 1 Gbps (10x faster than the #1 pick)
If you need high speed, this is the best compromise between price/GB and performance.

🥉 Third Best Value
بسته ۳۶۵ روزه ۸۸۰۰ گیگابایتی فیبرنوری
(365-day, 8800 GB – 1 Gbps)
Price: 14,000,000 تومان
Price per GB: 1,590 تومان/GB
Price per day: 38,356 تومان/day
Speed: up to 1 Gbps
Great for heavy users who want a full year of coverage with top speed.

❌ Worst Value (Avoid)
بسته ۳۰ روزه ۵۵ گیگابایتی
(30-day, 55 GB – 100 Mbps)
Price: 198,000 تومان
Price per GB: 3,600 تومان/GB
Very expensive per GB compared to larger packages.
Also, the small Rial-based packages (e.g., 1 GB for 115,000 Rial = ~11,500 تومان/GB) are extremely poor value – avoid unless you absolutely need a tiny top-up.

📊 Summary Table (Top Picks)
Package
Duration
Volume
Speed
Price (تومان)
Price/GB
Price/Day
Best For
180-day 5000 GB
180 days
5000 GB
100 Mbps
7,750,000
1,550
43,055
Best price/GB
365-day 8800 GB
365 days
8800 GB
1 Gbps
14,000,000
1,590
38,356
Best yearly + speed
180-day 3700 GB
180 days
3700 GB
1 Gbps
6,400,000
1,730
35,555
Best speed for price
90-day 2500 GB (100 Mbps)
90 days
2500 GB
100 Mbps
4,000,000
1,600
44,444
Good short-term value


✅ Final Recommendation
If you want the absolute cheapest per GB → 180-day 5000 GB (100 Mbps)
If you want speed + value → 180-day 3700 GB (1 Gbps)
If you want a full year + speed → 365-day 8800 GB (1 Gbps)
Avoid any package under 100 GB – they are priced at a huge premium.
Yes. I converted everything to the same unit: تومان per GB and compared the plans purely on volume/value, ignoring speed differences for the moment.
🏆 Best value among the FTTH/fiber packages
Package
Price
Volume
Cost / GB
Value
365 روزه 8500GB / 100Mbps
12,750,000 تومان
8,500 GB
1,500 تومان/GB
🥇
180 روزه 5000GB / 100Mbps
7,750,000
5,000 GB
1,550
🥈
365 روزه 8800GB / 1Gbps
14,000,000
8,800 GB
1,591
🥉
90 روزه 2500GB / 100Mbps
4,000,000
2,500 GB
1,600
Excellent
90 روزه 2500GB / 1Gbps
4,250,000
2,500 GB
1,700
Excellent
180 روزه 3700GB / 1Gbps
6,400,000
3,700 GB
1,730
Very good
365 روزه 2100GB / 100Mbps
3,890,000
2,100 GB
1,852
Good
30 روزه 800GB / 100Mbps
1,320,000
800 GB
1,650
Very good

Important: the 8500GB annual package is the cheapest per GB of all the fiber packages you supplied.

But there is an even bigger issue
The other packages you listed are mobile/general Internet packages, and their prices are in ریال, while the FTTH prices are in تومان.
After converting ریال → تومان:
Cheapest cost/GB in the second group
Package
Price
Volume
تومان/GB
365 روزه 150GB
105,000 تومان
150GB
700
365 روزه 400GB
280,000 تومان
400GB
700
270 روزه 50GB
37,500 تومان
50GB
750
270 روزه 72GB
54,000 تومان
72GB
750
365 روزه 80GB
60,000 تومان
80GB
750
90 روزه 18GB
14,040 تومان
18GB
780
180 روزه 36GB
28,080 تومان
36GB
780
90 روزه 15GB
12,000 تومان
15GB
800
60 روزه 15GB
12,000 تومان
15GB
800

So if those ریالی prices are correct, the mobile/general packages are dramatically cheaper per GB than the fiber packages.
🚨 However, there is likely a unit/source difference
For example:
Fiber:
8500 GB = 12,750,000 تومان
Other package:
400 GB = 28,000,000 ریال = 2,800,000 تومان
That's 700 تومان/GB, versus 1,500 تومان/GB for the fiber package.
So the second package is about 53% cheaper per GB.
But these aren't necessarily apples-to-apples because the second list appears to be mobile operator packages, while the first is FTTH home broadband. They may have different traffic policies, network quality, peak/off-peak restrictions, FUP, activation conditions, etc.

🥇 My picks
If you specifically want fiber/FTTH
Best absolute value:
🏆 365 روزه — 8500GB — 100Mbps — 12,750,000 تومان
1,500 تومان/GB
You get approximately:
8.5 TB/year = 708 GB/month average
That's a very large allowance.
Best value if you want 1Gbps
🏆 365 روزه — 8800GB — 1Gbps — 14,000,000 تومان
Only 1,250,000 تومان more than the 8500GB/100Mbps package, while giving you:
+300 GB
10× advertised speed
1Gbps instead of 100Mbps
That's arguably the best premium/value package.
The additional cost is only about 9.8%, while the advertised speed increases by 10×.

💰 The sweet spot
I would particularly look at these:
🥇 365d 8500GB / 100Mbps
12.75m تومان
Best if you care almost exclusively about maximum GB per تومان.
🥈 180d 5000GB / 100Mbps
7.75m تومان
Excellent if you don't want to commit to a full year.
🥉 90d 2500GB / 100Mbps
4m تومان
Very good if you want to spend less upfront.
⭐ 365d 8800GB / 1Gbps
14m تومان
My overall favorite if the 1Gbps connection actually delivers close to that speed.

One surprising result
The 365-day 1500GB package for 3.3m is actually worse value than the 365-day 2100GB package for 3.89m.
Compare:
1500GB:
 3,300,000 ÷ 1,500 = 2,200 تومان/GB
2100GB:
 3,890,000 ÷ 2,100 = 1,852 تومان/GB
You pay only 590,000 تومان more but get 600GB extra.
So I'd skip the 1500GB and take the 2100GB if your usage fits.

Bottom line
For FTTH:
 🥇 8500GB / 365d / 100Mbps — 12.75m = best pure value
 🥇 8800GB / 365d / 1Gbps — 14m = best overall/premium value
 🥈 5000GB / 180d / 100Mbps — 7.75m = best shorter-term value
 🥉 2500GB / 90d / 100Mbps — 4m = best lower-cost option
For the second list: the 365-day 400GB and 150GB packages at 700 تومان/GB are actually the best value per GB, assuming the prices and units you pasted are correct.
If you want, I can also calculate exactly which package wins for 100GB/month, 200GB/month, 300GB/month, 500GB/month and 1TB/month usage, including the cost per month and cost per year.
Got it — comparing the two lists. One important detail first: the fiber (FTTH) section is priced in **Toman**, while all the mobile sections are in **Rial** (1 Toman = 10 Rial), so I converted everything to Toman per GB before comparing.

## Verdict: Fiber wins by a wide margin — roughly 4–5× cheaper per GB

| Type | Best-value plan | Effective cost |
|---|---|---|
| Fiber (best overall) | 365-day, 8,500 GB @ 12,750,000 T | **~1,500 T/GB** |
| Fiber (best short-term) | 30-day, 800 GB @ 1,320,000 T | ~1,650 T/GB |
| Mobile (best standard) | 365-day, 150 GB or 400 GB | **~7,000 T/GB** |
| Mobile (30-day flat) | any of the 4/8/10/20 GB plans | ~10,500 T/GB |

So the cheapest mobile data on the list still costs about 4.5× more per GB than the worst fiber plan, and nearly 7× more than the best fiber plan. If FTTH is available at your address, every fiber package dominates every mobile package on pure cost per GB — no contest.

## Best picks within each category

**Fiber:**
- 30-day: 800 GB @ 1,320,000 T (1,650 T/GB) — note the 750 GB plan @ 1,390,000 T costs *more* for less data; skip it.
- 90-day: 2,500 GB @ 4,000,000 T (1,600 T/GB) — there's a duplicate listed at 4,250,000 T; take the cheaper one.
- 180-day: 5,000 GB @ 7,750,000 T (1,550 T/GB).
- 365-day: 8,500 GB @ 12,750,000 T (1,500 T/GB) — best value in the entire file.

**Mobile:**
- Best standard value: 365-day 150 GB @ 10,500,000 R or 400 GB @ 28,000,000 R (both 7,000 T/GB). The longer plans get progressively cheaper (30-day ≈ 10,500 → 90/180-day ≈ 7,800 → 270-day ≈ 7,500 → yearly ≈ 7,000).
- Night-only (شبانه): 30-day 14 GB @ 700,000 R works out to ~5,000 T/GB — the cheapest mobile data here, but only usable during night hours.
- Rubika bundles (~5,700 T/GB) are cheap but restricted to that one app.
- The "unlimited 2am–7am" 30-day plan at 377,400 R is excellent *only* if you can schedule heavy downloads in that 5-hour window.

## Watch out for these traps in the list

- Fiber 30-day 60 GB (3,917 T/GB) is worse value than the smaller 55 GB plan (3,600 T/GB).
- Fiber 90-day 750 GB and 365-day 2,100 GB @ 4,500,000 T are both undercut by bigger/same-size plans — the 2,100 GB plan appears twice at 3,890,000 T and 4,500,000 T for identical data.
- Mobile daily/weekly small packs (1 GB for 11,500–12,000 T/GB) are the worst value in the file — emergency use only.

One caveat: per-GB numbers assume you actually consume the full volume before expiry. A yearly 8,500 GB fiber plan averages ~23 GB/day — if your real usage is much lower, a smaller plan at a slightly higher per-GB rate can still be the smarter spend. As a rule of thumb: heavy household use → fiber yearly plans; mobile only as backup or where fiber can't reach.


مقایسه بسته ها اینترنت ا
یران value   profitablity
مشاهده و خرید بسته فیبر نوری
برای مشاهده و خرید بسته‌ها ابتدا شماره سرویس فیبر نوری یا FTTH ID (کد ۱۰ رقمی ارسال‌شده در هنگام خرید) خود را وارد نمایید.

شماره سرویس فیبر نوری
بررسی
شماره سرویس فیبر نوری ندارید؟ ثبت‌نام

شماره سرویس فیبر نوری خود را فراموش کرده‌اید؟ کلیک کنید

فیلتر
اعتبار بسته:
۳۰ روزه
۹۰ روزه
۱۸۰ روزه
۳۶۵ روزه
حجم بسته:
50GB تا 180GB
180GB تا 600GB
600GB تا 3TB
6TB تا 12TB
سرعت بسته:
50Mbps
100Mbps
300Mbps
1Gbps
تا ۱۰۰ مگابیت برثانیه
بسته ۳۰ روزه ۵۵ گیگابایتی فیبرنوری

کد تائیدیه سازمان تنظیم مقررات: ۵۳۴۰۷۵
۱۹۸,۰۰۰ تومان

خرید و فعال‌سازی
تا ۱۰۰۰ مگابیت برثانیه
بسته ۳۰ روزه ۶۰ گیگابایتی فیبرنوری

کد تائیدیه سازمان تنظیم مقررات: ۵۳۴۰۷۵
۲۳۵,۰۰۰ تومان

خرید و فعال‌سازی
تا ۱۰۰ مگابیت برثانیه
بسته ۳۰ روزه ۱۶۰ گیگابایتی فیبرنوری

کد تائیدیه سازمان تنظیم مقررات: ۵۳۴۰۷۵
۴۱۰,۰۰۰ تومان

خرید و فعال‌سازی
تا ۱۰۰۰ مگابیت برثانیه
بسته ۳۰ روزه ۱۸۰ گیگابایتی فیبرنوری

کد تائیدیه سازمان تنظیم مقررات: ۵۳۴۰۷۵
۵۳۰,۰۰۰ تومان

خرید و فعال‌سازی
تا ۱۰۰ مگابیت برثانیه
بسته ۳۰ روزه ۳۲۰ گیگابایتی فیبرنوری

کد تائیدیه سازمان تنظیم مقررات: ۵۳۴۰۷۵
۶۲۵,۰۰۰ تومان

خرید و فعال‌سازی
تا ۱۰۰ مگابیت برثانیه
بسته ۳۰ روزه ۸۰۰ گیگابایتی فیبرنوری

کد تائیدیه سازمان تنظیم مقررات: ۵۳۴۰۷۵
۱,۳۲۰,۰۰۰ تومان

خرید و فعال‌سازی
تا ۱۰۰۰ مگابیت برثانیه
بسته ۳۰ روزه ۷۵۰ گیگابایتی فیبرنوری

کد تائیدیه سازمان تنظیم مقررات: ۵۳۴۰۷۵
۱,۳۹۰,۰۰۰ تومان

خرید و فعال‌سازی
تا ۱۰۰ مگابیت برثانیه
بسته ۹۰ روزه ۲۵۰ گیگابایتی فیبرنوری

کد تائیدیه سازمان تنظیم مقررات: ۵۳۴۰۷۵
۸۰۰,۰۰۰ تومان

خرید و فعال‌سازی
تا ۱۰۰۰ مگابیت برثانیه
بسته ۹۰ روزه ۲۸۰ گیگابایتی فیبرنوری

کد تائیدیه سازمان تنظیم مقررات: ۵۳۴۰۷۵
۹۶۰,۰۰۰ تومان

خرید و فعال‌سازی
تا ۱۰۰ مگابیت برثانیه
بسته ۹۰ روزه ۴۰۰ گیگابایتی فیبرنوری

کد تائیدیه سازمان تنظیم مقررات: ۵۳۴۰۷۵
۹۹۲,۰۰۰ تومان

خرید و فعال‌سازی
تا ۱۰۰۰ مگابیت برثانیه
بسته ۹۰ روزه ۵۵۰ گیگابایتی فیبرنوری

کد تائیدیه سازمان تنظیم مقررات: ۵۳۴۰۷۵
۱,۳۸۰,۰۰۰ تومان

خرید و فعال‌سازی
تا ۱۰۰ مگابیت برثانیه
بسته ۹۰ روزه ۷۵۰ گیگابایتی فیبرنوری

کد تائیدیه سازمان تنظیم مقررات: ۵۳۴۰۷۵
۱,۴۷۰,۰۰۰ تومان

خرید و فعال‌سازی
تا ۱۰۰ مگابیت برثانیه
بسته ۹۰ روزه ۲۵۰۰ گیگابایتی فیبرنوری

کد تائیدیه سازمان تنظیم مقررات: ۵۳۴۰۷۵
۴,۰۰۰,۰۰۰ تومان

خرید و فعال‌سازی
تا ۱۰۰۰ مگابیت برثانیه
بسته ۹۰ روزه ۲۵۰۰ گیگابایتی فیبرنوری

کد تائیدیه سازمان تنظیم مقررات: ۵۳۴۰۷۵
۴,۲۵۰,۰۰۰ تومان

خرید و فعال‌سازی
تا ۱۰۰ مگابیت برثانیه
بسته ۱۸۰ روزه ۴۵۰ گیگابایتی فیبرنوری

کد تائیدیه سازمان تنظیم مقررات: ۵۳۴۰۷۵
۱,۴۰۰,۰۰۰ تومان

خرید و فعال‌سازی
تا ۱۰۰۰ مگابیت برثانیه
بسته ۱۸۰ روزه ۵۵۰ گیگابایتی فیبرنوری

کد تائیدیه سازمان تنظیم مقررات: ۵۳۴۰۷۵
۱,۸۰۰,۰۰۰ تومان

خرید و فعال‌سازی
تا ۱۰۰ مگابیت برثانیه
بسته ۱۸۰ روزه ۸۰۰ گیگابایتی فیبرنوری

کد تائیدیه سازمان تنظیم مقررات: ۵۳۴۰۷۵
۱,۸۴۰,۰۰۰ تومان

خرید و فعال‌سازی
تا ۱۰۰۰ مگابیت برثانیه
بسته ۱۸۰ روزه ۹۰۰ گیگابایتی فیبرنوری

کد تائیدیه سازمان تنظیم مقررات: ۵۳۴۰۷۵
۲,۲۰۰,۰۰۰ تومان

خرید و فعال‌سازی
تا ۱۰۰ مگابیت برثانیه
بسته ۱۸۰ روزه ۱۲۰۰ گیگابایتی فیبرنوری

کد تائیدیه سازمان تنظیم مقررات: ۵۳۴۰۷۵
۲,۲۸۰,۰۰۰ تومان

خرید و فعال‌سازی
تا ۱۰۰۰ مگابیت برثانیه
بسته ۱۸۰ روزه ۳۷۰۰ گیگابایتی فیبرنوری

کد تائیدیه سازمان تنظیم مقررات: ۵۳۴۰۷۵
۶,۴۰۰,۰۰۰ تومان

خرید و فعال‌سازی
تا ۱۰۰ مگابیت برثانیه
بسته ۱۸۰ روزه ۵۰۰۰ گیگابایتی فیبرنوری

کد تائیدیه سازمان تنظیم مقررات: ۵۳۴۰۷۵
۷,۷۵۰,۰۰۰ تومان

خرید و فعال‌سازی
تا ۱۰۰ مگابیت برثانیه
بسته ۳۶۵ روزه ۹۵۰ گیگابایتی فیبرنوری

کد تائیدیه سازمان تنظیم مقررات: ۵۳۴۰۷۵
۲,۸۵۰,۰۰۰ تومان

خرید و فعال‌سازی
تا ۱۰۰۰ مگابیت برثانیه
بسته ۳۶۵ روزه ۱۰۰۰ گیگابایتی فیبرنوری

کد تائیدیه سازمان تنظیم مقررات: ۵۳۴۰۷۵
۳,۱۰۰,۰۰۰ تومان

خرید و فعال‌سازی
تا ۱۰۰ مگابیت برثانیه
بسته ۳۶۵ روزه ۱۵۰۰ گیگابایتی فیبرنوری

کد تائیدیه سازمان تنظیم مقررات: ۵۳۴۰۷۵
۳,۳۰۰,۰۰۰ تومان

خرید و فعال‌سازی
تا ۱۰۰ مگابیت برثانیه
بسته ۳۶۵ روزه ۲۱۰۰ گیگابایتی فیبرنوری

کد تائیدیه سازمان تنظیم مقررات: ۵۳۴۰۷۵
۳,۸۹۰,۰۰۰ تومان

خرید و فعال‌سازی
تا ۱۰۰۰ مگابیت برثانیه
بسته ۳۶۵ روزه ۲۱۰۰ گیگابایتی فیبرنوری

کد تائیدیه سازمان تنظیم مقررات: ۵۳۴۰۷۵
۴,۵۰۰,۰۰۰ تومان

خرید و فعال‌سازی
تا ۱۰۰ مگابیت برثانیه
بسته ۳۶۵ روزه ۸۵۰۰ گیگابایتی فیبرنوری

کد تائیدیه سازمان تنظیم مقررات: ۵۳۴۰۷۵
۱۲,۷۵۰,۰۰۰ تومان

خرید و فعال‌سازی
تا ۱۰۰۰ مگابیت برثانیه
بسته ۳۶۵ روزه ۸۸۰۰ گیگابایتی فیبرنوری

کد تائیدیه سازمان تنظیم مقررات: ۵۳۴۰۷۵
۱۴,۰۰۰,۰۰۰ تومان

خرید و فعال‌سازی




1 روزه
1 گیگ
کد رگولاتور : 533685
115,000 ریال


7 روزه
1 گیگ
کد رگولاتور : 533685
120,000 ریال


14 روزه
3 گیگ
کد رگولاتور : 533685
325,000 ریال


30 روزه
3 گیگ
کد رگولاتور : 533685
350,000 ریال


30 روزه
4 گیگ
کد رگولاتور : 533685
420,000 ریال


30 روزه
8 گیگ
کد رگولاتور : 534063
840,000 ریال


30 روزه
10 گیگ
کد رگولاتور : 534063
1,050,000 ریال


30 روزه
20 گیگ
کد رگولاتور : 534063
2,100,000 ریال


60 روزه
10 گیگ
کد رگولاتور : 533685
825,000 ریال


60 روزه
15 گیگ
کد رگولاتور : 534063
1,200,000 ریال


90 روزه
15 گیگ
کد رگولاتور : 534063
1,200,000 ریال


90 روزه
18 گیگ
کد رگولاتور : 534063
1,404,000 ریال


180 روزه
36 گیگ
کد رگولاتور : 534063
2,808,000 ریال


270 روزه
50 گیگ
کد رگولاتور : 534063
3,750,000 ریال


270 روزه
72 گیگ
کد رگولاتور : 534063
5,400,000 ریال


365 روزه
80 گیگ
کد رگولاتور : 534063
6,000,000 ریال


365 روزه
150 گیگ
کد رگولاتور : 534063
10,500,000 ریال


365 روزه
400 گیگ
کد رگولاتور : 534063
28,000,000 ریال
بسته‌های نذرآب


30 روزه
14 گیگ
کد رگولاتور : 534067
1,190,000 ریال


90 روزه
30 گیگ
کد رگولاتور : 534067
2,580,000 ریال


365 روزه
200 گیگ
کد رگولاتور : 534067
17,400,000 ریال

با مشارکت در طرح نذر آب به تامین زیرساخت های آب آشامیدنی دانش آموزان سیستان و بلوچستان خواهیم پرداخت.

بسته‌های شبانه


30 روزه
14 گیگ
کد رگولاتور : 534105
700,000 ریال


30 روزه
20 گیگ
کد رگولاتور : 534105
990,000 ریال

بازه زمانی استفاده از بست
بسته اینترنت 120 روزه 100 گیگابایت
بلند مدت
7,550,000
ریال
بسته اینترنت 90 روزه 80 گیگابایت
بلندمدت
6,135,000
ریال
بسته اینترنت 90 روزه 60 گیگابایت
بلندمدت
4,605,000
ریال
بسته اینترنت 30 روزه 50 گیگابایت
ماهانه
3,835,000
ریال
بسته اینترنت 90 روزه 45 گیگابایت
بلندمدت
3,458,000
ریال
بسته اینترنت 30 روزه 6 گیگابایت
ماهانه
523,900
ریال
بسته اینترنت سی روزه 5 گیگابایت
ماهانه
447,600
ریال
بسته اینترنت 30 روزه 4 گیگابایت
ماهانه
404,000
ریال
بسته اینترنت نامحدود سی‌روزه (2بامداد تا 7صبح)
ماهانه
377,400
ریال
بسته اینترنت سی روزه 3 گیگابایت
ماهانه
360,400
ریال
بسته اینترنت سی روزه 7 گیگابایت (ویژه مشترکین جدید، ثبت نامی در 30 روز گذشته)
ماهانه
349,000
ریال
بسته اینترنت 15 روزه 3.5 گیگابایت
15 روزه
313,000
ریال
بسته اینترنت 7 روزه 4 گیگابایت (فعالسازی همزمان)
هفتگی
303,400
ریال
بسته اینترنت سی روزه 5 گیگابایت (ویژه مشترکین جدید، ثبت نامی در 30 روز گذشته)
ماهانه
292,000
ریال
بسته اینترنت 15 روزه 2.5 گیگابایت
15 روزه
275,000
ریال
بسته اینترنت 30 روزه 2گیگابایت
ماهانه
265,600
ریال
بسته اینترنت 7 روزه 2.5 گیگابایت (فعالسازی همزمان)
هفتگی
246,600
ریال
بسته اینترنت سی روزه 3 گیگابایت (ویژه مشترکین جدید، ثبت‌نامی در 30 روز گذشته)
ماهانه
234,800
ریال
بسته اینترنت 15 روزه 1.5 گیگابایت
15 روزه
218,100
ریال
بسته اینترنت 7 روزه 1.5 گیگابایت (فعالسازی همزمان)
هفتگی
206,700
ریال
بسته اینترنت 30روزه 1 گیگابایت
ماهانه
199,100
ریال
بسته اینترنت سی روزه 2 گیگابایت (ویژه مشترکین جدید، ثبت نامی در 30 روز گذشته)
ماهانه
197,100
ریال
بسته اینترنت صبحانت 12گیگابایت سی روزه (6صبح تا 12ظهر)
ماهانه
189,700
ریال
بسته اینترنت 3 روزه 1.5 گیگابایت
3 روزه
170,700
ریال
بسته اینترنت 15 روزه 750 مگابایت
15 روزه
170,700
ریال
بسته اینترنت 1 روزه 2 گیگابایت (فعالسازی همزمان)
روزانه
159,300
ریال
بسته اینترنت7 روزه 750 مگابایت (فعالسازی همزمان)
هفتگی
157,200
ریال
بسته اینترنت 7 روزه 500 مگابایت (فعالسازی همزمان)
هفتگی
132,700
ریال
بسته اینترنت 3 روزه 750 مگابایت
3 روزه
127,000
ریال
بسته اینترنت 1 روزه 1 گیگابایت (فعالسازی همزمان)
روزانه
121,300
ریال
بسته اینترنت 1 روزه 750 مگابایت (فعالسازی همزمان)
روزانه
111,800
ریال
بسته اینترنت 7 روزه 300 مگابایت (فعالسازی همزمان)
هفتگی
104,200
ریال
بسته اینترنت 3 روزه 400 مگابایت
3 روزه
100,500
ریال
بسته اینترنت 1 روزه 500 مگابایت (فعالسازی همزمان)
روزانه
92,800
ریال
بسته اینترنت 3 روزه 250 مگابایت
3 روزه
83,400
ریال
بسته اینترنت 7 روزه 200 مگابایت (فعالسازی همزمان)
هفتگی
81,900
ریال
بسته اينترنت 1 روزه 250 مگابايت (فعالسازی همزمان)
روزانه
68,200
ریال
بسته اینترنت 3 روزه 150مگابایت
3 روزه
61,200
ریال
بسته اينترنت 1روزه 150 مگابايت (فعالسازی همزمان)
روزانه
51,000
ریال
بسته اینترنت 1 روزه 60 مگابایت (فعالسازی همزمان)
روزانه
24,500
ریال
بسته اینترنت بلندمدت 180روزه 96گیگابایت(فعالسازی همزمان)
بلند مدت
6,192,000
ریال
بسته اینترنت بلندمدت 120روزه 67گیگابایت(فعالسازی همزمان)
بلند مدت
4,152,800
ریال
بسته اینترنت بلندمدت 90روزه 30گیگابایت(فعالسازی همزمان)
بلند مدت
1,827,000
ریال
بسته اینترنت 30روزه 22گیگابایت ویژه روبیکا
ماهانه
1,254,000
ریال
بسته اینترنت 30روزه 11گیگابایت ویژه روبیکا
ماهانه
649,000
ریال
بسته اینترنت 30روزه 6گیگابایت ویژه روبیکا
ماهانه
384,000
ریال
بسته اینترنت 7روزه 3گیگابایت ویژه روبیکا
هفتگی
225,000
ریال
بسته اینترنت 3روزه 1گیگابایت ویژه روبیکا
3 روزه
80,000
ریال


What is Encrypted Client Hello (ECH) and how do I enable it?


See reasoning
→
Documentation
→
getSkillContent
→
searchProductReleases
→
searchDashboardPages
→
Searched API endpoints
Agent
ECH (Encrypted Client Hello) is a TLS extension that encrypts the Server Name Indication (SNI) during the TLS handshake, hiding which website a client is connecting to from anyone observing the network. It's the successor to ESNI (Encrypted SNI) and is defined in the IETF ECH draft standard.

What ECH protects
Normally, even with HTTPS, the SNI is sent in plaintext during the TLS handshake. This means an observer (ISP, network administrator, or anyone on the path) can see which hostname you're connecting to before encryption kicks in. ECH encrypts that information inside the ClientHello message, so only the server (Cloudflare's edge) can read it.

How to enable ECH on Cloudflare
Cloudflare supports ECH automatically on its edge network for proxied zones. There is no separate ECH toggle in the dashboard — ECH is served to clients that support it when your zone meets these prerequisites:

Enable TLS 1.3 — Go to SSL/TLS → Edge Certificates and turn on TLS 1.3. ECH requires TLS 1.3.
Enable DNSSEC — ECH relies on authenticated DNS records to publish the ECH configuration. Enable DNSSEC on your zone via the DNS settings page.
Proxy your traffic — ECH is only available for traffic going through Cloudflare's proxy (orange-cloud DNS records).
Once these are in place, Cloudflare publishes the ECH configuration in DNS and serves it to compatible browsers (Firefox, Chrome, and others that support ECH) automatically. No additional client-side configuration is needed for visitors.

Important caveat: ECH and TLS inspection
ECH encrypts the SNI, which means it is incompatible with TLS/HTTP inspection tools that rely on reading the SNI. This is relevant if you use Cloudflare Gateway for HTTP inspection — Gateway cannot match ECH-encrypted traffic to HTTP policies based on SNI. If ECH fails, browsers fall back to an unencrypted SNI retry. You can disable ECH in users' browsers if you need inspection to work.

Where to find the relevant settings
To check or enable the prerequisites, navigate to your zone's SSL/TLS settings. Which domain would you like me to help you configure ECH for? I can check your zone's current TLS 1.3 and DNSSEC status.

دامنه cloudflare-gateway بازه
برید تو زیروتراست یه doh شخصی بسازی بذارید تو echconfiglist و خلاص
نسبت به فرگمنت دیلی و اختلال هم نداره


See reasoning
→
Documentation
→
searchDashboardPages
Agent
ECH و DoH دو تکنولوژی جدا هستند و نمی‌توانید endpoint مربوط به DoH شخصی Gateway را داخل «ECH config list» بگذارید. بگذارید توضیح بدم چی کار می‌تونید بکنید و چی کار نمی‌تونید:

چی می‌تونید بکنید: ساخت DoH شخصی از طریق Zero Trust
وقتی تو Zero Trust یک DNS Location می‌سازید، Gateway یک endpoint اختصاصی DoH به شما می‌ده با فرمت:

<random-subdomain>.cloudflare-gateway.com
این یک DNS resolver شخصی‌سازیشده است که policyهای Gateway شما (فیلترینگ DNS، بلاک‌کردن دامنه‌ها و غیره) را روی کوئری‌های DNS اعمال می‌کند. می‌تونید این URL رو داخل مرورگر یا سیستم‌عامل به عنوان DoH resolver تنظیم کنید.

برای ساخت DNS Location:

به Zero Trust → Settings → Network (یا My Team → Locations) برید
یک DNS Location جدید بسازید
Gateway یک DoH subdomain اختصاصی به شما می‌ده
چی نمی‌تونید بکنید: استفاده از DoH endpoint به عنوان ECH config
ECH (Encrypted Client Hello) یک قابلیت سطح TLS است که SNI رو داخل handshake رمزگذاری می‌کنه. این با DoH (DNS over HTTPS) فرق داره:

DoH	ECH
چی رو رمز می‌کنه	کوئری‌های DNS	SNI در TLS handshake
کجا کار می‌کنه	لایه DNS	لایه TLS
چطور فعال می‌شه	مرورگر/سیستم‌عامل	خودکار روی edge کلودفلر (با TLS 1.3 + DNSSEC)
ECH config در DNS به صورت خودکار توسط کلودفلر publish می‌شه وقتی zone شما TLS 1.3 و DNSSEC داشته باشه. هیچ «ECH config list» دستی وجود نداره که شما endpoint DoH رو داخلش بذارید.

درباره fragmentation delay و اختلال
DoH از طریق Gateway: ترافیک DNS به جای IP مستقیم از طریق cloudflare-gateway.com عبور می‌کنه. این ممکنه کمی latency اضافه کنه چون کوئری‌ها از طریق Gateway پردازش می‌شن، اما نباید fragmentation یا اختلال جدی ایجاد کنه.
ECH: اگر مرورگر کلاینت ECH رو support کنه و zone هم ECH رو serve کنه، handshake به‌صورت خودکار انجام می‌شه. اگر ECH fail بشه، مرورگر fallback می‌کنه به SNI غیررمزشده. این می‌تونه یک round trip اضافه ایجاد کنه (delay جزئی) اما disruption دائمی نداره.
خلاصه
✅ می‌تونید DoH شخصی از طریق Zero Trust Gateway بسازید و به عنوان resolver مرورگر استفاده کنید
❌ نمی‌تونید اون DoH endpoint رو داخل ECH config بذارید — این‌ها تکنولوژی‌های جدا هستند
✅ ECH به‌صورت خودکار روی edge کلودفلر فعال می‌شه با TLS 1.3 + DNSSEC + proxy
اگر هدف خاصی دارید (مثلاً دور زدن فیلترینگ، پنهان کردن ترافیک DNS، یا چیز دیگه)، بگید تا دقیق‌تر راهنماییتون کنم.
انتخاب آگاهانه
اپراتورهای اینترنت ایران
نوع سرویس را انتخاب کنید؛ شرایط و بسته‌های هر اپراتور را ببینید و سپس پوشش دقیق محل خود را بررسی کنید.

همه اپراتورها
فیبر نوری
TD-LTE
ADSL / VDSL
اینترنت همراه

ایرانسل
۳ بسته قابل بررسی

ایرانسل به‌عنوان بزرگ‌ترین اپراتور دیتای کشور، اینترنت فیبر نوری FTTH را با سرعت بالا و بسته‌های نامحدود در مناطق گسترده‌ای از ایران ارائه می‌دهد.

فیبر
TD-LTE
همراه
مشاهده سرویس‌ها
←

همراه اول
۲ بسته قابل بررسی

همراه اول با گسترده‌ترین شبکه‌ی موبایل کشور، اینترنت همراه و TD-LTE پرسرعت را برای منازل و کسب‌وکارها فراهم می‌کند.

همراه
TD-LTE
مشاهده سرویس‌ها
←

مخابرات ایران
۲ بسته قابل بررسی

شرکت مخابرات ایران مجری اصلی طرح ملی فیبر نوری است و سرویس FTTH و ADSL را در سراسر کشور ارائه می‌دهد.

فیبر
ADSL
مشاهده سرویس‌ها
←

شاتل
۲ بسته قابل بررسی

شاتل با سابقه‌ای طولانی در ارائه‌ی اینترنت پرسرعت، بسته‌های فیبر نوری خانگی و سازمانی متنوعی با پشتیبانی قوی عرضه می‌کند.

فیبر
ADSL
TD-LTE
مشاهده سرویس‌ها
←

آسیاتک
۲ بسته قابل بررسی

آسیاتک یکی از پیشروان اینترنت فیبر نوری در ایران است و بسته‌های پرسرعت با کیفیت پایدار ارائه می‌دهد.

فیبر
ADSL
مشاهده سرویس‌ها
←

های‌وب
۲ بسته قابل بررسی

های‌وب با تمرکز بر اینترنت پرسرعت خانگی، بسته‌های فیبر نوری و TD-LTE اقتصادی با حجم بالا عرضه می‌کند.

فیبر
TD-LTE
مشاهده سرویس‌ها
←

مبین‌نت
۰ بسته قابل بررسی

مبین‌نت نخستین اپراتور اینترنت بی‌سیم ثابت کشور است و سرویس TD-LTE را در مناطق متعددی ارائه می‌دهد.

TD-LTE
فیبر
مشاهده سرویس‌ها
←

پیشگامان
۲ بسته قابل بررسی

گروه پیشگامان با زیرساخت گسترده، سرویس فیبر نوری و TD-LTE را با تعرفه‌های رقابتی فراهم می‌کند.

فیبر
TD-LTE
مشاهده سرویس‌ها
←

رایتل
۱ بسته قابل بررسی

رایتل به‌عنوان اپراتور نسل سوم، اینترنت همراه و TD-LTE پرسرعت را برای کاربران خانگی و سیار ارائه می‌دهد.

همراه
TD-LTE
فیبر
مشاهده سرویس‌ها
←

فناپ تلکام
۱ بسته قابل بررسی

فناپ تلکام با تکیه بر زیرساخت فناوری، سرویس اینترنت فیبر نوری پرسرعت و پایدار برای منازل و سازمان‌ها ارائه می‌کند.

فیبر
همراه
مشاهده سرویس‌ها
←

صبانت
۱ بسته قابل بررسی

صبانت بسته‌های اینترنت فیبر نوری و ADSL را با تمرکز بر کیفیت سرویس و پشتیبانی ارائه می‌دهد.

فیبر
ADSL
مشاهده سرویس‌ها
←
ZT
زیتل
۰ بسته قابل بررسی

زیتل سرویس اینترنت بی‌سیم TD-LTE را با بسته‌های متنوع برای مناطق تحت پوشش عرضه می‌کند.

TD-LTE
مشاهده سرویس‌ها
The discussion you're viewing focuses on a Pull Request (PR) for `Xray-core` aimed at bypassing Deep Packet Inspection (DPI) in Iran, specifically by mimicking a "python-tls-fingerprint."

Here is a summary of the technical debate within that thread:

  * **The Goal:** The primary objective was to enable the use of "InsecureCipherSuites" (which are actually just legacy/obsolete cipher suites) within `uTLS` configurations. This is necessary because current DPI mechanisms in Iran appear to specifically check for these cipher suites, and the `python-tls-fingerprint` requires them to successfully bypass detection.
  * **The Conflict:**
      * **`patterniha` (Author):** Argued that enabling `InsecureCipherSuites` is the most straightforward solution. They initially attempted to add several new parameters to `copyconfig` to gain more control over the TLS handshake, but this was criticized by others.
      * **`Fangliding` (Member):** Pointed out that `uTLS` is designed to ignore these configurations for standard fingerprints because it manages the handshake internally. They argued that the new parameters were invalid for standard use cases and suggested just enabling `InsecureCipherSuites` directly via `gotls` rather than modifying `uTLS` configurations unnecessarily.
      * **`RPRX` (Member):** Expressed skepticism about the effectiveness of this specific "python-fingerprint" mimicry, noting that the Iranian GFW could easily adapt to it without much collateral damage. They preferred implementing a proper "python fingerprint" instead of relying on custom cipher suites.
  * **The Resolution:** The discussion moved toward limiting the scope of the changes. The contributors agreed to revert unnecessary modifications to `tls.go` and `copyconfig` to avoid polluting the `uTLS` configuration logic. They settled on a more surgical approach, allowing `InsecureCipherSuites` primarily for `unsafe` fingerprints where it is actually effective, and acknowledging that more comprehensive work (like a native Python fingerprint) might be needed if the GFW becomes stricter.

Would you like me to help you summarize the technical steps they eventually agreed upon for your implementation, or are you looking for more information on a specific part of the code they discussed?


Weirdly, if you use python-tls-fingerprint, you can bypass dpi even on the most restrictive ISPs in Iran.
and for now to imitate python-tls-fingerprint, you just need to imitate it's cipherSuites (of course, the fragment also needs to be set up correctly so that cipherSuites is read by GFW but not SNI)

but even python-3.14.6-default-tls uses some cipherSuites that are listed in go-crypto/tls-InsecureCipherSuites.
so to imitate python-tls-fingerprint, you need to be able to use "InsecureCipherSuites" as well.

The word "InsecureCipherSuites" is a bit confusing. actually, they are not insecure, they are just obsolete and generally not recommended.

///
to be more precise, they only allowed python-tls-cipherSuites, which means the first 13 cipher should be almost identical to the first 13 in python-cipherSuites (with a few exceptions), for example the 13th-cipher must be "TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256 (0xc027)", otherwise dpi cannot be bypassed.

also, utls does not have python-fingerprint and none of the other fingerprints, even the old ones, have this feature, so we have to use tls with custom-cipherSuites.

جعبه ابزار قطعی کامل اینترنتدانلود فیلترشکن مجانی وی پی ان رایگان
https://github.com/appshubcc/Bettbox/releases 
بت باکس ویتوری وی توری
https://chromewebstore.google.com/detail/rooza/cclmobdmakfgnpnnibjfcgkinmejblej/privacy
دوبله فارسی همه جا خودکار اتوماتیک سرخود
https://chromewebstore.google.com/detail/livdub/egoacpkbpnnjfebaadejafadmocfhenp?utm_source=x
rooza تقویم روزا
https://github.com/guardianproject/orbot-android
وی پی ان فیلترشکن اوربوت تور
https://github.com/CluvexStudio/Aether
ایتر اتر وی توری
atomicmail.io ایمیل رایگان مجانی
https://github.com/WhiteDNS/WhiteDNS-Android/releases
فیلترشکن برای قطعی کامل اینترنت


دانلود و نصب اپ ios Coreforge:
https://testflight.apple.com/join/u1vfEHur...


CoreForge دو موتور اتصال دارد:

RelayForge
حالت روزمره و پیشنهادی برای استفاده عادی، سرعت بهتر، پایداری بیشتر، وب‌گردی، اپلیکیشن‌ها و استفاده عمومی.

DnsForge
حالت اضطراری و آخرین راه‌حل برای زمانی که روش‌های معمول مثل VPN، پروکسی، VLESS، Trojan یا WireGuard بسته می‌شوند و فقط مسیر DNS قابل استفاده است.

در این آموزش بخش‌های اصلی برنامه، نحوه اتصال، انتخاب سرور، تست Resolverها، حالت Full Tunnel، تنظیمات پیشرفته و کاربرد CoreForge در دوران قطعی اینترنت توضیح داده شده.

دانلود و نصب CoreForge برای iOS 
https://github.com/WhiteDNS/WhiteDNS-Wizard
معماری نوین سرکوب دیجیتال در ایران: از اختلال هوشمند تا زیرساختهای وارداتی

تبیین تغییر رویکرد سیستم فیلترینگ ایران از مسدودسازی ساده به تخریب هوشمند (DBF) و نقش تکنولوژیهای چینی و روسی
بخش دوم: زیرساختهای سركوب و متحدان بينالمللى

بخش اول: پارادایم جدید فیلترینگ (تخريب به جاى قطع)

صادرات مدل «دیوار آتش بزرگ» چین

فیلترینگ جدید (DBF)

فیلترینگ سنتی (Binary)

X

HIKVISION Tiandy

ZTE

Vs

10

HUAWE

س -

00000

DPI
0000 18

OO

Frart٦

O

شركتهای Hikvision و Tiandy

شرکتهای Huawei و ZTE

ابزارهاى نظارت تصويرى را تامين می كنند.

تجهیزات DPI تامين مى كنند.

وضعيت اتصال: اتصال برقرار اما بسيار كند وفرسایشی

وضعيت اتصال: قطع يا ريست فورى (Reset/Drop)

همكاری فنی روسیه در شنود واختلال

قابلیت ردبابی: نامرئی و با هزینهی سیاسى كمتر

قابليت رديابى: شفاف و قابل تشخيص توسط كارير

تاکتیک اصلی: تحلیل رفتار و امضای پروتکل
(Fingerprinting)

تاکتیک اصلى: مسدودسازى IP يا دامنه (SNI)

IP/SHI

شركتهای روسی ®Protei

فیلترینگ مبتنى بر تخريب كیفیت (DBF)

شرکتهای روسی مانند Protel در ارتقاى

ME

سیستمهای شنود و شناسایی هستههای هماهنگی

تحلیل رفتاری و انگشتنگاری

O

اعتراضات نقش دارند.

(Fingerprinting)
سیستم با تحلیل امضای ديجيتال TLS،
به جای قطع می یابد که سرویس عملاً.
ترافيکهای غیرمرورگر و فیلترشكنها را
شناسایی و قطع میکند.

مقابله با اينترنت ماهوارهاى

پایداری ترنسپورتهای بدون رمزنگاری

استفاده از سامانههای جنگ الکترونیک

Starlink

LS

O

روسی برای ایجاد پارازیت و اختلال در

در كمال تمجب، ترنسپورتهای بدون TLS (مانند WebSocket

سرویسهایی مانند استارلینک.

ساده) در برابر سیستم جدید پایدارتر از نسخههای

TLS

رمزنگاریشده عمل کردهاند.

٠٠٠

WebSocket ساده notebookllm gemininotebook


فیلترشکن VPn 
وی پی ان رایگان ایران واتساپ یوتیوب اینستاگرام instagram whatsapp youtube facebook فیس بوک فیسبوک 

blackout status report june 19 6/19/2026 

what isps have internet none
what datacenters have internet non

[
    {
        "__Credits__": {
            "creator": "@patterniha",
            "donate1": "USDT (BEP20): 0x76a768B53Ca77B43086946315f0BDF21156bF424",
            "donate2": "USDT (TRC20): TU5gKvKqcXPn8itp1DouBCwcqGHMemBm8o",
            "donate3": "TON (TON): UQAc-mZB3y7uxWHKiMmq0ORZEYgycWDWZ4V1k73HsXvTJx-i"
        },
        "remarks": "Serverless-v44-low_delay",
        "version": {
            "min": "26.6.1"
        },
        "log": {
            "loglevel": "warning",
            "dnsLog": false,
            "access": "none"
        },
        "policy": {
            "levels": {
                "0": {
                    "uplinkOnly": 0,
                    "downlinkOnly": 0
                },
                "1": {
                    "uplinkOnly": 0,
                    "downlinkOnly": 0,
                    "connIdle": 12
                }
            }
        },
        "dns": {
            "hosts": {
                "cloudflare-dns.com": "challenges.cloudflare.com"
            },
            "servers": [
                {
                    "address": "fakedns",
                    "domains": [
                        "domain:ir",
                        "geosite:private",
                        "geosite:category-ir",
                        "geosite:xai",
                        "geosite:openai",
                        "geosite:google-deepmind",
                        "geosite:anthropic",
                        "geosite:github",
                        "geosite:microsoft",
                        "geosite:golang",
                        "geosite:python",
                        "geosite:rust",
                        "full:challenges.cloudflare.com"
                    ]
                },
                {
                    "tag": "no-filter-dns",
                    "address": "https://cloudflare-dns.com/dns-query",
                    "timeoutMs": 12000,
                    "finalQuery": true
                },
                {
                    "address": "localhost",
                    "domains": [
                        "domain:ir",
                        "geosite:private",
                        "geosite:category-ir",
                        "geosite:xai",
                        "geosite:openai",
                        "geosite:google-deepmind",
                        "geosite:anthropic",
                        "geosite:github",
                        "geosite:microsoft",
                        "geosite:golang",
                        "geosite:python",
                        "geosite:rust",
                        "full:challenges.cloudflare.com"
                    ],
                    "finalQuery": true
                }
            ],
            "queryStrategy": "UseSystem",
            "useSystemHosts": true,
            "serveStale": true
        },
        "inbounds": [
            {
                "tag": "mixed-in",
                "port": 10808,
                "protocol": "mixed",
                "sniffing": {
                    "enabled": true,
                    "destOverride": [
                        "fakedns",
                        "tls",
                        "http",
                        "quic"
                    ],
                    "routeOnly": false
                },
                "settings": {
                    "udp": true,
                    "ip": "127.0.0.1"
                },
                "streamSettings": {
                    "sockopt": {
                        "tcpKeepAliveInterval": 1,
                        "tcpKeepAliveIdle": 11
                    }
                }
            }
        ],
        "outbounds": [
            {
                "tag": "block",
                "protocol": "block"
            },
            {
                "tag": "tcp-direct",
                "protocol": "direct",
                "streamSettings": {
                    "sockopt": {
                        "domainStrategy": "ForceIP",
                        "happyEyeballs": {
                            "tryDelayMs": 300,
                            "prioritizeIPv6": true,
                            "interleave": 2,
                            "maxConcurrentTry": 20
                        }
                    }
                }
            },
            {
                "tag": "udp-direct",
                "protocol": "direct",
                "settings": {
                    "targetStrategy": "ForceIPv6v4"
                }
            },
            {
                "tag": "dns-out",
                "protocol": "dns",
                "settings": {
                    "userLevel": 1
                }
            },
            {
                "tag": "tcp-fragment",
                "protocol": "direct",
                "streamSettings": {
                    "finalmask": {
                        "tcp": [
                            {
                                "type": "fragment",
                                "settings": {
                                    "packets": "1-1",
                                    "length": "1",
                                    "delay": "1",
                                    "maxSplit": "163"
                                }
                            }
                        ]
                    },
                    "sockopt": {
                        "domainStrategy": "ForceIP",
                        "happyEyeballs": {
                            "tryDelayMs": 300,
                            "prioritizeIPv6": true,
                            "interleave": 2,
                            "maxConcurrentTry": 20
                        }
                    }
                }
            },
            {
                "tag": "tcp-fragment-tls",
                "protocol": "direct",
                "streamSettings": {
                    "finalmask": {
                        "tcp": [
                            {
                                "type": "fragment",
                                "settings": {
                                    "packets": "1-1",
                                    "length": "1",
                                    "delay": "1",
                                    "maxSplit": "163"
                                }
                            },
                            {
                                "type": "fragment",
                                "settings": {
                                    "packets": "tlshello",
                                    "length": "124",
                                    "delay": "0",
                                    "maxSplit": "0"
                                }
                            }
                        ]
                    },
                    "sockopt": {
                        "domainStrategy": "ForceIP",
                        "happyEyeballs": {
                            "tryDelayMs": 300,
                            "prioritizeIPv6": true,
                            "interleave": 2,
                            "maxConcurrentTry": 20
                        }
                    }
                }
            },
            {
                "tag": "udp-noises",
                "protocol": "direct",
                "settings": {
                    "targetStrategy": "ForceIPv6v4"
                },
                "streamSettings": {
                    "finalmask": {
                        "udp": [
                            {
                                "type": "noise",
                                "settings": {
                                    "reset": "28",
                                    "noise": [
                                        {
                                            "rand": "1200-1230",
                                            "delay": "10"
                                        },
                                        {
                                            "rand": "1200-1230",
                                            "delay": "10"
                                        },
                                        {
                                            "rand": "1200-1230",
                                            "delay": "10"
                                        },
                                        {
                                            "rand": "1200-1230",
                                            "delay": "10"
                                        },
                                        {
                                            "rand": "1200-1230",
                                            "delay": "10"
                                        },
                                        {
                                            "rand": "1200-1230",
                                            "delay": "10"
                                        },
                                        {
                                            "rand": "1200-1230",
                                            "delay": "10"
                                        },
                                        {
                                            "rand": "1200-1230",
                                            "delay": "10"
                                        },
                                        {
                                            "rand": "1200-1230",
                                            "delay": "10"
                                        },
                                        {
                                            "rand": "1200-1230",
                                            "delay": "10"
                                        },
                                        {
                                            "rand": "1200-1230",
                                            "delay": "10"
                                        },
                                        {
                                            "rand": "1200-1230",
                                            "delay": "10"
                                        },
                                        {
                                            "rand": "1200-1230",
                                            "delay": "10"
                                        },
                                        {
                                            "rand": "1200-1230",
                                            "delay": "10"
                                        },
                                        {
                                            "rand": "1200-1230",
                                            "delay": "10"
                                        },
                                        {
                                            "rand": "1200-1230",
                                            "delay": "10"
                                        },
                                        {
                                            "rand": "1200-1230",
                                            "delay": "10"
                                        },
                                        {
                                            "rand": "1200-1230",
                                            "delay": "10"
                                        },
                                        {
                                            "rand": "1200-1230",
                                            "delay": "10"
                                        },
                                        {
                                            "rand": "1200-1230",
                                            "delay": "10"
                                        },
                                        {
                                            "rand": "1200-1230",
                                            "delay": "10"
                                        },
                                        {
                                            "rand": "1200-1230",
                                            "delay": "10"
                                        },
                                        {
                                            "rand": "1200-1230",
                                            "delay": "10"
                                        },
                                        {
                                            "rand": "1200-1230",
                                            "delay": "10"
                                        }
                                    ]
                                }
                            }
                        ]
                    }
                }
            }
        ],
        "routing": {
            "domainStrategy": "IPOnDemand",
            "rules": [
                {
                    "outboundTag": "tcp-fragment",
                    "inboundTag": [
                        "no-filter-dns"
                    ]
                },
                {
                    "outboundTag": "dns-out",
                    "port": 53
                },
                {
                    "outboundTag": "tcp-direct",
                    "network": "tcp",
                    "domain": [
                        "domain:ir",
                        "geosite:private",
                        "geosite:category-ir",
                        "geosite:xai",
                        "geosite:openai",
                        "geosite:google-deepmind",
                        "geosite:anthropic",
                        "geosite:github",
                        "geosite:microsoft",
                        "geosite:golang",
                        "geosite:python",
                        "geosite:rust"
                    ]
                },
                {
                    "outboundTag": "udp-direct",
                    "network": "udp",
                    "domain": [
                        "domain:ir",
                        "geosite:private",
                        "geosite:category-ir",
                        "geosite:xai",
                        "geosite:openai",
                        "geosite:google-deepmind",
                        "geosite:anthropic",
                        "geosite:github",
                        "geosite:microsoft",
                        "geosite:golang",
                        "geosite:python",
                        "geosite:rust"
                    ]
                },
                {
                    "outboundTag": "block",
                    "ip": [
                        "10.10.34.0/24",
                        "2001:4188:2:600::/64"
                    ]
                },
                {
                    "outboundTag": "tcp-direct",
                    "network": "tcp",
                    "ip": [
                        "geoip:private",
                        "geoip:ir"
                    ]
                },
                {
                    "outboundTag": "udp-direct",
                    "network": "udp",
                    "ip": [
                        "geoip:private",
                        "geoip:ir"
                    ]
                },
                {
                    "outboundTag": "udp-noises",
                    "network": "udp",
                    "protocol": [
                        "quic"
                    ],
                    "ip": [
                        "0.0.0.0/0",
                        "::/0"
                    ]
                },
                {
                    "outboundTag": "udp-noises",
                    "network": "udp",
                    "port": "443",
                    "ip": [
                        "0.0.0.0/0",
                        "::/0"
                    ]
                },
                {
                    "outboundTag": "udp-direct",
                    "network": "udp",
                    "ip": [
                        "0.0.0.0/0",
                        "::/0"
                    ]
                },
                {
                    "outboundTag": "tcp-fragment",
                    "network": "tcp",
                    "protocol": [
                        "tls"
                    ],
                    "ip": [
                        "0.0.0.0/0",
                        "::/0"
                    ]
                },
                {
                    "outboundTag": "tcp-fragment",
                    "network": "tcp",
                    "port": "443",
                    "ip": [
                        "0.0.0.0/0",
                        "::/0"
                    ]
                },
                {
                    "outboundTag": "tcp-fragment",
                    "network": "tcp",
                    "ip": [
                        "0.0.0.0/0",
                        "::/0"
                    ]
                },
                {
                    "outboundTag": "block",
                    "port": "0-65535"
                }
            ]
        }
    },
    {
        "__Credits__": {
            "creator": "@patterniha",
            "donate1": "USDT (BEP20): 0x76a768B53Ca77B43086946315f0BDF21156bF424",
            "donate2": "USDT (TRC20): TU5gKvKqcXPn8itp1DouBCwcqGHMemBm8o",
            "donate3": "TON (TON): UQAc-mZB3y7uxWHKiMmq0ORZEYgycWDWZ4V1k73HsXvTJx-i"
        },
        "remarks": "Serverless-v44-high_delay",
        "version": {
            "min": "26.6.1"
        },
        "log": {
            "loglevel": "warning",
            "dnsLog": false,
            "access": "none"
        },
        "policy": {
            "levels": {
                "0": {
                    "uplinkOnly": 0,
                    "downlinkOnly": 0
                },
                "1": {
                    "uplinkOnly": 0,
                    "downlinkOnly": 0,
                    "connIdle": 12
                }
            }
        },
        "dns": {
            "hosts": {
                "cloudflare-dns.com": "challenges.cloudflare.com"
            },
            "servers": [
                {
                    "address": "fakedns",
                    "domains": [
                        "domain:ir",
                        "geosite:private",
                        "geosite:category-ir",
                        "geosite:xai",
                        "geosite:openai",
                        "geosite:google-deepmind",
                        "geosite:anthropic",
                        "geosite:github",
                        "geosite:microsoft",
                        "geosite:golang",
                        "geosite:python",
                        "geosite:rust",
                        "full:challenges.cloudflare.com"
                    ]
                },
                {
                    "tag": "no-filter-dns",
                    "address": "https://cloudflare-dns.com/dns-query",
                    "timeoutMs": 12000,
                    "finalQuery": true
                },
                {
                    "address": "localhost",
                    "domains": [
                        "domain:ir",
                        "geosite:private",
                        "geosite:category-ir",
                        "geosite:xai",
                        "geosite:openai",
                        "geosite:google-deepmind",
                        "geosite:anthropic",
                        "geosite:github",
                        "geosite:microsoft",
                        "geosite:golang",
                        "geosite:python",
                        "geosite:rust",
                        "full:challenges.cloudflare.com"
                    ],
                    "finalQuery": true
                }
            ],
            "queryStrategy": "UseSystem",
            "useSystemHosts": true,
            "serveStale": true
        },
        "inbounds": [
            {
                "tag": "mixed-in",
                "port": 10808,
                "protocol": "mixed",
                "sniffing": {
                    "enabled": true,
                    "destOverride": [
                        "fakedns",
                        "tls",
                        "http",
                        "quic"
                    ],
                    "routeOnly": false
                },
                "settings": {
                    "udp": true,
                    "ip": "127.0.0.1"
                },
                "streamSettings": {
                    "sockopt": {
                        "tcpKeepAliveInterval": 1,
                        "tcpKeepAliveIdle": 11
                    }
                }
            }
        ],
        "outbounds": [
            {
                "tag": "block",
                "protocol": "block"
            },
            {
                "tag": "tcp-direct",
                "protocol": "direct",
                "streamSettings": {
                    "sockopt": {
                        "domainStrategy": "ForceIP",
                        "happyEyeballs": {
                            "tryDelayMs": 300,
                            "prioritizeIPv6": true,
                            "interleave": 2,
                            "maxConcurrentTry": 20
                        }
                    }
                }
            },
            {
                "tag": "udp-direct",
                "protocol": "direct",
                "settings": {
                    "targetStrategy": "ForceIPv6v4"
                }
            },
            {
                "tag": "dns-out",
                "protocol": "dns",
                "settings": {
                    "userLevel": 1
                }
            },
            {
                "tag": "tcp-fragment",
                "protocol": "direct",
                "streamSettings": {
                    "finalmask": {
                        "tcp": [
                            {
                                "type": "fragment",
                                "settings": {
                                    "packets": "1-1",
                                    "length": "1",
                                    "delay": "11",
                                    "maxSplit": "163"
                                }
                            }
                        ]
                    },
                    "sockopt": {
                        "domainStrategy": "ForceIP",
                        "happyEyeballs": {
                            "tryDelayMs": 300,
                            "prioritizeIPv6": true,
                            "interleave": 2,
                            "maxConcurrentTry": 20
                        }
                    }
                }
            },
            {
                "tag": "tcp-fragment-tls",
                "protocol": "direct",
                "streamSettings": {
                    "finalmask": {
                        "tcp": [
                            {
                                "type": "fragment",
                                "settings": {
                                    "packets": "1-1",
                                    "length": "1",
                                    "delay": "11",
                                    "maxSplit": "163"
                                }
                            },
                            {
                                "type": "fragment",
                                "settings": {
                                    "packets": "tlshello",
                                    "length": "124",
                                    "delay": "0",
                                    "maxSplit": "0"
                                }
                            }
                        ]
                    },
                    "sockopt": {
                        "domainStrategy": "ForceIP",
                        "happyEyeballs": {
                            "tryDelayMs": 300,
                            "prioritizeIPv6": true,
                            "interleave": 2,
                            "maxConcurrentTry": 20
                        }
                    }
                }
            },
            {
                "tag": "udp-noises",
                "protocol": "direct",
                "settings": {
                    "targetStrategy": "ForceIPv6v4"
                },
                "streamSettings": {
                    "finalmask": {
                        "udp": [
                            {
                                "type": "noise",
                                "settings": {
                                    "reset": "28",
                                    "noise": [
                                        {
                                            "rand": "1200-1230",
                                            "delay": "10"
                                        },
                                        {
                                            "rand": "1200-1230",
                                            "delay": "10"
                                        },
                                        {
                                            "rand": "1200-1230",
                                            "delay": "10"
                                        },
                                        {
                                            "rand": "1200-1230",
                                            "delay": "10"
                                        },
                                        {
                                            "rand": "1200-1230",
                                            "delay": "10"
                                        },
                                        {
                                            "rand": "1200-1230",
                                            "delay": "10"
                                        },
                                        {
                                            "rand": "1200-1230",
                                            "delay": "10"
                                        },
                                        {
                                            "rand": "1200-1230",
                                            "delay": "10"
                                        },
                                        {
                                            "rand": "1200-1230",
                                            "delay": "10"
                                        },
                                        {
                                            "rand": "1200-1230",
                                            "delay": "10"
                                        },
                                        {
                                            "rand": "1200-1230",
                                            "delay": "10"
                                        },
                                        {
                                            "rand": "1200-1230",
                                            "delay": "10"
                                        },
                                        {
                                            "rand": "1200-1230",
                                            "delay": "10"
                                        },
                                        {
                                            "rand": "1200-1230",
                                            "delay": "10"
                                        },
                                        {
                                            "rand": "1200-1230",
                                            "delay": "10"
                                        },
                                        {
                                            "rand": "1200-1230",
                                            "delay": "10"
                                        },
                                        {
                                            "rand": "1200-1230",
                                            "delay": "10"
                                        },
                                        {
                                            "rand": "1200-1230",
                                            "delay": "10"
                                        },
                                        {
                                            "rand": "1200-1230",
                                            "delay": "10"
                                        },
                                        {
                                            "rand": "1200-1230",
                                            "delay": "10"
                                        },
                                        {
                                            "rand": "1200-1230",
                                            "delay": "10"
                                        },
                                        {
                                            "rand": "1200-1230",
                                            "delay": "10"
                                        },
                                        {
                                            "rand": "1200-1230",
                                            "delay": "10"
                                        },
                                        {
                                            "rand": "1200-1230",
                                            "delay": "10"
                                        }
                                    ]
                                }
                            }
                        ]
                    }
                }
            }
        ],
        "routing": {
            "domainStrategy": "IPOnDemand",
            "rules": [
                {
                    "outboundTag": "tcp-fragment",
                    "inboundTag": [
                        "no-filter-dns"
                    ]
                },
                {
                    "outboundTag": "dns-out",
                    "port": 53
                },
                {
                    "outboundTag": "tcp-direct",
                    "network": "tcp",
                    "domain": [
                        "domain:ir",
                        "geosite:private",
                        "geosite:category-ir",
                        "geosite:xai",
                        "geosite:openai",
                        "geosite:google-deepmind",
                        "geosite:anthropic",
                        "geosite:github",
                        "geosite:microsoft",
                        "geosite:golang",
                        "geosite:python",
                        "geosite:rust"
                    ]
                },
                {
                    "outboundTag": "udp-direct",
                    "network": "udp",
                    "domain": [
                        "domain:ir",
                        "geosite:private",
                        "geosite:category-ir",
                        "geosite:xai",
                        "geosite:openai",
                        "geosite:google-deepmind",
                        "geosite:anthropic",
                        "geosite:github",
                        "geosite:microsoft",
                        "geosite:golang",
                        "geosite:python",
                        "geosite:rust"
                    ]
                },
                {
                    "outboundTag": "block",
                    "ip": [
                        "10.10.34.0/24",
                        "2001:4188:2:600::/64"
                    ]
                },
                {
                    "outboundTag": "tcp-direct",
                    "network": "tcp",
                    "ip": [
                        "geoip:private",
                        "geoip:ir"
                    ]
                },
                {
                    "outboundTag": "udp-direct",
                    "network": "udp",
                    "ip": [
                        "geoip:private",
                        "geoip:ir"
                    ]
                },
                {
                    "outboundTag": "udp-noises",
                    "network": "udp",
                    "protocol": [
                        "quic"
                    ],
                    "ip": [
                        "0.0.0.0/0",
                        "::/0"
                    ]
                },
                {
                    "outboundTag": "udp-noises",
                    "network": "udp",
                    "port": "443",
                    "ip": [
                        "0.0.0.0/0",
                        "::/0"
                    ]
                },
                {
                    "outboundTag": "udp-direct",
                    "network": "udp",
                    "ip": [
                        "0.0.0.0/0",
                        "::/0"
                    ]
                },
                {
                    "outboundTag": "tcp-fragment",
                    "network": "tcp",
                    "protocol": [
                        "tls"
                    ],
                    "ip": [
                        "0.0.0.0/0",
                        "::/0"
                    ]
                },
                {
                    "outboundTag": "tcp-fragment",
                    "network": "tcp",
                    "port": "443",
                    "ip": [
                        "0.0.0.0/0",
                        "::/0"
                    ]
                },
                {
                    "outboundTag": "tcp-fragment",
                    "network": "tcp",
                    "ip": [
                        "0.0.0.0/0",
                        "::/0"
                    ]
                },
                {
                    "outboundTag": "block",
                    "port": "0-65535"
                }
            ]
        }
    }
]


{
  "__Credits__": {
    "creator": "@patterniha",
    "donate1": "USDT (BEP20): 0x76a768B53Ca77B43086946315f0BDF21156bF424",
    "donate2": "USDT (TRC20): TU5gKvKqcXPn8itp1DouBCwcqGHMemBm8o",
    "donate3": "TON (TON): UQAc-mZB3y7uxWHKiMmq0ORZEYgycWDWZ4V1k73HsXvTJx-i"
  },


  "remarks": "Serverless-v44-high_delay",

  "version": {
    "min": "26.6.1"
  },

  "log": {
    "loglevel": "warning", "dnsLog": false, "access": "none"
  },

  "policy": {
    "levels": {
      "0": {
        "uplinkOnly": 0,
        "downlinkOnly": 0
      },
      "1": {
        "uplinkOnly": 0,
        "downlinkOnly": 0,
        "connIdle": 12
      }
    }
  },

  "dns":{
    "hosts": {
      "cloudflare-dns.com": "challenges.cloudflare.com"
    },
    "servers": [
      {
        "address": "fakedns",
        "domains": ["domain:ir", "geosite:private", "geosite:category-ir", "geosite:xai", "geosite:openai", "geosite:google-deepmind", "geosite:anthropic", "geosite:github", "geosite:microsoft", "geosite:golang", "geosite:python", "geosite:rust", "full:challenges.cloudflare.com"]
      },
      {
        "tag": "no-filter-dns",
        "address": "https://cloudflare-dns.com/dns-query",
        "timeoutMs": 12000,
        "finalQuery": true
      },
      {
        "address": "localhost",
        "domains": ["domain:ir", "geosite:private", "geosite:category-ir", "geosite:xai", "geosite:openai", "geosite:google-deepmind", "geosite:anthropic", "geosite:github", "geosite:microsoft", "geosite:golang", "geosite:python", "geosite:rust", "full:challenges.cloudflare.com"],
        "finalQuery": true
      }
    ],
    "queryStrategy": "UseSystem",
    "useSystemHosts": true,
	"serveStale": true
  },

  "inbounds": [
    {
      "tag": "mixed-in",
      "port": 10808,
      "protocol": "mixed",
      "sniffing": {
        "enabled": true,
        "destOverride": ["fakedns", "tls", "http", "quic"],
        "routeOnly": false
      },
      "settings": {
        "udp": true,
        "ip": "127.0.0.1"
      },
      "streamSettings": {
        "sockopt": {
          "tcpKeepAliveInterval": 1,
          "tcpKeepAliveIdle": 11
        }
      }
    }
  ],

  "outbounds": [
    {
      "tag": "block",
      "protocol": "block"
    },
    {
      "tag": "tcp-direct",
      "protocol": "direct",
      "streamSettings": {
        "sockopt": {
          "domainStrategy": "ForceIP",
          "happyEyeballs": {"tryDelayMs": 300, "prioritizeIPv6": true, "interleave": 2, "maxConcurrentTry": 20}
        }
      }
    },
	{
      "tag": "udp-direct",
      "protocol": "direct",
      "settings": {
        "targetStrategy": "ForceIPv6v4"
	  }
	},
    {
      "tag": "dns-out",
      "protocol": "dns",
      "settings": {
        "userLevel": 1
      }
    },
    {
      "tag": "tcp-fragment",
      "protocol": "direct",
      "streamSettings": {
        "finalmask": {
          "tcp": [
            {"type": "fragment", "settings": {"packets": "1-1", "length": "1", "delay": "11", "maxSplit": "163"}}
          ]
        },
        "sockopt": {
          "domainStrategy": "ForceIP",
          "happyEyeballs": {"tryDelayMs": 300, "prioritizeIPv6": true, "interleave": 2, "maxConcurrentTry": 20}
        }
      }
    },
    {
      "tag": "tcp-fragment-tls",
      "protocol": "direct",
      "streamSettings": {
        "finalmask": {
          "tcp": [
            {"type": "fragment", "settings": {"packets": "1-1", "length": "1", "delay": "11", "maxSplit": "163"}},
			{"type": "fragment", "settings": {"packets": "tlshello", "length": "124", "delay": "0", "maxSplit": "0"}}
          ]
        },
        "sockopt": {
          "domainStrategy": "ForceIP",
          "happyEyeballs": {"tryDelayMs": 300, "prioritizeIPv6": true, "interleave": 2, "maxConcurrentTry": 20}
        }
      }
    },
    {
      "tag": "udp-noises",
      "protocol": "direct",
      "settings": {
        "targetStrategy": "ForceIPv6v4"
      },
      "streamSettings": {
        "finalmask": {
          "udp": [
            {
              "type": "noise",
              "settings": {
                "reset": "28",
                "noise": [
                  {"rand": "1200-1230", "delay": "10"}, {"rand": "1200-1230", "delay": "10"}, {"rand": "1200-1230", "delay": "10"},
                  {"rand": "1200-1230", "delay": "10"}, {"rand": "1200-1230", "delay": "10"}, {"rand": "1200-1230", "delay": "10"},
                  {"rand": "1200-1230", "delay": "10"}, {"rand": "1200-1230", "delay": "10"}, {"rand": "1200-1230", "delay": "10"},
                  {"rand": "1200-1230", "delay": "10"}, {"rand": "1200-1230", "delay": "10"}, {"rand": "1200-1230", "delay": "10"},
                  {"rand": "1200-1230", "delay": "10"}, {"rand": "1200-1230", "delay": "10"}, {"rand": "1200-1230", "delay": "10"},
                  {"rand": "1200-1230", "delay": "10"}, {"rand": "1200-1230", "delay": "10"}, {"rand": "1200-1230", "delay": "10"},
                  {"rand": "1200-1230", "delay": "10"}, {"rand": "1200-1230", "delay": "10"}, {"rand": "1200-1230", "delay": "10"},
                  {"rand": "1200-1230", "delay": "10"}, {"rand": "1200-1230", "delay": "10"}, {"rand": "1200-1230", "delay": "10"}
                ]
              }
            }
          ]
        }
      }
    }
  ],

  "routing": {
    "domainStrategy": "IPOnDemand",
    "rules": [
      {
        "outboundTag": "tcp-fragment",
        "inboundTag": ["no-filter-dns"]
      },
      {
        "outboundTag": "dns-out",
        "port": 53
      },
      {
        "outboundTag": "tcp-direct",
        "network": "tcp", "domain": ["domain:ir", "geosite:private", "geosite:category-ir", "geosite:xai", "geosite:openai", "geosite:google-deepmind", "geosite:anthropic", "geosite:github", "geosite:microsoft", "geosite:golang", "geosite:python", "geosite:rust"]
      },
	  {
        "outboundTag": "udp-direct",
        "network": "udp", "domain": ["domain:ir", "geosite:private", "geosite:category-ir", "geosite:xai", "geosite:openai", "geosite:google-deepmind", "geosite:anthropic", "geosite:github", "geosite:microsoft", "geosite:golang", "geosite:python", "geosite:rust"]
      },
      {
        "outboundTag": "block",
        "ip": ["10.10.34.0/24", "2001:4188:2:600::/64"]
      },
      {
        "outboundTag": "tcp-direct",
        "network": "tcp", "ip": ["geoip:private", "geoip:ir"]
      },
	  {
        "outboundTag": "udp-direct",
        "network": "udp", "ip": ["geoip:private", "geoip:ir"]
      },
      {
        "outboundTag": "udp-noises",
        "network": "udp", "protocol": ["quic"], "ip": ["0.0.0.0/0", "::/0"]
      },
      {
        "outboundTag": "udp-noises",
        "network": "udp", "port": "443", "ip": ["0.0.0.0/0", "::/0"]
      },
      {
        "outboundTag": "udp-direct",
        "network": "udp", "ip": ["0.0.0.0/0", "::/0"]
      },
      {
        "outboundTag": "tcp-fragment",
        "network": "tcp", "protocol": ["tls"], "ip": ["0.0.0.0/0", "::/0"]
      },
      {
        "outboundTag": "tcp-fragment",
        "network": "tcp", "port": "443", "ip": ["0.0.0.0/0", "::/0"]
      },
      {
        "outboundTag": "tcp-fragment",
        "network": "tcp", "ip": ["0.0.0.0/0", "::/0"]
      },
      {
        "outboundTag": "block",
        "port": "0-65535"
      }
    ]
  }
}
سلام.
به طور کلی، اون طور که روی چندتا open proxy تست کردم، فرگمنت به صورت selective روی بعضی آی پی ها راحت کار میکنه ولی بعضی آی پی ها مثل کلودفلر، فایروال هنوز سخت گیر هست و اجازه فرگمنت رو نمیده.
البته این تست ها روی دیتاسنتر فروغ آروان گرفته شده که انگار مثل اینترنت خانگی/همراه آی پی ها باز هستن ولی محدودیت ها بیشتره و حتی آی پی هایی که فرگمنت روشون کار میکنه خیلی کند هستن و بعد از چند ثانیه قطع میشن. ( احتمالا همون محدودیت 6 پکت هنوز روی دیتاسنتر فروغ اعمال میشه )

مثالی از open proxy های کمتر محدود شده روی دیتاسنتر فروغ:

{
     "protocol": "freedom",
     "settings": {
       "redirect": "Less-Restricted-ProxyIP:443"
     },
     "streamSettings": {
       "finalmask": {
         "tcp": [
       {"type": "fragment", "settings": {"packets": "tlshello", "length": "1", "delay": "0", "maxSplit": "2"}}
         ]
       }
     },
     "tag": "RedirectToProxyIP"
   }
این مشاهده نشون میده که فایروال کاملا آگاهی داره نسبت به جریان پکت ها و میتونه Reassemble کنه.
البته هنوز اینترنت کاملا باز نشده و خیلی از رنج آی پی ها مثل گوگل کلود و... بسته هستن، از اونجایی که بازسازی کردن پکت ها منابع زیادی مصرف میکنه، انتظار میره در صورت باز شدن اینترنت و بقیه آی پی ها، دیگه محدودیت روی فرگمنت برداشته بشه، ولی باز هم میتونن یه سری آی پی های خاص رو کاملا inspect کنن.
به هر روی، هدف از این issue این بود که بتونیم دنبال یک راه حل دیگه غیر از فرگمنت برای این موضوع باشیم.
من روی همراه اول یه تستی انجام دادم، روی یه آی پی که فرگمنت روش جواب میداد ( اون اوایل که فرگمنت روی آی پی های کلودفلر باز نبود ) اومدم و کانفیگ ورکر رو فرگمنت کردم با دامنه فیلتر و رد شد، اما به هیچ عنوان با SNI Spoofing موفق نشدم.
متد های Desync رو با ابزار های مختلف تست کردم و جواب ندادن.
فقط MitM راحت جواب میده.


ارزیابی بنده این هست که به طور کلی، DPI نمیتونه همه آی پی هارو کامل inspect کنه، چون بسیار هزینه زا هست، صرفا یه سری آی پی های خاص مثل کلودفلر که همین کلودفلر به تنهایی کلی بار ترافیکی داره، چه برسه به مایکروسافت و... که اگر اونها هم قرار باشه کامل inspect بشن، سنگ رو سنگ بند نمیشه.
پس خواه ناخواه آی پی هایی وجود خواهند داشت که محدودیت کمتری روشون اعمال میشه و همین امر به ما کمک میکنه تا از آی پی های دیگه استفاده کنیم.
ما تا الان از ظرفیت آی پی های Edge بسیار کم بهره بردیم.
دوتا راه وجود داره، اگر روشی برای دور زدن محدودیت inspect کامل وجود داره، میشه از اون طریق اقدام کرد و به طور کلی محدودیت رو دور زد.
اگر روشی برای مورد اول وجود نداره، باید با استفاده از ظرفیت آی پی های کمتر محدود شده، راه حلی پیدا کنیم.
هرچند در توییت خودتون خوندم که چندتا راه وجود داره که کار میکنن، امیدوارم اگر روش های هزینه زایی هستن که سخت بلاک میشن، در انتشار اون تعلل نکنید.
به هرحال ورکر های کلادفلر هم محدودیت دارن، بدرد دانلود نمیخورن چون منابع بسیار کمی دارن.
دلایل متعددی ناظر بر این موضوع وجود داره که روش های دور زدن این محدودیت هارو بیشتر انتشار بدیم.
البته صلاح مملکت خویش خسروان دانند، نظر حقیر این بود.





راه اندازی در اندروید
۱. ابتدا آخرین ورژن برنامه v2rayNG را از https://github.com/2dust/v2rayNG/releases دانلود و نصب کنید

۲. حال نیاز به یک سرتیفیکیت شخصی دارید برای اینکار میتوانید همان فایلهای mycert.crt, mycert.key را که در ویندوز ایجاد کردید را به گوشی خود منتقل کنید و از همانها استفاده کنید یا اینکه به طور مثال میتوانید به طور مستقیم از سایت

https://regery.com/en/security/ssl-tools/self-signed-certificate-generator

با یک نام دلخواه سرتیفیکیت بسازید و هر دو فایل crt و key را دانلود کنید در این صورت باید نام فایل crt را به mycert.crt و نام فایل key را به mycert.key تغییر دهید

هشدار: حتما از سرتیفیکیت شخصی خود استفاده کنید و به هیچ عنوان از سرتیفیکیت (crt) دیگران استفاده نکنید و همچنین فایل پرایویت‌کی (key) خود را به هیچ شخصی ندهید

۳. در برنامه v2rayNG و در قسمت Asset files هر دو فایل mycert.crt, mycert.key را وارد کنید

۴. حال باید سرتیفیکیت (crt) را به عنوان یک trusted root certificate به سیستم عامل اندروید معرفی کنید برای این کار مراحل زیر را طی کنید:

Setting -> Security and privacy -> More security settings -> Install from device storage -> CA Certificate -> Install anyway -> Select mycert.crt file on your storage.

اگر با موفقیت این قسمت انجام شود میتوانید سرتیفیکیت وارد شده را در قسمت

Setting -> Security and privacy -> More security settings -> View security certificates -> User.

مشاهده کنید، دقت کنید که این مراحل ممکن است بر روی گوشی های مختلف کمی متفاوت باشد

۵. کانفیگ MITM-DomainFronting.json را از طریق import from locally وارد برنامهv2rayNG کنید و اجرا کنید همچنین دقت کنید که Enable Hev TUN FEATURE در تنظیمات v2rayNG فعال باشد و همچنین پورت پیشفرض 10808 را تغییر نداده باشید.

۶. کار تمام است اکنون میتوانید بر روی مرورگر کروم (و به طور کلی تمامی مرورگرهای مبتنی بر کرومیوم) از این متد استفاده کنید

و در صورتی که از مرورگر فایرفاکس استفاده میکنید باید مراحل اضافه زیر را طی کنید

firefox browser -> Settings -> About Firefox -> Tap the Firefox logo five times -> Navigate to Settings -> Secret Settings -> Toggle "Use third party CA certificates"

دقت کنید برای اندروید غیر روت فقط از طریق مرورگرها میتوانید ازین متد استفاده کنید و برنامه های مستقل امکان استفاده از این متد را معمولا ندارند.



json
{
  "__Credits__": {
    "creator": "@patterniha",
    "donate1": "USDT (BEP20): 0x76a768B53Ca77B43086946315f0BDF21156bF424",
    "donate2": "USDT (TRC20): TU5gKvKqcXPn8itp1DouBCwcqGHMemBm8o",
    "donate3": "TON (TON): UQAc-mZB3y7uxWHKiMmq0ORZEYgycWDWZ4V1k73HsXvTJx-i"
  },


  "remarks": "MITM-DomainFronting_v22",

  "version": {
    "min": "26.2.6"
  },

  "log": {
    "loglevel": "warning", "dnsLog": false, "access": "none"
  },

  "policy": {
    "levels": {
      "0": {
        "uplinkOnly": 0,
        "downlinkOnly": 0
      }
    }
  },

  "dns":{
    "hosts": {
      "geosite:category-ads-all": "#3",
	  "fastly.redirect": "github.githubassets.com",
      "dns.redirect": ["1.1.1.1", "1.0.0.1"]
    },
    "servers": [
      {
        "address": "fakedns",
        "domains": ["domain:ir", "geosite:private", "geosite:category-ir", "full:github.githubassets.com"]
      },
      {
        "tag": "no-filter-dns",
        "address": "h2c://1.1.1.1/dns-query",
        "timeoutMs": 15000,
        "finalQuery": true
      },
      {
        "address": "localhost",
        "domains": ["domain:ir", "geosite:private", "geosite:category-ir", "full:github.githubassets.com"],
        "finalQuery": true
      }
    ],
    "queryStrategy": "UseSystem",
    "useSystemHosts": true,
    "serveStale": true
  },

  "inbounds": [
    {
      "tag": "mixed-in",
      "port": 10808,
      "protocol": "mixed",
      "sniffing": {
        "enabled": true,
        "destOverride": ["fakedns", "tls"],
        "routeOnly": false
      },
      "settings": {
        "udp": true,
        "ip": "127.0.0.1"
      },
      "streamSettings": {
        "sockopt": {
          "tcpKeepAliveInterval": 1,
          "tcpKeepAliveIdle": 11
        }
      }
    },
	{
      "port": 11666,
      "tag": "tls-decrypt-h11",
      "protocol": "tunnel",
      "settings": {
        "network": "tcp",
        "port": 443,
        "followRedirect": true
      },
      "streamSettings": {
        "security": "tls",
        "tlsSettings": {
          "alpn": ["http/1.1"],
          "certificates": [
            {
              "usage": "issue",
              "certificateFile": "mycert.crt",
              "keyFile": "mycert.key"
            }
          ]
        }
      }
    },
    {
      "port": 11777,
      "tag": "tls-decrypt-h211",
      "protocol": "tunnel",
      "settings": {
        "network": "tcp",
        "port": 443,
        "followRedirect": true
      },
      "streamSettings": {
        "security": "tls",
        "tlsSettings": {
          "alpn": ["h2","http/1.1"],
          "certificates": [
            {
              "usage": "issue",
              "certificateFile": "mycert.crt",
              "keyFile": "mycert.key"
            }
          ]
        }
      }
    }
  ],

  "outbounds": [
    {
      "tag": "block",
      "protocol": "block"
    },
	{
      "tag": "direct",
      "protocol": "direct",
      "streamSettings": {
        "sockopt": {
          "domainStrategy": "ForceIP",
          "happyEyeballs": {
            "tryDelayMs": 300,
            "prioritizeIPv6": false,
            "interleave": 2,
            "maxConcurrentTry": 20
          }
        }
      }
	},
    {
      "tag": "dns-out",
      "protocol": "dns"
    },
	{
      "tag": "redirect-out-h11",
      "protocol": "direct",
      "settings": {
        "redirect": "127.0.0.1:11666"
      }
    },
    {
      "tag": "redirect-out-h211",
      "protocol": "direct",
      "settings": {
        "redirect": "127.0.0.1:11777"
      }
    },
    {
      "tag": "tls-repack-frommitm",
      "protocol": "direct",
      "streamSettings": {
        "security": "tls",
        "tlsSettings": {
          "serverName": "fromMitM",
          "verifyPeerCertByName": "fromMitM",
          "alpn": ["fromMitM"],
          "fingerprint": "chrome"
        },
		"sockopt": {
          "domainStrategy": "ForceIP",
          "happyEyeballs": {
            "tryDelayMs": 300,
            "prioritizeIPv6": false,
            "interleave": 2,
            "maxConcurrentTry": 20
          }
        }
      }
    },
    {
      "tag": "tls-repack-dns",
      "protocol": "direct",
      "settings": {
        "redirect": "dns.redirect:443"
      },
      "streamSettings": {
        "security": "tls",
        "tlsSettings": {
          "serverName": "www.microsoft.com",
          "verifyPeerCertByName": "fromMitM,www.microsoft.com,www.google.com,dns.google,cloudflare-dns.com,one.one.one.one",
          "alpn": ["fromMitM"],
          "fingerprint": "chrome"
        },
		"sockopt": {
          "domainStrategy": "ForceIP",
          "happyEyeballs": {
            "tryDelayMs": 300,
            "prioritizeIPv6": false,
            "interleave": 2,
            "maxConcurrentTry": 20
          }
        }
      }
    },
	{
      "tag": "tls-repack-google",
      "protocol": "direct",
      "streamSettings": {
        "security": "tls",
        "tlsSettings": {
          "serverName": "www.google.com",
          "verifyPeerCertByName": "fromMitM,www.google.com,dns.google,www.googlevideo.com,www.youtube.com",
          "alpn": ["fromMitM"],
          "fingerprint": "chrome"
        },
		"sockopt": {
          "domainStrategy": "ForceIP",
          "happyEyeballs": {
            "tryDelayMs": 300,
            "prioritizeIPv6": false,
            "interleave": 2,
            "maxConcurrentTry": 20
          }
        }
      }
    },
	{
      "tag": "tls-repack-fastly",
      "protocol": "direct",
      "settings": {
        "redirect": "fastly.redirect:443"
      },
      "streamSettings": {
        "security": "tls",
        "tlsSettings": {
          "serverName": "github.githubassets.com",
          "verifyPeerCertByName": "fromMitM,www.python.org,pypi.org,fastly.com,www.fastly.com,developer.fastly.com,reddit.com,githubassets.com,github.com,github.io,githubusercontent.com,github.githubassets.com",
          "alpn": ["fromMitM"],
          "fingerprint": "chrome"
        },
		"sockopt": {
          "domainStrategy": "ForceIP",
          "happyEyeballs": {
            "tryDelayMs": 300,
            "prioritizeIPv6": false,
            "interleave": 2,
            "maxConcurrentTry": 20
          }
        }
      }
    },
    {
      "tag": "tls-repack-meta",
      "protocol": "direct",
      "streamSettings": {
        "security": "tls",
        "tlsSettings": {
          "serverName": "www.microsoft.com",
          "verifyPeerCertByName": "fromMitM,www.google.com,www.microsoft.com,www.whatsapp.com,www.facebook.com,www.ar.meta.com,www.fb.com,www.whatsapp.net,www.atlassolutions.com,www.secure.facebook.com,www.extern.facebook.com,www.internet.org,www.oculus.com,www.wit.ai,www.facebook-dns.com,www.instagram.com,www.meta.com,www.external-disputes.meta.com,www.fbe2e.com,www.cloud.x2p.facebook.net,www.secure.latest.facebook.com",
          "alpn": ["fromMitM"],
          "fingerprint": "chrome"
        },
		"sockopt": {
          "domainStrategy": "ForceIP",
          "happyEyeballs": {
            "tryDelayMs": 300,
            "prioritizeIPv6": false,
            "interleave": 2,
            "maxConcurrentTry": 20
          }
        }
      }
    }
  ],

  "routing": {
    "domainStrategy": "IPOnDemand",
    "rules": [
      {
	   "outboundTag": "block",
       "domain": ["geosite:category-ads-all"]
      },
      {
	   "outboundTag": "tls-repack-dns",
       "inboundTag": ["no-filter-dns"]
      },
      {
	   "outboundTag": "dns-out",
       "port": 53
      },
      {
	   "outboundTag": "direct",
       "domain": ["domain:ir", "geosite:private", "geosite:category-ir", "geosite:khanacademy"]
      },
      {
	   "outboundTag": "tls-repack-google",
       "domain": ["domain:googlevideo.com"],
       "inboundTag": ["tls-decrypt-h11"]
	  },
      {
	   "outboundTag": "block",
       "inboundTag": ["tls-decrypt-h11"]
	  },
      {
	   "outboundTag": "tls-repack-google",
       "domain": ["geosite:google"],
       "inboundTag": ["tls-decrypt-h211"]
	  },
	  {
	   "outboundTag": "tls-repack-fastly",
       "domain": ["geosite:fastly", "geosite:reddit", "geosite:cnn", "domain:buzzfeed.com"],
       "inboundTag": ["tls-decrypt-h211"]
	  },
      {
	   "outboundTag": "tls-repack-meta",
       "domain": ["geosite:meta"],
       "inboundTag": ["tls-decrypt-h211"]
	  },
	  {
	   "outboundTag": "tls-repack-fastly",
       "ip": ["geoip:fastly"],
       "inboundTag": ["tls-decrypt-h211"]
	  },
      {
	   "outboundTag": "block",
       "inboundTag": ["tls-decrypt-h211"]
	  },
      {
        "outboundTag": "redirect-out-h11",
        "network": "tcp",
        "port": 443,
        "domain": ["domain:googlevideo.com"]
      },
      {
        "outboundTag": "redirect-out-h211",
        "network": "tcp",
        "port": 443,
        "domain": ["geosite:google", "geosite:meta", "geosite:fastly", "geosite:reddit", "geosite:cnn", "domain:buzzfeed.com"]
      },
      {
        "outboundTag": "block",
        "ip": ["10.10.34.0/24", "2001:4188:2:600::/64"]
      },
      {
	   "outboundTag": "direct",
       "ip": ["geoip:private", "geoip:ir"]
      },
	  {
        "outboundTag": "redirect-out-h211",
        "network": "tcp",
        "port": 443,
        "ip": ["geoip:fastly"]
      },
      {
	   "outboundTag": "direct",
       "ip": ["0.0.0.0/0", "::/0"]
      },
      {
	   "outboundTag": "block",
       "port": "0-65535"
      }
    ]
  }
}

































api.figma.com
api2.cursor.sh
atlassian.com
auth.vercel.com
cdnjs.cloudflare.com
cdnjs.com
certum.eu
chess.com
code.visualstudio.com
coursera.org
cursor.com
debian.org
digicert.com
fedoraproject.org
figma.com
github.com
google.com
grafana.com
kiwix.bokhary.fun
libgen.pw
linuxmint.com
mirrormanager.fedoraproject.org
mirrors.mit.edu
mirrors.xtom.de
mirrors.xtom.ee
npmjs.com
nuget.org
pubmed.ncbi.nlm.nih.gov
react.dev
sciencedirect.com
tailwindcss.com
tradingview.com
ubuntu.com
udemy.com
vercel.com
www.atlassian.com




Charles
Use alt domain fronting control depending
 android https://github.com/therealaleph/MasterHttpRelayVPN-RUST/issues
Windows 
https://github.com/patterniha/MITM-DomainFronting
https://github.com/masterking32/MasterHttpRelayVPN/
Psiphon
Https://Telegram.me/s/projectxhttp/346279

https://sub.white-ghost.ru/Q5-2QZ_P35rceF0-

https://bia-pain-bache.github.io/BPB-Worker-Panel/installation/pages-manual/
3.https://github.com/MatinSenPai/SenPaiScanner/
https://github.com/imanbarati/cfnew
ست نیم بها اصلا برای هدف دیگری طراحی شده بود و فقط برای ip های ایران بود و باید ip , sni مچ میبودن تا نیم بها حساب بشه، ولی الان برداشتن کل لیست رو برای ip های کلودفلر سفید کردن
![Uploading media_HJgb_ILWkAEME0U.webp…]()

الان تقریبا اکثر ip های خارجی خاکستری هستند، یعنی در هر کانکشن شما مجاز هستید حداکثر ۶ پکت به سمت سرور خارجی بفرستید، این محدودیت به شدت سختگیرانه است و تقریبا هیچ سرویسی نمیتواند با این محدودیت کار کند، به طور مثال برای کانکشن های https صرفا میتوان یک ریسپانس ساده http را دریافت کرد و شما حتی نمیتوانید درخواست دیگری بفرستید.

///

تقریبا تمام ip های خارجی الان خاکستری هستند، برای بعضی از این ip ها مثل ip های cdn ها و ... sni های محدودی سفید شده، یعنی اگر شما یک درخواست tls با یک sni سفید به یک ip خاکستری ارسال کنید آن کانکشن سفید میشود و میتوانید به صورت نامحدود پکت ارسال کنید! به طور مثال با اینکه الان تمام ip های کلودفلر خاکستری هستند ولی اگه شما یک درخواست با sni سفیدی مثل www .speedtest.net ارسال کنید کانکشن سفید شده و محدودیت ۶ پکت برداشته میشود.

///

در حال حاضر sni های سفید به صورت وایتلیست بسیار محدود هستند، با وجود میلیون ها وبسایت میتوان گفت عملا اینترنت همچنان قطع است و صرفا دسترسی به سرویسهای خاصی امکان پذیر است

///

برای بهبود کیفیت اینترنت حکومت مجبور است بسیاری از دامنه ها رو بدون بررسی دقیق به لیست وایتلیست اضافه کند، به طور مثال الان تمام دامنه هایی که در لیست نیم بها ثبت شده اند همگی سفید هستند، نکته ی قابل تامل این است که اکثر این دامنه ها را فیلترشکن فروشها ثبت کرده اند (قبلا شما میتوانستید صرفا با بالا آوردن یک وبسایت فیک و ثبت درخواست دامنه ی خود را در لیست نیم بها ثبت کنید). بنابراین فیلترشکن فروشهایی که دامنه شان را در لیست نیم بها ثبت کرده اند اکنون دارند سود خوبی به جیب میزنند. [این سیاست های بستن و وایتلیست کردن اینترنت موجب رانت و فساد زیادی شده و شک نکنید که خشم خدا را در بر خواهد داشت]

///

تکنیک sni-spoofing باعث میشود که یک sni فیک توسط فایروال دیده شود و کانکشن سفید شود و محدودیت ۶ پکت ارسال برداشته شود. روش اولی که منتشر کردم اکنون در بسیاری از نت ها بسته شده (یعنی فایروال sni اصلی رو میبینه) ولی طبق گزارشات همچنان بر روی ایرانسل و بسیاری از مناطق حاشیه ای برقرار است. روش دیگری که آن را plan B نامیدم را دیروز با موفقیت تست کردم (با تشکر از دوستانی که نکات فنی خوبی را متذکر شدند و باعث جرقه ایده جدید شدند).
ولی به ۳ دلیل فعلا قصد انتشار ندارم، اول اینکه بسیاری از فیلترشکنهای رایگان اکنون وصل میشوند (به طور مثال سایفون به راحتی با فستلی وصل میشود [توضیحاتش رو در کانال تلگرامم دادم])، دوم اینکه همانطور که گفتم روش اول همچنان رو ایرانسل و بسیاری از مناطق فعال است، و سوم اینکه بسیاری از سرویسها مثل اینستاگرام، واتس‌آپ و یوتویوب و ... به طور مستقیم با mitm در دسترس هستند (در آپدیت جدیدی که بزودی منتشر میشود)

///

به امید پایان رانت در
