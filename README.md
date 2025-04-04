# dabble
Grow a hobby. Grow a you.

## I. User Workfloww
### Initial Setup
**1. First App Launch (Onboarding)** 
1. Welcome animation: your pet “egg” appears
2. Short quiz: pick goals or interests (e.g., “I want to be more creative,” “I want to feel calmer”)
3. Choose 2–3 habits or select from suggestions (with tags: creativity, movement, rest, etc.)
4. Name your pet + choose its initial style

### Daily User Interaction + App Mechanism

**1. Landing on Homescreen**
* Your pet is there, smiling (or looking sleepy if you missed habits)
* “Here’s what we can do today!” → Habits listed
* "How are you feeling today?" → optional mood check 
* “Talk to [pet name]” → AI chat opens with encouragement or a tiny conversation

**2. Daily Routine & User Interaction** 
* **a. Daily Check-in**
  * A gentle push notification reminds the user to “Dabble Today” with a cheerful greeting from their pet.
  * Home Screen Overview:
    * Their pet in the center, showing its current mood or growth stage.
    * A list of scheduled habits for the day, along with progress indicators (e.g., streaks, checkmarks).
    * A quick “How are you feeling?” mood prompt.
  
* **b. Habit Logging & Engagement**
  * Logging Habits: As the user completes a habit (e.g., journaling, a quick workout), they tap the corresponding habit tile to mark it done.
  * Instant Feedback: The pet reacts in real time (e.g., cheerful animations or new accessory unlocks) when habits are logged, reinforcing the connection between self-care and pet care.

* **c. AI-Powered Pet Interaction**
  * An AI-driven chatbot “talks” with the pet. The pet might ask about the user’s day, offer a motivational quote, or suggest a new mini-challenge.
  * Users can add a quick journal entry or select an emoji to describe their mood. The AI then provides gentle feedback or tips, adjusting the pet’s demeanor accordingly.

* **d. Progress & Gamification**
  * Once a habit is consistent for X days, pet “evolves” or unlocks a new accessory; Growth animations → dopamine boost!
  * Pet Evolution Screen: A dedicated section shows the pet’s growth over time (e.g., new forms or animations unlocked after maintaining habit streaks).
  * Statistics & Insights: Visual graphs display habit streaks, mood trends, and overall progress, letting users see how small daily efforts contribute to long-term growth.
 
## II. Developer's End
### A. Tech Stack
**Front-end**
* Framework: React Native
* UI Libraries:
  * Expo
  * React Native Reanimated + Gesture Handle (for pet interactions)
  * TailwindCSS-like styling via NativeWind (optional but fast)
**Back-end**
* Backend Framework: FastAPI (Python) or Node.js
* Database: PostgreSQL (via Supabase or hosted solution like NeonDB)
* Cloud Hosting: Render, Railway, or Vercel (for APIs)

**Extras**
* Push Notifications: OneSignal or Firebase Cloud Messaging
* Storage (Pet Avatars, Customizations): Firebase Storage or Cloudinary
* CI/CD: Expo EAS or GitHub Actions for building + deploying to both app stores

### B. Infrastructure
**a. API Endpoints**
| Endpoint                     | Method | Description                                   |
|-----------------------------|--------|-----------------------------------------------|
| /register                   | POST   | Create a new user account                     |
| /login                      | POST   | Authenticate user and return token            |
| /user/dashboard             | GET    | Fetch user data: habits, pet status, mood     |
| /habits/add                 | POST   | Add a new habit                               |
| /habits/log                 | POST   | Log a completed habit                         |
| /pet/status                 | GET    | Get current pet growth state and progress     |
| /pet/customize              | POST   | Customize pet appearance                      |
| /mood/checkin               | POST   | Submit mood + optional journal entry          |
| /ai/chat                    | GET    | Generate AI response from pet                 |
| /ai/suggestions             | GET    | Get habit/hobby suggestions based on behavior |
| /community/challenges       | GET    | View current habit challenges                 |
| /feedback                   | POST   | Submit user feedback or bug report            |

**b. MVP vs Full Version Table**
| Feature                           | MVP ✅                              | Full Version 🚀                                |
|----------------------------------|-------------------------------------|------------------------------------------------|
| User Registration/Login          | ✅ Email/password                   | ✅ Sign in with Apple/Google                   |
| Habit Tracking                   | ✅ Manual input + checkboxes        | ✅ Smart suggestions + streak analytics       |
| Virtual Pet                      | ✅ Static image + emoji reactions   | ✅ Animated pet, evolution, cosmetics         |
| AI Interaction (Chat)            | ✅ Basic GPT replies                | ✅ Mood-aware dialogue + memory               |
| Journaling / Mood Check-ins      | ✅ Simple text input + emoji scale  | ✅ Sentiment analysis + habit correlation     |
| Progress Tracking                | ✅ Habit streaks                    | ✅ Charts, streak trends, habit-mood graph    |
| Pet Evolution                    | ✅ Based on habit streaks           | ✅ Multiple forms, hobby archetypes           |
| Community Challenges             | ❌                                 | ✅ Habit challenges, friend pets visit        |
| Notifications                    | ❌                                 | ✅ Pet sends push encouragements              |
| Customization                    | ❌                                 | ✅ Pet skins, accessories, backgrounds        |
| Widgets (iOS/Android)            | ❌                                 | ✅ Home screen pet widget or habit preview    |
| Monetization                     | ❌                                 | ✅ Freemium tier + cosmetic item store        |


### C. App Management & Background Maintenance
**a. Automated Reminders & Notifications**
* Push Notifications: The backend schedules daily reminders for habit logging, mood check-ins, and challenge alerts.
* AI-Driven Prompts: Based on user data (e.g., if a habit wasn’t logged for a few days), the system generates personalized nudges to keep the routine on track.
**b. Data Analytics & AI Processing**
* Sentiment & Behavior Analysis: The AI continuously analyzes journal entries and habit data to refine suggestions, detect patterns, and adjust pet behavior to match user mood.
* Progress Tracking: Habit data is securely stored and processed to generate personalized insights and growth graphs on the user dashboard.
