 # Python Project 9: Build a Simple Weather App using OpenWeather API 🌦️📲

## 📌 Problem Statement:  
Create a Python script that fetches and displays live weather info for any city using the OpenWeatherMap API.

## 🧠 What You'll Learn:

- Making API requests  
- Reading query parameters  
- Parsing weather data  
- Displaying results clearly

## ✅ Python Code:
```
import requests

def get_weather(city):
    api_key = "YOUR_API_KEY"  # Replace with your OpenWeather API key
    base_url = "https://api.openweathermap.org/data/2.5/weather"

    params = {
        "q": city,
        "appid": api_key,
        "units": "metric"  # For Celsius
    }

    response = requests.get(base_url, params=params)

    if response.status_code == 200:
        data = response.json()
        print(f"Weather in {city}:\n")
        print(f"🌡 Temperature: {data['main']['temp']}°C")
        print(f"☁ Condition: {data['weather'][0]['description'].capitalize()}")
        print(f"💧 Humidity: {data['main']['humidity']}%")
        print(f"💨 Wind Speed: {data['wind']['speed']} m/s")
    else:
        print("City not found or error fetching data.")

Example usage
get_weather("Mumbai")
```

## 📥 How It Works:

1. Sends a GET request with your city and API key.
2. Parses JSON weather data.
3. Displays temperature, condition, humidity & wind.

## 🔧 Try Modifying:

- Add input() to take city from user  
- Display more details (sunrise, pressure, etc.)  
- Save data to a file or send alerts

## 💡 Use Cases:

✅ CLI weather checker  
✅ Integrate into dashboards  
✅ Learn API authentication & parsing 
