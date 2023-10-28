# 10 سوال متداول در مورد جاوااسکریپت

### سوال 1

تفاوت بین undefined و null چیه؟

<details><summary><b>پاسخ</b></summary>
<p>

**پاسخ:**

قبل از اینکه درباره تفاوت‌های این دو صحبت کنیم، بهتره که بدونیم این دو جزو ۸ نوع داده‌ای هستن که توی جاوا اسکریپت وجود دارن:
```javascript
['null','undefined', 'string', 'number', 'boolean', 'object', 'symbol', 'bigint'];
```
همچنین این دو به اصطلاح falsy value هستن. یعنی مقدارهایی که وقتی اونها رو به Boolean تبدیل می‌کنیم، خروجی false هست:
```javascript
console.log(!!null); // false
console.log(!!undefined); // false

console.log(Boolean(null)); // false
console.log(Boolean(undefined)); // false
```
و اما تفاوت‌ها. از undefined شروع کنیم:

ویژگی‌های منحصر به فرد undefined:

undefined یک مقدار پیشفرض برای متغیرهایی هست که مقدار ندارن. یعنی موقع ساختن این متغیر بهش مقدار داده نشده
undefined یک خروجی پیشفرض هست برای تابعی که return نداره
وقتی یک پراپرتی (یا key) از یک آبجکت رو صدا بزنیم که وجود نداره، خروجی undefined هست
```javascript
let undefinedVar;
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

console.log(typeof undefinedVar); // undefined
```
ویژگی‌های منحصر به فرد null:
در واقع null خودش یک مقدار هست. یک مقدار "پوچ" یا ‌‌"خالی" که می‌تونیم اون رو به متغیرها نسبت بدیم:
```javascript
let x = null;

console.log(x); // null
console.log(typeof x); // object!
```
به این مقایسه‌ها دقت کنین:
```javascript
null == undefined; // true
null === undefined // false
```
مقایسه اول true شد چون مقایسه این دو با == همیشه true هست. مقایسه دوم برای این false شد که توی سه مساوی (===) تبدیل نوع انجام نمی‌گیره. نوع یک ‌null برابر با آبجکت و نوع یک undefined همون undefined هست.


