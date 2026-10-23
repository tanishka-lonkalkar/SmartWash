# SmartWash – Hostel Laundry Slot Booking System

> **College Design Thinking Project Prototype**  
> An intuitive, student-centric web application built to eliminate hostel laundry queues, reduce waiting time, and optimize washing machine availability for campus residents.

---

## 🌟 Overview & Design Thinking Context

Hostel students regularly face friction when doing laundry: walking down multiple flights of stairs only to find every washing machine occupied, clothes sitting idle in machines for hours, or long lines forming during peak evening hours.

**SmartWash** was designed using the **Design Thinking framework**:
1. **Empathize:** Observed student laundry bottlenecks and interviewed hostel residents who reported losing 45–90 minutes waiting for open machines.
2. **Define:** Need a low-friction, accessible, and real-time slot reservation system that works seamlessly on student smartphones and laptops.
3. **Ideate:** Developed a centralized single-screen dashboard showing availability for all machines, instant one-tap booking, and smart nearest-time recommendations when peak slots are full.
4. **Prototype:** Built this fully interactive, high-fidelity front-end prototype.
5. **Test:** Ready for direct usability testing by hostel students with zero configuration or login hurdles.

---

## 🚀 How to Run the Prototype

### Option 1: Direct Browser Launch (Zero Dependencies)
Simply double-click [`index.html`](file:///d:/DT%20Project/index.html) or right-click and choose **"Open with Google Chrome / Microsoft Edge / Firefox"**.  
*No Node.js, npm, or server installation is required.*

### Option 2: Local Static Server (Included)
A zero-dependency Node server is included:
```bash
node server.js
```
Then open your browser to **`http://localhost:3000/`**.

---

## 🎨 Key Features & Architecture

### 1. Modern, Soft Blue & Teal Aesthetic
- **Color Palette:** Soft ocean blue (`#0284c7`), deep teal (`#0d9488`), mint accents (`#ccfbf1`), clean white cards, and accessible slate text.
- **Typography:** Modern typography using Google Fonts *Plus Jakarta Sans* and *Outfit*.
- **Accessibility:** Status badges include both text and visual iconography (checkmarks, locks, and pulsing indicators); **never relies on color alone** to communicate availability.

### 2. Streamlined Login & Instant Guest Testing
- Quick pre-fill demo button: fills `rahul.k@hostel.edu` with one tap.
- **"Continue as Guest"** button: enables instant tester onboarding without typing anything.
- Password field with show/hide toggle.
- Clear prototype disclaimer stating availability is simulated for user testing.

### 3. All Slots on One Screen (Main Dashboard)
- **Top Greeting & Date:** Friendly greeting ("Hi, Rahul!"), dynamic date display, and hostel room location.
- **Summary Stat Counters:** Instant counts of **Available**, **Booked**, and **In Use** slots for the chosen day.
- **7-Day Date Selector Track:** Seamlessly switch between Today, Tomorrow, and upcoming days.
- **Time Filter Pills:** Instantly filter slots by:
  - *All Slots*
  - *Available Only*
  - *Morning (7:00 AM – 12:00 PM)*
  - *Afternoon (1:00 PM – 5:00 PM)*
  - *Evening (5:00 PM – 10:00 PM)*
- **Washing Machine Cards:** Displays machine specifications, load capacity (7kg, 8kg heavy, 7.5kg, 6kg quick wash), operational status, and time slot timetable.

### 4. Interactive Booking Flow
- Clicking **"Book Slot"** opens a confirmation modal displaying:
  - Machine name and load type.
  - Date, time range, and estimated cycle duration (60 mins).
  - Helpful student reminder: *Bring detergent pods and arrive 5 minutes early.*
- Upon confirmation:
  - Generates a unique booking reference ID (e.g., `#SW-4821`).
  - Updates slot status to **Booked** in local state.
  - Adds booking to **"My Bookings"**.
  - Displays an animated success toast notification.
  - Prevents duplicate booking of the same slot.

### 5. Smart Recommendation Engine ("If No Slot Is Available")
When a selected period is fully booked (e.g., peak weekend evening):
- Does **not** show a blank or dead-end page.
- Displays an empathetic banner:  
  *“All slots are booked for this time. Don't worry! Check the next available slots and choose a time that works for you.”*
- Automatically computes and shows the **Nearest Open Alternatives** across machines and upcoming dates.
- One-click **"Show Next Available Slot"** button jumps directly to the nearest open slot.
- Interactive **"Find a Slot That Suits Me"** matcher allows students to pick their preferred time window and machine.

### 6. "My Bookings" Management & Cancellation
- Accessible via the top navigation bar with a live active-booking counter badge.
- View upcoming slots, machine locations, and time countdowns.
- **Cancel Booking:** Users can cancel upcoming bookings with a confirmation step; the slot is **immediately released back to "Available"** for fellow hostel residents.
- Friendly empty state with a "Find a Slot" call-to-action when no bookings exist.

### 7. Design Thinking Testing Helper (Floating Widget)
Located in the bottom-left corner is a non-intrusive **"DT Test Scenarios"** helper for evaluators:
1. **Scenario 1:** Book an available slot (Today Morning).
2. **Scenario 2:** Test the "All Slots Booked" peak rush scenario & see smart alternatives.
3. **Scenario 3:** Filter slots for Evening hours.
4. **Scenario 4:** View and cancel an existing reservation.
5. **Reset Prototype Demo Data:** Restores initial demo state at any time.

---

## 📁 File Structure

```
d:/DT Project/
├── index.html          # Semantic HTML5 app structure, screens, and modals
├── css/
│   └── styles.css      # Design system, CSS variables, responsive grid, animations
├── js/
│   ├── data.js         # Machine specs, time slots, days generator, sample state
│   └── app.js          # Reactive state, booking flow, filters, localStorage, toasts
├── server.js           # Built-in lightweight local HTTP server (zero dependencies)
└── README.md           # Project documentation and test walkthrough
```

---

## 👥 Student & Evaluator Testing Checklist

| Task | Expected Outcome |
| :--- | :--- |
| **Login as Guest** | Click "Continue as Guest" on login page; redirects directly to dashboard with personalized welcome. |
| **View Slot Availability** | Review the 4 washing machines and observe green "Available", gray "Booked", and amber "In Use" slots. |
| **Filter by Time** | Tap "Morning" or "Evening" pill; machine grids update instantly without page reloads. |
| **Reserve a Slot** | Click "Book Slot", verify modal details, tap "Confirm Booking". Toast appears and button changes to "Unavailable". |
| **Review My Bookings** | Click "My Bookings" in top nav; verify new booking card is present with reference ID. |
| **Cancel a Slot** | Click "Cancel Booking" and confirm; slot releases back to "Available" on the dashboard. |
| **Test Peak Rush** | Open DT Helper → select Scenario 2 (Peak Evening); verify empathy alert and recommended alternative slots. |
