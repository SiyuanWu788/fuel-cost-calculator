# Every Mile — Fuel Cost Calculator

Compare the gas cost of two vehicles over the same distance, using a different fuel grade and price for each. Includes an interactive cost chart and an editable MPG ↔ L/100 km converter.

Everything runs in one HTML file. No installation, account, or API key is required.

## Quick start

1. Open **`fuel-cost-calculator_20261102.html`** in your browser. On a Mac, double-click the file or use **Open With → Google Chrome / Safari**.
2. Enter your trip distance in miles.
3. The calculator opens with automatic prices turned off and your preset values: **1,000 miles**, A at **13 MPG / Regular / $0.361 per gallon**, and B at **10 MPG / Premium / $0.400 per gallon**. To use market averages instead, enable **Use average gas prices** and choose a location.
4. Set each vehicle’s MPG and fuel grade: **Regular**, **Mid-grade**, or **Premium**.
5. Compare the total costs, dollar savings, and percentage savings.

To adjust MPG on the chart, select **Vehicle A** or **Vehicle B**, then click the chart or drag a marker. Number fields and sliders work too.

## Features

- **Separate vehicle settings:** MPG, fuel grade, and price per gallon for each vehicle.
- **Automatic prices:** national and state averages, matched to the selected fuel grade.
- **Interactive chart:** two cost curves, with markers for the current vehicle settings.
- **Savings comparison:** identifies the cheaper option and calculates savings relative to the more expensive one.
- **Editable unit converter:** enter MPG or L/100 km to calculate the other value. This is independent of the vehicle settings.
- **Conversion table:** common MPG values plus the current A and B values.
- **Offline calculations:** use saved average prices, when available, or enter prices manually.
- **Responsive layout:** adjusts to desktop and narrow screens.

## Fuel prices and status

Prices come from [AAA](https://gasprices.aaa.com/), through the independent [Gas Price Tracker project](https://github.com/jacobschulman/gas-tracker). The calculator reads its public data feed; it does not connect directly to an official AAA API.

These are **daily regional averages**, not live prices at individual stations. Availability and freshness depend on the data provider.

The calculator checks for prices when opened, when **Refresh prices** is clicked, and when the browser detects that the connection has returned. It does not poll continuously.

| Status | Meaning |
| --- | --- |
| Gray dot — **Checking prices…** | An update is in progress. |
| Green dot — **Prices up to date** | A request succeeded and the available price data is no more than three days old. It may still be dated yesterday. |
| Red dot — **Prices last updated [date]** | The browser is offline, an update failed, or the available data is more than three days old. |
| Red dot — **No saved prices** | No usable price data is available. Example prices may still be shown. |

The displayed date is the **source’s price date**, not the time you opened the calculator. Check the details under **Refresh prices** for the location and date in use.

## Calculations and units

```text
Fuel used (U.S. gallons) = distance in miles / MPG
Trip fuel cost          = fuel used × that vehicle’s price per gallon
Dollar savings          = higher fuel cost − lower fuel cost
Savings percentage      = dollar savings / higher fuel cost × 100

L/100 km = 235.214583 / U.S. MPG
U.S. MPG = 235.214583 / L/100 km
```

For example, **20 MPG ≈ 11.76 L/100 km**, and **30 MPG ≈ 7.84 L/100 km**. Higher MPG and lower L/100 km both mean better fuel economy. Imperial MPG is not supported.

Costs are in **U.S. dollars**. Only fuel spending is compared; purchase price, maintenance, insurance, and other ownership costs are excluded. Displayed results are rounded.

## FAQ

### Can I use the calculator without internet?

Yes. The calculations, chart, and converter work offline. Previously downloaded prices can be reused if your browser retained them. Otherwise, turn off **Use average gas prices** and enter your own prices.

### Why does the price differ from my local station?

The data represents a national or state average. For a specific station, membership discount, or cash price, use manual input.

### Why can a vehicle with higher MPG cost more?

It may require more expensive fuel. The calculator uses each vehicle’s own price, so both MPG and price per gallon affect the result.

### Why does the green indicator show an older price date?

“Up to date” means the latest successfully retrieved data passes the calculator’s freshness check. It does not mean the price was measured just now. Data more than three days old receives a red indicator.

### Does the converter change Vehicle A or B?

No. Entering a number in either converter field only updates the other converter field. Edit the vehicle’s MPG separately to change the cost comparison. Conversion inputs must be greater than zero.

### What is saved, and is anything uploaded?

When browser storage is available, the latest downloaded price dataset is saved locally. The location starts at the U.S. national average each time you open the calculator. Custom prices, MPG, trip distance, and converter entries are not saved across reloads.

Calculations stay on your device. Entered values are not sent to the price provider. Fetching prices makes a normal web request to the public feed. Private browsing, clearing browser data, or moving the HTML file may affect access to saved data.


