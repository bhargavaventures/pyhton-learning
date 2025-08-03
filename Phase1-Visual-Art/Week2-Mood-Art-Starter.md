# 🌈 Week 2: Mood Art Generator - Building Blocks

## **🚀 SETUP (Copy this to start every project)**
```python
import turtle
import random

screen = turtle.Screen()
screen.bgcolor("black")  # Try: "white", "navy", "deep purple"
screen.setup(800, 600)
pen = turtle.Turtle()
pen.speed(0)
```

## **🎨 BUILDING BLOCK 1: Mood Colors**
```python
# Create your own color palettes!
happy_colors = ["#FFD700", "#FF69B4", "#00CED1"]  # Add 2 more colors you love
sad_colors = ["#4169E1", "#6495ED", "#B0C4DE"]    # What colors feel sad to you?
angry_colors = ["#FF0000", "#DC143C", "#B22222"]  # Add your angry colors
calm_colors = ["____", "____", "____"]            # Fill in calming colors

# Use them like this:
pen.color(random.choice(happy_colors))
```

## **🧱 BUILDING BLOCK 2: Getting User Input**
```python
# Ask questions and store answers
mood = input("How are you feeling? ").lower()
name = input("What's your name? ")

# Use the answers in your code
print(f"Hi {name}! Let's create {mood} art!")
```

## **🔀 BUILDING BLOCK 3: Making Decisions**
```python
# Choose colors based on mood
if mood == "happy":
    colors = happy_colors
elif mood == "sad":
    colors = sad_colors
else:
    colors = ["white", "gray"]  # Default colors

# Now use: pen.color(random.choice(colors))
```

## **🎯 BUILDING BLOCK 4: Art Patterns**

### **Random Circles (Good for happy/bubbly moods)**
```python
for i in range(___):  # How many circles?
    pen.penup()
    pen.goto(random.randint(-300, 300), random.randint(-200, 200))
    pen.pendown()
    pen.circle(random.randint(10, 50))  # Try different size ranges
```

### **Falling Lines (Good for sad/rain moods)**
```python
for i in range(___):  # How many lines?
    pen.penup()
    pen.goto(random.randint(-400, 400), random.randint(100, 300))
    pen.pendown()
    pen.right(90)
    pen.forward(random.randint(50, 150))  # Try different lengths
    pen.left(90)  # Reset direction
```

### **Jagged Lines (Good for angry/energetic moods)**
```python
for i in range(___):  # How many jagged shapes?
    pen.penup()
    pen.goto(random.randint(-300, 300), random.randint(-200, 200))
    pen.pendown()
    for j in range(5):  # Number of jagged edges
        pen.forward(random.randint(20, 60))
        pen.right(random.randint(30, 150))  # Sharp angles
```

## **🎨 YOUR CHALLENGE: Build a Mood Art Generator**

### **Template to Fill In:**
```python
import turtle
import random

# Setup
screen = turtle.Screen()
screen.bgcolor("____")  # What background matches your style?
screen.setup(800, 600)
pen = turtle.Turtle()
pen.speed(0)
pen.pensize(___)  # How thick should the lines be?

# YOUR color palettes (fill in at least 3 colors each):
happy_colors = ["____", "____", "____"]
sad_colors = ["____", "____", "____"]
excited_colors = ["____", "____", "____"]

# Get user's mood
mood = input("____")  # What question will you ask?

# Choose colors (fill in the logic):
if mood == "____":
    colors = happy_colors
elif mood == "____":
    colors = sad_colors
# Add more mood options!

# Create art based on mood
for i in range(___):  # How many shapes?
    pen.color(random.choice(colors))
    # YOUR ART CODE HERE
    # Choose one of the patterns above or create your own!

screen.exitonclick()
```

## **💡 EXPERIMENT IDEAS**

### **Mix and Match Patterns:**
1. **Circles + Lines:** What if happy moods get circles AND lines?
2. **Size Changes:** Make shapes bigger when mood is "intense"
3. **Color Gradients:** Start with light colors and get darker

### **Add Your Own Moods:**
```python
# What patterns would represent these?
creative_colors = ["____", "____", "____"]
sleepy_colors = ["____", "____", "____"]
confident_colors = ["____", "____", "____"]
```

## **🌟 BUILDING BLOCK 5: Advanced Patterns**

### **Waves (for calm/peaceful moods)**
```python
pen.penup()
pen.goto(-400, 0)
pen.pendown()
for i in range(___):  # How wavy?
    pen.forward(20)
    pen.right(___)    # Try 10, 15, 30
    pen.forward(20)
    pen.left(___)     # Try 20, 30, 60
```

### **Spirals (for dreamy/mystical moods)**
```python
for i in range(___):  # How many spirals?
    pen.forward(i * 2)  # Gets bigger each time
    pen.right(___)      # Try 89, 90, 91, 121
```

## **🎵 MUSIC-INSPIRED CHALLENGE**
*What if art matched your favorite songs?*

```python
# Ask about music mood instead of personal mood
music_type = input("What music matches your mood? (pop/rock/classical/electronic): ")

# Create different patterns for each music type:
if music_type == "electronic":
    # What shapes feel electronic? (Hint: try geometric patterns)
    pass  # Replace with your code
elif music_type == "classical":
    # What shapes feel classical? (Hint: try flowing, organic patterns)
    pass  # Replace with your code
# Add more music types!
```

## **🎯 THIS WEEK'S CHALLENGES**

### **Beginner (Pick 2-3):**
- [ ] Make a basic mood detector with 3 moods and 3 color palettes
- [ ] Try all the different art patterns with your colors
- [ ] Add your name to the corner of your artwork

### **Intermediate (Try 1-2):**
- [ ] Create 5 different moods with unique patterns for each
- [ ] Make patterns that get bigger/smaller based on mood intensity
- [ ] Add music-based art generation

### **Advanced (If you're on a roll!):**
- [ ] Save different artworks with today's date in the filename
- [ ] Create a "mood calendar" - different art for each day
- [ ] Mix multiple moods in one artwork

## **🔧 DEBUGGING HINTS**

**"Colors aren't showing up"**
- Make sure color names are in quotes: `"red"` not `red`
- Check that your color lists have items: `["red", "blue"]` not `[]`

**"Nothing is drawn"**
- Make sure you have `pen.pendown()` after `pen.penup()` and `pen.goto()`
- Check that your `for` loop range isn't 0

**"Art looks messy"**
- Try reducing the number in your `range()` - fewer shapes can look cleaner
- Use fewer colors for a more cohesive look

## **✨ MAKE IT YOURS**

- What colors represent YOUR moods?
- What shapes match YOUR personality?
- How would YOU visualize different emotions?
- What questions would YOU ask to create personalized art?

**Remember:** There's no wrong way to express a mood through art! Experiment and have fun! 🎨