# 🌤️ Telegram Weather + Daily Task Bot with Google Sheets Backup

This is a simple no-code automation using **Make.com**, **WeatherAPI**, **Telegram**, and **Google Sheets**.

You’ll build a system that:
- ⛅ Sends you today’s **weather forecast** and a **custom task** to your Telegram via a bot.
- 📋 Saves the **raw API response** (JSON) to a **Google Sheet** for later use or analysis.

![image](https://github.com/user-attachments/assets/2aa663e5-59cd-42d5-a7d9-2b0deec4851c)

---

## 🧠 What You’ll Learn

Even if you’ve never coded before, you’ll learn how to:
- Create a Telegram bot from scratch
- Pull live weather data using a public API
- Automatically send messages to your Telegram
- Log data to Google Sheets
- Fix and troubleshoot automation flows

---

## 🛠 Tools You’ll Need (All Free)

| Tool | What it's used for |
|------|--------------------|
| [Make.com](https://www.make.com/) | To automate everything (no-code platform) |
| [WeatherAPI.com](https://www.weatherapi.com/) | To get real-time weather data |
| [Telegram](https://web.telegram.org) | To receive weather/task updates |
| [Google Sheets](https://sheets.google.com) | To store data |

---

## 🧱 Step-by-Step Setup

---

### ✅ Step 1: Create a Telegram Bot

1. Open Telegram and search for `@BotFather`
2. Type `/newbot` and follow the instructions:
   - Give your bot a name (e.g. `WeatherTaskBot`)
   - Choose a unique username (must end in `bot`, like `myweatherbot`)
3. BotFather will give you a **token** – copy it! You’ll use it in Make.com.

✅ Done! You now have your own bot.

---

### ✅ Step 2: Get Your Telegram User ID

1. Open Telegram and search for `@userinfobot`
2. Start the bot. It will show your **Telegram User ID** (e.g., `123456789`)
3. Copy this – it’s where your bot will send messages.

---

### ✅ Step 3: Get a WeatherAPI Key

1. Go to [WeatherAPI.com](https://www.weatherapi.com/)
2. Sign up for a free account
3. Go to your dashboard → copy your **API key**
4. Use your farm or location’s GPS coordinates (e.g., `13.2800,77.3111`)

---

### ✅ Step 4: Create a Google Sheet

1. Open [Google Sheets](https://sheets.google.com)
2. Create a new blank sheet
3. Rename it to something like `WeatherLog`
4. Leave it with just one row (header optional)

---

### ✅ Step 5: Set Up Make.com Scenario

1. Go to [Make.com](https://make.com/) → Create a free account
2. Click **Create a new scenario**

---

### 🧩 Add Modules in This Order:

---

#### 🔹 Module 1: **HTTP > Make a Request**

- Method: `GET`
- URL:  https://api.weatherapi.com/v1/forecast.json?key=YOUR_API_KEY&q=LAT,LONG&days=1&aqi=no&alerts=yes

Replace:
- `YOUR_API_KEY` with your real WeatherAPI key
- `LAT,LONG` with your coordinates (e.g., `13.2800,77.3111`)

✅ This fetches today’s weather forecast and alerts

---

#### 🔹 Module 2: **Telegram Bot > Send a Message**

- Connect your bot using the token from BotFather
- Fill in:
- **Chat ID**: Your Telegram User ID (from @userinfobot)
- **Text**: Write the message you want, like:

  ```
  🌤️ Weather Today:
  - Condition: {{response.body.forecast.forecastday[1].day.condition.text}}
  - Max Temp: {{...}}
  - Alerts: {{...}}
  
  📋 Task: Water your vegetable patch and check for pests.
  ```

✅ This sends a formatted message to your Telegram

---

#### 🔹 Module 3: **Google Sheets > Add a Row**

- Connect to your Google Account
- Choose your Google Sheet
- In the “Values” box, just add: {{JSON.stringify(response.body)}}


✅ This stores the **entire response** in a single cell for later review

---

## 🛡️ Optional: Add Error Handling

- Right-click the Telegram module
- Click **Add error handler**
- Choose **Resume or ignore**
- This prevents your flow from breaking if Telegram fails

---

## ✅ Final Steps

1. Click **Run once** to test the scenario
2. Check:
 - Your Telegram: Did the bot send the weather and task?
 - Your Google Sheet: Did a new row get added?

3. If everything works, click the clock icon (top-left) and **schedule it**
 - E.g., every day at 7 AM

🎉 You’ve now automated your daily weather + task updates!

---

## 🧠 What's Next?

Here are some powerful ideas you can build next:

| Idea | Benefit |
|------|---------|
| Add sunrise/sunset data | Plan your farming or outdoor tasks better |
| Add motivational quotes | Start your day with positivity |
| Add mandi/market rates | Get real-time price updates for your produce |
| Pull top Reddit posts | See what’s trending in your niche |
| Store multiple APIs in one sheet | Build a knowledge or planning dashboard |

---

## 🧩 Want the Blueprint?

DM me if you’d like the **ready-to-import Make.com blueprint** to save time.

---

## 💬 Credits

Built with ❤️ using:
- [Make.com](https://make.com)
- [WeatherAPI](https://www.weatherapi.com)
- [Telegram Bots](https://core.telegram.org/bots)
- [Google Sheets](https://sheets.google.com)

---

## 📸 Screenshots (Optional)

Include screenshots of:
- Telegram message
- Google Sheet data
- Make.com scenario layout

---




