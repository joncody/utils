# `utils.js` – Universal JavaScript Utility Library

A lightweight, dependency-free utility library offering common type checks, deep copying, data conversion, DOM utilities, polyfills, and more — all in one powerful module.

---

## ✅ Features

- 🔍 Type utilities: `isArray`, `isTypedArray`, `isBuffer`, etc.
- 🔄 Data conversion: `toArray`, `toUint8`, `toBuffer`, etc.
- 🧠 Object manipulation: `copy`, `extend`, `each`, `inherits`
- 🧾 String utilities: `supplant`, `uuid`, casing functions
- 🌐 DOM support: `getStyle`, `getPosition`, `select`, `scrollIntoView`
- ⚙️ Polyfills: `ArrayBuffer.slice`, `Number.isNaN`
- 📦 No dependencies, fully tree-shakable, modern ES module

---

## 📦 Installation

Include it in your project:

```bash
# Directly download or clone
git clone https://github.com/your-username/your-repo.git
```

Or import as a module:

```js
import utils from './utils.js';
```

---

## 🧠 Quick Examples

```js
utils.isArray([1, 2, 3]); // true
utils.toUint8("ABC");     // Uint8Array([65, 66, 67])
utils.copy({ a: 1 });      // deep clone
utils.supplant("Hi {name}", { name: "Alice" }); // "Hi Alice"
utils.uuid();              // "xxxxxxxx-xxxx-4xxx-yxxx-xxxxxxxxxxxx"
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
| `copy(value)` | Performs deep clone of arrays/objects |
| `extend(target, source, [overwrite=true])` | Shallow merges `source` into `target` |
| `inherits(ctor, superCtor)` | Classical inheritance via prototype chain |
| `inArray(array, value)` | Returns `true` if value exists in array |
| `noop()` | A no-op function |
| `each(items, fn, [thisArg])` | Iterates over arrays, objects, or DOM nodes |

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
