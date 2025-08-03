# 🌀 Week 3: Instagram-Worthy Patterns - Building Blocks

## **🚀 SETUP (Copy this to start)**
```python
import turtle
import random
import math  # We might need this for cool patterns!

screen = turtle.Screen()
screen.bgcolor("____")  # What background makes your patterns pop?
screen.setup(800, 800)   # Square canvas for Instagram!
pen = turtle.Turtle()
pen.speed(0)
pen.pensize(___)  # Try 1, 2, or 3 for clean lines
```

## **🎨 BUILDING BLOCK 1: Aesthetic Color Palettes**
*Fill in your favorite aesthetic colors!*

```python
# Trending aesthetics - customize with YOUR colors:
pastel_vibes = ["#FFB3BA", "____", "____", "____"]  # Add 3 more pastels
neon_energy = ["#FF6EC7", "____", "____", "____"]   # Add 3 more neons  
earth_tones = ["#D4A574", "____", "____", "____"]   # Add 3 more earthy colors

# Create your own aesthetic:
my_aesthetic = ["____", "____", "____", "____"]     # What colors are YOU?

# Use them like this:
colors = pastel_vibes  # Or neon_energy, earth_tones, my_aesthetic
pen.color(random.choice(colors))
```

## **🔄 BUILDING BLOCK 2: The Magic of Repetition**
```python
# Basic pattern loop - experiment with these numbers!
for i in range(___):  # Try: 36, 72, 100, 360
    pen.color(random.choice(colors))
    pen.forward(___)  # Try: 50, 100, i*2, i*3
    pen.right(___)    # Try: 90, 91, 89, 121, 144
```

## **⭐ BUILDING BLOCK 3: Pattern Shapes**

### **Circles (Great for mandalas)**
```python
for i in range(___):  # How many circles?
    pen.color(random.choice(colors))
    pen.circle(___)   # Try: 50, 100, i*5
    pen.right(___)    # Try: 10, 15, 30 (360/number of circles)
```

### **Lines (Great for geometric patterns)**
```python
for i in range(___):  # How many lines?
    pen.color(random.choice(colors))
    pen.forward(___)  # Try: 100, i*2, random.randint(50, 150)
    pen.backward(___)  # Go back to center? Or not?
    pen.right(___)    # Try: 360/number of lines
```

### **Polygons (Triangles, squares, hexagons)**
```python
def draw_polygon(sides, size):
    for i in range(sides):
        pen.forward(size)
        pen.right(360/sides)  # This makes any polygon!

# Use it like this:
for i in range(___):  # How many polygons?
    pen.color(random.choice(colors))
    draw_polygon(___, ___)  # (sides, size) - Try: (3, 50), (6, 30), (8, 40)
    pen.right(___)  # Rotation between polygons
```

## **📸 YOUR CHALLENGE: Create Instagram-Worthy Art**

### **Template 1: Spirograph-Style Pattern**
```python
import turtle
import random

# Setup
screen = turtle.Screen()
screen.bgcolor("____")  # Try: "black", "white", "navy"
screen.setup(800, 800)
pen = turtle.Turtle()
pen.speed(0)
pen.pensize(1)

# YOUR aesthetic colors:
my_colors = ["____", "____", "____", "____"]

# Experiment with these numbers:
for i in range(___):  # Try: 100, 200, 360
    pen.color(random.choice(my_colors))
    pen.forward(___)   # Try: 100, i, i*2
    pen.right(___)     # THE MAGIC NUMBER! Try: 89, 90, 91, 121, 144

screen.exitonclick()
```

### **Template 2: Mandala Creator**
```python
import turtle
import random

screen = turtle.Screen()
screen.bgcolor("white")  # Mandalas often look good on white
screen.setup(800, 800)
pen = turtle.Turtle()
pen.speed(0)

# YOUR mandala colors:
mandala_colors = ["____", "____", "____"]

# How many "petals" in your mandala?
petals = ___  # Try: 12, 8, 6, 24

for petal in range(petals):
    pen.color(random.choice(mandala_colors))
    
    # What shape is each petal?
    pen.circle(___)  # Try: 50, 80, 100
    # Or try: draw_polygon(6, 40)
    
    pen.right(360/petals)  # This spaces them evenly

screen.exitonclick()
```

## **🎯 PATTERN EXPERIMENTS**

### **Size Changes:**
```python
# Patterns that grow or shrink
for i in range(50):
    pen.color(random.choice(colors))
    pen.circle(i)      # Gets bigger each time
    # Or try: pen.circle(50 - i)  # Gets smaller
    pen.right(10)
```

### **Color Gradients:**
```python
# Smooth color transitions
colors = ["#FF0000", "#FF3300", "#FF6600", "#FF9900", "#FFCC00"]
for i in range(len(colors) * 10):
    pen.color(colors[i // 10])  # Changes color gradually
    pen.forward(5)
    pen.right(90)
```

### **Randomness:**
```python
# Controlled chaos
for i in range(___):
    pen.color(random.choice(colors))
    pen.penup()
    pen.goto(random.randint(-300, 300), random.randint(-300, 300))
    pen.pendown()
    pen.circle(random.randint(10, 50))
```

## **💡 CREATIVE CHALLENGES**

### **Beginner (Pick 2-3):**
- [ ] Create a spirograph with your favorite colors
- [ ] Make a simple mandala with 8 or 12 petals
- [ ] Try changing ONE number in the templates to see what happens

### **Intermediate (Try 1-2):**
- [ ] Combine two different patterns in one artwork
- [ ] Create patterns that change size or color gradually
- [ ] Make a pattern that represents your personality

### **Advanced (If you're feeling creative!):**
- [ ] Create different patterns for different moods/seasons
- [ ] Make interactive patterns (different each time you run it)
- [ ] Design patterns inspired by your favorite things (music, nature, etc.)

## **🌟 PATTERN IDEAS TO EXPLORE**

### **What happens if you...?**
1. **Change the magic number:** In `pen.right(91)`, try 89, 90, 92, 121, 144
2. **Mix shapes:** Use both circles and polygons in the same pattern
3. **Layer patterns:** Draw one pattern, then draw another on top with different colors
4. **Break the rules:** What if not every repetition is exactly the same?

### **Instagram Aesthetics to Try:**
- **Minimalist:** Few colors, clean lines, lots of white space
- **Maximalist:** Many colors, complex patterns, fill the whole screen
- **Pastel Dreams:** Soft colors, gentle curves, dreamy feeling
- **Bold & Graphic:** High contrast, geometric shapes, striking patterns

## **🔧 DEBUGGING HELPERS**

**"My pattern looks boring"**
- Try changing the angle by just 1 degree (89 instead of 90)
- Mix different sizes in the same pattern
- Use more contrasting colors

**"Pattern is too messy"**
- Reduce the number in your `range()`
- Use fewer colors (2-3 instead of 5-6)
- Make shapes smaller

**"Nothing shows up"**
- Check that your numbers aren't too big (try smaller forward/circle sizes)
- Make sure you have `pen.pendown()` if you used `pen.penup()`

## **📱 INSTAGRAM SUCCESS TIPS**
- Square images (800x800) work best for Instagram
- High contrast between background and pattern colors
- Patterns with repetition look professional
- Don't be afraid of negative space (empty areas)

## **✨ MAKE IT YOURS**

### **Personal Pattern Inspiration:**
- What patterns do you see in your daily life? (tiles, fabric, nature)
- What colors make you happy?
- How would you represent your favorite season/holiday/mood as a pattern?
- What shapes feel like "you"?

### **Challenge Questions:**
- Can you create a pattern that changes based on the time of day?
- What would your favorite song look like as a geometric pattern?
- How would you make the same pattern feel happy vs. sad vs. energetic?

**Remember:** The best patterns come from experimenting! Don't be afraid to break things and try again! 🌟