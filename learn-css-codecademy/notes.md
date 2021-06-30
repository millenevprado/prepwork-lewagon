# LEARN CSS - CODECADEMY



### CSS Anatomy

![](images/css-anatomy.png)



#### Inline Styles

<p style='color:red;'>I'm learning to code!</p>

<p style='color:blue; font-size:30px;'>I'm learning to code!</p>

> It’s important to know that inline styles are a quick way of directly styling an HTML element, but are rarely used when creating websites. 



#### Internal Stylesheet

HTML allows you to write CSS code in its own dedicated section with a element nested inside of the `<head>` element. The CSS code inside the `<style>` element is often referred to as an *internal stylesheet*.

> An internal stylesheet has certain benefits and use cases over inlines styles, but once again, it’s not best practice. 



To create an internal stylesheet:

```html
<head>
  <style>
    p {
      color: red;
      font-size: 20px;
    }
  </style>
</head>
```



#### External Stylesheet

Developers avoid mixing code by storing HTML and CSS code in separate files (HTML files contain only HTML code, and CSS files contain only CSS code).

You can create an external stylesheet by using the **.css** file name extension, like so: **style.css**

When HTML and CSS codes are in separate files, the files must be linked.

You can use the `<link>` element to link HTML and CSS files together. The `<link>` element must be placed within the head of the HTML file. It is a self-closing tag and requires the following attributes:

1. `href` — like the anchor element, the value of this attribute must be the address, or path, to the CSS file.
2. `rel` — this attribute describes the relationship between the HTML file and the CSS file. Because you are linking to a stylesheet, the value should be set to `stylesheet`.



```html
<link href='./style.css' rel='stylesheet'>
```



### Selectors

#### Type

A selector is used to target the specific HTML element(s) to be styled by the declaration. One selector you may already be familiar with is the *type* selector. Just like its name suggests, the type selector matches the *type* of the element in the HTML document.

```css
p {
  color: green;
}
```

The element type is `p`, which comes from the HTML `<p>` tag.

> Since element types are often referred to by their opening tag name, the type selector is sometimes referred to as the *tag name* or *element* selector.



#### Universal

You learned how the *type selector* selects all elements of a given type. Well, the *universal selector* selects all elements of *any* type.

Targeting all of the elements on the page has a few specific use cases, such as resetting default browser styling, or selecting all children of a parent element.

The universal selector uses the `*` character in the same place where you specified the type selector in a ruleset, like so:



```css
* { 
  font-family: 'Verdana';
}
```



#### Class

CSS is not limited to selecting elements by their type. As you know, HTML elements can also have attributes. When working with HTML and CSS a *class* attribute is one of the most common ways to select an element.

```html
<p class='brand'>Sole Shoe Company</p>
```

To select an HTML element by its class using CSS, a period (`.`) must be prepended to the class’s name.

```css
.brand {

}
```



#### Multiple Classes

We can use CSS to select an HTML element’s `class` attribute by name. And so far, we’ve selected elements using only one class name per element. If every HTML element had a single class, all the style information for each element would require a new class.

Luckily, it’s possible to add more than one class name to an HTML element’s `class` attribute.

For instance, perhaps there’s a heading element that needs to be green and bold. You could write two CSS rulesets like so:

```css
.green {
  color: green;
}
 
.bold {
  font-weight: bold;
}
```

Then, you could include both of these classes on one HTML element like this:

```html
<h1 class='green bold'> ... </h1>
```

We can add multiple classes to an HTML element’s `class` attribute by separating them with a space. This enables us to mix and match CSS classes to create many unique styles without writing a custom class for every style combination needed.



### ID

Oftentimes it’s important to select a single element with CSS to give it its own unique style. If an HTML element needs to be styled uniquely, we can give it an ID using the `id` attribute.

```html
<h1 id='large-title'> ... </h1>
```

In contrast to `class` which accepts multiple values, and can be used broadly throughout an HTML document, an element’s `id` can only have a single value, and only be used once per page.

To select an element’s ID with CSS, we prepend the `id` name with a number sign (`#`). 

```css
#large-title {
 
}
```



#### Attribute

You may remember that some HTML elements use attributes to add extra detail or functionality to the element. Some familiar attributes may be `href` and `src`, but there are [many more](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes)—including `class` and `id`!

The *attribute selector* can be used to target HTML elements that already contain attributes. Elements of the same type can be targeted differently by their attribute or attribute value. This alleviates the need to add new code, like the `class` or `id` attributes.

Attributes can be selected similarly to types, classes, and IDs.

```css
[href]{
    color: magenta;
}
```

The most basic syntax is an attribute surrounded by square brackets. In the above example: `[href]` would target all elements with an `href` attribute and set the `color` to `magenta`.

And it can get [more granular](https://developer.mozilla.org/en-US/docs/Web/CSS/Attribute_selectors#syntax) from there by adding type and/or attribute values. One way is by using `type[attribute*=value]`. In short, this code selects an element where the attribute contains any instance of the specified value. Let’s take a look at an example.

```html
<img src='/images/seasons/cold/winter.jpg'>
<img src='/images/seasons/warm/summer.jpg'>
```

The HTML code above renders two `<img>` elements, each containing a `src` attribute with a value equaling a link to an image file.

```css
img[src*='winter'] {
  height: 50px;
}
 
img[src*='summer'] {
  height: 100px;
}
```

Now take a look at the above CSS code. The *attribute selector* is used to target each image individually.

- The first ruleset looks for an `img` element with an attribute of `src` that contains the string `'winter'`, and sets the `height` to `50px`.
- The second ruleset looks for an `img` element with an attribute of `src` that contains the string `'summer'`, and sets the `height` to `100px`.

Notice how no new HTML markup (like a class or id) needed to be added, and we were still able to modify the styles of each image independently. This is one advantage to using the attribute selector!