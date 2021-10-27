---
## Processing Syntax

Processing is a simplified java-based programming language development environment designed for use by designers and artists. Students use a software "sketchbook" and production tool to manipulate images, animation and other visual interactions. 



### Processing Commands
---
The first step is to create a background. Using `background()` indicate the color and be sure to indicate the `size()`. Run the following code in the file to the left:

```
size(400, 400);
background(192, 64, 0);
```

<table><tbody ><tr><td><details><summary>
<b>Sample Code #1:</b> Try this code below. </summary><hr>
	
```
size(400, 400);
background(192, 64, 0);
line(15, 25, 70, 90);
```

</details></td></tr></tbody>
</table>

<table><tbody ><tr><td><details><summary>
<b>Sample Code #2:</b> Try this code below. </summary><hr>

```
size(400, 400);
background(192, 64, 0);    // sets background at burnt orange color
stroke(255);               // sets the stroke color to white
line(150, 25, 270, 350);   // tells line where to go
stroke(255, 128, 0, 128);  // bright orange with 50% transparency
```

</details></td></tr></tbody>
</table>

<table><tbody ><tr><td><details><summary>
<b>Sample Code #3:</b> Try this code below. </summary><hr>
	
```
void setup() {
    size(400, 400);
    stroke(255);
    background(192, 64, 0);
} 
void draw() {
    line(150, 25, mouseX, mouseY);
}
```

</details></td></tr></tbody>
</table>

<table><tbody ><tr><td><details><summary>
<b>Sample Code #4:</b> Try this code below. </summary><hr>
	
```
void setup() {
    size(400, 400);
    stroke(255);
} 
void draw() {
    line(150, 25, mouseX, mouseY);  
void mousePressed() {
    backgroun(192, 64, 0);
}
```

</details></td></tr></tbody>
</table>

### Run your Code
---
The processing console gives incredibly helpful debugging tips. Run your program  using the buttons in the top left corner of the window.

![Run in Processing](.guides/img/run2.png)

### Basic Commands
|command|description|
|:---|:---|
|`point()`|point`(x,y)` or point`(x,y,z)`|
|`triangle()`|triangle`(x1, y1, x2, y2, x3, y3)`|
|`quad()`|quad`(x1,y1,x2,y2,x3,y3,x4,y4)`|
|`rect()`|rect`(x,y,w,h)` where `w` and `h` are pixels|
|`ellipse()`|ellipse`(x,y,w,h)` where `w` and `h` should be equal |
|`text()`|text`(c,x,y)` where `c` is any alphanumeric character|
|`fill()`|fill`(r,g,b)` where red, green and blue values as an integer|
|`strokeWeight()`|`strokeWeight(x)` where `x` is an integer that sets width of stroke|

For a more complete list, [**click here.**](https://www.toptal.com/game/ultimate-guide-to-processing-the-fundamentals)

## Setting up Processing in Codio

Instruction through Codio is built around the guides feature. This is a brief description on how the demo on the previous page was built. Please see the [**documentation**](https://docs.codio.com/authoring.html) for more information about content authoring with guides.

### Build on this Starter Pack
---
Please note that there are softwares, files, scripts, etc. preconfigured in this **Hello Processing/p5 in Codio** Starter Pack that allow their use. Follow the directions below to build out this project with your own activities in processing.


Please note that this Starter Pack uses the Codio-Certified **Processing Language Stack.** 

![Processing Stack](.guides/img/stack.png)

### Page Layout
---
Each page in the guide can have its own layout. You can select how many panels you want, and what information goes in each panel. 

1. Open the settings wrench icon and select **2 Panels without tree** so that you can have one panel for the Processing environment and one panel for the Guide. Toggle on **Close Tabs.** Don't forget to **Save and Close Settings.**

2. The next step is to select `Add Tab` and select **Preview.** Copy and paste `https://{{domain3000}}/` and select panel 0.

3. Select the **Preview** button to see the rendered content. 

### Add this Project to a Course
---
You can add this project as an assignment to an existing course:

1. In the course module, click **Add Assignment**.
2. On the Create Assignment page, click **Project based**.
3. To import a project, click the **Click here** link under **Starting Point.** 
4. Click **Copy Project** and browse to the project and select it.
5. Click **Create.**

