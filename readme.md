### 1. **Debounce Function**
Limits the number of times a function is called over time (e.g., for window resize or scroll events).

```javascript
function debounce(fn, delay) {
  let timeout;
  return function (...args) {
    clearTimeout(timeout);
    timeout = setTimeout(() => fn.apply(this, args), delay);
  };
}
```
### 2. Deep Clone an Object
Creates a deep copy of an object or array.

```javascript
function deepClone(obj) {
  return JSON.parse(JSON.stringify(obj));
}
```

### 3. Format Date
Formats a given date to a more readable string format.

```javascript
function formatDate(date) {
  const options = { year: 'numeric', month: 'long', day: 'numeric' };
  return new Date(date).toLocaleDateString('en-US', options);
}
```

### 4. Generate a Random Integer Between Two Values

```javascript
function getRandomInt(min, max) {
  return Math.floor(Math.random() * (max - min + 1)) + min;
}
```

### 5. Check If an Array is Empty

```javascript
function isArrayEmpty(arr) {
  return Array.isArray(arr) && arr.length === 0;
}
```

### 6. Throttle Function
Limits the number of times a function is called in a given time period (e.g., for mouse or scroll events).

```javascript
function throttle(fn, limit) {
  let lastFunc;
  let lastRan;
  return function () {
    const context = this;
    const args = arguments;
    if (!lastRan) {
      fn.apply(context, args);
      lastRan = Date.now();
    } else {
      clearTimeout(lastFunc);
      lastFunc = setTimeout(function () {
        if (Date.now() - lastRan >= limit) {
          fn.apply(context, args);
          lastRan = Date.now();
        }
      }, limit - (Date.now() - lastRan));
    }
  };
}
```

### 7. Convert Seconds to HH:MM:SS Format

```javascript
function secondsToHms(seconds) {
  const h = Math.floor(seconds / 3600);
  const m = Math.floor((seconds % 3600) / 60);
  const s = seconds % 60;
  return `${h}:${m < 10 ? '0' + m : m}:${s < 10 ? '0' + s : s}`;
}
```

### 8. Check if a String is a Valid Email

```javascript
function isValidEmail(email) {
  const re = /^[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}$/;
  return re.test(email);
}
```

### 9. Get URL Parameters

```javascript
function getUrlParam(name) {
  const url = new URL(window.location.href);
  return url.searchParams.get(name);
}
```

### 10. Detect Browser Type

```javascript
function getBrowser() {
  const userAgent = navigator.userAgent;
  if (userAgent.includes("Chrome")) return "Chrome";
  if (userAgent.includes("Firefox")) return "Firefox";
  if (userAgent.includes("Safari")) return "Safari";
  if (userAgent.includes("Edge")) return "Edge";
  return "Unknown";
}
```

### 11. Check if a String is a Palindrome

```javascript
function isPalindrome(str) {
  const cleanedStr = str.replace(/[^A-Za-z0-9]/g, '').toLowerCase();
  const reversedStr = cleanedStr.split('').reverse().join('');
  return cleanedStr === reversedStr;
}
```

### 12. Convert an Object to URL Parameters

```javascript
function objectToUrlParams(obj) {
  return Object.keys(obj)
    .map(key => `${encodeURIComponent(key)}=${encodeURIComponent(obj[key])}`)
    .join('&');
}
```

### 13. Generate a UUID (Universally Unique Identifier)

```javascript
function generateUUID() {
  return 'xxxxxxxx-xxxx-4xxx-yxxx-xxxxxxxxxxxx'.replace(/[xy]/g, function(c) {
    const r = Math.random() * 16 | 0;
    const v = c === 'x' ? r : (r & 0x3 | 0x8);
    return v.toString(16);
  });
}
```

### 14. Format Currency

```javascript
function formatCurrency(amount, currency = 'USD') {
  return new Intl.NumberFormat('en-US', {
    style: 'currency',
    currency: currency,
  }).format(amount);
}
```
