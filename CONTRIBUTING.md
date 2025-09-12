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
└── Flight-<AirlineCode><FlightNumber>-<YYYY-MM-DD>/
├── metadata.json
└── data.csv

shell
Copia codice

### Example:
datasets/
└── Flight-LH1234-2025-09-12/
├── metadata.json
└── data.csv

pgsql
Copia codice

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
Fields explanation:

flight → Flight number (airline code + digits, e.g. LH1234).

date → Date of the flight in YYYY-MM-DD format.

departure → Departure airport IATA code (e.g. FRA).

arrival → Arrival airport IATA code (e.g. SFO).

airline → Name of the airline.

weather → Short description of weather conditions.

notes → Free text, any observation about the connection or context.

2. data.csv
This file contains the actual measurements you collected.
Preferably use CSV (comma-separated values) with clear headers.

Example format:

csv
Copia codice
timestamp,lat,lon,ping_ms,download_mbps,upload_mbps
2025-09-12T10:00:00Z,50.1109,8.6821,45,55.2,10.1
2025-09-12T10:05:00Z,51.1657,10.4515,47,52.8,9.7
2025-09-12T10:10:00Z,52.5200,13.4050,49,50.1,9.4
timestamp → UTC ISO 8601 timestamp (YYYY-MM-DDTHH:MM:SSZ).

lat,lon → GPS coordinates if available (optional but useful).

ping_ms → Average latency in milliseconds.

download_mbps → Download speed.

upload_mbps → Upload speed.

👉 If you don’t have all fields, include whatever data you have. Just keep headers clear.

🔀 How to contribute (step by step)
Fork this repository

Click the “Fork” button on the top-right of this repo.

This creates a personal copy under your GitHub account.

Clone your fork (optional)
If you know Git, clone your fork locally:

bash
Copia codice
git clone https://github.com/<your-username>/open-starlink-flight-data.git
cd open-starlink-flight-data
👉 If you don’t use Git, you can also upload files directly on GitHub’s web interface (see step 3).

Add your dataset

Go to the /datasets folder.

Create a new subfolder following the naming convention:

php-template
Copia codice
Flight-<AirlineCode><FlightNumber>-<YYYY-MM-DD>
Inside that folder, add:

metadata.json

data.csv

Commit your changes

If using the GitHub web UI: click Commit changes.

If using Git locally:

bash
Copia codice
git add datasets/
git commit -m "Add dataset for Flight LH1234 on 2025-09-12"
git push origin main
Open a Pull Request (PR)

Go to your fork on GitHub.

Click Compare & pull request.

Write a short description of your dataset.

Submit the PR.

Review & Merge

A maintainer will review your contribution.

If everything looks good, your dataset will be merged into the main repo. 🎉

✅ Best practices
Use consistent naming (flight number + date).

Keep metadata.json human-readable.

Keep data.csv clean and structured.

If you have multiple flights, create multiple folders.

💬 Need help?
Open an Issue if you’re not sure how to contribute.

Or join the discussions tab to talk with other contributors.

Thanks again for helping the community! 🌍
