# 🎮 Week 9: Aesthetic Game Makeovers - Building Blocks

## **🚀 SETUP (Copy this first)**
```python
import pygame
import random
import sys

# Initialize Pygame
pygame.init()

# Screen setup - try different sizes!
SCREEN_WIDTH = 800
SCREEN_HEIGHT = 600
screen = pygame.display.set_mode((SCREEN_WIDTH, SCREEN_HEIGHT))
pygame.display.set_caption("____")  # What's your game called?

# Colors - customize these to match YOUR aesthetic!
BLACK = (0, 0, 0)
WHITE = (255, 255, 255)
AESTHETIC_COLOR_1 = (____, ____, ____)  # Your main color (R, G, B)
AESTHETIC_COLOR_2 = (____, ____, ____)  # Your accent color
AESTHETIC_COLOR_3 = (____, ____, ____)  # Your highlight color

# Game clock
clock = pygame.time.Clock()
```

## **🧱 BUILDING BLOCK 1: Game Loop Structure**
```python
def main_game_loop():
    running = True
    
    while running:
        # Handle events (clicks, key presses)
        for event in pygame.event.get():
            if event.type == pygame.QUIT:
                running = False
            # YOUR EVENT HANDLING HERE
            
        # Update game state
        # YOUR GAME LOGIC HERE
        
        # Draw everything
        screen.fill(______)  # What background color?
        # YOUR DRAWING CODE HERE
        
        pygame.display.flip()
        clock.tick(60)  # 60 FPS
    
    pygame.quit()
    sys.exit()
```

## **🎨 BUILDING BLOCK 2: Drawing Game Elements**
```python
def draw_game_board(board, theme="space"):
    """Draw a game board with different themes"""
    
    themes = {
        "space": {
            "bg_color": (25, 25, 112),      # Midnight blue
            "line_color": (255, 255, 255),   # White
            "accent": (138, 43, 226)         # Blue violet
        },
        "ocean": {
            "bg_color": (____, ____, ____),  # What ocean colors?
            "line_color": (____, ____, ____),
            "accent": (____, ____, ____)
        },
        "forest": {
            "bg_color": (____, ____, ____),  # What forest colors?
            "line_color": (____, ____, ____), 
            "accent": (____, ____, ____)
        },
        "your_theme": {  # Create your own theme!
            "bg_color": (____, ____, ____),
            "line_color": (____, ____, ____),
            "accent": (____, ____, ____)
        }
    }
    
    current_theme = themes.get(theme, themes["space"])
    
    # Fill background
    screen.fill(current_theme["bg_color"])
    
    # YOUR CODE: How do you want to draw the game board?
    # Try: pygame.draw.line(), pygame.draw.rect(), pygame.draw.circle()
```

## **🎯 BUILDING BLOCK 3: Player Input & Game Logic**
```python
def handle_player_move(mouse_pos, game_board):
    """Handle when player clicks to make a move"""
    
    mouse_x, mouse_y = mouse_pos
    
    # YOUR LOGIC: How do you convert mouse position to game position?
    # For tic-tac-toe: which cell did they click?
    # For snake: which direction should snake go?
    
    # Example for tic-tac-toe:
    cell_size = 200  # Adjust based on your game
    row = mouse_y // cell_size
    col = mouse_x // cell_size
    
    # YOUR VALIDATION: Is this move legal?
    if is_valid_move(row, col, game_board):
        # Make the move
        game_board[row][col] = "____"  # What represents player move?
        return True
    
    return False

def is_valid_move(row, col, board):
    """Check if a move is legal"""
    # YOUR LOGIC: What makes a move valid in your game?
    pass

def check_win_condition(board):
    """Check if someone won the game"""
    # YOUR LOGIC: How do you detect a win?
    # Hint: Check rows, columns, diagonals
    pass
```

## **🎵 BUILDING BLOCK 4: Sound & Visual Effects**
```python
# Load sounds (create these folders and add sound files!)
def load_game_sounds():
    sounds = {}
    try:
        sounds['move'] = pygame.mixer.Sound("sounds/____")      # Move sound file name
        sounds['win'] = pygame.mixer.Sound("sounds/____")       # Win sound file name
        sounds['click'] = pygame.mixer.Sound("sounds/____")     # Click sound file name
    except:
        print("Sound files not found - playing without sound")
        sounds = {}
    
    return sounds

def create_particle_effect(x, y, color):
    """Create visual effects when something happens"""
    particles = []
    
    for i in range(___):  # How many particles?
        particle = {
            'x': x + random.randint(-10, 10),
            'y': y + random.randint(-10, 10),
            'dx': random.randint(-3, 3),
            'dy': random.randint(-3, 3),
            'life': ___,  # How long should particles live?
            'color': color
        }
        particles.append(particle)
    
    return particles

def update_particles(particles):
    """Update and draw particle effects"""
    for particle in particles[:]:  # Copy list to modify while iterating
        # Update position
        particle['x'] += particle['dx']
        particle['y'] += particle['dy']
        particle['life'] -= 1
        
        # Draw particle
        if particle['life'] > 0:
            pygame.draw.circle(screen, particle['color'], 
                             (int(particle['x']), int(particle['y'])), 
                             max(1, particle['life'] // 10))
        else:
            particles.remove(particle)
```

## **🎯 YOUR CHALLENGE: Build Your Aesthetic Game**

### **Template 1: Aesthetic Tic-Tac-Toe**
```python
import pygame
import sys

# Setup (copy from Building Block 1)
pygame.init()
screen = pygame.display.set_mode((600, 600))
pygame.display.set_caption("____")  # Your game title

# YOUR THEME COLORS:
theme_colors = {
    "background": (____, ____, ____),
    "lines": (____, ____, ____),
    "player1": (____, ____, ____),
    "player2": (____, ____, ____),
    "accent": (____, ____, ____)
}

# Game state
board = [["" for _ in range(3)] for _ in range(3)]
current_player = "____"  # "X" or "O" or your symbols
game_over = False

def draw_board():
    screen.fill(theme_colors["background"])
    
    # Draw grid lines
    for i in range(1, 3):
        # Vertical lines
        pygame.draw.line(screen, theme_colors["lines"], 
                        (i * 200, 0), (i * 200, 600), ___)  # Line thickness?
        # Horizontal lines  
        pygame.draw.line(screen, theme_colors["lines"],
                        (0, i * 200), (600, i * 200), ___)
    
    # Draw X's and O's (or your custom symbols)
    for row in range(3):
        for col in range(3):
            if board[row][col] == "X":
                # YOUR CODE: How do you want to draw X?
                # Try: lines, circles, custom shapes, images
                pass
            elif board[row][col] == "O":
                # YOUR CODE: How do you want to draw O?
                pass

def handle_click(pos):
    global current_player, game_over
    
    if game_over:
        return
    
    # YOUR LOGIC: Convert click to board position
    mouse_x, mouse_y = pos
    col = ____  # Which column?
    row = ____  # Which row?
    
    # YOUR VALIDATION: Check if move is valid
    if board[row][col] == "":
        board[row][col] = current_player
        
        # Check for win
        if check_winner():
            game_over = True
            print(f"{current_player} wins!")
        
        # Switch players
        current_player = "O" if current_player == "X" else "X"

def check_winner():
    # YOUR LOGIC: How do you check for three in a row?
    # Check rows, columns, and diagonals
    pass

# Main game loop
clock = pygame.time.Clock()
running = True

while running:
    for event in pygame.event.get():
        if event.type == pygame.QUIT:
            running = False
        elif event.type == pygame.MOUSEBUTTONDOWN:
            handle_click(event.pos)
    
    draw_board()
    pygame.display.flip()
    clock.tick(60)

pygame.quit()
```

### **Template 2: Aesthetic Snake Game**
```python
import pygame
import random

# Setup
pygame.init()
screen = pygame.display.set_mode((800, 600))
pygame.display.set_caption("____")  # Your snake game title

# YOUR AESTHETIC:
SNAKE_COLOR = (____, ____, ____)
FOOD_COLOR = (____, ____, ____)  
BACKGROUND = (____, ____, ____)

# Game variables
snake = [(400, 300)]  # Starting position
direction = (20, 0)   # Moving right
food = (____, ____)   # Where should food start?

def draw_snake():
    for segment in snake:
        # YOUR STYLE: How do you want snake segments to look?
        pygame.draw.rect(screen, SNAKE_COLOR, (segment[0], segment[1], 20, 20))
        # Try: circles, rounded rectangles, custom shapes

def draw_food():
    # YOUR STYLE: How should food look?
    pygame.draw.rect(screen, FOOD_COLOR, (food[0], food[1], 20, 20))
    # Try: circles, hearts, stars, fruits

def move_snake():
    global snake, food
    
    # Move snake head
    head_x, head_y = snake[0]
    new_head = (head_x + direction[0], head_y + direction[1])
    
    # YOUR LOGIC: What happens when snake hits walls?
    # Option 1: Game over
    # Option 2: Wrap around screen
    # Option 3: Bounce off walls
    
    snake.insert(0, new_head)
    
    # Check if food eaten
    if new_head == food:
        # Snake grows! Don't remove tail
        food = (______, ______)  # Generate new food position
    else:
        # Remove tail
        snake.pop()

# Main game loop template
clock = pygame.time.Clock()
running = True

while running:
    for event in pygame.event.get():
        if event.type == pygame.QUIT:
            running = False
        elif event.type == pygame.KEYDOWN:
            # YOUR CONTROLS: What keys control the snake?
            if event.key == pygame.K_UP:
                direction = (0, -20)
            # Add more directions...
    
    move_snake()
    
    screen.fill(BACKGROUND)
    draw_snake()
    draw_food()
    
    pygame.display.flip()
    clock.tick(______)  # How fast should snake move?

pygame.quit()
```

## **🎨 CREATIVE CHALLENGES**

### **Beginner (Pick 2-3):**
- [ ] Choose a color theme and apply it to a classic game
- [ ] Add custom win/lose messages in your style
- [ ] Create different visual styles for game pieces (circles vs squares vs custom shapes)

### **Intermediate (Try 1-2):**
- [ ] Add sound effects for moves, wins, and game events
- [ ] Create multiple themes players can choose from
- [ ] Add particle effects when something exciting happens

### **Advanced (If you're feeling creative!):**
- [ ] Create completely new game mechanics or rules
- [ ] Build a two-player mode with custom controls
- [ ] Add animations and smooth transitions between game states

## **🌟 BUILDING BLOCK 5: Game Enhancement Ideas**

### **Visual Upgrades:**
```python
# Smooth animations
def animate_piece_placement(start_pos, end_pos, color):
    # YOUR CODE: How do you animate a piece moving into place?
    pass

# Custom fonts
def draw_text(text, size, color, pos):
    font = pygame.font.Font(None, size)
    text_surface = font.render(text, True, color)
    screen.blit(text_surface, pos)

# Background patterns
def draw_patterned_background():
    # YOUR CREATIVITY: Geometric patterns, gradients, textures?
    pass
```

### **Interaction Improvements:**
```python
def add_hover_effects():
    mouse_pos = pygame.mouse.get_pos()
    
    # YOUR CODE: What happens when mouse hovers over game elements?
    # Change colors? Show preview? Add glow effect?
    pass

def add_game_menu():
    # YOUR DESIGN: Start screen, options, theme selector?
    pass
```

## **💡 THEME INSPIRATION IDEAS**

### **Aesthetic Themes to Try:**
- **Space Aesthetic:** Dark blues, purples, stars, cosmic feel
- **Ocean Vibes:** Blues, teals, wave patterns, underwater feel  
- **Forest Theme:** Greens, browns, natural textures
- **Neon Cyber:** Bright colors on dark background, glowing effects
- **Pastel Dreams:** Soft colors, gentle animations, cozy feel
- **Dark Academia:** Rich browns, golds, sophisticated feel

### **Custom Game Ideas:**
- **Musical Tic-Tac-Toe:** Different sounds for each move
- **Seasonal Snake:** Snake changes colors through seasons
- **Friendship Games:** Games designed to play with your bestie
- **Mood Games:** Game appearance changes based on selected mood

## **🎵 SOUND & MUSIC TIPS**
```python
# Create sounds folder and add these file types:
# - .wav files for sound effects (move.wav, win.wav, click.wav)
# - .mp3 or .ogg files for background music

def play_background_music():
    try:
        pygame.mixer.music.load("music/____")  # Your music file
        pygame.mixer.music.play(-1)  # Loop forever
        pygame.mixer.music.set_volume(___)  # 0.0 to 1.0
    except:
        print("Background music not found")
```

## **🔧 DEBUGGING HELPERS**

**"Black screen" or "Nothing shows up"**
- Make sure you have `pygame.display.flip()` in your main loop
- Check that you're drawing before calling flip()
- Verify your colors aren't the same as background

**"Game doesn't respond to clicks/keys"**
- Make sure you're handling `pygame.event.get()` in your main loop
- Check that your event handling code actually does something
- Print mouse positions to debug click detection

**"Sounds don't work"**
- Create a "sounds" folder in your project directory
- Use .wav files for best compatibility
- Add try/except blocks around sound loading

**"Game runs too fast/slow"**
- Adjust the number in `clock.tick(60)` - higher = faster
- For snake: change the direction step size
- Add delays with `pygame.time.delay(milliseconds)`

## **✨ MAKE IT YOURS**

### **Questions to Consider:**
- What games do YOU actually enjoy playing?
- What colors and themes represent YOUR personality?
- What would make a game feel authentically "you"?
- How could you add elements from your hobbies or interests?

### **Personal Touch Ideas:**
- Use your favorite colors as the game theme
- Add references to things you love (music, movies, books)
- Create games you'd want to play with your friends
- Design win messages that sound like something you'd say
- Add your name or initials as design elements

### **Share-Worthy Features:**
- Screenshot-worthy color combinations
- Games that tell a story about your interests
- Unique twists on classic games that feel fresh
- Visual effects that make people say "whoa, you made this?"

**Remember:** The best games are the ones that reflect the personality of their creator. Make yours uniquely YOU! 🎮✨