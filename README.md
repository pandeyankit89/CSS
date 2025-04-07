### ▪️ What is CSS ?
- CSS stands for: **Cascading Style Sheets**. CSS is the language used to style and design web pages.
---
### ▪️ Inline vs Internal vs External CSS :
| Type of CSS | Where it's written | Syntax / Example | When to use it | Pros ✅  | Cons ❌|
|-------------|-------------------|-------------------|----------------|-----------|--------|
| **Inline CSS**  | Inside the HTML tag itself                | `<h1 style="color:red;">Hello</h1>`                                 |🔸For quick testing or 1-2 style overrides| • Very specific<br>• No separate file needed    |• Hard to maintain<br> Clutters HTML<br>• Not reusable|
| **Internal CSS**| In `<style>` tag in the `<head>` section | `<style> h1 { color: red; } </style>`|🔸For small projects or single HTML pages|• Easy to manage in one place<br>• Better than inline|• Still mixes content & design<br>• Not reusable across pages|
| **External CSS**| In a separate `.css` file linked via `<link>`| `<link rel="stylesheet" href="style.css">`<br>`/* style.css */ h1 { color: red; }`|🔸Best for large/multi-page sites | • Clean separation<br>• Reusable across pages<br>• Caching friendly |• Extra HTTP request (but cached)<br>• File must load successfully |
---
### ▪️ Specificity Score Table :

| Selector Type                     | Specificity Value | Example             |
|----------------------------------|-------------------|---------------------|
| Inline style                     | 1000              | `<h1 style="...">`  |
| ID selector                      | 100               | `#header`           |
| Class / Attribute / Pseudo-class| 10                | `.main`, `[type="text"]`, `:hover` |
| Element selector / Pseudo-element| 1                | `div`, `h1`, `::after` |
| Universal selector               | 0                 | `*`                 |

- If two rules apply, the one with higher specificity wins.
- If specificity is equal, the one defined later wins (bottom rule overrides top).
- You can use ```!important``` to force apply a style (not recommended unless necessary).
---
### ▪️ Best Practice:
- HTML → Structure
- CSS → Style
- JavaScript → Behavior
It is recommended to define styles in CSS rather than changing them via JavaScript. Instead of modifying styles directly, add predefined CSS classes dynamically.
---
