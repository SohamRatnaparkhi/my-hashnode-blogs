---
title: "CSS - flexbox"
seoTitle: "Web Development"
datePublished: Mon Aug 01 2022 05:39:01 GMT+0000 (Coordinated Universal Time)
cuid: cl6abmt5t0di3y6nvakz5f1wm
slug: css-flexbox
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1659266359902/DKxKFZMpT.jpg
tags: css3, css-flexbox, web-development, html5, blogswithcc

---

Flexbox display property seems to be a bit confusing or intimidating initially but is a great tool that helps make your website responsive. This article will cover all the paramount/important flexbox properties (which include properties on the parent container as well as its children)that are generally used. *Let's begin our journey to learn the basics of flexbox!*

# Introduction
The flexbox display property provides a super efficient way to align the children elements of the parent flexbox container by providing methods to: 
  * improve the use of space on the screen, and 
  * change the dimensions of children (inner) containers (divs, sections, etc.)

One of the biggest advantages of using a flexbox is that it adds certain responsive behavior to your website. This means that it can dynamically (and of course automatically) change the dimensions of inner containers when the size (viewport) of the parent container.
**Note**: Flexbox layout is most appropriate to the components of an application, and small-scale layouts, while the Grid layout is intended for larger-scale layouts.

# Flexbox properties
> *Now let's deep dive into the properties of a* `CSS flexbox`.

Note that you have to first add the property `display: flex;` to the parent container.

```
<body>
    <div class="parent-container">
        <div class="flex-items"> 1 </div>
        <div class="flex-items"> 2 </div>
        <div class="flex-items"> 3 </div>
        <!-- <div class="flex-items"> 4 </div>
             <div class="flex-items"> 5 </div>
             <div class="flex-items"> 6 </div> -->
    </div>
</body>
```

```
body {
    background-color: rgb(146, 196, 235);
}

.parent-container {
    display: flex;
/* This initializes a flexbox in the parent container */
}

.flex-items {
    background: rgb(255, 148, 7);
    color: white;
    font-size: 25px;
    text-align: center;
    width: 70px;
    line-height: 50px;
    margin: 10px;
}
```
This is the default HTML and CSS and here's its output.


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1659272003139/MpCl804E-.png align="left")
[image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1659270469294/Mf-w1xCBw.png align="left")

* ### `flex-direction: `
This establishes the main-axis, thus defining the direction flex items are placed in the flex container. Flexbox is (aside from optional wrapping) a single-direction layout concept.
The following 4 values can be applied to this property.
** All of them need to be written in the parent- container only.**
 
a) flex-direction:  column

```
 /* This property aligns elements in a vertical line. */
.parent-container {
     display: flex;
    flex-direction: column;
}
``` 

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1659271565125/ba5_bQ9n7.png align="left")
 
  b)  flex-direction:  row

 ```
 /* This property aligns elements in a horizontal line. */
parent-container {
    display: flex;
    flex-direction: row;
}
``` 


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1659272121051/FoWhvab9b.png align="left")

c) flex-direction: row-reverse

```
.parent-container {
    /* Reverses the elements in row and right aligns them */
    display: flex;
    flex-direction: row-reverse;
}

``` 


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1659272255941/N90-n6-bp.png align="left")

d) flex-direction: column-reverse


```
.parent-container {
    /* Reverses the elements column-wise and doesn't affect their alignment */
    display: flex;
    flex-direction: column-reverse;
}
``` 


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1659272395740/N_gs8Zsh_.png align="left")


* ### `flex-wrap: `
By default, flex items will all try to fit onto one line. You can change that and allow the items to wrap as needed with this property. 
> I added some more HTML divs under the class ` flex-item ` to demonstrate this.

```
.parent-container {
    /* Wraps the rows/columns without affecting the spacing and size of divs */
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
}
``` 

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1659272824276/hapL6Hiba.png align="left")

Without using this property, the divs would probably squeeze in to fit themselves in the div somewhat like this:

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1659272900276/5LoRPLmFP.png align="left")

* ### `flex-flow: `
This is basically a short-hand property that combines flex-direction and flex-wrap.

```
.parent-container {
    /* Wraps the rows/columns without affecting the spacing and size of divs */
    display: flex;
    flex-flow: row wrap;
}
``` 
Outputs are similar as shown above.

* ### `justify-content: `
This property determines how divs would be aligned on the major axis.
If required, it will affect the spacing between the divs (children containers).
> Now I'll be again commenting out the extra divs in the HTML file and will keep divs numbered 1 to 4.

It has around 6 different values to be paired up, but, generally in the context of `justify-content` - only 2 of them are used, and the rest of them are generally used with the `align-items` property which I will tell after this one.

a)  justify-content: center

```
/* aligns all the children containers to the center of their main axis (horizontal axis) without affecting the spacing and order.  */
.parent-container {
    display: flex;
    justify-content: center;
}
``` 


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1659274401271/KqH2w8WX8.png align="left")

b)  justify-content: space-around

```
.parent-container {
    /*Affects the spacing between the containers*/
    display: flex;
    justify-content: space-around;

}
``` 

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1659274372229/rShA0cIat.png align="left")

By now we were using properties that are generally used in the external CSS file.

> All the properties henceforth are generally used as inline CSS. It is not a thumb rule but generally, they are preferred in that manner. 

The reason behind this is that the henceforth properties are usually used for individual elements of a flexbox. You can still use them in the external CSS file but then every item will require a new class or id which is a bit tedious and repetitive.

* ### `flex: `

There are three sub-properties of this keyword `flex`. They are:

 a) `flex-grow` - It controls the overall size of that element with respect to other elements in the flexbox. If a single element is given this property while all others are not given, then that element will stretch itself and occupy all the remaining space in that particular axis of the flexbox. To avoid this, you can always set this property of those elements whose size need not be changed to 1.
b) `flex-shrink` - It deals with the size of elements when the flexbox shrinks; i.e. when the size of the device screen is changed to a smaller screen. It provides a threshold value for the children element's size when it shrinks.
c) `flex-basis` - It also deals with the overall size of the child element of the flexbox.  

You can use a shorthand operator for these which is
```
flex: <grow_value> <shrink_value> <basis_value>
```
Here's a  demonstration of this:-
 
```
<div class="parent-container">
        <div class="flex-items" style="
            flex-grow: 2;          
        "> 1 </div>
        <div class="flex-items" style="
            flex-grow: 1;
        "> 2 </div>
        <div class="flex-items" style="
            flex-grow: 3;
          "> 3 </div>
        <div class="flex-items" style="
            flex-grow: 0.5;
           "> 4 </div>
    </div>
``` 

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1659329822727/icbX6Z7ku.png align="left")
> You can see that the size of boxes 1 and 3 are larger than 2 while the size of 4 is smaller.
This is due to the `grow` property. 


```
<div class="parent-container">
        <div class="flex-items" style="
            flex-grow: 1;
            flex-shrink: 2;
            flex-basis: 1;
        "> 1 </div>
        <div class="flex-items" style="
            flex-grow: 1;
            flex-shrink: 3;
            flex-basis: 1;
        "> 2 </div>
        <div class="flex-items" style="
            flex-grow: 1;
            flex-shrink: 0.5;
            flex-basis: 1;
        "> 3 </div>
        <div class="flex-items" style="
            flex-grow: 1;
            flex-shrink: 1;
            flex-basis: 1;
        "> 4 </div>
    </div>
``` 

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1659330436280/4_RRI0Zfx.png align="left")

> I decreased the width of the viewport and you can see in the image as to the how shrink property worked.
The flex-basis property usually doesn't show many visual effects and is worth ignoring😁.

All this can be combined into a shorthand notation using the flex keyword as mentioned above.

Now comes the final property that is:
* ### `align-self: `
As the name suggests, this property aligns elements without affecting the position of other elements. It has three different values which are - `center`, `flex-start` and `flex-end`.

```
<div class="parent-container" style=" flex-direction: column;">
        <div class="flex-items" style="
            align-self: flex-start;
        "> 1 </div>
        <div class="flex-items" style="
            align-self: center
        "> 2 </div>
        <div class="flex-items" style="
            align-self: center;
        "> 3 </div>
        <div class="flex-items" style="
            align-self: flex-end;
        "> 4 </div>
    </div>
``` 


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1659331571928/MdIHxqFJ1.png align="left")

This brings us to the end of this chapter! I have tried covering almost all the major flexbox properties. Hope you like it!

You can consider following me on [Twitter](https://twitter.com/SohamR_7113) if you like my content. Thankyou!

