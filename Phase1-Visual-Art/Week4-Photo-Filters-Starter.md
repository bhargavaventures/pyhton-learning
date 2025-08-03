# 📸 Week 4: Photo Filter Creator - Building Blocks

## **🚀 SETUP (Copy this first)**
```python
from PIL import Image, ImageFilter, ImageEnhance
import os

# Make sure you create these folders:
# 1. "photos" folder - put your test photos here (.jpg or .png files)
# 2. "filtered_photos" folder - for saving your results
```

## **📁 BUILDING BLOCK 1: Loading & Displaying Photos**
```python
# Load a photo
img = Image.open("photos/your_photo.jpg")  # Change to your photo name
img.show()  # This opens the photo to see it

# Get photo info
print(f"Size: {img.size}")
print(f"Format: {img.format}")
```

## **🎨 BUILDING BLOCK 2: Basic Color Changes**
```python
# Convert to black and white
bw_img = img.convert("L")  # L = grayscale
bw_img.show()
bw_img.save("filtered_photos/bw_your_photo.jpg")

# Make it brighter or darker
from PIL import ImageEnhance
brightness = ImageEnhance.Brightness(img)
bright_img = brightness.enhance(___)  # Try: 0.5 (darker), 1.5 (brighter), 2.0 (very bright)
bright_img.show()
```

## **🌈 BUILDING BLOCK 3: Color Tinting**
```python
# Add color overlays (like Instagram filters!)
img_rgba = img.convert("RGBA")

# Create colored overlay - experiment with these colors:
pink_overlay = Image.new("RGBA", img.size, (255, 182, 193, ___))  # Try: 30, 60, 100
blue_overlay = Image.new("RGBA", img.size, (173, 216, 230, ___))  # Try different opacity numbers
# Make your own: (red, green, blue, opacity)
my_overlay = Image.new("RGBA", img.size, (___, ___, ___, ___))

# Apply the tint
tinted = Image.blend(img_rgba, pink_overlay, ___)  # Try: 0.2, 0.4, 0.6
tinted_rgb = tinted.convert("RGB")
tinted_rgb.show()
```

## **✨ BUILDING BLOCK 4: Instagram-Style Filters**

### **Vintage/Sepia Effect**
```python
def create_vintage_filter(image):
    # Reduce color saturation
    color_enhancer = ImageEnhance.Color(image)
    less_colorful = color_enhancer.enhance(___)  # Try: 0.3, 0.5, 0.7
    
    # Add sepia tint
    sepia_img = less_colorful.convert("RGBA")
    sepia_overlay = Image.new("RGBA", sepia_img.size, (___, ___, ___, ___))  # Try: (210, 180, 140, 80)
    vintage = Image.alpha_composite(sepia_img, sepia_overlay)
    
    return vintage.convert("RGB")

# Use it:
vintage_photo = create_vintage_filter(img)
vintage_photo.show()
```

### **Bright & Vibrant Filter**
```python
def create_vibrant_filter(image):
    # Increase brightness
    brightness = ImageEnhance.Brightness(image)
    bright = brightness.enhance(___)  # Try: 1.2, 1.3, 1.4
    
    # Increase contrast
    contrast = ImageEnhance.Contrast(bright)
    contrasted = contrast.enhance(___)  # Try: 1.1, 1.2, 1.3
    
    # Boost colors
    color = ImageEnhance.Color(contrasted)
    vibrant = color.enhance(___)  # Try: 1.3, 1.5, 1.7
    
    return vibrant

# Use it:
vibrant_photo = create_vibrant_filter(img)
vibrant_photo.show()
```

## **🎯 YOUR CHALLENGE: Build Your Own Filter**

### **Template: Custom Aesthetic Filter**
```python
from PIL import Image, ImageEnhance

def my_aesthetic_filter(image):
    # Step 1: Adjust brightness (darker/lighter?)
    brightness = ImageEnhance.Brightness(image)
    adjusted = brightness.enhance(___)  # Fill in your number
    
    # Step 2: Adjust contrast (more dramatic/softer?)
    contrast = ImageEnhance.Contrast(adjusted)
    contrasted = contrast.enhance(___)  # Fill in your number
    
    # Step 3: Color saturation (more colorful/less colorful?)
    color = ImageEnhance.Color(contrasted)
    colored = color.enhance(___)  # Fill in your number
    
    # Step 4: Add your signature color tint
    tinted_img = colored.convert("RGBA")
    my_tint = Image.new("RGBA", tinted_img.size, (___, ___, ___, ___))  # Your color + opacity
    final = Image.alpha_composite(tinted_img, my_tint)
    
    return final.convert("RGB")

# Test your filter:
my_photo = my_aesthetic_filter(img)
my_photo.show()
my_photo.save("filtered_photos/my_filter_photo.jpg")
```

## **💡 BUILDING BLOCK 5: Popular Aesthetics**

### **Dark Academia (Brown/Moody)**
```python
# What settings would create a dark, scholarly vibe?
brightness_level = ___  # Try: 0.8, 0.9 (darker)
brown_tint = (___, ___, ___, ___)  # Try: (101, 67, 33, 40)
```

### **Cottagecore (Soft/Peachy)**
```python
# What settings would create a soft, dreamy vibe?
blur_amount = ___  # Try: 1, 2 (subtle blur)
peach_tint = (___, ___, ___, ___)  # Try: (255, 218, 185, 30)
```

### **Y2K/Cyber (Bright/Neon)**
```python
# What settings would create a futuristic vibe?
contrast_level = ___  # Try: 1.4, 1.5 (high contrast)
cyan_tint = (___, ___, ___, ___)  # Try: (0, 255, 255, 25)
```

## **🔄 BUILDING BLOCK 6: Batch Processing**
```python
import os

def apply_my_filter_to_all():
    # Get all photos in the folder
    photo_files = [f for f in os.listdir("photos") if f.lower().endswith(('.png', '.jpg', '.jpeg'))]
    
    for photo_file in photo_files:
        print(f"Processing {photo_file}...")
        
        # Load photo
        img = Image.open(f"photos/{photo_file}")
        
        # Apply YOUR filter (use your function from above)
        filtered = my_aesthetic_filter(img)
        
        # Save with new name
        filtered.save(f"filtered_photos/filtered_{photo_file}")
    
    print("All photos processed!")

# Use it:
# apply_my_filter_to_all()
```

## **🎨 CREATIVE CHALLENGES**

### **Beginner (Pick 2-3):**
- [ ] Create a black & white filter with a single color tint
- [ ] Make a "vintage" filter using sepia tones
- [ ] Experiment with brightness/contrast to match your room's vibe

### **Intermediate (Try 1-2):**
- [ ] Create 3 different aesthetic filters (dark academia, cottagecore, cyberpunk)
- [ ] Make a filter that enhances specific colors (make blues bluer, pinks pinker)
- [ ] Create a "selfie enhancer" that makes photos look better

### **Advanced (If you're on a roll!):**
- [ ] Make filters that match different seasons/holidays
- [ ] Create a before/after comparison image
- [ ] Make filters that work better for different types of photos (portraits vs landscapes)

## **🔍 FILTER INSPIRATION IDEAS**

### **Mood-Based Filters:**
- **Happy:** Bright, saturated, warm tints
- **Dreamy:** Soft blur, pastel tints, high brightness
- **Dramatic:** High contrast, darker tones, bold colors
- **Vintage:** Reduced saturation, sepia/brown tints, slightly darker

### **Aesthetic Trends to Try:**
- **Film Photography:** Slightly desaturated, grain effect, vintage colors
- **Golden Hour:** Warm orange/yellow tints, soft glow
- **Minimalist:** Clean, bright, reduced colors
- **Moody:** Dark shadows, muted colors, high contrast

## **🧪 EXPERIMENTATION GUIDE**

### **Numbers to Try:**
- **Brightness:** 0.5 (dark), 0.8 (slightly dark), 1.2 (bright), 1.5 (very bright)
- **Contrast:** 0.8 (soft), 1.0 (normal), 1.3 (dramatic), 1.5 (very dramatic)
- **Saturation:** 0.3 (desaturated), 0.7 (muted), 1.3 (vibrant), 1.6 (very colorful)
- **Tint Opacity:** 20-40 (subtle), 50-70 (noticeable), 80+ (strong)

### **Color Combinations for Tints:**
- **Warm:** (255, 200, 150) - peachy/golden
- **Cool:** (150, 200, 255) - blue/icy
- **Vintage:** (210, 180, 140) - sepia/brown
- **Dreamy:** (255, 240, 255) - soft pink/white

## **🚨 DEBUGGING HELPERS**

**"Error: cannot identify image file"**
- Make sure your photo is .jpg, .jpeg, or .png
- Check that the filename matches exactly (case-sensitive!)

**"No module named 'PIL'"**
- Install Pillow: open command prompt, type `pip install Pillow`

**"My filter looks too extreme"**
- Try smaller numbers (1.1 instead of 1.5)
- Reduce tint opacity (30 instead of 80)

## **✨ MAKE IT YOURS**

### **Personal Questions:**
- What's your favorite Instagram filter? How could you recreate it?
- What colors represent your personality?
- How do you want your photos to feel? (dreamy, dramatic, vintage, futuristic?)
- What aesthetic matches your room/style?

### **Challenge Yourself:**
- Can you create a filter that makes any photo match your room's color scheme?
- What would a filter based on your favorite song look like?
- How would you make the same photo feel like different seasons?

**Remember:** The best filters enhance photos while keeping them looking natural. Experiment and find YOUR signature style! 📸✨