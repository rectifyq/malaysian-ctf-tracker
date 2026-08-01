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

## Data Entry Schema & Format (`data.json`)

All competition data is stored as an array of event objects inside `data.json`. 

### Field Specification

| Field | Type | Required | Description |
| :--- | :--- | :--- | :--- |
| `name` | String | **Yes** | The official name of the CTF competition series/event. |
| `url` | String | **Yes** | The main landing page or official website URL for the CTF. |
| `years` | Object | **Yes** | A dictionary of year keys (e.g., `"2024"`), each mapping to event details for that year edition. |
| `years.<YEAR>.date` | String | **Yes** | The date or date range when the edition took place (e.g., `"6-8 August 2024"`). |
| `years.<YEAR>.link` | String | **Yes** | Primary reference link for that specific year (official page, social post, or archive link). |
| `years.<YEAR>.location` | String | **Yes** | Venue, institution, or platform where the event took place (e.g., `"UiTM Shah Alam"` or `"Online"`). |
| `years.<YEAR>.prize_pool` | String | Optional | Total cash prize pool numerical amount as a string (e.g., `"21000"`). |
| `years.<YEAR>.sponsors` | Array[String] | Optional | List of corporate or institutional sponsors. |
| `years.<YEAR>.winners` | Array[String] | Optional | List of winning teams or participants (e.g., `"Team Name (University/Affiliation)"`). |
| `years.<YEAR>.writeups` | Array[String] | Optional | URLs pointing to challenge writeups or writeup repositories. |
| `years.<YEAR>.refs` | Array[String] | Optional | Additional supporting URLs, news articles, press releases, or social media posts. |

---

### Template Entry

Below is a template for adding or updating an event entry in `data.json`:

```json
{
  "name": "EVENT_NAME",
  "url": "https://example.com/event-main-page",
  "years": {
    "2024": {
      "date": "START_DATE - END_DATE MONTH 2024",
      "link": "https://example.com/2024-edition",
      "location": "LOCATION_OR_ONLINE",
      "prize_pool": 1234,
      "sponsors": [
        "SPONSOR_1",
        "SPONSOR_2"
      ],
      "winners": [
        "1ST_PLACE_TEAM (AFFILIATION)",
        "2ND_PLACE_TEAM (AFFILIATION)",
        "3RD_PLACE_TEAM (AFFILIATION)"
      ],
      "writeups": [
        "https://example.com/writeup-1",
        "https://example.com/writeup-2"
      ],
      "refs": [
        "https://example.com/reference-link-1",
        "https://example.com/reference-link-2"
      ]
    },
    "2026": {
      "date": "START_DATE - END_DATE MONTH 2026",
      "link": "https://example.com/2026-edition",
      "location": "LOCATION_OR_ONLINE",
      "sponsors": [
        "SPONSOR_1",
        "SPONSOR_2"
      ]
    }
  }
}
```

## License
This project is open-source and available under the MIT License.
