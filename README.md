
<div align="center">
  <img height="300" width="500" src="/photo_2023-10-03_17-36-00.jpg">
  <h1> سوالات استخدامی مربوط به جاوا اسکریپت</h1>
</div>

<p align="center">
  <a href="https://t.me/js_challenges">Telegram</a> 
</p>

###### سوال 1

تفاوت بین undefined و null چیه؟

<details><summary><b>پاسخ</b></summary>
<p>

قبل از اینکه درباره تفاوت‌های این دو صحبت کنیم، بهتره که بدونیم این دو جزو ۸ نوع داده‌ای هستن که توی جاوا اسکریپت وجود دارن:

```javascript
;[
	'null',
	'undefined',
	'string',
	'number',
	'boolean',
	'object',
	'symbol',
	'bigint',
]
```

همچنین این دو به اصطلاح falsy value هستن. یعنی مقدارهایی که وقتی اونها رو به Boolean تبدیل می‌کنیم، خروجی false هست:

```javascript
console.log(!!null) // false
console.log(!!undefined) // false

console.log(Boolean(null)) // false
console.log(Boolean(undefined)) // false
```

و اما تفاوت‌ها. از undefined شروع کنیم:

ویژگی‌های منحصر به فرد undefined:

undefined یک مقدار پیشفرض برای متغیرهایی هست که مقدار ندارن. یعنی موقع ساختن این متغیر بهش مقدار داده نشده
undefined یک خروجی پیشفرض هست برای تابعی که return نداره
وقتی یک پراپرتی (یا key) از یک آبجکت رو صدا بزنیم که وجود نداره، خروجی undefined هست

```javascript
let undefinedVar
function noReturn() {}

const alphabet = {
	a: 'ay',
	b: 'bee',
	c: 'si',
}

console.log(undefinedVar) // undefined
console.log(noReturn()) // undefined
console.log(alphabet.d) // undefined

console.log(typeof undefinedVar) // undefined
```

ویژگی‌های منحصر به فرد null:
در واقع null خودش یک مقدار هست. یک مقدار "پوچ" یا ‌‌"خالی" که می‌تونیم اون رو به متغیرها نسبت بدیم:

```javascript
let x = null

console.log(x) // null
console.log(typeof x) // object!
```

به این مقایسه‌ها دقت کنین:

```javascript
null == undefined // true
null === undefined // false
```

مقایسه اول true شد چون مقایسه این دو با == همیشه true هست. مقایسه دوم برای این false شد که توی سه مساوی (===) تبدیل نوع انجام نمی‌گیره. نوع یک ‌null برابر با آبجکت و نوع یک undefined همون undefined هست.

</p>
</details>

---

###### سوال 2

عملگر && چکار میکنه؟

<details><summary><b>پاسخ</b></summary>
<p>

عملگر && که AND منطقی گفته میشه بیشتر ماها با اون آشنایی داریم، اما شاید توضیح و کاربرد دقیقش رو ندونیم. دو یا چند عبارت رو درنظر بگیرید که ممکنه هر نوعی داشته باشن. مثلا رشته، عدد یا بولین. وقتی یک && بین دو یا چند عبارت قرار بگیره، بررسی می‌کنه که آیا همه‌ی این عبارت‌ها غیر false هستن یا نه و اگه هیچ کدوم از این مقادیر false نبودن، مقدار آخرین عبارت رو برمی‌گردونه. اما اگه یک کدوم از این عبارت‌ها falsy بودن، مقدار اولین عبارت falsy رو برمی‌گردونه. به بیان ساده‌تر:

‌AND منطقی مقدار اولین عبارت falsy رو برمی‌گردونه و اگه عبارتی falsy نبود، مقدار آخرین عبارت رو برمی‌گردونه.

مثال‌های زیر رو در نظر بگیرید:

```javascript
true && true && true // true
true && true && false // false
null && false && undefined // null

'Hans' && 'Alex' && 'Ali' // "Ali"
true && true && 'Ali' // "Ali"
```

خروجی خط ۱ و ۲ که واضح هستن. خروجی مثال سوم null شده. چون اولین عبارت falsy هست بین این عبارات. توی مثال چهارم و پنجم هیچ کدوم از عبارت‌ها falsy نیستن. پس مقدار آخرین عبارت که "Ali" هست برگردونده میشه.

</p>
</details>

---

###### سوال 3

عملگر || چکار میکنه؟

<details><summary><b>پاسخ</b></summary>
<p>
عملگر || یا ‌OR منطقی اگه بین دو یا چند عبارت با نوع‌های گوناگون قرار بگیره، دنبال اولین عبارتی می‌گرده که truthy هست:

```javascript
console.log(null || 'Oh you again!' || undefined) // Oh you again!
console.log(false || false || 'Yaaay!') // Yaaay!
```

</p>
</details>

---

###### سوال 4

سریع‌ترین راه تبدیل یک رشته به عدد چیه؟

<details><summary><b>پاسخ</b></summary>
<p>
راه‌های زیادی برای تبدیل یک رشته به یک عدد وجود داره. اما سریع‌ترین راه، استفاده از Unary plus (+) هست:

```javascript
console.log(+'29') // 29 (typeof number);
console.log(+'-29') // -29 (typeof number);
```

</p>
</details>

---

###### سوال 5

توابع در جاوا اسکریپت چطوری تعریف میشن؟

<details><summary><b>پاسخ</b></summary>
<p>
توابع در جاوااسکریپت با استفاده از کلمه کلیدی function تعریف می‌شوند. برای فراخوانی یک تابع از نام تابع به همراه پرانتز استفاده می‌شود. مثال:

```javascript
function myFunction() {
	console.log('Hello, World!')
}

myFunction() // فراخوانی تابع
```

</p>
</details>

---

###### سوال 6

تفاوت بین توابع let، var، و const در جاوااسکریپت چیست و چه زمانی از هر یک استفاده می‌کنید؟

<details><summary><b>پاسخ</b></summary>
<p>
توابع let، var، و const به عنوان متغیرها در جاوااسکریپت مورد استفاده قرار می‌گیرند. let و const متغیرهای محلی هستند که در اسکوپ بلوکی (Block Scope) قرار دارند. var در اسکوپ تابعی (Function Scope) قرار دارد. const برای تعریف متغیرهای ثابت استفاده می‌شود. متغیرهای let و var قابلیت تغییر مقدار دارند، اما const ثابت است و مقدارش نمی‌تواند تغییر کند.
</p>
</details>

---

###### سوال 7

توضیحی دقیق در مورد اسکوپ (Scope) در جاوااسکریپت بدهید و تفاوت بین اسکوپ محلی (Local Scope) و اسکوپ سراسری (Global Scope) را توضیح دهید.

<details><summary><b>پاسخ</b></summary>
<p>

اسکوپ در جاوااسکریپت به معنای دامنه دید متغیرها است. اسکوپ محلی (Local Scope) محدود به یک بلوک کد مانند یک تابع یا یک شرطی است. اسکوپ سراسری (Global Scope) در کل کد قرار دارد. متغیرهای تعریف شده در اسکوپ محلی فقط در آن اسکوپ قابل دسترسی هستند. متغیرهای تعریف شده در اسکوپ سراسری به همه بخش‌های کد دسترسی دارند.

</p>
</details>

---

###### سوال 8

توضیح دهید چگونه از Promise و async/await برای مدیریت عملیات ناهمزمان (Asynchronous Operations) در جاوااسکریپت استفاده می‌کنید.

<details><summary><b>پاسخ</b></summary>
<p>

Promise و async/await ابزارهایی برای مدیریت عملیات ناهمزمان در جاوااسکریپت هستند. Promise به شما اجازه می‌دهد عملیات ناهمزمان را مدیریت کرده و پس از انجام آنها وضعیت (resolved یا rejected) را اعلام کنید. async/await از اسکوپیک‌ها برای ساختاردهی کد ناهمزمان استفاده می‌کند و کد را بخواناتر و قابل فهم‌تر می‌کند.

</p>
</details>

---

###### سوال 9

چگونه یک درخواست HTTP (HTTP Request) به یک سرور ارسال می‌کنید و درخواست‌های Ajax را با استفاده از جاوااسکریپت انجام می‌دهید؟

<details><summary><b>پاسخ</b></summary>
<p>

برای ارسال یک درخواست HTTP به سرور در جاوااسکریپت می‌توانید از XMLHttpRequest یا fetch استفاده کنید. XMLHttpRequest ابزار سنتی برای ارسال درخواست‌های HTTP است، در حالی که fetch یک API جدیدتر و بهتر است که Promise محور است.

</p>
</details>

---

###### سوال 10

چرا کد زیر به خطا منجر میشه؟
```javascript
const book = {};

console.log(book.page.number); // TypeError: book.page is undefined
```

<details><summary><b>پاسخ</b></summary>
<p>
چون ما داریم از یک چیز undefined که page.book هست، یک پراپرتی دیگه رو فراخونی می‌کنیم. یعنی مثلا یک چیزی مثل این:

```javascript
<undefined value>.property;

```
مشخصه که یک مقدار undefined نمیتونه شامل یک پراپرتی یا هر چیز دیگه‌ای باشه.


</p>
</details>

---