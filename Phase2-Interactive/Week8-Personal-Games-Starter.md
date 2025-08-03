# 🎮 Week 8: Games That Reflect You - Building Blocks

## **🚀 SETUP (Copy this first)**
```python
import random
from datetime import datetime
```

## **🤔 BUILDING BLOCK 1: Choice-Based Games**
```python
# Create lists of choices for "This or That" games
choice_categories = {
    "food": [
        ("Pizza", "Burgers"), ("Sweet", "Salty"), ("____", "____"),  # Add your own food choices
    ],
    "entertainment": [
        ("Movies", "TV Shows"), ("____", "____"), ("____", "____"),  # Add entertainment choices
    ],
    "lifestyle": [
        ("Morning person", "Night owl"), ("____", "____"), ("____", "____"),  # Add lifestyle choices
    ]
}

# Use them in a game
category = "food"  # Try: "entertainment", "lifestyle"
choices = random.choice(choice_categories[category])

print(f"This or That: {choices[0]} or {choices[1]}?")
user_choice = input("Choose A or B: ").upper()

if user_choice == 'A':
    print(f"You chose: {choices[0]}")
else:
    print(f"You chose: {choices[1]}")
```

## **🧠 BUILDING BLOCK 2: Trivia Questions**
```python
# Create trivia about YOUR interests
my_trivia = {
    "music": [
        {"question": "What's your favorite music genre?", "options": ["Pop", "Rock", "Hip-hop"], "answer": 0},
        {"question": "____", "options": ["____", "____", "____"], "answer": ___},  # Add your music question
    ],
    "movies": [
        {"question": "____", "options": ["____", "____", "____"], "answer": ___},  # Add movie question
        {"question": "____", "options": ["____", "____", "____"], "answer": ___},  # Add another
    ]
}

def ask_trivia_question(category):
    questions = my_trivia[category]
    q = random.choice(questions)
    
    print(f"🎯 {q['question']}")
    for i, option in enumerate(q['options']):
        print(f"{i+1}. {option}")
    
    answer = int(input("Your answer (1-3): ")) - 1
    
    if answer == q['answer']:
        print("✅ Correct!")
    else:
        print(f"❌ Wrong! The answer was: {q['options'][q['answer']]}")

# Use it:
ask_trivia_question("music")
```

## **💫 BUILDING BLOCK 3: Personality Analysis**
```python
def analyze_personality(choices):
    """Analyze personality based on user choices"""
    
    # Count certain types of choices
    creative_words = ["art", "music", "creative", "books"]
    social_words = ["friends", "group", "party", "social"]
    active_words = ["sports", "outdoor", "exercise", "adventure"]
    
    choice_text = " ".join(choices).lower()
    
    # YOUR LOGIC: How do you determine personality from choices?
    if any(word in choice_text for word in creative_words):
        personality = "🎨 The Creative"
        description = "____"  # Describe creative personality
    elif any(word in choice_text for word in social_words):
        personality = "👥 The Social Butterfly" 
        description = "____"  # Describe social personality
    elif any(word in choice_text for word in active_words):
        personality = "🏃‍♀️ The Adventurer"
        description = "____"  # Describe adventurous personality
    else:
        personality = "🌟 The Balanced One"
        description = "____"  # Describe balanced personality
    
    return {"type": personality, "description": description}

# Test it:
test_choices = ["art", "friends", "pizza"]
result = analyze_personality(test_choices)
print(f"You are: {result['type']}")
print(f"Description: {result['description']}")
```

## **🎯 YOUR CHALLENGE: Build Your Personal Game**

### **Template 1: This or That - Personal Edition**
```python
import random

def my_this_or_that_game():
    print("🤔 This or That - All About You!")
    
    # YOUR PERSONAL CHOICES - fill these with things YOU care about:
    my_choices = {
        "interests": [
            ("____", "____"),  # Your interest choice 1
            ("____", "____"),  # Your interest choice 2
            ("____", "____"),  # Your interest choice 3
        ],
        "preferences": [
            ("____", "____"),  # Your preference choice 1
            ("____", "____"),  # Your preference choice 2  
            ("____", "____"),  # Your preference choice 3
        ],
        "fun": [
            ("____", "____"),  # Your fun choice 1
            ("____", "____"),  # Your fun choice 2
            ("____", "____"),  # Your fun choice 3
        ]
    }
    
    user_answers = []
    
    # Play through categories
    for category, choices in my_choices.items():
        print(f"\n--- {category.title()} ---")
        
        for choice_pair in choices:
            print(f"\n{choice_pair[0]} or {choice_pair[1]}?")
            answer = input("Choose A or B: ").upper()
            
            if answer == 'A':
                user_answers.append(choice_pair[0])
            else:
                user_answers.append(choice_pair[1])
    
    # YOUR CODE: Analyze the answers
    print(f"\n✨ Your choices reveal...")
    # How will you analyze their personality based on their answers?

my_this_or_that_game()
```

### **Template 2: Personal Trivia Quiz**
```python
def create_personal_trivia():
    print("🧠 Trivia About Your Interests!")
    
    # YOUR TRIVIA QUESTIONS - make them about things you love:
    my_questions = [
        {
            "question": "____",  # Question about your favorite topic
            "options": ["____", "____", "____", "____"],  # 4 options
            "correct": ___,  # Index of correct answer (0-3)
            "explanation": "____"  # Fun fact or explanation
        },
        {
            "question": "____",  # Another question
            "options": ["____", "____", "____", "____"],
            "correct": ___,
            "explanation": "____"
        },
        # Add 3 more questions...
    ]
    
    score = 0
    
    for i, q in enumerate(my_questions, 1):
        print(f"\nQuestion {i}: {q['question']}")
        
        for j, option in enumerate(q['options']):
            print(f"{j+1}. {option}")
        
        try:
            answer = int(input("Your answer (1-4): ")) - 1
            
            if answer == q['correct']:
                print("✅ Correct!")
                print(f"💡 {q['explanation']}")
                score += 1
            else:
                print(f"❌ Wrong! The answer was: {q['options'][q['correct']]}")
                print(f"💡 {q['explanation']}")
                
        except (ValueError, IndexError):
            print("❌ Invalid answer!")
    
    print(f"\n🎉 Final Score: {score}/{len(my_questions)}")
    
    # YOUR CODE: Add score-based messages
    if score == len(my_questions):
        print("____")  # Perfect score message
    elif score >= len(my_questions) * 0.7:
        print("____")  # Good score message  
    else:
        print("____")  # Encouraging message

create_personal_trivia()
```

## **🎨 CREATIVE CHALLENGES**

### **Beginner (Pick 2-3):**
- [ ] Create a "This or That" game with 10 choices about your interests
- [ ] Make a simple personality quiz with 5 questions
- [ ] Build a trivia game about your favorite topic

### **Intermediate (Try 1-2):**
- [ ] Create games that give different results each time
- [ ] Make personality analyzers that combine multiple factors
- [ ] Build themed games (seasonal, holiday, mood-based)

### **Advanced (If you're having fun!):**
- [ ] Create games that "learn" and ask better questions based on previous answers
- [ ] Make multiplayer versions you can play with friends
- [ ] Build a "game suite" with multiple mini-games

## **🌟 BUILDING BLOCK 4: Memory & Preferences**
```python
# Simple way to remember user preferences across games
user_profile = {
    "name": "",
    "favorite_color": "",
    "interests": [],
    "personality_type": "",
    "game_scores": {}
}

def update_profile(key, value):
    user_profile[key] = value
    print(f"📝 Remembered: {key} = {value}")

def get_personalized_greeting():
    if user_profile["name"]:
        return f"Welcome back, {user_profile['name']}! 👋"
    else:
        name = input("What's your name? ")
        update_profile("name", name)
        return f"Nice to meet you, {name}! 🌟"

# Use it:
print(get_personalized_greeting())
```

## **🎲 BUILDING BLOCK 5: Random Events & Surprises**
```python
# Add unexpected elements to make games more fun
surprise_events = [
    "🎁 Bonus question worth double points!",
    "🌟 You get a free correct answer!",
    "🎭 Next question is about a random topic!",
    "____",  # Add your own surprise event
    "____",  # Add another surprise
]

def maybe_trigger_surprise():
    if random.randint(1, 10) <= 3:  # 30% chance
        event = random.choice(surprise_events)
        print(f"\n✨ SURPRISE! {event}")
        return True
    return False

# Use in your games:
if maybe_trigger_surprise():
    # Handle the surprise event
    pass
```

## **💡 PERSONALIZATION IDEAS**

### **Make Games About YOUR Life:**
- What topics do YOU know a lot about?
- What choices represent YOUR real dilemmas?
- What would YOUR friends find fun to answer?
- What personality traits do YOU find interesting?

### **Seasonal & Themed Versions:**
- **Holiday Games:** Christmas preferences, Halloween choices
- **Seasonal Games:** Summer vs winter activities, spring vs fall vibes  
- **School Games:** Subject preferences, study style choices
- **Friend Games:** Inside jokes, shared memories

### **Different Difficulty Levels:**
- **Easy:** Basic preferences, obvious choices
- **Medium:** Requires some thought, multiple factors
- **Hard:** Complex scenarios, philosophical questions

## **🎯 GAME IDEAS TO EXPLORE**

### **"Would You Rather" Scenarios:**
```python
scenarios = [
    ("Have the ability to fly", "Have the ability to be invisible"),
    ("____", "____"),  # Add your scenarios
    ("____", "____"),
]
```

### **"Perfect Day" Builder:**
```python
day_elements = {
    "morning": ["____", "____", "____"],    # Morning activity options
    "afternoon": ["____", "____", "____"],  # Afternoon options
    "evening": ["____", "____", "____"],    # Evening options
}
```

### **"Life Priorities" Sorter:**
```python
priorities = ["friends", "family", "career", "hobbies", "travel", "____"]  # Add more
# Ask user to rank them in order of importance
```

## **🔧 DEBUGGING HELPERS**

**"Index out of range" errors**
- Check that your answer indices match list lengths
- Use `try/except` for user input validation

**"Games feel repetitive"**
- Add more variety to your question/choice lists
- Include random elements and surprises

**"User input issues"**
- Use `.upper()` and `.strip()` for consistent input handling
- Provide clear instructions for expected input format

## **✨ MAKE IT YOURS**

### **Reflection Questions:**
- What aspects of personality are YOU most curious about?
- What topics could you create 20+ questions about?
- What would make a game feel authentically "you"?
- How do YOU like to learn about yourself and others?

### **Personal Touch Ideas:**
- Include references to your school, hometown, or culture
- Add inside jokes or family references
- Create questions about your actual friend group
- Make games that reflect your sense of humor

### **For Your Friends:**
- Create "How well do you know [your name]?" quizzes
- Make group games for parties or sleepovers
- Build games that help friends learn about each other
- Design icebreaker games for new friend groups

**Remember:** The best personality games are the ones that actually help you understand yourself and others better! Make yours meaningful and fun! 🌟