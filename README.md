# PUBG Weapons Analysis Project

## Project Overview

This project analyzes PUBG weapons data to explore damage statistics, bullet types, fire modes, and weapon types using Power BI. The goal is to uncover insights into weapon performance, such as damage distribution, shots to kill, and effectiveness across different categories, to support strategic gameplay decisions.

## Table of Contents

- Project Overview
- Dataset
- Prerequisites
- Setup
- Analysis Workflow
- Key Measures
- Results
- Contributing
- License

## Dataset

- **Source**: The dataset is sourced from the provided PUBG weapons data file (e.g., "PUBG_Weapons_Data.csv").
- **Description**: The dataset contains records of PUBG weapons, including columns like `Damage`, `Bullet Type`, `Fire Mode`, `Weapon Type`, `Shots to Kill (Chest)`, and `Shots to Kill (Head)`, representing weapon performance metrics.
- **Schema**:
  - `Damage`: Damage dealt by the weapon
  - `Bullet Type`: Type of bullet used (e.g., 5.56, 7.62, 9.00)
  - `Fire Mode`: Firing mode (e.g., Automatic, Single, Burst)
  - `Weapon Type`: Category of weapon (e.g., Shotgun, Assault Rifle, Pistol)
  - `Shots to Kill (Chest)`: Average shots to kill with chest hits
  - `Shots to Kill (Head)`: Average shots to kill with headshots

## Prerequisites

- Power BI Desktop for data analysis and visualization

## Setup

1. **Clone the Repository**:

   ```bash
   git clone https://github.com/Islam-Ossama/PUBG.git
   ```

2. **Configure Power BI**:

   - Open Power BI Desktop and import the PUBG weapons data file (e.g., `PUBG_Weapons_Data.csv`) directly.
   - Use Power BI's data transformation tools (Power Query Editor) to clean and prepare the data.

## Analysis Workflow

1. **Data Cleaning**: Use Power BI's Power Query Editor to handle missing values, duplicates, and inconsistencies in columns like `Bullet Type`, `Fire Mode`, and `Weapon Type`.
2. **Exploratory Analysis**: Leverage Power BI to analyze weapon damage, shots to kill, and distribution across bullet types, fire modes, and weapon types using data modeling and DAX calculations.
3. **Visualization**: Create an interactive dashboard in Power BI to visualize key metrics like total damage, weapon counts by bullet type, damage by fire mode, and shots to kill.

## Key Measures

In this project, analysis was performed directly in Power BI using DAX (Data Analysis Expressions). Below are examples of DAX measures used for the analysis:

- **Measure 1**: Calculate total damage by bullet type

  ```
  Total Damage by Bullet Type = 
  CALCULATE(
      SUM('pubg_weapons'[Damage]),
      ALLEXCEPT('pubg_weapons', 'pubg_weapons'[Bullet Type])
  )
  ```

- **Measure 2**: Calculate count of weapons by bullet type

  ```
  Weapon Count by Bullet Type = 
  CALCULATE(
      COUNT('pubg_weapons'[Bullet Type]),
      ALLEXCEPT('pubg_weapons', 'pubg_weapons'[Bullet Type])
  )
  ```

- **Measure 3**: Calculate total damage by fire mode

  ```
  Total Damage by Fire Mode = 
  CALCULATE(
      SUM('pubg_weapons'[Damage]),
      ALLEXCEPT('pubg_weapons', 'pubg_weapons'[Fire Mode])
  )
  ```

## Results

- Total damage across all weapons: 2787.
- Total weapon count: 44.
- **Bullet Type Analysis**: 
  - 7.62 bullet type deals the highest damage at 790, followed by 5.56 at 624.
  - 5.56 bullet type has the highest weapon count at 11, followed by 7.62 at 9.
- **Fire Mode Analysis**: 
  - Automatic fire mode deals the highest damage at 1.41K, followed by Single at 0.70K.
  - Weapons with Single, Automatic, and Burst fire modes are the most common.
- **Weapon Type Analysis**: Shotguns and Assault Rifles lead in damage output.
- **Shots to Kill**: Headshots generally require fewer shots to kill compared to chest shots, with averages varying by bullet type.
- A Power BI dashboard was created to visualize these insights, including charts for damage by bullet type, fire mode, weapon type, and shots to kill.

## Contributing

Contributions are welcome! Please fork the repository and submit a pull request with your changes. For major updates, open an issue to discuss first.

## License

This project is licensed under the MIT License. See the `LICENSE` file for details.
