# سطح مقدماتی

## unit 2

##### Spread syntax (...):

در React، **Spread Syntax (`...`)** برای پاس دادن چندین prop به یک کامپوننت به‌صورت همزمان استفاده می‌شود و باعث **کاهش تکرار** و **خوانایی بیشتر کد** می‌شود.

##### مثال ساده

```jsx
const userProps = {
  name: "Amirhossein",
  age: 22,
  role: "Frontend Developer",
};

<UserCard {...userProps} />;
```

#### رندر شرطی

در ریکت می‌توان بر اساس یک شرط، مقدار، استایل یا کامپوننت متفاوتی رندر کرد

##### مثال ساده

```jsx
const isLogin = true;

<div className={isLogin ? "bg-red" : "bg-green"}>Welcome</div>;
```
