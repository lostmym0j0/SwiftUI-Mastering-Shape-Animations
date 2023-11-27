# SwiftUI: Mastering Shape Animations
## Introduction

In this article, I explain the nuances of working with Shapes in SwiftUI. Topics covered include building custom Shapes, working with AnimatableData to animate Shape changes, and utilizing AnimatableVector to create custom types that will assist in working with complex Shapes and difficult animations.

I provide quite a bit of code. Much of the provided code will have originated from other authors. Their articles will be cited at the end. Some of the provided code will be mine, but based on something I saw in an article or StackOverflow post. These will also be cited. All code referenced in this article is completely available for use without restriction.

First, I will provide an example of the finished product and briefly explain what my "specs" were. Then I will discuss the entire process of satisfying the specs, the steps taken to accomplish building this Shape, and it's accompying animation. Hopefully I provided enough detail and code for most readers to build and animate their own custom shapes. I will also provide a list of all resources I used to understand Shape animation in SwiftUI.

### The Specs, Shape and Animation
This is the bottom of my "Exercise Explorer" scene. This is my attempt at creating a sort of tab bar with a bit of a blurry glass design. The user may click the plus button if they want to create a new exercise. After the plus button is clicked, five options move out from under the plus button. But I also wanted the five options to hover over the glass tab bar just like the other three buttons shown. So I needed the bubble at the top of this shape to expand when the user clicks the plus button.

| ![](https://github.com/lostmym0j0/SwiftUI-Mastering-Shape-Animations/blob/main/Media/Final%20Product%20Slowed.gif) |
|:--:| 
| *This is the final product.* |

| ![](https://github.com/lostmym0j0/SwiftUI-Mastering-Shape-Animations/blob/main/Media/Final%20Product%20(-buttons)%20Slowed.gif) |
|:--:|
| *This is the final animation without the buttons.* |

## Accessibility

I wanted to maintain compliance with accessibility requirements so I had to build these shapes around the sizing of my buttons. The buttons are also built around the text they contain. So if the user changes text size or if the app is ever translated into different languages, the buttons will match the new text size or text length and the shape will also match the buttons sizes.

### Collecting Size Information

In order to do this, I needed to collect size information on first, the button text, and second, the buttons.

![](https://github.com/lostmym0j0/SwiftUI-Mastering-Shape-Animations/blob/main/Media/Just%20The%20Buttons.gif)
