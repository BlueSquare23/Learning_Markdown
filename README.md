<!-- Basic Markdown Notes -->

<a name="top"></a>

This is a simple Markdown cheatsheet.

<!-- Headings -->

# Heading 1
## Heading 2
### Heading 3
#### Heading 4
##### Heading 5
###### Heading 6

<!-- Spacing -->

## Spacing

Instead of \<p\> tags, Markdown uses empty lines between sentances to denote
new paragraphs.

For example, this is a new paragraph!

Otherwise
newlines,       spaces,
and
	tabs
		are
     			ignored.

<!-- Italics -->

*Word* in italics

Another _word_ in italics

<!-- Strong -->

**This text** is strong

__This text__ is also strong

<!-- Strikethrough -->

~~This text~~ is striken through

<!-- Horizontal Rule -->

---

___

<!-- Escaped Characters -->

\_\_init\_\_.py

\*\*NOT STRONG TEXT\*\*

<!-- Block Quote -->

> This is a quote!

<!-- Links -->

[Example Link](http://example.com/)

[Example Link](http://example.com/ "Hover Text")

<!-- Unordered Lists -->

* Item 1
* Item 2
* Item 3
    * Nested Item 1
    * Nested Item 2

<!-- Ordered Lists -->

1. Item 1
1. Item 2
1. Item 3
    1. Nested Item 1
    1. Nested Item 2

<!-- Inline Codeblock -->

`<p>Preformatted Text</p>`

<!-- Multi-line Codeblock -->

```
This is a 
	multi-line 
		block of 
			preformatted text
```

<!-- Images -->

![Random Dog](https://random.dog/12297f35-1812-4a63-9e17-64dd05c7a759.jpg){class="img-fluid"}

<!-- Github Specific Markdown Tricks -->

<!-- Syntax Highlighted Multi-line Codeblocks -->

```python3
def fib(n):
    a, b = 0, 1
    while a < n:
        print(a, end=' ')
        a, b = b, a+b
    print()
fib(1000)
```

<!-- Task Lists -->

* [x] Task 1
* [x] Task 2 
* [ ] Task 3 

<button id="myBtn"><a href="#top" style="color: white">/\\ Top /\\</a></button>
