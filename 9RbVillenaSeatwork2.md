# Seatwork #2 - Getting to know CSS Position and z-index.
### This seatwork will ask you to implement the different CSS position on a given code.
### short link to this .md file is: https://bit.ly/4c61P9K
#### Resources (also found in Khub week 5)
- [4 Minute Youtube Video on CSS Position](https://www.youtube.com/watch?v=YEmdHbQBCSQ)
- [CSS Position Tutorial](https://roycan.github.io/CssPositioningZIndexLab/)

### Instructions: 
1. This is individual submission in khub, but you can work with a partner.  When you submit in khub please place both your names in the submission bin.
2. Guided Activity (30 minutes), please follow what is being required.  

    - Make a copy of this .md file to your Q4 repository and name it as **SectionLNseatwork2.md** example **9LiCruzSeatwork2.md**. Place it in your q4 repository vscode local computer. Committing frequently to your Github repository.  
    - Copy the code below and paste it inside a new file (name it as SectionLNseatwork2.html). Place this file in the same location where the .md file is saved. 
    - Change the content values of the meta tags to your names for author/s and the date today for revised.
    - Please do the following tasks that will ask you to reposition HTML elements then answer the guided question for each task on the .md file. Commit changes to the .md file and to the .html file as well.
    **- This seatwork is worth 20pts and should be submitted by the end of the period** The link to [KHub submission bin](https://khub.mc.pshs.edu.ph/mod/assign/view.php?id=15481).
      - Submit the links to your .md file and .html file.

```html
<!DOCTYPE html>
<html>
<head>
  <meta name="author" content="<your names>" />
  <meta name="revised" content="<date today>" />
  <style>
    body { font-family: Arial, sans-serif; }
    .header, .footer {
      background: lightblue;
      padding: 10px;
    }
    .footer {
       opacity: 0.5;
    }
    .sidebar {
      background: lightgreen;
      width: 150px;
      height: 200px;
    }
    .content {
      background: lightyellow;
      width: 300px;
      height: 200px;
    }    
  </style>
</head>
<body>
  <div class="header">Header</div>
  <div class="sidebar">Sidebar</div>
  <div class="content">Main Content</div>
  <div class="footer">Footer</div>
</body>
</html>
```
### Step 1 (Static vs Relative):

- Add in css ```position: relative; top: 20px; left: 20px;``` to .sidebar.

- Guided Question: What changed compared to the default static positioning? Try to give different values to top and left or you can change it to bottom, right.


> Answer: What changed with the sidebar box was that the sidebar boxed move a little bit to the bottom and a bit to the right. It means that it was moving 20px away from the top and 10px away from the left. 

### Step 2 (Fixed):

- Add in css ```position: fixed; bottom: 0; width: 100%;``` to .footer.

- Guided Question: What happens when you scroll the page? Why does the footer behave differently from position relative?


> Answer: The footer now will be fixed at the very bottom and it will not move when scrolling because fixed postion makes it stay in the same place even when the page is scrolled. A footer with position fixed is pinned to the viewport and removed from the normal document flow which mean it is anchored to the viewport which makes it visible even when the page is scorlled, while position relative keeps it in the flow and moves it relative to its original position.
### Step 3 (Absolute):

- Add in css ```position: absolute; top: 66px; left: 200px;``` to .content.

- Guided Question: What is the effect of position: absolute on an element? How is it different from fixed?

> Well absolute postiion removes an element form nor document flow and positions it releative to its closest positioned ancestor, unlike position fixed, it positions an element relative to the viewport and keeps it in place during scrolling.
### Step 4 : (Absolute)

- Add in html ```<div class="notice">Notice!</div>``` and include the css below:

```css
.notice {
    position: absolute;
    top: 60px;
    left: 400px;
    background: orange;
    padding: 10px;
    z-index: 2;
}
```

- Give .content a z-index: 1.2

- Guided Question: Why does the notice appear on top of the content? What happens if you swap the z‑index values?

> Well since .notice has a higher z-index(2) than .content(1), the browser renders .notice above .content in the stacking context. If you swap the index values like .notice will have a z-index of 1 and .content will have a z-index of 2, .content will now have the higher z-index, so it will be drawn above .notice. This means the notice could be hidden behind the content if they overlap.

- Challenge: 
    * What changes that you have to do on the code that will position .notice box on the top right corner of the .content box? Please write the code on paper as well (both html and css on the part of .notice and .content).

    > To place the .notice box at the top-right corner inside the .content box, you need to make .content the positioning reference by adding position: relative; to it, then set .notice to position: absolute; top: 0; right: 0; so it pins to the top-right of .content (not the whole page). You have to put the <div class="notice">Notice!</div> inside the .content div so it becomes a child of the content area.

    * Try to change the position of .content to relative then to fixed. What do you observed each time?
    * What do you observe on about the effect of z-index on .notice and .content boxes?

3. Please answer the following reflection questions (15 minutes)

    a. Could you summarize the differences between the CSS position values (static, relative, absolute, fixed)? 

    > Static is the default positioning for all HTML elements, elements follow the normal document flow, appearing one after another, the Top, right, bottom, and left properties have no effect.
    > In relative, the element remains in the normal flow, but can be offset relative to its original position using top, right, bottom, or left. The space it originally occupies is preserved, so other elements are not affected.
    > In Absolute, the element is removed from the normal document flow; it does not occupy space in the layout and it is positioned relative to its nearest positioned ancestor (an ancestor with position other than static). If none exists, it defaults to the initial containing block (usually the document body). It is also commonly used for overlays, popups, or floating elements inside a container.
    > Fixed is where the element is removed from the normal flow and anchored to the viewport, staying in the same position even when the page is scrolled. It is positioned using top, right, bottom, or left relative to the viewport. It is ideal for sticky headers, floating buttons, or persistent navigation elements ().

    b. How does absolute positioning depend on its parent element?

    c. How do you differentiate sticky from fixed (you can research on sticky)?

    d. If you were designing a webpage for a school event, how might you use positioning to highlight important information? Please give concrete examples.