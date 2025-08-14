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
