# CSS

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

