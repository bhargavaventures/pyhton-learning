# 🤖 Week 6: Personal Assistant Programs - Building Blocks

## **🚀 SETUP (Copy this first)**
```python
import random
import string
from datetime import datetime, timedelta
```

## **🔐 BUILDING BLOCK 1: Password Generation**
```python
# Character sets for passwords
letters = string.ascii_letters  # a-z, A-Z
numbers = string.digits         # 0-9
symbols = "!@#$%&*"            # Easy to type symbols

# Combine them based on what you want
all_characters = letters + numbers + symbols

# Generate random password
password_length = ___  # Try: 8, 12, 16
password = ''.join(random.choice(all_characters) for _ in range(password_length))
print(f"Generated password: {password}")
```

## **📚 BUILDING BLOCK 2: Study Planning**
```python
# Get subjects from user
subjects = []
print("What subjects do you need to study?")
while True:
    subject = input("Subject (or press enter when done): ").strip()
    if subject == "":
        break
    subjects.append(subject)

# Calculate time per subject
total_hours = int(input("How many hours can you study? "))
time_per_subject = total_hours * 60 // len(subjects)  # Convert to minutes

print(f"📖 Study {time_per_subject} minutes per subject")
for i, subject in enumerate(subjects):
    print(f"{i+1}. {subject}")
```

## **👗 BUILDING BLOCK 3: Decision Making**
```python
# Weather-based choices
weather_outfits = {
    "sunny": ["shorts", "t-shirt", "sandals"],
    "rainy": ["jeans", "jacket", "boots"], 
    "cold": ["____", "____", "____"],  # Fill in cold weather clothes
    "mild": ["____", "____", "____"]   # Fill in mild weather clothes
}

weather = input("What's the weather? (sunny/rainy/cold/mild): ").lower()
outfit_options = weather_outfits.get(weather, ["casual outfit"])

print(f"Perfect for {weather} weather:")
for item in outfit_options:
    print(f"• {item}")
```

## **🎵 BUILDING BLOCK 4: Mood-Based Recommendations**
```python
# Create your own mood-based recommendations
mood_playlists = {
    "happy": ["upbeat pop", "feel-good classics", "____", "____"],  # Add 2 more
    "sad": ["emotional ballads", "comfort songs", "____", "____"],   # Add 2 more
    "energetic": ["workout beats", "pump-up songs", "____", "____"], # Add 2 more
    "chill": ["____", "____", "____", "____"]  # Fill in all 4 chill song types
}

current_mood = input("What's your mood? (happy/sad/energetic/chill): ")
playlist = mood_playlists.get(current_mood, ["general music"])

print(f"🎵 Perfect playlist for {current_mood} mood:")
for song_type in playlist:
    print(f"♪ {song_type}")
```

## **🎯 YOUR CHALLENGE: Build Your Personal Assistant**

### **Template 1: Smart Password Generator**
```python
import random
import string

def create_password():
    print("🔐 Smart Password Generator")
    
    # Get user preferences
    purpose = input("What's this password for? ")
    length = int(input("How long? (8-16): "))
    
    # Build character set based on preferences
    characters = string.ascii_letters  # Always include letters
    
    include_numbers = input("Include numbers? (y/n): ").lower() == 'y'
    if include_numbers:
        characters += ____  # What should you add?
    
    include_symbols = input("Include symbols? (y/n): ").lower() == 'y' 
    if include_symbols:
        characters += ____  # What should you add?
    
    # Generate password
    password = ''.join(random.choice(characters) for _ in range(length))
    
    print(f"📱 Password for {purpose}: {password}")
    
    # YOUR CODE: Add password strength rating
    # How would you rate password strength? What makes a password strong?

create_password()
```

### **Template 2: Study Helper**
```python
from datetime import datetime, timedelta

def study_planner():
    print("📚 Personal Study Helper")
    
    # Get current tasks - YOUR CODE
    subjects = []
    # How will you collect all the subjects?
    
    # Get time available - YOUR CODE
    total_time = ____  # How will you ask for available time?
    
    # Calculate schedule - YOUR CODE  
    time_per_subject = ____  # How do you divide time equally?
    
    print("⏰ Your study schedule:")
    current_time = datetime.now()
    
    for i, subject in enumerate(subjects):
        # YOUR CODE: Calculate start and end times for each subject
        # Hint: use timedelta(minutes=time_per_subject)
        
        print(f"{i+1}. {subject}: ___ to ___")  # Fill in times
        
        # Add study tips
        study_tips = [
            "📝 Take notes on main points",
            "____",  # Add your own study tips
            "____",
            "____"
        ]
        print(f"   💡 Tip: {random.choice(study_tips)}")

study_planner()
```

## **💡 BUILDING BLOCK 5: Solving Big Tasks**
```python
def break_down_task():
    big_task = input("What big task are you avoiding? ")
    time_available = int(input("How many minutes do you have? "))
    
    # YOUR CODE: How would you break this into smaller pieces?
    mini_tasks = []
    
    if "study" in big_task.lower():
        mini_tasks = [
            f"📖 Gather materials for {big_task}",
            "____",  # Add more study-related mini-tasks
            "____",
            "____"
        ]
    elif "clean" in big_task.lower():
        mini_tasks = [
            "🧹 Pick one small area to clean",
            "____",  # Add more cleaning-related mini-tasks  
            "____",
            "____"
        ]
    else:
        # Generic breakdown
        mini_tasks = [
            f"🎯 Define what '{big_task}' actually means",
            "____",  # Add generic mini-tasks
            "____",
            "____"
        ]
    
    print("✨ Your action plan:")
    for i, task in enumerate(mini_tasks, 1):
        print(f"{i}. {task}")

break_down_task()
```

## **🎨 CREATIVE CHALLENGES**

### **Beginner (Pick 2-3):**
- [ ] Make a password generator with different security levels
- [ ] Create a simple study scheduler for your real subjects
- [ ] Build a basic outfit picker based on weather

### **Intermediate (Try 1-2):**
- [ ] Create a "life dashboard" that combines multiple tools
- [ ] Make assistants with different personalities (organized vs creative)
- [ ] Add time-based recommendations (different for morning vs evening)

### **Advanced (If you're feeling ambitious!):**
- [ ] Create assistants for specific situations (school, weekends, study week)
- [ ] Add "learning" features that remember your preferences
- [ ] Build a procrastination-busting system with rewards

## **🌟 BUILDING BLOCK 6: Advanced Features**

### **Saving Preferences**
```python
# Simple way to remember user preferences
user_preferences = {
    "favorite_colors": [],
    "study_subjects": [],
    "style_preferences": {}
}

# Get preferences
fav_color = input("What's your favorite color? ")
user_preferences["favorite_colors"].append(fav_color)

# Use preferences later
if user_preferences["favorite_colors"]:
    print(f"Based on your love of {fav_color}, I recommend...")
```

### **Time-Based Recommendations**
```python
from datetime import datetime

current_hour = datetime.now().hour

if current_hour < 12:
    time_of_day = "morning"
elif current_hour < 17:
    time_of_day = "afternoon"  
else:
    time_of_day = "evening"

# YOUR CODE: How would different times affect recommendations?
morning_activities = ["____", "____", "____"]  # Fill in morning activities
evening_activities = ["____", "____", "____"]  # Fill in evening activities
```

### **Personality-Based Assistants**
```python
assistant_personalities = {
    "organized": {
        "greeting": "Let's get organized! 📋",
        "style": "structured and detailed"
    },
    "creative": {
        "greeting": "Time to get creative! 🎨", 
        "style": "flexible and inspiring"
    },
    "motivational": {
        "greeting": "You've got this! 💪",
        "style": "encouraging and energetic"
    }
}

# Let user choose assistant personality
print("Choose your assistant:")
for key, personality in assistant_personalities.items():
    print(f"- {key.title()}: {personality['style']}")

choice = input("Which assistant? ")
chosen_assistant = assistant_personalities.get(choice, assistant_personalities["organized"])
print(chosen_assistant["greeting"])
```

## **💭 PERSONALIZATION IDEAS**

### **Make It About YOUR Life:**
- What tasks do YOU actually need help with?
- What are YOUR biggest procrastination challenges?
- How do YOU like to organize your time?
- What motivates YOU to get things done?

### **For Your Real Needs:**
- Create a homework tracker for your actual classes
- Make a outfit picker with your actual clothes
- Build a study helper for your learning style
- Design a procrastination buster for your specific challenges

### **Different Versions:**
- **School Mode:** Focus on assignments, tests, study schedules
- **Weekend Mode:** Fun activities, creative projects, social plans
- **Stress Mode:** Calming activities, simplified tasks, self-care
- **Productive Mode:** Efficiency tips, time management, goal-setting

## **🔧 DEBUGGING HELPERS**

**"List is empty"**
- Make sure you're adding items to lists correctly: `list.append(item)`
- Check that your input collection loop has a way to stop

**"Time calculations are wrong"**
- Remember: 60 minutes = 1 hour
- Use `//` for integer division when dividing time

**"Input validation not working"**
- Use `.lower()` and `.strip()` to handle different input formats
- Provide default values for unexpected inputs

## **✨ MAKE IT YOURS**

### **Questions to Consider:**
- What kind of "assistant" would be most helpful to YOU?
- How do you prefer to receive advice or suggestions?
- What are your biggest daily challenges that could be automated?
- What would make you actually WANT to use these tools?

### **Personal Touch Ideas:**
- Add your own motivational quotes or phrases
- Include references to your hobbies and interests
- Create versions that match your personality
- Add features that solve YOUR specific problems

**Remember:** The best personal assistants are the ones that actually help with YOUR real life! Make tools you'd want to use every day! 🌟