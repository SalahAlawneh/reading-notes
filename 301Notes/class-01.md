# SMACSS
- SMACSS stands for 'Scalable and Modular Architecture for CSS'.
- SMACSS used to orgained the cascade styling sheet.
- In general we use those fiels:
1. base.css: for the general styling in page
1. layout.css: for nav, div, section... and another layout selector, and we can use classes here.
1. modules.css: for small individual elements like img, button,....
- There is another files we will use in the future.

# All About Floats
- For me it's better to use float when you don't have another option like wrapping text around image.
- The float don't miss with the HTML flow in general, like position absolute do.
- float have four values:
1. left
1. right
1. non
1. inherint
- The property we use to unfloat element is clear.
- Some times the flow property will miss the the container and make shrink or expand.
- To solve the problem with unwanted container change we use three methods:
1. make empty div element
1. use overflow
1. use one particular pseudo class `:after`


# Responsive Web Design
- responsive design have all features of mobile and adaptive design, so the developer can desing his web just one time and the web will work anywhere.
- There alot of way we can use to make our design reponsive:
   - flexible layout using percentage and em instead of pixeles and inches.
   ```target ÷ context = result```
   - Media Queries
   - Mobile First
   - Flexible Media
   - viewport
## Media Queries
- media queries used in CSS with adding two things:
  - @improt ...
  - @media ...
- there is query type and query experssion and media features, used to specify where? and what?
- query types like: all, screen...
- query experssion have three values: and, not, and only.
- media features have alot of values, like:
  - resoultion
  - height and width
  - orientaion ( landscape and portrait)
  - aspect ratio
## Mobile First
**the general idea that it's better to design the website for the mobile viewport and after that we can make media query or make our site responsive to another veiwports, so that the mobile don't have to deal with extra CSS**
## Flexible Media
**to make the media responsive, there is to way used:**
- using values for the CSS tags like percentages and em ....
- in embeded media using specific values for the containers and child, like:
``container=> width:100%, height:0, position:relative``
``|child=> width:100%, height:100%, position:absolute``

## viewport
- it's meta tag with name `viewport`
- some types of viewport:
  - width=device-width
  - initial-scale: usually= 1, and it's the ratio between device widh or length to th viewport width of lenght repectivly
  - min-scale
  - max-scale
- viewport could used in CSS file as @viewport, but it will not work in some browsers like internet explorer 8 or older browser.