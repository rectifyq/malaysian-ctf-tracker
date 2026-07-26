# Malaysian CTF Tracker

A platform tracking cybersecurity Capture The Flag (CTF) competitions, prize pools, organizer metrics, and hall-of-fame rankings across Malaysia.

## Features
- **Event Matrix (2002–2030):** Interactive visualization of historical and upcoming local CTF editions.
- **Monthly Event Cadence:** Heatmap identifying peak competition months.
- **Stacked Prize Pool Analytics:** Interactive Chart.js breakdown of prize distribution filtered by organizers, complete with dynamic hover sums.
- **Winners & Hall of Fame:** Word bubbles and multi-title tracking for top-performing teams and individuals.
- **Static & Modular:** Built on a clean separation of static frontend files (`index.html`) and structured JSON data (`data.json`).

---

## Getting Started

To run or modify this project locally:

1. Clone the repository:
   ```bash
   git clone https://github.com/rectifyq/malaysian-ctf-tracker.git
   ```
2. Navigate into the directory:
   ```bash
   cd malaysian-ctf-tracker
   ```
4. Open index.html locally using a live server or static file server (due to fetch requests for data.json, running via a local server like Live Server in VS Code or python3 -m http.server is recommended).

## Contributing
We welcome contributions to keep the Malaysian CTF timeline accurate and up to date!

### Adding or Updating Data
All event data, historical editions, dates, prize pools, and winner rankings are maintained in data.json.
1. Fork the repository.
2. Edit data.json to add new events, update upcoming 2026+ editions, or correct metadata.
3. Ensure your JSON structure aligns with the existing schema (organizers array containing nested year objects/links/winners).
4. Test locally to ensure the frontend parses your updates correctly without breaking charts or modals.
5. Open a Pull Request detailing the updates made with references in the commit description.

## License
This project is open-source and available under the MIT License.
