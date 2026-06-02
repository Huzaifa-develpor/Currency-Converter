# Currency Converter (Vanilla JS)

## Overview

A simple currency converter built using HTML, CSS, and JavaScript without using any external API. The project uses a custom-defined exchange rate object to perform currency conversions.

## Features

* Convert between multiple currencies
* Custom exchange rate system (no API dependency)
* Instant conversion results
* Simple and responsive UI
* Lightweight and fast

## Technologies Used

* HTML5
* CSS3
* JavaScript (ES6)

## How It Works

The application uses a predefined JavaScript object containing currency exchange rates. The conversion is calculated using a mathematical formula based on relative values.

## Example Logic

```js id="logic1"
const rates = {
  USD: 1,
  PKR: 280,
  EUR: 0.92
};

function convert(amount, from, to) {
  return (amount / rates[from]) * rates[to];
}
```

## Learning Outcomes

* JavaScript objects and data structures
* DOM manipulation
* Mathematical logic implementation
* Event handling in JavaScript
* UI interaction handling

## Future Improvements

* Integration with real-time currency API
* Historical exchange rate tracking
* Currency chart visualization
* Dark mode UI

## Author

Huzaifa Anwar
