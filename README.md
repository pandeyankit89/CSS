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
### ▪️ CSS Selectors :

| Selector Type        | Syntax              | Description                                              | Example                        |
|----------------------|---------------------|----------------------------------------------------------|--------------------------------|
| Universal Selector   | `*`                 | Selects all elements                                     | `* { margin: 0; }`             |
| Element Selector     | `tagname`           | Selects all elements of a given type                     | `p { color: red; }`            |
| Class Selector       | `.classname`        | Selects all elements with a specific class               | `.box { border: 1px solid; }` |
| ID Selector          | `#idname`           | Selects one element with a specific ID                   | `#header { background: gray; }`|
| Grouping Selector    | `A, B`              | Applies same styles to multiple selectors                | `h1, h2 { font-size: 20px; }` |
| Descendant Selector  | `A B`               | Selects elements `B` inside `A`                          | `div p { color: blue; }`      |
| Child Selector       | `A > B`             | Selects <ins>direct child</ins> `B` of `A`               | `ul > li { list-style: none; }`|
| Adjacent Sibling     | `A + B`             | Selects `B` immediately after `A`                        | `h1 + p { margin-top: 0; }`   |
| General Sibling      | `A ~ B`             | Selects all `B` siblings after `A`                       | `h1 ~ p { color: green; }`    |
| Attribute Selector   | `[attr=value]`      | Selects elements with a specific attribute value         | `input[type="text"]`          |
| Pseudo-class         | `:pseudo-class`     | Selects elements in a specific state                    | `a:hover`, `li:first-child`   |
| Pseudo-element       | `::pseudo-element`  | Styles parts of elements                                | `p::first-line`, `div::after` |

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
### ▪️ CSS Cascading :
  | Rule                     | Description                                                | Example / Notes                                                |
|--------------------------|------------------------------------------------------------|----------------------------------------------------------------|
| 1. Importance            | `!important` overrides all other rules                     | `color: red !important;` wins over everything else             |
| 2. Specificity           | More specific selectors win over general ones              | `#id` > `.class` > `element`                                   |
| 3. Source Order          | If specificity is equal, the later rule in CSS wins        | Last defined style is applied                                  |
| 4. Inline Styles         | Inline styles beat internal/external (unless `!important`) | `<p style="color: green;">` has high priority                  |
| 5. Style Origin          | User styles > Author styles > Browser default              | Inline > Internal > External > User Agent                      |

---
### ▪️ Best Practice:
- HTML → Structure
- CSS → Style
- JavaScript → Behavior
It is recommended to define styles in CSS rather than changing them via JavaScript. Instead of modifying styles directly, add predefined CSS classes dynamically.
---
### ▪️ CSS `display` Property Values :

| `<display>` Value | Description                                                                 | Example Usage                                                               |
|-----------------|-----------------------------------------------------------------------------|-------------------------------------------------------------------------------|
| `display: block;`         | Element starts on a new line and stretches to the full width of its container. | `<div>`, `<p>`, `<section>`                                      |
| `display: inline;`        | Element does not start on a new line and only takes up as much width as necessary. | `<span>`, `<a>`, `<strong>`                                  |
| `display: inline-block;`  | Similar to `inline`, but allows setting width and height.                   | `<button>`, `<input>`                                               |
| `display: none;`          | Hides the element; it will not be displayed on the page and <ins>does not take up space</ins>. | Used to hide elements dynamically with CSS or JavaScript. |
| `display: flex;`          | Enables flexbox layout, allowing responsive arrangement of child elements.  | Creating navigation bars, aligning items horizontally or vertically.|
| `display: grid;`          | Enables grid layout, allowing arrangement of child elements in rows and columns. | Designing complex web layouts with rows and columns.           |
| `display: inline-flex;`   | Similar to `flex`, but the container behaves like an inline element.        | Inline navigation menus.                                            |
| `display: inline-grid;`   | Similar to `grid`, but the container behaves like an inline element.        | Inline grid layouts within text.                                    |
---
### ▪️ CSS `position` Property:

The `position` property in CSS specifies how an element is positioned in a document. It can take the following values:

| Position Value | Description                                                                                      | Example                                                                        |
|----------------|--------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------|
| `static`       | Default positioning method. Elements are positioned <ins>according to the normal flow</ins> of the document. | ```position: static;```                                            |
| `relative`     | The element is positioned <ins>relative to its normal position</ins>.                                        | ```position: relative;```<br>```top: 10px;```<br>```left: 10px;``` |
| `absolute`     | The element is positioned <ins>relative to its nearest positioned ancestor</ins> (not static).               | ```position: absolute;```<br>```top: 10px;```<br>```left: 10px;```  |
| `fixed`        | The element is positioned <ins>relative to the browser window, and does not move when the page is scrolled.</ins> | ```position: fixed;```<br>```top: 10px;```<br>```right: 10px;``` |
| `sticky`       | The element is positioned <ins>based on the user's scroll position</ins>. It toggles between relative and fixed. | ```position: sticky;```<br>```top: 0;```                       |

---
### ▪️ How to make your webpage mobile or tablet friendly ?
- by setting the "viewport"rule inside `<head>`
```javascript
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
```

- `<meta>`: A tag that gives extra information about the web page (called metadata). It's not shown on the page itself.
- `name="viewport"`: You're <b>setting rules for the visible area</b> of a webpage on a device.
- `content="width=device-width"`: Make the <b>width of the page equal to the width of the user's device</b> (like phone, tablet, laptop).
- `initial-scale=1.0"`: Set the <b>initial zoom level to 100% (no zoom)</b>.
---
### ▪️ How to set Different styles based on some condition ?
- By using `@media` rule in CSS. It **applies different styles depending on the device's screen size or type**.
- It is part of **Responsive Design** 
```css
 /* If screen is 600px or less, apply this style */
    @media (max-width: 600px) {
      body {
        background-color: lightgreen;
      }
    }
```
- Common Conditions Used in `@media` :
  
| Condition				        | What it means                                                         |   
|-------------------------|-----------------------------------------------------------------------|
|`max-width`			        |Apply styles if the screen is less than or equal to a certain width    |
|`min-width`			        |Apply styles if the screen is greater than or equal to a certain width |
|`orientation: portrait`  |Apply styles if the device is vertical                                 |
|`orientation: landscape` |Apply styles if the device is horizontal                               |

---
