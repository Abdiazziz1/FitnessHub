#FitnessHub

A beginner-friendly web platform that brings structured workout plans, goal-based nutrition guidance, and a local gym finder into one place. Built as a final-year university project.

## What it does

FitnessHub is designed for people who are starting out with fitness and feel overwhelmed by scattered information. The site has six main pages:

- **Home** — landing page with a BMI calculator and platform highlights
- **Workouts** — categorised workout plans with detailed guidance
- **Nutrition** — basics, sample meal plans, goal-based nutrition, and pre/post-workout advice
- **Find Gyms** — searchable gym list with city and facility filters
- **About** — mission and target audience
- **Contact** — support information

There are also three JSON API endpoints (`/api/workouts`, `/api/gyms`, `/api/nutrition-tips`) that serve the same data programmatically.

## Tech stack

- **Backend:** Python 3 + Flask
- **Templates:** Jinja2
- **Frontend:** Vanilla JavaScript (ES6+) and custom CSS — no frameworks
- **Data layer:** Static JSON file (`data/sample_data.json`)

## How to run it locally

You'll need Python 3.10 or newer installed.

1. **Clone or download the repository.**
2. **Open a terminal in the project folder.**
3. **(Recommended) Create a virtual environment:**
   ```
   python -m venv venv
   ```
   Then activate it:
   - On Windows: `venv\Scripts\activate`
   - On Mac/Linux: `source venv/bin/activate`
4. **Install dependencies:**
   ```
   pip install -r requirements.txt
   ```
5. **Run the application:**
   ```
   python app.py
   ```
6. **Open your browser** and go to:
   ```
   http://127.0.0.1:5000
   ```

## Project structure

```
fitnesshub/
├── app.py                  # Flask app: routes and rendering
├── data/
│   └── sample_data.json    # All site content (workouts, gyms, nutrition)
├── templates/              # Jinja2 HTML templates
│   ├── base.html
│   ├── index.html
│   ├── workouts.html
│   ├── nutrition.html
│   ├── gyms.html
│   ├── about.html
│   └── contact.html
├── static/
│   ├── css/style.css       # All site styling
│   └── js/script.js        # BMI calculator, gym search, meal selector
├── requirements.txt
├── .gitignore
└── README.md
```

## Key interactive features

Three small JavaScript pieces deliver the main interactions, all without any framework:

- **BMI calculator** (Home page) — calculates locally, displays a WHO category, and writes to an `aria-live` region for accessibility.
- **Gym search & filter** (Gyms page) — combined predicate that evaluates a text query and active city/facility chip together in real time.
- **Meal plan selector** (Nutrition page) — driven by an embedded JSON block; selecting a goal swaps the visible meal items.

## Notes

This is a final-year university project. The site uses a static JSON file rather than a database, and there is no user authentication or persistence — these were deliberately kept out of scope.
