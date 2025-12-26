# Phenological Stage Simulator for Pelayo S.A.

## Project Description

This web simulator allows you to **model and visualize the phenological stages of soybean**, specifically designed for **Pelayo S.A.** The tool calculates the days corresponding to each phenological stage (from **VN** to **R8**), considering climate variables generated randomly using stochastic simulation techniques.

## Main Features

- **Random number generation**:  
  Uses the **mixed congruential** method to obtain pseudo-random variables.

- **Statistical distributions used**:
  - **Normal** → to simulate **daily temperature**
  - **Uniform** → to simulate **wind speed**

- **Simulated variables**:
  - Daily temperature (°C)
  - GDD (Growing Degree Days) daily and accumulated
  - Wind speed (km/h)
  - Rainy days (🌧️)
  - Phenological stages (VN, R1 to R8)
  - Monitoring days (👁️)

## Technologies Used

- HTML5 + CSS3
- JavaScript
- Bootstrap 5.3
- SweetAlert2

## How to Use

### 1. Select the start date
- Navigate through the months (December to April) using the `"<"` and `">"` buttons
- Click the day you want as the **start of the simulation**

### 2. Run the simulation
- Press the **"Simulate"** button
- The system will automatically calculate all variables day by day

### 3. View results
- Each day is colored according to the phenological stage reached
- Icons appear:
  - 🌧️ for **rainy** days
  - 👁️ for **monitoring** days
- When you click on a day, its data is shown in the **side panel**

### 4. Reset
- Use the **"Reset"** button to start a new simulation

## Mathematical Foundation

### Random number generation
A **Mixed Congruential Generator** is implemented with the formula:

Xₙ₊₁ = (a · Xₙ + c) mod m

Where:
- `X₀` is the initial seed
- `a`, `c`, `m` are integer constants

This generator is used to:
- Generate uniform variables 0 ≤ u ≤ 1 
- Randomize month days
- Assign daily rain and wind

### Distributions used

#### Normal Distribution (Daily temperature)
A truncated normal distribution is used:

temp = max(min(N(μ, σ), μ + σ), μ − σ)

Where:
- `μ`: monthly mean
- `σ`: monthly standard deviation

#### Uniform Distribution (Daily wind)
Wind is generated as:

wind = a + (b − a) · u

Where `a` and `b` are monthly limit values.

### GDD (Growing Degree Days) calculation

GDD = daily_temperature − 10°C

### Crop Phenological Stages

The stages are determined according to **accumulated GDD**:

| Stage | Accumulated GDD range |
|-------|------------------------|
| VN    | 0 – 500                |
| R1    | 501 – 600              |
| R2    | 601 – 750              |
| R3    | 751 – 900              |
| R4    | 901 – 1050             |
| R5    | 1051 – 1250            |
| R6    | 1251 – 1400            |
| R7    | 1401 – 1500            |
| R8    | > 1500                 |

## Project Status
Completed ✔️

The simulator is functional and ready for use.

## File Description
- **css/style.css**: Custom styles for the application
- **js/scripts.js**: Main simulator logic
- **js/calculadorIndex.js**: Animations for the home page
- **public/favicon.png**: Application icon
- **public/video.mp4**: Background video for the main page
- **index.html**: Presentation landing page
- **simulador.html**: Main simulator application
 
## Access to the simulator
This project is available online free of charge.
You can access the simulator at the following link:

[Phenological Stage Simulator - Pelayo S.A.](https://simulador-pelayosa.netlify.app/)

## Development Team

This project was developed by Facundo Moya, a student of **Information Systems Engineering** at the **National Technological University – Tucumán Regional Faculty (UTN-FRT)** for the **Simulation** course, in collaboration with **Pelayo S.A.**

## Code Management

The project was developed using a simple Git workflow, where:

- **Single active branch**: `master` (now called `main` in many repositories)

## Compatibility and Design

This simulator is designed to be responsive and can be used on different devices. However, its display and operation are optimal on large screens, where the calendar and information panels are shown more clearly.

## How to clone the repository

Follow these steps to clone the project to your local machine:

1. Open a terminal or command prompt.

2. Run the following command to clone the repository:

```bash
git clone https://github.com/facundomoya/simulador-pelayosa.git
