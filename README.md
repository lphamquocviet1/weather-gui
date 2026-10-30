# [README.md](https://github.com/user-attachments/files/34163222/README.md)
# Weather App 🌤️

A simple desktop weather application built with **Python** and **PyQt5**. Enter a city name to retrieve its current temperature and weather conditions using the **OpenWeatherMap API**.

This project helped me practice building graphical user interfaces, working with REST APIs, handling HTTP requests, and displaying real-time data in a desktop application.

## Features

- Search for current weather by city name.
- Display the temperature in **Fahrenheit (°F)**.
- Show a short description of current weather conditions.
- Handle common HTTP and connection errors with messages in the application.
- Simple GUI styled with PyQt5 and Qt stylesheets.

## Tech Stack

- **Python 3.10+** (uses `match` / `case`)
- **PyQt5** — desktop graphical interface
- **Requests** — HTTP requests
- **OpenWeatherMap API** — current weather data

## Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/YOUR_USERNAME/YOUR_REPOSITORY.git
cd YOUR_REPOSITORY
```

Replace the placeholders with your GitHub username and repository name.

### 2. Install dependencies

```bash
python -m pip install PyQt5 requests python-dotenv
```

### 3. Configure your API key

Get an API key from [OpenWeatherMap](https://openweathermap.org/api).

Create a `.env` file in the project folder:

```env
OPENWEATHER_API_KEY=your_api_key_here
```

**Important:** The application code needs a small update to read this environment variable instead of using a hardcoded API key:

```python
import os
from dotenv import load_dotenv

load_dotenv()
api_key = os.getenv("OPENWEATHER_API_KEY")
```

Place this configuration in your code and use `api_key` when calling the API. The original code does **not yet** read `.env` automatically.

Add `.env` to `.gitignore` to avoid publishing secrets:

```gitignore
.env
__pycache__/
.venv/
```

### 4. Run the application

```bash
python main.py
```

Replace `main.py` with the actual name of your Python file.

## How It Works

1. Enter a city name in the input field.
2. Click **Get Weather**.
3. The app requests current weather data from OpenWeatherMap.
4. If the request succeeds, it displays the temperature in Fahrenheit and the weather description.
5. If the request fails, it shows an error message.

## What I Learned

- Creating a desktop GUI with PyQt5 widgets and layouts.
- Connecting button clicks to functions using Qt signals and slots.
- Sending GET requests and processing JSON responses.
- Understanding HTTP status codes and exception handling.
- Converting temperatures from Kelvin to Fahrenheit.
- Styling a GUI with Qt stylesheets.

## Future Improvements

- Add Celsius/Fahrenheit switching.
- Show weather icons and additional details such as humidity and wind speed.
- Add request timeouts and validate empty input.
- Improve layout responsiveness and visual design.

## Acknowledgments

Weather data provided by [OpenWeatherMap](https://openweathermap.org/).
