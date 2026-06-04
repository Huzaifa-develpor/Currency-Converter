# Currency Converter 💱

## Overview

Currency Converter is a sleek, modern, and fully responsive web application built using HTML5, CSS3, and Vanilla JavaScript (ES6+). Upgraded from a static hardcoded architecture, the application now connects directly to a live, open-source currency API to fetch accurate, real-time global exchange rates.

The project also integrates dynamic country flag rendering that updates instantly based on the selected currencies.

## Features

* **Live Exchange Rates:** Dynamically fetches global exchange rates directly from a continuous deployment open-source repository.
* **No API Key Needed:** Powered by a keyless public API endpoint, eliminating configuration hurdles and trial-period expirations.
* **Dynamic Flag Syncing:** Integrates with `flagsapi.com` to render the precise country flag whenever the user updates the currency dropdown.
* **Smart Input Validation:** Automatically handles empty or invalid numeric queries, resetting the baseline calculation to 1 unit for a seamless user experience.
* **Responsive Styling:** Built with a premium, mobile-optimized dark radial gradient layout.

## Technologies Used

* **Frontend:** HTML5, CSS3 (Flexbox, Radial Gradients, Transition Layers)
* **Scripting:** JavaScript (ES6+, Async/Await Fetch API, Query Selectors)
* **Assets:** FontAwesome Icons, FlagsAPI Endpoint

## How It Works

The application skips local hardcoded data structures entirely. When the user selects the currencies and clicks the activation button, the script runs a network fetch to acquire a fresh global conversion map in JSON format.

### API & Integration Logic

```js
async function doSearch() {
    const cityInput = document.getElementById("city-input").value.trim();
    const url = `https://wttr.in/${encodeURIComponent(cityInput)}?format=j1`;

    try {
        const response = await fetch(url);
        const data = await response.json();
        
        // Extracting live attributes from the JSON response object
        const currentCondition = data.current_condition[0];
        
        document.getElementById("degree").textContent = currentCondition.temp_C + "°C";
        document.getElementById("feels-like").textContent = currentCondition.FeelsLikeC + "°C";
        document.getElementById("humidity").textContent = currentCondition.humidity + "%";
        document.getElementById("wind-speed").textContent = currentCondition.windspeedKmph + " km/h";
    } catch (error) {
        console.error("Failed to fetch real-time data:", error);
    }
}
```

## Learning Outcomes
Utilizing Asynchronous JavaScript workflows (async/await, try/catch matrix) to manipulate network data streams.

Writing clean utility functions for complex programmatic string interpolations to switch out external static images (flagsapi).

Architecting multi-tier iteration logic across complex layout arrays using dynamic object mapping keys.

Structuring clean fallback validations to prevent system-wide application crashes during server-side connection latency.

Future Improvements
Add a reverse toggle swap button to instantly switch the "From" and "To" currency states.

Implement a local storage cache system to store current data sheets for offline performance support.

Embed interactive historical analytics graphs tracking values over a 30-day timeline.

Author
Huzaifa Anwar
