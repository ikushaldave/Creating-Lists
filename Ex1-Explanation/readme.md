## BLOCK-readText

### Creating Lists

List are the fundamental part of HTML. They are useful for displaying things like todo list, navigational menu items, list of ingredients and instructions fo recipes etc. Lists are the way that makes a short piece of information easy to understand.

When it comes to specify a list of information on a website, HTML offeres three different way: unordered, ordered, and description lists.

#### Unordered List

An unordered list is a list in which the order of items doesn't matter. To introuduce such list in HTML `<ul>` tag is used and the item inside the list is represented usning `<li>` tag.

```html
<ul>
  <li>Milk</li>
  <li>Bread</li>
  <li>Tea</li>
  <li>Fruits</li>
</ul>
```

Both `<ul>` and `<li>` are the block-level elements. By default there exists a vertical margin and left padding on `<ul>` element and all the list item(`<li>`) precede with a bullet point(or solid dot). The bullet point is known as list style which can be modified using `list-style-type` property in CSS.

#### Ordered Lists

The ordered list in an HTML document is represented by `<ol>` tag, which works similar to an unordered lists. The list item in ordered list also marked up by `<li>`. The main difference is that in an ordered list the order of list item matters.

The sequence of the items in which it will represented is really important. Therefore, instead of bullet points the marker of each item will be a number in an ordered list.

```html
<ol>
  <li>Milk</li>
  <li>Bread</li>
  <li>Tea</li>
  <li>Fruits</li>
</ol>
```

By default an ordered list will begin from `1`. However you can set a custom begining point or reversed the order of the item, using `start` and `reversed` attribute.

**Start Attribute**

The `start` attribute on `<ol>` element will decide from which the ordered list should start. For example:

```html
<ol start="20">
  <li>Milk</li>
  <li>Bread</li>
  <li>Tea</li>
  <li>Fruits</li>
</ol>
```

The above list contains a `start` attribute of a value `20`, so the list will begin from `20` and susequently the next item marker will `21` and so on.

**Reversed Attribute**

The `reversed` is a boolean attribute, that reverse the order of items inside ordered lists. By default the value for `reversed` attribute is `false`, just adding `reversed` without any value it becomes true.

```html
<ol reversed>
  <li>Milk</li>
  <li>Bread</li>
  <li>Tea</li>
  <li>Fruits</li>
</ol>
```

In the above example, there are four items, and the `<ol>` element contains reverse attribute. Therefore the order of item will begin from `4` and end at `1`.

**Value Attribute**

The `value` attribute is applied on individual items, `<li>`. The value of `value` attribute will decide the order number of the item. For example:

```html
<ol>
  <li>Milk</li>
  <li value="10">Bread</li>
  <li>Tea</li>
  <li>Fruits</li>
</ol>
```

In the above ordered list the second item has value of 10 within the value attribute. The list will begin at `1` and the second list item marker will be `10`. Afterwards each item will be having marker upwards from `10`.

#### Nesting Lists

In HTML a list can nest another list inside it. That means you can have several sublist inside a list.

```html
<ol>
  <li>Milk</li>
  <li value="10">Bread</li>
  <li>
    Fruits
    <ul>
      <li>Apple</li>
      <li>Banana</li>
      <li>Mango</li>
    </ul>
  </li>
  <li>Tea</li>
</ol>
```

Nesting lists can be sometimes tricky, so you need to be careful while doing so. Keep in mind both the `<ol>` or `<ul>` element can only have `<li>` element as a direct child. However, a li element can several other elements inside it as desired.

#### List Item Styling

CSS offers handful of styling properties, that allow us to modify the default list style marker in a list.

**List Style Type Property**

The `list-style-type` property is used to set the content of a list item marker. The acceptable values for `list-style-type` are:

| List Style Type Value     | Content                                 |
| ------------------------- | --------------------------------------- |
| disc                      | A filled circle                         |
| circle                    | A hollow circle                         |
| square                    | A filled square                         |
| decimal                   | Decimal numbers                         |
| decimal-leading-zero      | Decimal numbers padded by initial zeros |
| lower-roman               | Lowercase roman numerals                |
| upper-roman               | Uppercase roman numerals                |
| lower-greek               | Lowercase classical Greek               |
| lower-alpha / lower-latin | Lowercase ASCII letters                 |
| upper-alpha / upper-latin | Uppercase ASCII letters                 |
| armenian                  | Traditional Armenian numbering          |
| georgian                  | Traditional Georgian numbering          |
| none                      | No list item                            |

A `list-style-property` can added on any `ordered` list or `unordered` list. Even on a list item also the `list-style-property` can be added.

```html
<ul>
  <li>Milk</li>
  <li>Bread</li>
  <li>Tea</li>
  <li>Fruits</li>
</ul>
```

```css
ul {
  list-style-type: square;
}
```

**List Style Image Property**

The `list-style-image` prperty is used to set an image as as an list item marker. Value of the `list-style-image` property is set using `url()` function that accepts the path of the image.

```css
ul {
  list-style-image: url(images/bullet.png);
}
```

**List Style Position Property**

The `list-style-postion` property will set the postion of the list item marker. The `outside` is default value which can be overwritten with `inside` or `inherit`.

```css
ul {
  list-style-postion: inside;
}
```

The `outside` value keeps the marker on the left side and outside the content, that does not allow content to wrap below the marker. The inside value will keep the marker wihin the content on the left side, where the content can wrap below the marker.

**Shorthand List Style Property**

The `list-style` is the shorthand property for `list-style-type`, `list-style-position` and `listi-style-image`.

Here is an example:

```css
ul {
  list-style: square outside none;
}
```

Which is same as the following longhand version:

```css
ul {
  list-style-type: square;
  list-style-position: outside;
  list-style-image: none;
}
```

If any of the values are omitted in the short-hand property that will be set to the default value of the property.

#### Navigational List Example

Most often the top navigation list on a webpage are marked up using unordered list. The list contains several navigational links. Let's how e add a navigational list on a page:

```html
<nav class="nav">
  <ul class="nav-menu">
    <li class="nav-item"><a href="#">Home</a></li>
    <li class="nav-item"><a href="#">About</a></li>
    <li class="nav-item"><a href="#">Services</a></li>
    <li class="nav-item"><a href="#">Blog</a></li>
    <li class="nav-item"><a href="#">Contact</a></li>
  </ul>
</nav>
```

By default `<li>` items are block-level elements so you will find each items are displayed vertically. But often the navigation lists are displayed horizontally in a single line. Let's style the list in a horizontal line using flex.

```css
body {
  font-family: "Open Sans";
}
.nav-menu {
  list-style: none;
  display: flex;
  align-items: center;
}
.nav-item {
  margin: 0 16px;
}
.nav-item a {
  text-decoration: none;
  font-size: 16px;
  text-transform: uppercase;
  font-weight: 600;
  background: linear-gradient(90deg, #247cca, #06b4a3);
  padding: 12px 20px;
  border-radius: 4px;
  color: #fff;
}
.nav-item a:hover {
  background: linear-gradient(90deg, #e52e71, #ff8a00);
}
```

To display list item horizontally you could have also `float` left or right the the li items or else changed it's display to `inline-block`. Depends upon the personal choice. I would recommend make the list(`<ul>`) `display:flex`, so that you dont have to worry about clearing or containing the floats or a small gap between the `inline-block` elements.

#### Description Lists

Another type of lists can be found online are description lists. Unlike ordered an unordered lists the description lists are not often used. To accomplish description list in HTML, `<dl>` tag is used. The `<dl>` element requires two block-level element, `<dt>` and `<dd>`. The `<dt>` represetns the description term and `<dd>` reprsents the description of the term.

```html
<dl>
  <dt>Bread</dt>
  <dd>A baked food made of flour.</dd>
  <dt>Coffee</dt>
  <dd>A drink made from roasted coffee beans.</dd>
</dl>
```

Similar to the `<ol>` and `<ul>`, `<dl>` element include vertical margins and `<dd>` element includes left margin.

Sometimes, the description list may have multiple terms per description, as well as multiple descriptions per term. For example:

```html
<dl>
  <dt>study</dt>
  <dd>
    The devotion of time and attention to acquiring knowledge on an academic
    subject, especially by means of books
  </dd>
  <dt>design</dt>
  <dd>
    A plan or drawing produced to show the look and function or workings of a
    building, garment, or other object before it is built or made
  </dd>
  <dd>
    Purpose, planning, or intention that exists or is thought to exist behind an
    action, fact, or material object
  </dd>
  <dt>business</dt>
  <dt>work</dt>
  <dd>A person's regular occupation, profession, or trade</dd>
</dl>
```
