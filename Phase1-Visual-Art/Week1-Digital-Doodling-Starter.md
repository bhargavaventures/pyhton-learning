# 🎨 Week 1: Digital Doodling - Building Blocks

## **🚀 SETUP (Copy this to start every project)**
```python
import turtle
import random

# Create your canvas
screen = turtle.Screen()
screen.bgcolor("black")  # Try: "white", "navy", "purple"
screen.setup(800, 600)

# Create your drawing pen
pen = turtle.Turtle()
pen.speed(0)  # Try: 1 (slow) to 10 (fast)
```

## **🧱 BUILDING BLOCK 1: Moving Around**
```python
# Basic movements - mix and match these!
pen.forward(100)      # Try different numbers
pen.backward(50)      
pen.right(90)         # Try: 45, 60, 120, 144
pen.left(45)          

# Jump without drawing
pen.penup()           
pen.goto(100, 50)     # Try: (-200, 100), (0, -150)
pen.pendown()         
```

## **🌈 BUILDING BLOCK 2: Colors & Style**
```python
# Pick your aesthetic!
pen.color("pink")           # Basic colors
pen.color("#FF69B4")        # Hex codes (Google "aesthetic color codes")

# Change thickness
pen.pensize(3)              # Try: 1, 5, 10

# Color lists for random effects
colors = ["red", "blue", "green"]
pen.color(random.choice(colors))
```

## **📐 BUILDING BLOCK 3: Basic Shapes**
```python
# Circle - try different sizes
pen.circle(50)        

# Square - experiment with the range number
for i in range(4):
    pen.forward(100)  # Try different sizes
    pen.right(90)

# Triangle
for i in range(3):
    pen.forward(100)
    pen.right(120)    # This makes it close properly
```

## **✏️ YOUR CHALLENGE: Draw Your Initials**

### **Example Letter "A" - Use as inspiration**
```python
# This is ONE way to draw an A - make it YOUR way!
pen.penup()
pen.goto(-50, -100)    
pen.pendown()
pen.left(75)           # Try different angles!
pen.forward(200)       # Try different lengths!
pen.right(150)         
pen.forward(200)       
pen.backward(75)       
pen.right(105)         
pen.forward(60)        
```

### **Your Turn - Fill in the Blanks:**
```python
# Draw YOUR first initial
pen.penup()
pen.goto(___, ___)     # Where should it start?
pen.pendown()
pen.color("____")      # What color do you want?

# YOUR CODE HERE - how will you draw your letter?
# Hint: Use pen.forward(), pen.right(), pen.left()

```

## **🎯 STARTER TEMPLATES (Modify These!)**

### **Template 1: Single Letter**
```python
import turtle
import random

screen = turtle.Screen()
screen.bgcolor("____")  # Fill in your background color
screen.setup(800, 600)
pen = turtle.Turtle()
pen.speed(0)

# YOUR CUSTOMIZATIONS:
pen.color("____")       # What color?
pen.pensize(___)        # How thick?

# Draw your letter here:
# (Use the building blocks above)

screen.exitonclick()
```

### **Template 2: Colorful Pattern**
```python
import turtle
import random

screen = turtle.Screen()
screen.bgcolor("black")
screen.setup(800, 600)
pen = turtle.Turtle()
pen.speed(0)

# Try changing these colors to match your style:
colors = ["____", "____", "____"]  # Fill in 3 colors you love

for i in range(___):  # How many times should it repeat?
    pen.color(random.choice(colors))
    pen.circle(100)   # What if you change this to pen.forward(100)?
    pen.right(10)     # What happens if you change this number?
    
screen.exitonclick()
```

## **🔧 BUILDING BLOCKS FOR LETTERS**

### **Straight Lines (for letters like I, L, T, H)**
```python
# Vertical line
pen.left(90)
pen.forward(100)

# Horizontal line  
pen.right(90)
pen.forward(100)
```

### **Curves (for letters like O, C, S)**
```python
# Half circle
pen.circle(50, 180)  # Try changing 180 to other numbers

# Full circle
pen.circle(50)
```

### **Diagonals (for letters like A, V, W, M)**
```python
# Slanted line
pen.left(60)    # Try different angles
pen.forward(100)
```

## **💡 EXPERIMENT IDEAS**

1. **What happens if you...?**
   - Change `pen.right(90)` to `pen.right(120)`?
   - Use `pen.circle(50, 90)` instead of `pen.circle(50)`?
   - Put your letter code inside a `for` loop?

2. **Make it personal:**
   - Use your favorite colors
   - Make letters really big or really small
   - Add extra decorations around your letters

3. **Try combinations:**
   - Draw both your initials
   - Make one letter big, one small
   - Use different colors for each letter

## **🎨 CREATIVE CHALLENGES**

### **Easy (Pick 1-2):**
- [ ] Change all colors to your favorites
- [ ] Make your letter 3 times bigger
- [ ] Add a circle around your letter

### **Medium (Try if you're feeling confident):**
- [ ] Draw your letter 3 times in different positions
- [ ] Make a "rainbow" version using different colors
- [ ] Create a simple pattern with basic shapes

### **Advanced (If you're having fun!):**
- [ ] Draw both your initials
- [ ] Make your letters "glow" by drawing them multiple times with slight offsets
- [ ] Create a design that looks like your personality

## **🚨 WHEN YOU GET STUCK**

**"My letter looks weird!"**
- Try changing the angle numbers (instead of 90, try 60 or 120)
- Adjust the forward distances (instead of 100, try 50 or 150)

**"I want different colors!"**
- Google "hex color codes" and copy ones you like
- Try: `"#FF6B9D"` (pink), `"#4ECDC4"` (teal), `"#45B7D1"` (blue)

**"Nothing shows up!"**
- Make sure you have `pen.pendown()` before drawing
- Check that you're not drawing outside the screen

## **✅ THIS WEEK'S GOALS**
- [ ] Make the basic setup work
- [ ] Draw at least one letter using the building blocks
- [ ] Experiment with 3 different colors
- [ ] Change at least 2 numbers to see what happens
- [ ] Create something you want to show someone!

**Remember:** There's no "right" way to draw a letter. Make it YOURS! 🌟