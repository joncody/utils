# `utils.js` – Universal JavaScript Utility Library

A lightweight, utility library offering common type checks, deep copying, data conversion, DOM utilities, easing functions, and polyfills — all in one powerful module.

---

## ✅ Features

- 🔍 Type utilities: `isArray`, `isTypedArray`, `isBuffer`, etc.
- 🔄 Data conversion: `toArray`, `toUint8`, `toBuffer`, etc.
- 🧠 Object manipulation: `copy`, `extend`, `each`, `inherits`
- 📈 Animation: Built-in Easing functions for smooth animations
- 🧾 String utilities: `supplant`, `uuid`, casing functions
- 🌐 DOM support: `getStyle`, `getPosition`, `select`, `scrollIntoView`
- ⚙️ Polyfills: `ArrayBuffer.slice`, `Number.isNaN`
- 📦 **Zero dependencies**, fully tree-shakable, modern ES module

---

## 📦 Installation

Copy `utils.js` into your project.

Import as a module:

```js
import utils from './utils.js';
```

---

## 🧠 Quick Examples

```js
utils.isArray([1, 2, 3]); // true
utils.toUint8("ABC");     // Uint8Array([65, 66, 67])
utils.copy({ a: { b: 1 } }); // Deep clone
utils.supplant("Hi {name}", { name: "Alice" }); // "Hi Alice"
utils.uuid();              // "xxxxxxxx-xxxx-4xxx-yxxx-xxxxxxxxxxxx"

// Use built-in easing
utils.scrollToTop(document.body, utils.ease.easeOutExpo);
```

---

## 📚 API Reference

### 🔍 Type Checks

| Function | Description |
|---------|-------------|
| `typeOf(value)` | Returns the type as a string (`"array"`, `"null"`, `"object"`, etc.) |
| `isArray(value)` | Checks if value is an array |
| `isBoolean(value)` | Checks for boolean |
| `isFunction(value)` | Checks for function |
| `isNull(value)` | Checks for null |
| `isNumber(value)` | Checks for number (excludes `NaN`) |
| `isObject(value)` | Checks for plain object |
| `isString(value)` | Checks for string |
| `isUndefined(value)` | Checks for `undefined` |
| `isArrayLike(value)` | Checks if object has numeric keys and a `length` property |
| `isBuffer(value)` | Checks if value is an `ArrayBuffer` |
| `isEmpty(value)` | Checks if object has no own properties |
| `isGG(value)` | Checks for a custom `gg === true` flag |
| `isNan(value, [noparse], [base])` | Checks if value is NaN, optionally parsed |
| `isNode(value)` | Checks if DOM node |
| `isTypedArray(value)` | Checks for typed arrays (`Uint8Array`, etc.) |

---

### 🔄 Conversion

| Function | Description |
|----------|-------------|
| `toArray(value)` | Converts various types into a flat array |
| `toCamelCase(string)` | Converts kebab-case to camelCase |
| `toHyphenated(string)` | Converts camelCase to kebab-case |
| `toCodesFromString(string)` | Converts a string into an array of char codes |
| `toFloat(value, [decimals])` | Converts to float, with optional fixed precision |
| `toInt(value, [radix])` | Converts to integer with optional radix |
| `toUint8(value)` | Converts strings, arrays, or buffers to `Uint8Array` |
| `toBuffer(value)` | Converts to `ArrayBuffer` |
| `toStringFromCodes(array)` | Converts char code array to string |

---

### 🧠 Object Utilities

| Function | Description |
|----------|-------------|
| `copy(value)` | Performs **deep clone** of arrays/objects |
| `extend(target, source, [overwrite=true])` | **Deep merges** `source` into `target` |
| `inherits(ctor, superCtor)` | Classical inheritance via prototype chain |
| `inArray(array, value)` | Returns `true` if value exists in array |
| `noop()` | A no-op function |
| `each(items, fn, [thisArg])` | Iterates over arrays, objects, or DOM nodes |

---

### 📈 Easing Functions

Access via `utils.ease`.
Usage: `utils.ease.easeInQuad(t, b, c, d)`

**Available functions:**
`linearTween`, `easeInQuad`, `easeOutQuad`, `easeInOutQuad`, `easeInCubic`, `easeOutCubic`, `easeInOutCubic`, `easeInQuart`, `easeOutQuart`, `easeInOutQuart`, `easeInQuint`, `easeOutQuint`, `easeInOutQuint`, `easeInSine`, `easeOutSine`, `easeInOutSine`, `easeInExpo`, `easeOutExpo`, `easeInOutExpo`, `easeInCirc`, `easeOutCirc`, `easeInOutCirc`.

---

### 🧾 String Utilities

| Function | Description |
|----------|-------------|
| `supplant(template, values)` | Replaces `{key}` in template with values from object |
| `uuid()` | Generates RFC4122-like UUID string |

---

### 🌐 DOM Utilities

| Function | Description |
|----------|-------------|
| `getStyle(node, [pseudo])` | Gets computed styles for a DOM element |
| `getPosition(node)` | Calculates element’s absolute position |
| `getById(id, [values])` | Gets element by ID with optional template |
| `select(selector, [values], [node])` | `querySelector` with optional templating |
| `selectAll(selector, [values], [node])` | `querySelectorAll` with optional templating |

---

### 🧭 Scroll Utilities

| Function | Description |
|----------|-------------|
| `scrollIntoView(node, [easingFn])` | Smoothly scrolls to a node |
| `scrollToTop(node, [easingFn])` | Smooth scrolls to top of scrollable container |

*Note: If `easingFn` is omitted, `easeInOutSine` is used.*

---

### ⏱ Misc Utilities

| Function | Description |
|----------|-------------|
| `setImmediate(fn, ...args)` | Executes function after current event loop, using `setTimeout(..., 0)` internally |

---

## 🧪 Polyfills

Included for broader compatibility:

- `ArrayBuffer.prototype.slice` – manually implemented
- `Number.isNaN()` – fallback added

---

## 📄 License

See the [LICENSE](./LICENSE) file for details.
