# Translate and Transform

## transform:-
The "transform" property in CSS allows you to apply various transformations to an element.like

1. rotations
2. translations (movement)
3. scaling
4. skewing

### 1. rotate(angle):
Rotates the element clockwise by the specified angle.
Example: "transform: rotate(45deg);" rotates the element by 45 degrees clockwise.

```css

.element {
    transform: rotate(45deg);
}

```
This rotation is around the center of the element by default, but you can change the rotation origin using the "transform-origin" property.


### 2. translate(tx, ty):
Moves the element horizontally by "tx" pixels and vertically by "ty" pixels.
Example: "transform: translate(50px, 100px);" moves the element 50 pixels to the right and 100 pixels down.


```css

.element {
    transform: translate(50px, 100px);
}

```

### 3. scale(sx, sy):

Scales the element horizontally by sx factor and vertically by sy factor.(stretch element element)
Example: "transform: scale(1.5, 2);" scales the element 1.5 times its original width and 2 times its original height

```css

.element {
    transform: scale(1.5, 2);
}

```


### 4. skew(ax, ay):(skew:तिरछा 🤣)
Skews the element along the "x-axis" by ax degrees and along the "y-axis" by ay degrees.

Example: "transform: skew(30deg, 0);" skews the element 30 degrees along the x-axis.

```css

.element {
    transform: skew(30deg, 0);
}

```
After applying the CSS mentioned above, the square element will be skewed by 30 degrees along the x-axis. This means its bottom edge will be shifted to the right while the top edge remains stationary, resulting in a slanted appearance. Since the ay parameter is set to 0, there is no skew along the y-axis.

```css

              |
              |
      \       |
       \      |
        \     |
         \    |
          \   |
           \  |
------------\ |
            \ |
             \|


```
Where the dashed lines represent the skewed element. It has been slanted 30 degrees along the "x-axis" from its original orientation. The "y-axis" remains unaffected because the "ay" parameter is set to 0.

### 5. transform-origin(x, y):
Sets the origin point of the transformation.
By default, transformations are applied relative to the center of the element.
Example: "transform-origin: top left;" sets the origin point to the top-left corner of the element.

1. top:Sets the origin point to the top center of the element.
2. left:Sets the origin point to the bottom center of the element.
3. right:Sets the origin point to the left center of the element.
4. bottom:Sets the origin point to the right center of the element.
5. center:Sets the origin point to the center of the element.

6. Percentage Values:
X% Y%: Sets the origin point to a specified percentage along the x-axis and y-axis of the element's box.

```css

/* Keyword Values */
.element-top {
    transform-origin: top;
}

.element-bottom {
    transform-origin: bottom;
}

.element-left {
    transform-origin: left;
}

.element-right {
    transform-origin: right;
}

.element-center {
    transform-origin: center;
}

/* Percentage Values */
.element-percent {
    transform-origin: 25% 75%;
}

```


### 6. transform-style:
1. Defines how nested elements are rendered in 3D space.
2. Values can be"flat" (default) or "preserve-3d".
3. Example: "transform-style: preserve-3d;" maintains the 3D positioning of child elements.

```css

.parent {
    transform-style: flat;
}

.child {
    transform: rotateY(45deg);
}

```
In this example, the parent element has nested child elements. When the parent element is transformed, the child elements will rotate but won't maintain their own 3D rendering. They will be flattened into the parent element's plane.

 preserve-3d Example:- 

```css

.parent {
    transform-style: preserve-3d;
}

.child {
    transform: rotateY(45deg);
}

```
With "transform-style: preserve-3d;", the child elements will maintain their own 3D rendering. When the parent element is transformed, the child elements will rotate while preserving their 3D positioning relative to the parent's transformation.

```html

<div class="parent">
    <div class="child">Child 1</div>
    <div class="child">Child 2</div>
</div>

```

#### Lets use it to create a 3d box.


