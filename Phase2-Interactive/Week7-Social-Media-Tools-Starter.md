# 📱 Week 7: Social Media Tools - Building Blocks

## **🚀 SETUP (Copy this first)**
```python
import random
from datetime import datetime
```

## **📝 BUILDING BLOCK 1: Caption Creation**
```python
# Create lists of caption elements
photo_types = {
    "selfie": ["Feeling good", "Just me being me", "____", "____"],  # Add 2 more selfie captions
    "food": ["This looks too good to eat", "____", "____", "____"],   # Add 3 more food captions  
    "friends": ["Squad goals", "____", "____", "____"],              # Add 3 more friend captions
    "nature": ["____", "____", "____", "____"]                       # Add 4 nature captions
}

vibes = {
    "happy": ["✨", "💫", "🌟", "😊"],
    "chill": ["😎", "🌿", "☁️", "💙"], 
    "confident": ["💪", "🔥", "👑", "💯"],
    "dreamy": ["____", "____", "____", "____"]  # Add 4 dreamy vibes
}

# Use them together
photo_type = "selfie"  # Try: "food", "friends", "nature"
mood = "happy"         # Try: "chill", "confident", "dreamy"

caption = random.choice(photo_types[photo_type])
emoji = random.choice(vibes[mood])

print(f'"{caption} {emoji}"')
```

## **#️⃣ BUILDING BLOCK 2: Hashtag Categories**
```python
# Build your own hashtag collections
category_hashtags = {
    "selfie": ["#selfie", "#me", "#portrait", "#____", "#____"],     # Add 2 more
    "food": ["#food", "#yum", "#delicious", "#____", "#____"],      # Add 2 more
    "style": ["#ootd", "#fashion", "#style", "#____", "#____"],     # Add 2 more
    "study": ["____", "____", "____", "____", "____"]               # Add 5 study hashtags
}

mood_hashtags = {
    "aesthetic": ["#aesthetic", "#vibes", "#mood", "#____"],         # Add 1 more
    "motivational": ["#motivated", "#goals", "#hustle", "#____"],   # Add 1 more
    "fun": ["____", "____", "____", "____"]                         # Add 4 fun hashtags
}

# Combine categories
def create_hashtag_set(category, mood_type):
    main_tags = random.sample(category_hashtags[category], 3)
    mood_tags = random.sample(mood_hashtags[mood_type], 2)
    return main_tags + mood_tags

# Use it:
my_hashtags = create_hashtag_set("selfie", "aesthetic")
print(" ".join(my_hashtags))
```

## **⏰ BUILDING BLOCK 3: Timing Recommendations**
```python
# Best posting times (you can customize these!)
platform_times = {
    "instagram": {
        "weekdays": ["11:00 AM", "1:00 PM", "____", "____"],  # Add 2 more times
        "weekends": ["10:00 AM", "____", "____"]              # Add 2 more times
    },
    "tiktok": {
        "weekdays": ["____", "____", "____", "____"],         # Add 4 good TikTok times
        "weekends": ["____", "____", "____"]                  # Add 3 weekend times
    }
}

# Check if it's weekend
from datetime import datetime
today = datetime.now()
is_weekend = today.weekday() >= 5  # Saturday=5, Sunday=6

platform = "instagram"  # Try: "tiktok"
time_key = "weekends" if is_weekend else "weekdays"
recommended_times = platform_times[platform][time_key]

print(f"Best {platform} times today: {', '.join(recommended_times)}")
```

## **📛 BUILDING BLOCK 4: Username Generation**
```python
# Elements for creative usernames
style_elements = {
    "aesthetic": {
        "prefixes": ["soft", "dreamy", "ethereal", "____"],          # Add 1 more
        "suffixes": ["vibes", "dreams", "aura", "____"],             # Add 1 more
    },
    "cool": {
        "prefixes": ["____", "____", "____", "____"],                # Add 4 cool prefixes
        "suffixes": ["____", "____", "____", "____"],                # Add 4 cool suffixes
    },
    "creative": {
        "prefixes": ["artsy", "creative", "____", "____"],           # Add 2 more
        "suffixes": ["artist", "creator", "____", "____"],           # Add 2 more
    }
}

def generate_username(name, style, interests):
    elements = style_elements[style]
    
    # Method 1: Name + Interest + Style
    if interests:
        interest = random.choice(interests).replace(" ", "")
        suffix = random.choice(elements["suffixes"])
        return f"{name.lower()}_{interest}_{suffix}"
    
    # Method 2: Style + Name + Number
    prefix = random.choice(elements["prefixes"])
    number = random.randint(10, 99)
    return f"{prefix}_{name.lower()}{number}"

# Use it:
my_name = "____"  # Fill in your name
my_interests = ["art", "music"]  # Add your interests
username = generate_username(my_name, "aesthetic", my_interests)
print(f"Suggested username: {username}")
```

## **🎯 YOUR CHALLENGE: Build Your Social Media Toolkit**

### **Template 1: Personal Caption Generator**
```python
import random

def caption_creator():
    print("📝 Personal Caption Creator")
    
    # Get photo details
    print("What's your photo about?")
    print("1. Selfie")
    print("2. Food") 
    print("3. Friends")
    print("4. ____")  # Add your own category
    
    photo_choice = input("Choose (1-4): ")
    
    # YOUR CAPTION COLLECTIONS - fill these in with your style:
    my_captions = {
        "1": ["____", "____", "____"],  # Your selfie captions
        "2": ["____", "____", "____"],  # Your food captions
        "3": ["____", "____", "____"],  # Your friend captions
        "4": ["____", "____", "____"]   # Your custom category captions
    }
    
    # Get vibe
    print("What vibe?")
    print("1. 😊 Happy")
    print("2. 😎 Chill") 
    print("3. ✨ Dreamy")
    
    vibe_choice = input("Choose (1-3): ")
    
    # YOUR VIBE EMOJIS:
    my_emojis = {
        "1": ["____", "____", "____"],  # Happy emojis
        "2": ["____", "____", "____"],  # Chill emojis  
        "3": ["____", "____", "____"]   # Dreamy emojis
    }
    
    # Generate caption
    caption = random.choice(my_captions[photo_choice])
    emoji = random.choice(my_emojis[vibe_choice])
    
    print(f'✨ Your caption: "{caption} {emoji}"')

caption_creator()
```

### **Template 2: Smart Hashtag Helper**
```python
def hashtag_helper():
    print("#️⃣ Smart Hashtag Helper")
    
    # YOUR hashtag database - customize for your interests:
    my_hashtags = {
        "hobbies": {
            "art": ["____", "____", "____"],      # Art hashtags
            "music": ["____", "____", "____"],    # Music hashtags
            "books": ["____", "____", "____"],    # Book hashtags
            "sports": ["____", "____", "____"]    # Sports hashtags
        },
        "moods": {
            "motivated": ["____", "____", "____"], # Motivational hashtags
            "relaxed": ["____", "____", "____"],   # Chill hashtags
            "excited": ["____", "____", "____"]    # Excited hashtags
        }
    }
    
    # Get user choices
    print("What's your post about?")
    hobbies = list(my_hashtags["hobbies"].keys())
    for i, hobby in enumerate(hobbies, 1):
        print(f"{i}. {hobby.title()}")
    
    hobby_choice = int(input("Choose: ")) - 1
    chosen_hobby = hobbies[hobby_choice]
    
    print("What's your mood?")
    moods = list(my_hashtags["moods"].keys()) 
    for i, mood in enumerate(moods, 1):
        print(f"{i}. {mood.title()}")
    
    mood_choice = int(input("Choose: ")) - 1
    chosen_mood = moods[mood_choice]
    
    # Generate hashtag set
    hobby_tags = random.sample(my_hashtags["hobbies"][chosen_hobby], 2)
    mood_tags = random.sample(my_hashtags["moods"][chosen_mood], 2)
    
    all_tags = hobby_tags + mood_tags
    print(f"📋 Your hashtags: {' '.join(all_tags)}")

hashtag_helper()
```

## **🎨 CREATIVE CHALLENGES**

### **Beginner (Pick 2-3):**
- [ ] Create caption collections that match YOUR personality
- [ ] Build hashtag sets for your actual interests/hobbies
- [ ] Make a simple post timing advisor

### **Intermediate (Try 1-2):**
- [ ] Create themed caption generators (seasonal, holiday, mood-based)
- [ ] Build a complete "post planner" combining captions, hashtags, and timing
- [ ] Make aesthetic color palette generators for your feed theme

### **Advanced (If you're on a creative roll!):**
- [ ] Create different "voices" for different platforms (Instagram vs TikTok)
- [ ] Build analytics to track what types of posts you create most
- [ ] Make a "brand identity" toolkit for consistent posting

## **🌈 BUILDING BLOCK 5: Color Aesthetics**
```python
# Create color palettes for your feed theme
aesthetic_palettes = {
    "pastel_dreams": ["#FFB3BA", "#FFDFBA", "#FFFFBA", "#____"],  # Add 1 more pastel
    "dark_academia": ["#8B4513", "#2F4F4F", "#____", "____"],     # Add 2 more dark colors
    "neon_vibes": ["____", "____", "____", "____"],               # Add 4 neon colors
    "earth_tones": ["____", "____", "____", "____"]               # Add 4 earth colors
}

def suggest_colors(aesthetic):
    colors = aesthetic_palettes.get(aesthetic, ["#FFFFFF"])
    print(f"🎨 Your {aesthetic} palette:")
    for i, color in enumerate(colors, 1):
        print(f"{i}. {color}")

# Use it:
suggest_colors("pastel_dreams")
```

## **💡 PERSONALIZATION IDEAS**

### **Make It About YOUR Style:**
- What kind of captions do YOU actually write?
- What hashtags represent YOUR interests?
- What colors match YOUR aesthetic?
- What time do YOU usually post?

### **For Different Platforms:**
- **Instagram:** Longer captions, aesthetic hashtags, square photos
- **TikTok:** Short, catchy captions, trending hashtags, video content
- **Twitter:** Witty, concise, news-related hashtags

### **Seasonal Variations:**
- **Spring:** Growth, renewal, pastel colors, #springvibes
- **Summer:** Adventure, bright colors, vacation hashtags
- **Fall:** Cozy, warm tones, #fallvibes, #sweaterweather
- **Winter:** Sparkly, cool tones, holiday themes

## **📊 BUILDING BLOCK 6: Content Planning**
```python
from datetime import datetime, timedelta

def weekly_content_planner():
    content_types = ["selfie", "food", "outfit", "study", "friends"]
    
    print("📅 Your Week's Content Plan:")
    
    today = datetime.now()
    for i in range(7):
        day = today + timedelta(days=i)
        day_name = day.strftime("%A")
        
        # YOUR LOGIC: What content fits what day?
        if day_name == "Monday":
            suggested_content = "____"  # What content for Monday motivation?
        elif day_name == "Friday":
            suggested_content = "____"  # What content for Friday fun?
        # Add more days...
        else:
            suggested_content = random.choice(content_types)
        
        print(f"{day_name}: {suggested_content}")

weekly_content_planner()
```

## **🔧 DEBUGGING HELPERS**

**"List index out of range"**
- Check that your lists have enough items before sampling
- Use `len(list)` to check list length

**"Random choice from empty sequence"**
- Make sure your lists aren't empty
- Provide default values: `my_list or ["default"]`

**"Dictionary key error"**
- Use `.get()` method: `dict.get(key, default_value)`
- Check that your keys match exactly (case-sensitive)

## **✨ MAKE IT YOURS**

### **Questions to Consider:**
- What's YOUR authentic voice on social media?
- What topics do YOU actually post about?
- What hashtags represent YOUR real interests?
- What aesthetic matches YOUR personality?

### **Personal Brand Ideas:**
- Create tools that help maintain YOUR consistent style
- Build generators that sound like YOU wrote them
- Make planners that fit YOUR actual posting schedule
- Design color palettes that match YOUR real aesthetic

### **For Your Friends:**
- Create group hashtag collections for shared interests
- Make caption generators with inside jokes
- Build tools for coordinating group posts
- Design aesthetic guides for friend group themes

**Remember:** The best social media tools help you be more authentically YOU, not someone else! 📱✨