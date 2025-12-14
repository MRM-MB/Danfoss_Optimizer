# Semester Project - Heat Production Optimization App

![.NET](https://img.shields.io/badge/.NET-512BD4?style=for-the-badge&logo=dotnet&logoColor=white)
![C#](https://img.shields.io/badge/c%23-%23239120.svg?style=for-the-badge&logo=c-sharp&logoColor=white)
![Avalonia](https://img.shields.io/badge/Avalonia-3F97E3?style=for-the-badge&logo=avalonia&logoColor=white)

**⚠️ Note for the Reviewer:**
This application uses CSV and JSON files in the `/Data` folder. You can test the optimization with sample data for heat demand and electricity prices.

## 📖 Table of Contents
- [Getting Started](#-getting-started)
- [Project Overview](#-project-overview)
- [Features](#-features)
- [Project Structure](#-project-structure)
- [Contributors](#-contributors)
- [Scenarios](#-scenarios)
- [Screenshots & Assets](#-screenshots--assets)

## 🚀 Getting Started

Run the application in two modes:

### GUI Mode
From the project root, run:
```bash
dotnet run
```
This starts the Avalonia-based graphical interface.

### Console Mode
From the project root, run:
```bash
dotnet run -- --term
```
This starts the original console-only version.

## 📌 Project Overview

This app automates district heating schedules for the city of Heatington. It finds the cheapest way to meet heat demand while maximizing electricity market profits. Built with **Avalonia** for a modern UI and modular design for clear data flow.

## 🎯 Features

- **Cost Optimization**: Calculates the cheapest mix of heat units hour by hour.
- **Dark Mode**: Toggle between light and dark themes.
- **Downtime Management**: Enable or disable individual machines for maintenance.
- **Customizable Unit Settings**: Edit production values, costs, and limits for each machine.
- **Modules**:
  - **Asset Manager (AM)**: Static data for machines and grid layout.
  - **Source Data Manager (SDM)**: Time series for heat demand and electricity prices.
  - **Result Data Manager (RDM)**: Saves optimization results to CSV.
  - **Optimizer (OPT)**: Core logic for schedule generation.
  - **Data Visualization (DV)**: Graphs for demand, production, costs, and emissions.
- **Unit Testing**: Verifies that methods and modules work correctly. We wrote:
  - 4 tests for Asset Manager (AM)
  - 3 for Source Data Manager (SDM)
  - 3 for Optimizer (OPT)
  - 2 for Result Data Manager (RDM)
  - 2 for User Interface (UI)
  - 4 functional tests

## 📁 Project Structure

```plaintext
DanfossHeating/
├── Assets/
│   ├── Danffy/          # UI screenshots
│   ├── Group3/          # Team photos
│   ├── Machines/        # Unit images
│   └── README/          # Images referenced by README
├── Converters/          # Data converters for UI
├── Data/                # CSV and JSON data files
├── Models/              
│   ├── AssetManager/    
│   ├── Optimizer/       
│   ├── ResultDataManager/
│   └── SourceDataManager/
├── ViewModels/          # UI logic
├── Views/               # UI layouts
├── Program.cs           # Entry point
└── README.md            # This file

DanfossHeatingTests/
├── AssetManagerTests.cs
├── OptimizerTests.cs
├── ResultDataManagerTests.cs
├── SourceDataManagerTests.cs
└── UITests.cs
```

## 👥 Contributors

| Name | GitHub Profile |
|------|----------------|
| **Luigi** | [Lucol24](https://github.com/Lucol24) |
| **Carolina** | [chaeyrie](https://github.com/chaeyrie) |
| **Gabriele** | [Gabbo693](https://github.com/Gabbo693) |
| **Lara** | [Lara-Ghi](https://github.com/Lara-Ghi) |
| **Mats** | [mqts241](https://github.com/mqts241) |
| **Manish** | - |

### File Responsibilities

| File | Contributor | Description |
| :--- | :--- | :--- |
| **AssetManager.cs** | Manish, Luigi, Carolina | Manages static data for machines, grid layout, and unit configuration. |
| **ProductionUnit.cs** | Manish, Luigi, Carolina | Defines the properties and behaviors of individual heating units (Gas Boiler, Oil Boiler, etc.). |
| **Optimizer.cs** | Manish, Gabriele, Mats | Core logic for calculating the cheapest mix of heat units to meet demand. |
| **ProductionSchedule.cs** | Manish, Gabriele, Mats | Represents the generated production schedule and optimization results. |
| **SourceDataManager.cs** | Manish, Gabriele, Lara | Handles loading and processing of time-series data for heat demand and electricity prices. |
| **HeatDemand.cs** | Manish, Gabriele, Lara | Data model representing heat demand entries from source files. |
| **ResultDataManager.cs** | Manish, Gabriele, Carolina, Luigi, Lara | Manages the export of optimization results to CSV files. |
| **ResultEntry.cs** | Manish, Gabriele, Carolina, Luigi, Lara | Data model for a single row of optimization results. |
| **MainWindowViewModel.cs** | Everyone (DV Team) | Main view model handling navigation, theme switching, and global state. |
| **OptimizerViewModel.cs** | Everyone (DV Team) | View model for the optimization page, connecting the UI to the Optimizer logic. |
| **MachineryViewModel.cs** | Everyone (DV Team) | View model for the machinery page, allowing users to configure unit parameters. |
| **CostViewModel.cs** | Everyone (DV Team) | Handles logic for displaying cost-related data and visualizations. |
| **CO2EmissionViewModel.cs** | Everyone (DV Team) | Handles logic for displaying CO2 emission data and visualizations. |
| **Unit Tests** | Everyone | Test suites for verifying the functionality of AM, OPT, SDM, RDM, and UI. |

- **UML Diagram:** [Mats](https://github.com/mqts241)

---

## 🔧 How to Run

1. **App:** Open a terminal in the `DanfossHeating` folder and run:

   ```bash
   dotnet run
   ```

2. **Tests:** Open a terminal in `DanfossHeatingTests` and run:

   ```bash
   dotnet test
   ```

---

## 📊 Scenarios

- **Scenario 1:** Two gas boilers and one oil boiler.
- **Scenario 2:** Gas boiler, oil boiler, gas motor (produces electricity), and heat pump (consumes electricity).

---

## 🖼️ Screenshots & Assets

Below is a quick visual tour of the app’s main features:

- **Welcome Page**  
  ![Welcome Page](DanfossHeating/Assets/README/welcome_page.png)

- **Home Page**  
  ![Main UI](DanfossHeating/Assets/README/main_ui.png)

- **Dark Mode Overview**  
  ![Dark Mode](DanfossHeating/Assets/README/dark_mode.png)

- **Machinery Configuration**  
  ![Machinery Configuration](DanfossHeating/Assets/README/machinery_page.png)

- **Optimizer Schedule Flow**  
  ![Optimizer Flow](DanfossHeating/Assets/README/optimizer_diagram.png)

- **Electricity Prices**  
  ![Electricity Prices](DanfossHeating/Assets/README/electricity_prices.png)

- **Production Cost Overview**  
  ![Production Cost](DanfossHeating/Assets/README/production_cost.png)

- **CO₂ Emissions Chart**  
  ![CO₂ Emissions Chart](DanfossHeating/Assets/README/CO2_emissions.png)
