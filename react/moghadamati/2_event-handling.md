### Event Handling

در React، **Event Handling** یعنی مدیریت رویدادهایی که توسط کاربر اتفاق می‌افتن؛  
مثل کلیک کردن روی دکمه، تایپ داخل input، ارسال فرم و…

#### تفاوت Event Handling در React با JavaScript معمولی

| JavaScript خام            | React                     |
| ------------------------- | ------------------------- |
| `onclick="handleClick()"` | `onClick={handleClick}`   |
| رشته (string)             | تابع (function reference) |
| DOM مستقیم                | کامپوننت‌محور             |

در React:

- اسم eventها **camelCase** هستن
- به‌جای string، **تابع** پاس می‌دیم

#### مثال ساده از Event Handling

```jsx
function handleClick() {
  console.log("Button clicked!");
}

<button onClick={handleClick}>کلیک کن</button>;
```

نکته مهم:  
اینجا **تابع رو صدا نمی‌زنیم**، فقط reference اون رو می‌دیم.  
 اشتباه:

```jsx
<button onClick={handleClick()}>
```

#### استفاده از Event Handling در کد نمونه‌ی پروژه

توی کدی که دادی، این دکمه رو داریم:

```jsx
<button className="btn primary-btn">خواندن مقالات</button>
```

حالا فرض کنیم می‌خوایم وقتی کاربر روش کلیک کرد، یه پیام تو کنسول چاپ بشه یا بعداً هدایتش کنیم.

##### قدم اول: تعریف تابع handler

```jsx
function handleReadArticles() {
  console.log("کاربر روی خواندن مقالات کلیک کرد");
}
```

#### قدم دوم: اتصال event به دکمه

```jsx
<button className="btn primary-btn" onClick={handleReadArticles}>
  خواندن مقالات
</button>
```

#### Event Handling با Arrow Function

گاهی لازم داریم پارامتر هم ارسال کنیم:

```jsx
<button onClick={() => handleReadArticles("articles")}>خواندن مقالات</button>
```

```jsx
function handleReadArticles(section) {
  console.log(`navigate to ${section}`);
}
```

این روش زمانی استفاده می‌شه که:

- نیاز به ارسال آرگومان داریم
- یا چند دستور داخل event داریم

#### مثال کاربردی‌تر (وابسته به state)

در کد تو متغیر زیر وجود داره:

```jsx
let hasPlan = false;
```

می‌تونیم از event handling برای تغییر رفتار بر اساس این مقدار استفاده کنیم:

```jsx
function handleSubscribeClick() {
  if (!hasPlan) {
    console.log("کاربر باید اشتراک تهیه کند");
  }
}
```

```jsx
{
  !hasPlan && (
    <button className="btn secondary-btn" onClick={handleSubscribeClick}>
      تهیه اشتراک
    </button>
  );
}
```

---
