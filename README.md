# 🐾 Mapaw

**Mapaw** is a comprehensive mobile platform for pet owners, blending daily care management with a specialized location discovery service.

---

## 📱 Project Overview & Features (MVP)

Mapaw aims to solve the fragmentation of pet care data by providing a unified solution for health tracking and local discovery.

### 🐕 User & Pet Profiles
* **Secure Accounts:** User authentication via Email/Social providers.
* **Digital Pet Passport:** Manage profiles for multiple pets (Photo, Breed, Age, Weight, Chip ID).
* **Medical History:** A dedicated log for Vet visits, surgeries, and allergies.

### 📅 Smart Care System
* **Reminders:** Custom alerts for grooming, medication, flea/tick prevention, and feeding.
* **Vaccination Tracker:** Visual tracking of vaccination status with push notification alerts for upcoming due dates.

### 📍 Location & Discovery (The "Map" in Mapaw)
* **Pet-Friendly Directory:** A curated list and map view of Veterinary Clinics, Pet Stores, Parks, and Cafés.
* **Smart Search:** Filter locations by specific needs (e.g., "24/7 Emergency Vet", "Dog Run").
* **Place Details:** Integration with Google Places to show ratings, photos, and opening hours.
* **User Interaction:** Save favorite spots and view recent searches.

---

## 🏗 Tech Stack

### Backend API
* **Framework:** Ruby on Rails 7+ (API Mode)
* **Database:** PostgreSQL
* **Background Jobs:** Redis + Sidekiq (Handling push notifications and data syncing)
* **Storage:** AWS S3 (for pet avatars and place images)

### Mobile App
* **Framework:** React Native / Flutter *(TBD)*
* **Maps Engine:** Google Maps SDK (Mobile)

### External Services
* **Google Places API (New):** For retrieving POI data (Vets, Shops).
* **Firebase Cloud Messaging (FCM):** For push notifications.

---

## ⚙️ Setup & Installation (Backend)

### Prerequisites
* Ruby 3.x
* PostgreSQL
* Redis

### Steps

1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/your-org/mapaw-backend.git](https://github.com/your-org/mapaw-backend.git)
    cd mapaw-backend
    ```

2.  **Install Gems:**
    ```bash
    bundle install
    ```

3.  **Environment Variables:**
    Copy the sample configuration and update with your credentials.
    ```bash
    cp .env.example .env
    ```
    *Make sure to set `Maps_API_KEY` in your .env file.*

4.  **Database Setup:**
    ```bash
    rails db:create db:migrate
    ```

5.  **Run the Server:**
    ```bash
    rails s
    ```

---

## ⚠️ Important Note on Google Maps API

To maintain cost efficiency for the startup MVP, this project implements strict **Field Masking** when querying the Google Places API.

* **List Views:** Fetch only `Basic` fields (ID, Name, Location, Status).
* **Detail Views:** Fetch `Contact` and `Atmosphere` fields (Phone, Rating, Website) **only upon user request** (click).

**Do not change the API query parameters without reviewing the pricing impact.**

---

## 📝 Roadmap

- [ ] **Phase 1 (MVP):** Core pet profiles, Medical records, Reminders, and Basic Location Search.
- [ ] **Phase 2:** Community features (Social Feed), User Reviews for places.
- [ ] **Phase 3:** Direct appointment booking with partner clinics.

---

## 📄 License

This project is proprietary and confidential.
