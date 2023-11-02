<div align="center">
  <img height="300" width="500" src="/js_challenges.jpg">
  <h1> سوالات استخدامی مربوط به جاوا اسکریپت</h1>
</div>

> [!note]
> This repository was created in 2023 and therefore the questions presented here are based on JavaScript syntax and behavior at this time. Since JavaScript is a constantly evolving language, there will be newer language features that will be updated in the future of this repository.

---

<p align="center">⚠️برای ارتباط با تیم js_challenges روی لینک تلگرام بزنید ⚠️</p>

<p align="center">
  <a href="https://t.me/js_challenges">Telegram</a> 
</p>

---

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
const book = {}

console.log(book.page.number) // TypeError: book.page is undefined
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

###### سوال 11

وقتی دو آبجکت مشابه رو با هم مقایسه می‌کنیم خروجی چیه؟

<details><summary><b>پاسخ</b></summary>
<p>
کد زیر رو در نظر بگیرید:

```javascript
let alex = { hairs: true }
let john = { hairs: true }

console.log(alex == john) // false
```

خب اگه کد بالا رو اجرا کنیم خروجی false خواهد بود.

توی مقایسه‌ی دو آبجکت مشابه جواب همیشه false هست.

چرا 🤔 ؟ توی جاوا اسکریپت زمان مقایسه دو آبجکت با هم، رفرنس یا آدرس هر دو آبجکت توی حافظه مقایسه میشه، نه مقدار اونها. برای همین دو آبجکت ممکنه ظاهر یکسانی داشته باشن اما آدرس اونها توی حافظه با هم متفاوت هست.

چکار کنیم هنگام مقایسه دو آبجکت جواب true بگیریم؟ باید هر دو آبجکت به یک آدرس از حافظه اشاره کنن که با کد زیر امکان پذیر هست:

```javascript
let fruit1 = { name: 'potato' }
let fruit2 = fruit1

console.log(fruit2 === fruit1) // true
```

توی کد بالا و خط دوم وقتی که یک آبجکت رو برابر یک آبجکت دیگه قرار دادیم، در واقع آدرس حافظه متغیر fruit1 به متغیر fruit2 داده شد.

</p>
</details>

---

###### سوال 12

عملگر !! چکار می‌کنه؟

<details><summary><b>پاسخ</b></summary>
<p>

عملگر Double NOT یا !! وقتی پشت یک مقداری قرار بگیره، اون رو به بولین تبدیل می‌کنه:

```javascript
console.log(!!null) // false
console.log(!!undefined) // false
console.log(!!'') // false
console.log(!!0) // false
console.log(!!NaN) // false
console.log(!!' ') // true
console.log(!!{}) // true
console.log(!![]) // true
console.log(!!1) // true
```

</p>
</details>

---

###### سوال 13

چه جوری توی یک خط یک عبارت رو محاسبه کنیم؟

<details><summary><b>پاسخ</b></summary>
<p>
چند عمل ضرب و تقسیم و ... رو می‌تونیم با کاما جدا کنیم تا توی یک خط ارزیابی بشن و برای اینکه اون رو به یک متغیر نسبت بدیم همه رو توی یک پرانتز قرار میدیم. مثل چیزی که تو خط آخر نوشتیم:

```javascript
function addFive(num) {
	return num + 5
}

let x = 5

x = (x++, (x = addFive(x)), (x *= 2), (x -= 5), (x += 10))
```

توی خط آخر عبارت‌ها از سمت چپ به راست محاسبه میشن و نهایتا خروجی که عدد ۲۷ هست به متغیر x نسبت داده میشه.

</p>
</details>

---

###### سوال 14

مفهوم Hoisting چیه؟

<details><summary><b>پاسخ</b></summary>
<p>
معنای تحت‌الفظی کلمه Hoisting "بالا بردن" هست. توی جاوااسکریپت قبل از اینکه کدهای ما به شکل واقعی اجرا بشن، همه‌ی توابع و متغیرها به اول حوزه‌ی خودشون جابجا میشن. به همین دلیل هست که کد زیر بدون خطا کار می‌کنه:

```javascript
smile()

function smile() {
	return ':)'
}
```

اول تابع رو صدا زدیم و پایین‌تر خود تابع رو تعریف کردیم.

همونطور که گفتم متغیرها به اول حوزه‌ی خودشون جابجا میشن. یعنی اگه یک متغیر توی حوزه‌ی سراسری تعریف شده باشه، به بالاترین قسمت کد جابجا میشه و اگه یک متغیر توی حوزه‌ی محلی تعریف شده باشه، به اول حوزه‌ی خودش جابجا میشه.

نکته: قبل از اجرای کد و وقتی که Hoisting انجام میشه، متغیرها، بدون مقدار به اول حوزه‌ی خودشون میرن. کد زیر رو درنظر بگیرید:

```javascript
console.log(name)

var name = 'Serena'
```

کد بالا در واقع به شکل زیر در نظر گرفته میشه:

```javascript
var name

console.log(name)

name = 'Serena'
```

خب احتمالا باید بدونیم که خروجی console.log برابر با undefined هست. به این دلیل که متغیر name تعریف شده ولی مقدار دهی نشده.

نکته:‌ مثال بالا برای متغیرهایی بود که با var تعریف شدن. متغیرهایی که با let و const تعریف میشن هم شامل Hoisting میشن. اما عملکرد اونها با var متفاوت هست. وقتی متغیرها با let و const ساخته میشن، قبل از استفاده از اونها باید تعریف شده باشن. در غیر این صورت کد با خطا مواجه میشه:

```javascript
let me = 'know'
console.log(me) // know

console.log(puppy) // ReferenceError: Cannot access 'puppy' before initialization
let puppy = 30
```

</p>
</details>

---

###### سوال 15

مفهوم use strict؟

<details><summary><b>پاسخ</b></summary>
<p>

کلمه strict به معنی سخت‌گیرانه هست. وقتی توی جاوا اسکریپت از این دستور استفاده می‌کنیم برنامه‌ی وارد حالت سخت‌گیرانه میشه. به قول معروف Strict Mode. استفاده از این دستور باعث میشه تا کدهایی امن‌تر و با باگ‌های کمتری بنویسیم. یکی از سخت‌گیری‌هایی که اعمال میشه موقع استفاده از متغیرهایی هست که تعریف نشدن:

```javascript
'use strict'
x = 3.14 // ReferenceError: assignment to undeclared variable x
```

خب کد بالا با استفاده از use strict باعث بروز خطا میشه و میگه به متغیر x داریم مقدار می‌دیم درحالی که تعریف نشده. اما این کد بدون استفاده از use strict بدون مشکل اجرا میشه. خب برای اصلاح این کد باید اون رو به شکل زیر بنویسیم:

```javascript
'use strict'
var x = 3.14
```

عبارت use strict رو همیشه اول اسکریپت یا اول توابع می‌نویسیم:

```javascript
x = 3.14 // No error
myFunction()

function myFunction() {
	'use strict'
	y = 3.14 // ReferenceError: assignment to undeclared variable y
}
```

</p>
</details>

---

###### سوال 16

مقدارهای falsy چی هستن؟

<details><summary><b>پاسخ</b></summary>
<p>
به مقادیری گفته میشه که وقتی اونها رو به Boolean تبدیل می‌کنیم، به false تبدیل میشن. مقادیر زیر falsy هستن:

```javascript
const falsyValues = ['', 0, null, undefined, NaN, false]
```

</p>
</details>

---

###### سوال 16

متد apply چکار می‌کنه؟

<details><summary><b>پاسخ</b></summary>
<p>
با متد apply می‌تونیم یه کاری کنیم که this توی یک تابع به آبجکت دلخواه ما اشاره کنه.

همونطور که می‌دونیم آبجکت‌ها می‌تونن متد داشته باشن. مثل متد name توی آبجکت زیر:

```javascript
const person = {
	firstname: 'John',
	lastname: 'Doe',

	name() {
		console.log(`${this.firstname} ${this.lastname}`)
	},
}

person.name() // John Doe
```

خب در حالت عادی متد name متعلق به آبجکت person هست و this به این آبجکت اشاره می‌کنه. با استفاده از متد apply می‌تونیم یه کاری کنیم که this توی متد name به یک آبجکت دلخواه دیگه اشاره کنه. یعنی متد name رو بتونیم جاهای دیگه استفاده کنیم:

```javascript
const person = {
	firstname: 'John',
	lastname: 'Doe',

	name() {
		console.log(`${this.firstname} ${this.lastname}`)
	},
}

const person1 = {
	firstname: 'Jeff',
	lastname: 'Olson',
}

const person2 = {
	firstname: 'Maria',
	lastname: 'Debug',
}

person.name.apply(person1)
person.name.apply(person2)
```

و حالا بصورت زیر می‌تونیم ازش استفاده کنیم:

```javascript
const person1 = {
	firstname: 'John',
	lastname: 'Doe',
}

person.name.apply(person1, [3, 'Japan'])
```

‌آرگومان دوم متد apply یک آرایه هست. هر کدوم از آیتم‌های این آرایه به عنوان آرگومان‌های متد name در نظر گرفته میشه.

</p>
</details>

---

###### سوال 17

متد call چکار می‌کنه؟

<details><summary><b>پاسخ</b></summary>
<p>
با استفاده از متد call می‌تونیم از یک تابع جوری استفاده کنیم که مقدار this توی اون، به آبجکت دلخواه ما اشاره کنه:

```javascript
function add(first, second, third) {
	this.result = first + second + third
}

const item1 = { result: 0 }
const item2 = { result: 0 }
const item3 = { result: 0 }

add.call(item1, 3, 2, 1)
add.call(item2, 9, 3, 2)
add.call(item3, 6, 1, 3)

console.log(item1.result) // 6
console.log(item2.result) // 14
console.log(item3.result) // 10
```

گه تابع ما نیاز به آرگومان داشته باشه، اون رو بصورت جدا جدا پاس می‌دیم.

همونطور که دیدیم call و apply شبیه به هم هستن. اما یک تفاوت جزئی دارن که توی سوال بعدی با اون آشنا میشیم.

</p>
</details>

---

###### سوال 18

تفاوت call و apply چیه؟

<details><summary><b>پاسخ</b></summary>
<p>
خروجی متدهای call و apply یکی هستن و دقیقاً یک کار رو انجام میدن. تفاوت اونها توی نحوه‌ی استفاده از اونهاست. توی متد apply ما آرگومان‌ها رو با یک آرایه پاس می‌دادیم. اما توی call باید بصورت جدا جدا پاس بدیم. مثال سوال قبل رو در نظر بگیرید:

```javascript
add.call(item1, 3, 2, 1)
add.apply(item1, [3, 2, 1])
```

هر دو عبارت خروجی یکسانی دارن.

</p>
</details>

---

###### سوال 19

متد bind چکار می‌کنه؟

<details><summary><b>پاسخ</b></summary>
<p>
متد bind برای ساختن تابعی استفاده میشه که مقدار this معین و مشخصی داره. همونطور که می‌دونیم در حالت عادی توابع ما تا زمانی که اجرا نشن نمی‌تونیم مقدار this اونها رو تشخیص بدیم. اما شرایطی هست که ما می‌خوایم صراحتاً مشخص کنیم که this چه مقداری داشته باشه. اینجا چنین متدی به کار ما میاد.

متد bind به ما یک تابع رو برمی‌گردونه که وقتی اون رو صدا می‌زنیم، مقدار this توی اون تابع به آبجکت دلخواه ما اشاره می‌کنه. پس به این بستگی نداره که این تابع چطوری و کجا داره صدا زده میشه.

مثال زیر رو درنظر بگیرید:

```javascript
function hit() {
	this.count++
}
```

ینجا تا زمانی که تابع hit اجرا نشه، مقدار this توی خط ۲ رو نمی‌تونیم تشخیص بدیم. اما از متد bind به شکل زیر استفاده می‌کنیم تا this دلخواه خودمون رو مشخص کنیم:

```javascript
const jumps = { count: 0 }

const hitJumps = hit.bind(jumps)
```

ما اینجا گفتیم که آبجکت jumps رو در نظر بگیر برای this که توی hit داره استفاده میشه. خروجی bind که الان یک تابع هست، ریخته میشه توی متغیر hitJumps و با هر بار فراخونی اون، متد hit یک واحد به count توی آبجکت jumps اضافه می‌کنه:

```javascript
function hit() {
	this.count++
}

const jumps = { count: 0 }
const hitJumps = hit.bind(jumps)

hitJumps()
hitJumps()
hitJumps()

console.log(jumps.count) // 3
```

</p>
</details>

---

###### سوال 20

چه چیزایی به جاوا اسکریپت توسط ES6 اضافه شده؟

<details><summary><b>پاسخ</b></summary>
<p>
۱۴ مورد زیر توسط ES6 به جاوا اسکریپت اضافه شده

***
1 - Arrow Functions
2 - Classes
3 - Template Strings یا Template Literals
4 - Enhanced Object literals
5 - Object Destructuring
6 - Promises
7 - Generators
8 - Modules
9 - Symbol
10 - Proxies
11 - Sets
12 - پارامترهای پیشفرض توابع
13 - عملگرهای Rest and Spread
14 - Let و Const
 ***
 </p>
</details>

---