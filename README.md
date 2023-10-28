# 10 سوال متداول در مورد جاوااسکریپت

### سوال 1

تفاوت بین undefined و null چیه؟

**پاسخ:**

قبل از اینکه درباره تفاوت‌های این دو صحبت کنیم، بهتره که بدونیم این دو جزو ۸ نوع داده‌ای هستن که توی جاوا اسکریپت وجود دارن:
```['null','undefined', 'string', 'number', 'boolean', 'object', 'symbol', 'bigint'];```
همچنین این دو به اصطلاح falsy value هستن. یعنی مقدارهایی که وقتی اونها رو به Boolean تبدیل می‌کنیم، خروجی false هست:
```console.log(!!null); // false
console.log(!!undefined); // false

console.log(Boolean(null)); // false
console.log(Boolean(undefined)); // false```
و اما تفاوت‌ها. از undefined شروع کنیم:

ویژگی‌های منحصر به فرد undefined:

undefined یک مقدار پیشفرض برای متغیرهایی هست که مقدار ندارن. یعنی موقع ساختن این متغیر بهش مقدار داده نشده
undefined یک خروجی پیشفرض هست برای تابعی که return نداره
وقتی یک پراپرتی (یا key) از یک آبجکت رو صدا بزنیم که وجود نداره، خروجی undefined هست
```let undefinedVar;
function noReturn() {

}

const alphabet = {
    a: "ay",
    b: "bee",
    c: "si"
};

console.log(undefinedVar); // undefined
console.log(noReturn()); // undefined
console.log(alphabet.d); // undefined

console.log(typeof undefinedVar); // undefined```
ویژگی‌های منحصر به فرد null:
در واقع null خودش یک مقدار هست. یک مقدار "پوچ" یا ‌‌"خالی" که می‌تونیم اون رو به متغیرها نسبت بدیم:
```let x = null;

console.log(x); // null
console.log(typeof x); // object!```
به این مقایسه‌ها دقت کنین:
```null == undefined; // true
null === undefined // false```
مقایسه اول true شد چون مقایسه این دو با == همیشه true هست. مقایسه دوم برای این false شد که توی سه مساوی (===) تبدیل نوع انجام نمی‌گیره. نوع یک ‌null برابر با آبجکت و نوع یک undefined همون undefined هست.


### سوال 2

تفاوت میان متغیرهای `let`، `var`، و `const` در جاوااسکریپت چیست؟

**پاسخ:**

- `let` و `const` متغیرهای محلی هستند که در اسکوپ بلوکی قرار دارند، در حالی که `var` متغیرهای تابعی هستند و در اسکوپ تابعی قرار دارند.

### سوال 3

چگونه می‌توان یک تابع (function) در جاوااسکریپت تعریف کرد؟

**پاسخ:**

توابع در جاوااسکریپت با استفاده از کلمه کلیدی `function` تعریف می‌شوند. برای فراخوانی یک تابع از نام تابع به همراه پرانتز استفاده می‌شود.

### سوال 4

تفاوت `null` و `undefined` در جاوااسکریپت چیست؟

**پاسخ:**

هر دو `null` و `undefined` به عنوان مقادیر نامعتبر در جاوااسکریپت شناخته می‌شوند. `null` معمولاً به عنوان مقداری که توسط برنامه‌نویس به عنوان "ناموجود" تعیین می‌شود، و `undefined` به عنوان مقداری که برنامه‌نویس به صراحت نیز تعیین نکرده باشد شناخته می‌شود.

### سوال 5

چگونه می‌توان یک آرایه (array) در جاوااسکریپت تعریف کرد؟

**پاسخ:**

برای تعریف یک آرایه در جاوااسکریپت از علامت `[ ]` استفاده می‌شود. برای اضافه کردن مقادیر به آرایه از دستورات `push()` و یا اندیس‌گذاری (indexing) استفاده می‌شود.

### سوال 6

چگونه می‌توان یک رشته (string) در جاوااسکریپت برش داد؟

**پاسخ:**

می‌توان از دستورات `slice()` یا `substring()` برای برش (substring) رشته‌ها در جاوااسکریپت استفاده کرد.

### سوال 7

تفاوت بین عملگرهای `==` و `===` در جاوااسکریپت چیست؟

**پاسخ:**

`==` یک عملگر مقایسه‌ای (equality operator) است که برای مقایسه مقادیر دو متغیر استفاده می‌شود. `===` نیز یک عملگر مقایسه‌ای است که به عنوان مقایسه مقدار و نوع دو متغیر به کار می‌رود.

### سوال 8

چگونه می‌توان در جاوااسکریپت از Promise و async/await برای مدیریت عملیات ناهمزمان استفاده کرد؟

**پاسخ:**

Promise و async/await ابزارهایی برای مدیریت عملیات ناهمزمان در جاوااسکریپت هستند.

### سوال 9

چگونه می‌توان در جاوااسکریپت یک درخواست HTTP به سرور ارسال کرد؟

**پاسخ:**

به منظور ارسال درخواست HTTP به سرور در جاوااسکریپت، می‌توانید از `fetch` یا `XMLHttpRequest` استفاده کنید.

### سوال 10

چگونه می‌توان عملکرد جاوااسکریپت در وب را بهینه‌سازی کرد؟

**پاسخ:**

بهینه‌سازی عملکرد جاوااسکریپت در وب شامل مواردی مانند Lazy Loading (بارگذاری تنبل) برای عناصر و تصاویر، ترکیب و فشرده‌سازی فایل‌های CSS و JavaScript (Minification) و بهینه‌سازی تصاویر می‌تواند به بهبود سرعت بارگذاری وب‌سایت‌ها و بهینه‌سازی مصرف منابع کمک کنند.
