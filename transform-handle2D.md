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

```css

<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>3D Box</title>
<style>
    .container {
        perspective: 1000px; /* Perspective for 3D effect */
        perspective-origin: center; /* Set the perspective origin */
    }

    .box {
        width: 200px;
        height: 200px;
        background-color: rgba(0, 0, 255, 0.5);
        position: relative;
        transform-style: preserve-3d; /* Maintain 3D positioning */
        animation: rotate 5s linear infinite; /* Optional: Rotate animation */
    }

    .side {
        position: absolute;
        width: 100%;
        height: 100%;
        background-color: rgba(255, 255, 255, 0.8);
        border: 1px solid #000;
    }

    .front { transform: translateZ(100px); }
    .back { transform: translateZ(-100px) rotateY(180deg); }
    .left { transform: rotateY(-90deg) translateZ(100px); }
    .right { transform: rotateY(90deg) translateZ(100px); }
    .top { transform: rotateX(90deg) translateZ(100px); }
    .bottom { transform: rotateX(-90deg) translateZ(100px); }

    @keyframes rotate {
        from { transform: rotateY(0); }
        to { transform: rotateY(360deg); }
    }
</style>
</head>
<body>
<div class="container">
    <div class="box">
        <div class="side front">Front</div>
        <div class="side back">Back</div>
        <div class="side left">Left</div>
        <div class="side right">Right</div>
        <div class="side top">Top</div>
        <div class="side bottom">Bottom</div>
    </div>
</div>
</body>
</html>

```


### 7. perspective(depth):
Specifies the perspective from which an element is viewed.
Affects the 3D transformations such as rotateX, rotateY, etc.
Example: perspective(1000px); sets the perspective depth to 1000 pixels.


```css

.element {
    transform: rotate(45deg) translate(50px, 50px) scale(1.5);
}

```

### 8. matrix(a, b, c, d, tx, ty):







