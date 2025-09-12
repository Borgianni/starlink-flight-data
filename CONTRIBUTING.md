# Contributing Guidelines ✍️

Thank you for contributing to **Open Starlink Flight Data**!  
This repository is designed to collect **Starlink connectivity datasets gathered during flights**, so that the scientific community can analyze and build upon them.

Your contribution will help researchers better understand how Starlink behaves in aviation environments. 🚀✈️📡

---

## 🛠 Requirements
- A GitHub account (free).
- Basic knowledge of how to create folders and files on your computer.
- If possible, some familiarity with GitHub Pull Requests (we’ll explain step by step).

---

## 📂 Repository structure

All contributed datasets are stored in the `/datasets` folder.  
Each dataset must be inside its **own subfolder** with a clear and consistent naming convention:

datasets/
/Flight-<AirlineCode><FlightNumber>-<YYYY-MM-DD>
/metadata.json
/data.csv


---

## 📑 Files to include

### 1. `metadata.json`
This file describes the flight and context of your data collection.


**Template:**
```json
{
  "flight": "LH1234",
  "date": "2025-09-12",
  "departure": "FRA",
  "arrival": "SFO",
  "airline": "Lufthansa",
  "weather": "Clear skies, light turbulence",
  "notes": "Stable connection during most of the flight. Minor dropouts over Greenland."
}
```
### 2. data.csv
This file contains the actual measurements you collected.
Preferably use CSV (comma-separated values) with clear headers.

---
## 🔀 How to contribute (step by step)
- Fork this repository
- Click the “Fork” button on the top-right of this repo.
- This creates a personal copy under your GitHub account.
- Clone your fork (optional)
- 
# Contributing Guidelines ✈️📡

Thank you for contributing to **Open Starlink Flight Data**!

This repository collects **Starlink connectivity datasets gathered during flights** to help the scientific community analyze and understand how Starlink performs in aviation environments. Your contribution will advance research into satellite internet connectivity at altitude.

---

## 🛠️ Prerequisites

- A GitHub account (free to create)
- Basic familiarity with file/folder organization
- Optional: Knowledge of Git and GitHub Pull Requests (we provide step-by-step instructions)

---

## 📂 Repository Structure

All datasets are organized in the `/datasets` folder using a consistent naming convention:

```
datasets/
└── Flight-<AirlineCode><FlightNumber>-<YYYY-MM-DD>/
    ├── metadata.json
    └── data.csv
```

**Example:**
```
datasets/
└── Flight-LH1234-2025-09-12/
    ├── metadata.json
    └── data.csv
```

---

## 📋 Required Files

### 1. `metadata.json`

This file describes your flight and data collection context.

**Template:**
```json
{
  "flight": "LH1234",
  "date": "2025-09-12",
  "departure": "FRA",
  "arrival": "SFO",
  "airline": "Lufthansa",
  "aircraft_type": "A350-900",
  "weather": "Clear skies, light turbulence over Atlantic",
  "collection_method": "Manual speedtests every 5 minutes using Speedtest.net",
  "notes": "Stable connection for most of flight. Brief dropouts over Greenland ice sheet."
}
```

**Field Descriptions:**
- `flight` → Flight number (airline code + digits)
- `date` → Flight date in YYYY-MM-DD format
- `departure` → Departure airport IATA code
- `arrival` → Arrival airport IATA code  
- `airline` → Airline name
- `aircraft_type` → Aircraft model (if known)
- `weather` → Weather conditions during flight
- `collection_method` → How you gathered the data
- `notes` → Any relevant observations about connectivity or context

### 2. `data.csv`

This file contains your actual connectivity measurements in CSV format with clear headers.

**Recommended format:**
```csv
timestamp,lat,lon,altitude_ft,ping_ms,download_mbps,upload_mbps,status
2025-09-12T10:00:00Z,50.1109,8.6821,35000,45,55.2,10.1,connected
2025-09-12T10:05:00Z,51.1657,10.4515,36500,47,52.8,9.7,connected
2025-09-12T10:10:00Z,52.5200,13.4050,37000,49,50.1,9.4,connected
2025-09-12T10:15:00Z,53.2734,14.5289,37500,-1,0,0,disconnected
```

**Field Descriptions:**
- `timestamp` → UTC time in ISO 8601 format (YYYY-MM-DDTHH:MM:SSZ)
- `lat,lon` → GPS coordinates (if available)
- `altitude_ft` → Flight altitude in feet (if available)
- `ping_ms` → Latency in milliseconds (-1 if no connection)
- `download_mbps` → Download speed in Mbps
- `upload_mbps` → Upload speed in Mbps  
- `status` → Connection status (connected/disconnected/limited)

> **Note:** Include whatever data you have available. Not all fields are required, but consistent headers help with analysis.

---

## 🔄 How to Contribute

### Step 1: Fork the Repository
1. Click the **"Fork"** button at the top-right of this repository
2. This creates a personal copy under your GitHub account

### Step 2: Clone Your Fork (Optional)
If you know Git, clone your fork locally:
```bash
git clone https://github.com/<your-username>/open-starlink-flight-data.git
cd open-starlink-flight-data
```
👉 If you don't use Git, you can also upload files directly on GitHub's web interface (continue to step 3).

### Step 3: Add Your Dataset
1. Go to the `/datasets` folder
2. Create a new subfolder following the naming convention:
   ```
   Flight-<AirlineCode><FlightNumber>-<YYYY-MM-DD>
   ```
3. Inside that folder, add:
   - `metadata.json`
   - `data.csv`

### Step 4: Commit Your Changes
**If using the GitHub web UI:** click "Commit changes".

**If using Git locally:**
```bash
git add datasets/
git commit -m "Add dataset for Flight LH1234 on 2025-09-12"
git push origin main
```

### Step 5: Open a Pull Request (PR)
1. Go to your fork on GitHub
2. Click "Compare & pull request"
3. Write a short description of your dataset
4. Submit the PR

### Step 6: Review & Merge
- A maintainer will review your contribution
- If everything looks good, your dataset will be merged into the main repo 🎉

---

## ✅ Best Practices

### Data Quality
- **Be consistent** with timestamps and units
- **Document your methodology** in metadata.json
- **Include context** about unusual readings or connection issues

### File Organization  
- Use the exact naming convention: `Flight-<Code><Number>-<YYYY-MM-DD>`
- Keep one flight per folder
- Use clear, descriptive commit messages

### Privacy & Safety
- **Never include** personal information, payment details, or passwords
- **Avoid** sharing sensitive flight information if requested by airline
- **GPS coordinates** are helpful but optional if privacy is a concern

---

## 📊 Data Usage

Your contributed data may be used for:
- Academic research on satellite internet performance
- Aviation connectivity analysis
- Starlink coverage mapping
- Network performance optimization studies

All data is shared under an open license for research purposes.

---

## 🆘 Need Help?

- **Have questions?** Open an [Issue](../../issues)
- **Want to discuss?** Use the [Discussions](../../discussions) tab
- **Found a bug?** Report it in [Issues](../../issues)

---

## 🙏 Thank You

Your contribution helps advance our understanding of satellite internet in aviation. Every dataset makes the research community stronger!

**Happy flying and measuring!** 🛫📊
