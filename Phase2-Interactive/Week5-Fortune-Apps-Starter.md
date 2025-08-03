# 🔮 Week 5: Magic 8-Ball & Fortune Apps - Building Blocks

## **🚀 SETUP (Copy this first)**
```python
import random
import time
from datetime import datetime
```

## **🧱 BUILDING BLOCK 1: Lists of Responses**
```python
# Create your own response lists!
magic_8_responses = [
    "Yes, definitely!",
    "Ask again later",
    "My sources say no",
    "____",  # Add your own responses
    "____",
    "____"
]

# Different personality responses - fill these in!
sassy_responses = [
    "Obviously yes! 💅",
    "That's a hard no",
    "____",  # What would a sassy 8-ball say?
    "____",
    "____"
]

funny_responses = [
    "Yes, but first... did you eat today?",
    "____",  # Add your own funny responses
    "____",
    "____"
]
```

## **🎲 BUILDING BLOCK 2: Getting Random Responses**
```python
# Pick a random item from a list
answer = random.choice(magic_8_responses)
print(answer)

# Add dramatic pause for effect
print("🔮 The magic 8-ball is thinking...")
time.sleep(___)  # Try: 1, 2, 3 seconds
print(f"🎱 {answer}")
```

## **🔄 BUILDING BLOCK 3: Loops for Repeated Questions**
```python
while True:
    question = input("Ask me anything (or 'quit' to exit): ")
    
    if question.lower() == 'quit':
        print("Thanks for playing!")
        break
    
    if question.strip() == "":  # Check for empty questions
        print("You need to ask a question!")
        continue
    
    # YOUR CODE HERE: pick random answer and display it
    
```

## **🎯 YOUR CHALLENGE: Build Your Personal Fortune Teller**

### **Template 1: Magic 8-Ball with Personality**
```python
import random
import time

# YOUR personality types - fill in the responses:
personality_responses = {
    "wise": [
        "The path will reveal itself in time",
        "____",  # Add 4 more wise responses
        "____",
        "____",
        "____"
    ],
    "sassy": [
        "Uh, obviously yes! 💅",
        "____",  # Add 4 more sassy responses
        "____", 
        "____",
        "____"
    ],
    "encouraging": [
        "You've got this! 💪",
        "____",  # Add 4 more encouraging responses
        "____",
        "____", 
        "____"
    ]
}

# Let user choose personality
print("Choose your 8-ball's personality:")
print("1. 🧙‍♀️ Wise")
print("2. 💅 Sassy") 
print("3. 🌟 Encouraging")

choice = input("Choose (1-3): ")

# YOUR CODE: Set the responses based on choice
if choice == "1":
    responses = personality_responses["wise"]
elif choice == "____":  # Fill in
    responses = ____
else:
    responses = ____

# Main game loop
while True:
    question = input("\nWhat's your question? (or 'quit'): ")
    
    if question.lower() == 'quit':
        break
    
    # YOUR CODE: Add dramatic pause and give random answer
    
```

## **🌟 BUILDING BLOCK 4: Creating Horoscopes**
```python
# Lists for generating random horoscopes
moods = ["energetic", "peaceful", "creative", "____", "____"]  # Add 2 more
activities = ["try something new", "call a friend", "____", "____"]  # Add 2 more
colors = ["purple", "blue", "____", "____"]  # Add 2 more
advice = [
    "Trust your instincts today",
    "____",  # Add your own advice
    "____",
    "____"
]

# Generate random horoscope
today_mood = random.choice(moods)
today_activity = random.choice(activities) 
today_color = random.choice(colors)
today_advice = random.choice(advice)

print(f"💫 Today's Mood: {today_mood}")
print(f"🎯 Recommended Activity: {today_activity}")
# Add more horoscope elements...
```

## **💕 BUILDING BLOCK 5: Compatibility Calculator**
```python
def calculate_compatibility(name1, name2):
    # Simple method: use name lengths to generate consistent score
    score = ((len(name1) + len(name2)) * 7) % 100
    
    # Make sure score isn't too low (for fun!)
    if score < 50:
        score += 50
    
    return score

# Use it:
your_name = input("Enter your name: ")
crush_name = input("Enter your crush's name: ")

compatibility = calculate_compatibility(your_name, crush_name)
print(f"💖 Compatibility: {compatibility}%")

# YOUR CODE: Add different messages based on score
if compatibility >= ___:  # High compatibility
    print("____")  # What message for high compatibility?
elif compatibility >= ___:  # Medium compatibility  
    print("____")  # What message for medium compatibility?
else:
    print("____")  # What message for low compatibility?
```

## **🎨 CREATIVE CHALLENGES**

### **Beginner (Pick 2-3):**
- [ ] Create a Magic 8-Ball with 3 different personalities
- [ ] Make a daily horoscope generator with at least 5 categories
- [ ] Build a simple compatibility calculator

### **Intermediate (Try 1-2):**
- [ ] Create themed fortune tellers (Harry Potter, Disney, etc.)
- [ ] Make a "What Should I Watch?" recommendation engine
- [ ] Add special predictions for holidays/seasons

### **Advanced (If you're feeling creative!):**
- [ ] Create a fortune journal that saves predictions with dates
- [ ] Make predictions based on current day/time
- [ ] Build a complete "Life Advisor" combining multiple tools

## **💡 BUILDING BLOCK 6: Advanced Features**

### **Date-Based Elements**
```python
from datetime import datetime

today = datetime.now()
day_of_week = today.weekday()  # 0=Monday, 6=Sunday

# Different predictions for different days
weekly_vibes = {
    0: "Motivational Monday energy",
    1: "Thoughtful Tuesday vibes", 
    # Fill in the rest of the week...
}

print(f"Today's special vibe: {weekly_vibes[day_of_week]}")
```

### **User Input Validation**
```python
def get_valid_input(prompt, valid_options):
    while True:
        choice = input(prompt).lower().strip()
        if choice in valid_options:
            return choice
        print(f"Please choose from: {valid_options}")

# Use it:
mood = get_valid_input("How are you feeling? (happy/sad/excited): ", ["happy", "sad", "excited"])
```

### **Personalized Responses**
```python
# Ask about user preferences and customize responses
favorite_color = input("What's your favorite color? ")
hobby = input("What's your favorite hobby? ")

personalized_advice = [
    f"Wear something {favorite_color} today for good luck!",
    f"Spend some time doing {hobby} this week",
    "____"  # Add more personalized advice using their answers
]
```

## **🌈 THEME IDEAS**

### **Seasonal Themes:**
- **Spring:** Growth, new beginnings, flower-themed responses
- **Summer:** Adventure, fun, bright energy
- **Fall:** Cozy vibes, reflection, warm colors
- **Winter:** Rest, planning, sparkly magic

### **Pop Culture Themes:**
- **Disney Princess:** What would each princess advise?
- **Hogwarts Houses:** Responses matching Gryffindor, Slytherin, etc.
- **K-pop Vibes:** Energetic, encouraging, trend-focused
- **Aesthetic Themes:** Dark academia, cottagecore, etc.

## **🎯 PERSONALIZATION IDEAS**

### **Make It About YOU:**
- What kind of advice do YOU like to hear?
- What are YOUR favorite ways to make decisions?
- How would YOUR best friend give advice?
- What are YOUR favorite quotes or sayings?

### **For Your Friends:**
- Create versions with inside jokes
- Add responses that reference shared memories
- Make themed versions for different friend groups
- Include references to things you all love

## **🔧 DEBUGGING HELPERS**

**"Program keeps running forever"**
- Make sure your `while` loop has a way to `break`
- Check that you're comparing strings correctly (`==` not `=`)

**"Random choices seem repetitive"**
- Make sure your lists have enough variety (at least 5-8 items)
- Use `random.choice()` not `random.randint()` for text lists

**"Input doesn't work as expected"**
- Use `.lower()` and `.strip()` to handle different ways people type
- Check for empty inputs with `if not input_text:`

## **✨ MAKE IT YOURS**

### **Questions to Consider:**
- What kind of personality should YOUR fortune teller have?
- What advice do you wish you could get every day?
- How would you want a fortune teller to talk to you?
- What questions do you and your friends actually wonder about?

### **Personal Touch Ideas:**
- Add your name as the "fortune teller"
- Include references to your school, town, or interests
- Create seasonal versions that change throughout the year
- Make it funny in YOUR way

**Remember:** The best fortune tellers reflect the personality of their creator. Make yours uniquely YOU! 🌟