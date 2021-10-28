---
## p5 Syntax

p5 is a JavaScript library for creative coding. It makes coding accessible and inclusive for artists, designers, beginners, and anyone else. 

<iframe src="https://giphy.com/embed/elbXlu1pSOx4CUV8Z9" width="300" height="300" frameBorder="0" class="giphy-embed" allowFullScreen></iframe><p><a href="https://giphy.com/gifs/elbXlu1pSOx4CUV8Z9"></a></p>

### p5 Commands
---
The first step is to create a canvas to draw on. The `createCanvas()` function makes a digital surface on which you can draw and `background();` specifies [color](https://p5js.org/reference/#/p5/background). 

```
function setup(){
  createCanvas(600,500);
	background(red);
}
```


<table><tbody ><tr><td><details><summary>
<b>Sample Code #1:</b> Try this code below. </summary><hr>
	
```
function setup() {
  createCanvas(400, 400);
	background(220);
}

function draw() {
  if (mouseIsPressed) {
    fill(0);
  } else {
    fill(255);
  }
  ellipse(mouseX, mouseY, 80, 80);
}
```

</details></td></tr></tbody>
</table>

<table><tbody ><tr><td><details><summary>
<b>Sample Code #2:</b> Try this code below. </summary><hr>
	
```
function setup() {
  
		// Create the canvas
		createCanvas(300, 300);
		background(200);
	
    //set colors
    fill(204, 101, 192, 127);
		stroke(127, 63, 120);
    
    //design for simple flower
    translate(150, 150);
		noStroke();
		for (let i = 0; i < 10; i ++) {
			ellipse(0, 30, 20, 80);
			rotate(PI/5);
		}
}
```

</details></td></tr></tbody>
</table>

<table><tbody ><tr><td><details><summary>
<b>Sample Code #3:</b> Try this code below. </summary><hr>
	
```
let v;

function setup() {
  createCanvas(640, 360);
  v = new Vehicle(width / 2, height / 2);
}

function draw() {
  background(220);

  let mouse = createVector(mouseX, mouseY);

  fill(200);
  stroke(0);
  strokeWeight(2);
  ellipse(mouseX, mouseY, 48, 48);

  v.arrive(mouse);
  v.update();
  v.display();
}

class Vehicle {
  constructor(x, y) {
    this.position = createVector(x, y);
    this.velocity = createVector(0, -2);
    this.acceleration = createVector(0, 0);
    this.r = 6;
    this.maxspeed = 4;
    this.macforce = 0.1;
  }

  update() {
    this.velocity.add(this.acceleration);
    this.velocity.limit(this.maxspeed);
    this.position.add(this.velocity);
    this.acceleration.mult(0);
  }

  applyForce(force) {
    this.acceleration.add(force);
  }

  seek(target) {
    let desired = p5.Vector.sub(target, this.position); // A vector pointing from the position to the target
    desired.setMag(this.maxspeed);
    let steer = p5.Vector.sub(desired, this.velocity);
    steer.limit(this.maxforce); // Limit to maximum steering force

    this.applyForce(steer);
  }

  arrive(target) {
        let desired = p5.Vector.sub(target, this.position);
    let d = desired.mag();
    
    if(d < 100){
      let m = map(d, 0, 100, 0, this.maxspeed);
      desired.setMag(m);
    } else {
      desired.setMag(this.maxspeed);
    }
    
    let steer = p5.Vector.sub(desired, this.velocity);
    steer.limit(this.maxforce);
    this.applyForce(steer);
  }

 display() {
    let theta = this.velocity.heading() + PI / 2;
    fill(127);
    stroke(0);
    strokeWeight(1);
    push();
    translate(this.position.x, this.position.y);
    rotate(theta);
    beginShape();
    vertex(0, -this.r * 2);
    vertex(-this.r, this.r * 2);
    vertex(this.r, this.r * 2);
    endShape(CLOSE);
    pop();
  }
}   
```

</details></td></tr></tbody>
</table>

### Run your Program
---
Whenever a change is made to your code, you must click the **Run/Refres** button in the preview panel for the animation to reflect the updates.  

![Run the Code](.guides/img/run.png)


### Basic Commands
---
Below are some basic shapes that you can draw to the screen in `function draw()`:
|Command|Parameter|
|:-----:|:-------:|
| `ellipse(x, y, w, h);` | This creates a circle with center `x,y` with `width` and `height` specified | 
| `rect(x, y, w, h);` | This creates a rectangle where `x,y` is the position of the rectangle's upper left hand corner; width` and `height` specified | 
| `triangle(x1, y1, x2, y2, x3, y3);` | Where the `x` and `y` pairs are the three points of the triangle |
| `triangle(x1, y1, x2, y2, x3, y3);` | Where the `x` and `y` pairs are the three points of the triangle |

||| 
**Want more commands?**

Visit the [p5.js website Reference page](https://p5js.org/reference/) to view more.
|||

## Setting up p5 in Codio
---
Instruction through Codio is built around the guide feature. This is a brief description on how the demo of the previous page was built. Please see the [**documentation**](https://docs.codio.com/authoring.html) for more information about content authoring with guides.

### Build on this Starter Pack
---
Please note that this Starter Pack uses the Codio-Certified **Processing Language Stack.** 

![Processing Stack](.guides/img/stack.png)

Follow the directions below to build out this project with your own activities in processing:

### Files
---
1. Please note that there are software, files, scripts, etc. preconfigured in this **Hello Processing/p5 in Codio** Starter Pack that allow their use.

<table><tbody ><tr><td><details><summary>
Collapse to view the contents of the existing <code>index.html</code> file. </summary><hr>
	
```
<!DOCTYPE html>
<html>
  <head>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/p5.js/0.9.0/p5.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/p5.js/0.9.0/addons/p5.dom.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/p5.js/0.9.0/addons/p5.sound.min.js"></script>
    <link rel="stylesheet" type="text/css" href="style.css">
    <meta charset="utf-8" />

  </head>
  <body>
    <script src="sketch.js"></script>
  </body>
</html>
```
	
</details></td></tr></tbody>
</table>


2. Select **File > New** from the Codio menu and create a file with a `.js` suffix. You will notice this file in your **FileTree.**


### Page Layout
---
Each page in the guide can have its own layout. You can select how many panels you want, and what information goes in each panel. Click the wrench in the top-right corner of your guide. You can select the layout from here. To set up Processing:

1. Click the settings wrench icon and select **3 Panels without a tree.** 
2. Navigate to **Open Tabs**. 
3. Drag your `.js` file under **Add Tabs** and position it in panel 0. 
4. Click the **Add Tab** button and select the **Type** as **Preview.** Enter the following in the field: `index.html`. Position this in panel 1. 
5. Preview the page to ensure your layout is as desired.


### Add this Project to a Course
---
You can add this project as an assignment to an existing course:

1. In the course module, click **Add Assignment**.
2. On the Create Assignment page, click **Project based**.
3. To import a project, click the **Click here** link under **Starting Point.** 
4. Click **Copy Project** and browse to the project and select it.
5. Click **Create.**

