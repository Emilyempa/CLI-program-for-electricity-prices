# Electricity Price Analysis Tool

This CLI program helps users optimize their energy consumption decisions by analyzing Swedish electricity prices.  
The application retrieves data from the [Elpris API](https://www.elprisetjustnu.se/elpris-api) and displays prices in **öre** (1/100 of a SEK).

---

## Features

- **Fetches electricity prices**  
  Retrieves the current day's prices and, if available, the prices for the next day from the Elpris API.

- **Zone selection**  
  Users can select their price zone via CLI interaction.  
  *If no console is available, the program defaults to **SE3**.*

- **Statistics**  
  - Displays mean price for the current 24-hour period (and next 24 hours, when available).  
  - Shows minimum and maximum prices based on the available dataset.

- **Optimal charging time**  
  Uses a sliding window algorithm to find the best charging period (2, 4, or 8 hours) starting from the current time.

---

## Error Handling & User Experience

- **Invalid input**  
  Zone selections are validated. If an invalid option is entered, the user is prompted to try again.

- **Unavailable data**  
  If the Elpris API is unreachable or tomorrow’s prices are not yet published, the program informs the user instead of crashing.

- **Friendly messages**  
  The program prints clear messages in Swedish (e.g. `"Kunde inte hämta dagens priser"`) rather than technical stack traces in most cases.

- **Default behavior in IDEs**  
  If console input is not available, the program automatically selects zone **SE3**.

---

## Getting Started

1. Compile and run the program, starting from the main entry point:  
   ```bash
   App.java
