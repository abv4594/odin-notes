# CSS

## Cascade

The priority: **ID Selector > Class Selector > Type selectors** which is known 

Now in many situations it's a bit more complex. So there are some additional rules:
### If an element is targeted by same priorities, wins the one with more selections. Examples:
```html
<div class="main">
    <div class="list subsection">Red text</div>
</div>
```

```css
/*rule 1*/
.subsection {
    color: blue
}

/*rule 2*/
.main .list {
    color: red
}
```
*In the above example, rule 2 wins because it targets the element more times.*

However, if **rule 1** were an id definition like:
```css
#subsection {
    color: blue
}
```
Then it would win.

### The operators ```* , >, (space)``` don't add to the specificity (specificity = 0)

```css
* {
    color: red
}

h1 {
    color: blue
}

.title {
    color: green
}
```

``` html
<h1 class="title"> Title </h1>
```

In the html above the title would appear green. 

### Inheritance

Typography-based properties are usually inherited. The inheritance loses when the element is directly targeted. No matter if the parent has a higher specificity. Example:

``` css
#parent {
    color: blue
}

.child {
    color: red
}
```

```html
<div id="parent">
    <div class="child"> Text </div>
</div>   
```

In the code above, Text would appear **red**

## Inner and Outer Display Types

Until I read about this, it was a bit confusing for me as some properties would affect the boxes outside whereas other properties would affect the elements inside the boxes.

This happens because some types affect how the box itself behave (Outer) others how elements inside the box behave.

```css
display: block /* will affect the box itself - it's an outer display type */
display: flex /* will affect the elements inside the box - it's an inner display type */
```

## Box Sizing

The box is composed of (from inside to outside):
- content
- padding
- border
- margin - margin is not considered part of the box itself but to the space between boxes

In the regular / original model, the **width** and **height** referred to the content only. 

In the alternate **border-box** model, **width** and **height** refer to content + padding + border. This makes development simpler.

## display: block VS display: inline

Certain elements like ```span``` are **inline** by default. In an **inline** element:

- top and bottom padding, border, margin are applied but don't affect other elements around it. 
- left and right padding, border and margin are applied and affect elements around.

