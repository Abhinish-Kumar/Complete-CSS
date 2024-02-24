# Complete-CSS


## Css-selectors
css selector allow used to select a specific element in our dom tree and style that element.
We can select the element by its Id,name and its classname.In css we can also conditionally style the elements.

1. div > p :- target the direct children of div if the child is p.(called as child selector)
2. div p:-select all the p which is inside div it can be child or grand child of div.but in abouve we only target the direct child(called descendent selector).
3. * :- select all elements (universal selector).

4. div * :-Select all the elements present in div.
5. a,div,span:-select multiple elements for applying common properties.(target multiple elements)


### Pseudo selectors(for link)

1. a:visited:- change color on visit the link.(after visit)
2. a:link:-change the color of all the links when created.(before visit)
3. a:active:-onhover and onclick change background.(onvisit)

# Pseudo selectors
Pseudo selectors are used to target a specific part of an element like first letter,first line.


### Pseudo selectors(hover)

1. div:hover:- apply css on hover.

### Pseudo elements

1. p::first-letter:- select the first letter of first line of the selector.

```css

p::first-letter{
font-size:2rem,
font-family:bold
}

```
2. p::first-line:- select the first line of all the paragraph.
3. p::before :-Insert the content before element.


```css

.name::before{
content:"Mr"
}

```
also used in animation like button hover slide up.
Where we only style the psudo element and animate that as related to real element of is.

4. p::after :- same as before selector but it add the content after the element.
 these type of selectors are used to apply quotation marks at last and begining.


### Pseudo selectors(for child elements)

1. div:first-child:-select the first p of a div element.


2. ::selection :- selected the portion of the text that is selected by the cuesr(to copy).

```css

::selector{
bg-color:red
}

div::selector{
bg-color:pink
}
```
3. ::placeholder :- Select the placeholder text in an input field.

```css

#name::placeholder{
color:red
}
```
4. ::marker :- select the marker of the list.

```css

li::marker{
color:red,
font-size:10px
}
```

5. input:focus :- select the input field when it is in focus.

```css

input:focus{
border:none
}
```


6. parent:nth-child:- select the child elements with numbers.

```css

parent:nth-child(even){
/* select all the elements which are even in position*/
}
parent:nth-child(odd){
/* select all the elements which are even in position*/
}

parent:nth-child(1+1){
/* select 2nd element*/
}

```

# select parent element with child element


## !important:- used to override all the previous property applied to an element.

```css

p{
color:red !important;
}
```















