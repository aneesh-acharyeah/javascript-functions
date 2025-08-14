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
