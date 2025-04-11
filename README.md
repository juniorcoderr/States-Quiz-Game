## 🇮🇳 Indian States Quiz Game 🎮 (with Turtle Graphics & Pandas)

This is a fun and educational **Python quiz game** built using the **Turtle graphics library** and **Pandas**. The goal of the game is to test and improve your knowledge of **Indian States and Union Territories** by guessing their names and locating them on the map.

---

### 🧠 What the Game Does

- A blank map of India is displayed using a `.gif` image.
- You are prompted to enter the names of Indian states/UTs one by one.
- When you guess a correct state, its name is written on the map at the correct x-y coordinates.
- If you type `"Exit"`, the game ends and saves a `.csv` file named `states_to_learn.csv` containing the states you missed — so you can revise later!

---

### 📌 Features

✅ Interactive guessing using pop-up textboxes  
✅ Real-time tracking of correct guesses  
✅ Accurate state positioning on the map  
✅ Automatically saves unguessed states to a CSV  
✅ Combines both **Indian States and Union Territories** in one dataset  

---

### 📁 Files in the Repo

- **`main.py`** – Main game logic
- **`states.csv`** – Contains names of all 28 states and 9 union territories along with their x and y coordinates on the map
- **`blank_states_img.gif`** – A blank map of India used for display

---

### 🧪 How it Works – Code Explained

```python
screen = turtle.Screen()
screen.title("Indian States Game")
image = "blank_states_img.gif"
screen.addshape(image)
turtle.shape(image)
```

🖼️ Sets up the Turtle screen and loads the map image.

---

```python
data = pandas.read_csv("states.csv")
all_states = data.state.to_list()
guessed_states = []
```

📋 Loads the state and union territory data from `states.csv`, and prepares a list for tracking correct guesses.

---

```python
answer_state = screen.textinput(title="...", prompt="...").title()
```

⌨️ Continuously prompts the user to enter state names and capitalizes the input for matching.

---

```python
if answer_state in all_states:
    guessed_states.append(answer_state)
    ...
    t.goto(x, y)
    t.write(answer_state)
```

🟢 If the answer is correct, it's marked on the map at the appropriate location using the turtle's `goto()` and `write()` methods.

---

```python
if answer_state == "Exit":
    ...
    new_data.to_csv("states_to_learn.csv")
```

🚪 If the user types `"Exit"`, the game ends and saves the list of unguessed states in `states_to_learn.csv`.

---

### 🧠 Prerequisites

Make sure you have the following Python packages installed:

```bash
pip install pandas
```

---

### 🏁 How to Run

1. Clone the repo or download the files
2. Run `main.py`
3. Enter state/UT names when prompted
4. Type `"Exit"` anytime to quit and see what you missed!

---

### 🗺️ About `states.csv`

This CSV contains all **28 states** and **9 union territories** of India with approximate `x`, `y` coordinates corresponding to their location on the map image.

---

### 💡 Motivation

This game was inspired by educational geography games like “U.S. States Quiz,” and adapted for India to help students and enthusiasts learn the Indian map in a more interactive and visual way.

---

### 🔖 License

Feel free to use and improve this project for educational purposes.
