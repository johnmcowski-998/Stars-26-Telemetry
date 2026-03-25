# STARS-26 Telemetry

**Real-time telemetry and race strategy dashboard for the Shell Eco-Marathon Battery Prototype competition.**

Built by Team STARS-26 — SW Christian High School (Chaska, MN) & Agape Christi Academy (Minnetonka, MN).

---

## What It Does

A two-part system: a phone app that transmits live GPS and speed data from inside the car, and a laptop dashboard that receives it and displays telemetry, strategy status, and lap timing in real time. Communication is peer-to-peer over the internet using PeerJS — no server required, no shared network required.

---

## Files

| File | Description |
|---|---|
| `ecomarathon-phone.html` | Phone transmitter app — runs in Safari/Chrome on iPhone or Android |
| `ecomarathon-dash.html` | Laptop dashboard — open in any desktop browser |

---

## Race Day Setup

### 1. Open the dashboard
Open `ecomarathon-dash.html` on the laptop. A connect screen will appear with a **dashboard code** like `DASH-AB3X7K`. Note this code.

### 2. Open the phone app
On the phone, navigate to:
```
https://johnmcowski-998.github.io/stars26-telemetry/ecomarathon-phone.html
```
The phone will generate its own room code and display it.

### 3. Connect
Enter the dashboard code into the phone app and tap **Connect to Dashboard** — or enter the phone code into the dashboard connect screen and click **Connect to Phone**. Either direction works.

### 4. Mount the phone in the car
Once connected, tap **Start Transmitting** on the phone. The phone can be connected well before the run starts (e.g. during tech inspection) — the run timer doesn't start until the first GPS packet arrives or you manually hit **Start Lap** on the dashboard.

### 5. Control laps from the dashboard
Use the **▶ Start Lap** and **■ End Lap** buttons on the dashboard to time each run. You do not need to touch the phone during the run.

---

## Phone App Requirements

- Must be opened via HTTPS URL (the GitHub Pages link above), not from a local file
- On iPhone: use Safari, tap **Allow While Using App** when prompted for location
- On Android: use Chrome
- Add to home screen for best experience: Share → Add to Home Screen

---

## Dashboard Features

- **Live speed** — large readout with speed history chart
- **GPS map** — real-time position with trail, dark-filtered map tiles
- **Strategy cards** — ON PACE / AHEAD / BEHIND based on checkpoint splits
- **Time window** — counts down to minimum time, warns if approaching maximum
- **Checkpoints** — configurable distance-based splits with goal times and +/- delta
- **Lap timing** — start/end laps from the dashboard; history saved across sessions
- **Manual lap entry** — add official scored times and energy figures after the run
- **Demo mode** — simulates a full run with no phone connected, for practice and testing
- **CSV export** — exports lap history and speed data

---

## Configuring Strategy

Click **EDIT** in the strategy panel to set:

- **Min run time** — the minimum time allowed before finishing (DSQ if faster)
- **Max run time** — the maximum time allowed to finish (DSQ if slower)
- **Target speed** — shown as a reference line on the speed chart
- **Course distance** — used for the progress bar
- **Checkpoints** — add any number of distance markers with goal split times

Settings are saved in the browser and persist between sessions.

---

## Adding Past Results

After a run, click **+ Entry** in the lap history panel to manually log:
- Official time from scoring
- A label (e.g. "Attempt 2 — official")
- Official score / energy figure (e.g. 842 MPGe)

All lap entries are saved in the browser and survive page refreshes. Use **EDIT** on any row to update it, or **CLR** to clear all history.

---

## No Network? No Problem

The phone and laptop do not need to be on the same WiFi network. PeerJS handles the connection through its public signaling servers — the phone can be on cell data and the laptop on a venue WiFi and it still works. An internet connection is required for the initial handshake.

---

## Shell Eco-Marathon Battery Prototype Rules Reference

> This dashboard does not replace official timing. Always verify run validity with official scorers.

Key timing rules to configure in the dashboard:
- Minimum and maximum run times vary by event — check the current rulebook
- The time window cards will turn red if you are at risk of exceeding the maximum

---

*STARS-26 · Shell Eco-Marathon · SW Christian High School & Agape Christi Academy*
