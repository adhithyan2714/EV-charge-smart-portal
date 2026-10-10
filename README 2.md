# ⚡ EV ChargeSmart

**An intelligent EV charging network platform that predicts congestion, lets drivers book slots in advance, and redirects them to a free station before the queue forms.**

🔗 **Live demo:** _add your GitHub Pages link here, e.g. https://your-username.github.io/ev-chargesmart/_

---

## 📌 The Problem

India's EV ecosystem is growing fast, but public charging is not keeping up:

- Only about **12,000 public chargers** exist today, against **400,000+ needed by 2030** (NITI Aayog, 2023).
- Drivers often wait **20+ minutes** at peak hours.
- Average charger utilization is only about **55%**: some stations are jammed while nearby ones sit idle.
- There is no single platform that combines live charger monitoring, congestion prediction and advance booking.

## 💡 What EV ChargeSmart Does

| Feature | Description |
|---|---|
| **Live station network** | Map and list of stations with real-time charger availability, charger types and status. |
| **Congestion prediction** | Forecasts how busy a station will be over the next 30 minutes to 3 hours (Low / Medium / High). |
| **Slot booking** | A 3-step flow: pick a station, choose date, time and charger type, then confirm. |
| **Smart redirection** | When a station is about to get busy, it suggests a better nearby alternative. |
| **Smart Pick** | One click scores all stations on availability, congestion, forecast and distance, then opens booking for the best one. |
| **Charging estimator** | Estimates charge time, cost, energy added and range added from battery size, charge levels and charger power. |
| **Station tools** | Search, filter by congestion or charger type, sort (nearest, most available, lowest utilization, A–Z) and favorite stations. |
| **My Bookings** | View, check in to or cancel bookings. |
| **Admin dashboard** | KPIs, fault alerts, utilization analytics, peak-hour demand heatmap, ML accuracy tracker, CSV export. |
| **Profile** | Account details, notification preferences and an impact summary (CO₂ saved, savings versus petrol). |
| **Dark mode** | One-click light and dark themes. |

## 🚀 How to Run

This demo is a **single static file with no installation, build step or server required.**

**Option 1: Open locally**
1. Download or clone this repository.
2. Double-click `index.html` to open it in any modern browser (Chrome, Edge, Firefox, Safari).

**Option 2: Clone with Git**
```bash
git clone https://github.com/your-username/ev-chargesmart.git
cd ev-chargesmart
# then open index.html in your browser
```

**Option 3: Run a local server (optional)**
```bash
python3 -m http.server 8000
# visit http://localhost:8000
```

**Option 4: GitHub Pages**
Go to **Settings → Pages**, choose branch `main` and folder `/ (root)`, then save.

> An internet connection is only needed to load the Google Fonts. Without it, the site still works with fallback fonts.

## 🧭 How to Use the Demo

1. **Home:** view the live network map, ticker and stats, and try the **SLI calculator** and **Charging Estimator**.
2. **Stations:** search, filter and sort stations, star favorites, or press **⚡ Smart Pick for me**.
3. **Book a slot:** click **Book** on any station and complete the 3 steps. If the station is congested, you'll get a redirection suggestion.
4. **My Bookings:** check in to or cancel a booking.
5. **Admin:** open the operator dashboard to see KPIs, fault alerts, charts and the demand heatmap.
6. **Profile:** edit your details and notification preferences.

## 🛠️ Built With

**This demo (front end):**
- HTML5
- CSS3, hand-written, with CSS variables for light and dark themes
- Vanilla JavaScript (no frameworks or libraries)
- Google Fonts: Syne, Inter, Space Mono

**Full system design (target architecture):**

| Layer | Technology |
|---|---|
| 1. IoT data | Sensors or MQTT simulator → Mosquitto broker → Python ingestion → MongoDB + Redis |
| 2. Intelligence | Random Forest, LSTM and GRU models served through a Flask REST API |
| 3. Application | Node.js + Express, JWT auth with role-based access (User / Admin), Nodemailer reminders |
| 4. Presentation | React.js, Tailwind CSS, Leaflet.js, Chart.js |

Database collections: `Users`, `Stations`, `Chargers`, `Bookings`, `CongestionLogs`, `ChargingSessionLogs`.

## 📊 Targets and Model Results

| Metric | Value |
|---|---|
| Random Forest accuracy | 88.4% |
| LSTM RMSE | 2.81 kWh |
| GRU RMSE | 2.94 kWh |
| Wait-time reduction target | 40% |
| Charger utilization target | 80% |

## ⚠️ Note on the Demo

The submitted website is a **front-end prototype** of the full design. Station data, congestion forecasts, bookings and charts are **sample data generated in the browser**, and bookings reset when the page is refreshed. The Node.js backend, MongoDB database, MQTT pipeline and trained ML models described above are the planned architecture and are not connected to this demo.

## 📁 Project Structure

```
ev-chargesmart/
├── index.html   # Entire application: markup, styles and JavaScript
└── README.md    # Project documentation
```

## 🔮 Future Work

- Connect the front end to the Node.js and Express API and MongoDB.
- Stream real charger data over MQTT and serve live ML predictions from Flask.
- Add payments, a native mobile app and vehicle-to-grid (V2G) support.

## 📄 License

Released under the MIT License.
