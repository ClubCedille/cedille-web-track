# 2. Core Building Block: Markdown (No HTML/CSS)

Before diving into Hugo, it’s essential to understand **Markdown** — the simple, lightweight syntax used to write content for static sites. Markdown is easy to learn and helps you focus on **writing**, not formatting.

---

## 2.1 Origin of Markdown and Its Usefulness

**Markdown** was created by John Gruber in 2004 with the goal of making writing for the web easy to read and easy to write.

Why Markdown?

- **Human-readable** syntax
- Converts easily to HTML
- Widely supported (GitHub, forums, blogs, CMS tools)
- Works seamlessly with Hugo

When you write content in Hugo, you’ll mostly write in Markdown — so it’s your first essential skill.

---

## 2.2 Basic Markdown Syntax

Here’s a quick reference of the most commonly used Markdown elements:

### Headings

``` markdown
# H1
## H2
### H3
```

### Emphasis

---

``` markdown
*italic* or _italic_
**bold** or __bold__
```

### Inline Code

---

You can use the ` character to insert line of code within a line of text.

Ex:

``` markdown
This is normal C arithmetic `c+=1;`.
```
Would be displayed like this:
This is normal C arithmetic `c+=1;`.

### Code block

---

You have to use ` ``` ` for opening and closing a code block. You can also specifiy which language it contains after the ` ``` `.

Example:

``` markdown
    ``` go
        package main

        import "ftm"

        func greet(){
            ftm.Println("Hello World")
        }
    ```
```
Would be displayed like this:

``` go
        package main

        import "ftm"

        func greet(){
            tm.Println("Hello World")
        }
```
### Lists

---

You can use `*` or `-` with a space afterwards to insert a list item.

Ex:

``` markdown
    * Item 1
    * Item 2
    * Item 3
```

Would be displayed like this:

* Item 1
* Item 2
* Item 3

You can also create nested list by entering a tab to go a level deeper.

Ex:

``` markdown
* Item 1
    * Item 1.1
        * Item 1.1.1
    * Item 1.2
* Item 2
```
Would be displayed like this:

* Item 1
    * Item 1.1
        * Item 1.1.1
    * Item 1.2
* Item 2

### Links

You redirect the user to a certain website