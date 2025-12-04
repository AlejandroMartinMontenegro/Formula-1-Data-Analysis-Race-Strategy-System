# Formula-1-Data-Analysis-Race-Strategy-System
This project is a complete Formula 1 analysis and prediction system written in C++.   It loads real F1 historical data (drivers, teams, races, standings, lap times, pit stops…) and provides multiple analytical and predictive tools, including driver and team performance forecasting, race strategy recommendations, and statistical reports. 

---
**Authors:** Alejandro Martín Montenegro y Alvaro Ros

**Year:** 2025

---
# Project Overview

This project implements a full Formula 1 analytics engine.  
Using real CSV files from historical F1 datasets, the program:

- Loads all racing information (drivers, teams, circuits, results…)
- Performs predictions for drivers and teams
- Analyzes correlations such as start-position impact
- Computes top drivers and teams over custom seasons
- Generates reports in external files
- Provides race-strategy recommendations (pit stops, tires, fuel, car setup)

---
# Repository Structure

**SRC**

| File | Description |
|------|-------------|
| `Circuit.cpp/hpp` | Circuit data structure and attributes |
| `Race.cpp/hpp` | Race information (location, year, circuit, etc.) |
| `Driver.cpp/hpp` | Driver entity |
| `Team.cpp/hpp` | Team entity |
| `DriverStandings.cpp/hpp` | Driver season performance |
| `TeamStandings.cpp/hpp` | Team season performance |
| `ResultsInfo.cpp/hpp` | Detailed race results per driver/team |
| `DataManager.cpp/hpp` | Loads all CSV files and builds object mappings |
| `CSVReader.cpp/hpp` | Internal CSV parser |
| `ResultsPredictor.cpp/hpp` | Predicts driver/team positions |
| `DrivingAnalysis.cpp/hpp` | Computes top drivers/teams and statistics |
| `StrategyRecommendation.cpp/hpp` | Pit stop, tires, setup, and fuel strategy engine |
| `main.cpp` | Interactive menu system |

 **DATABASE**
 | File | Description |
|------|-------------|
| `circuits.csv` | Circuit information |
| `races.csv` | Race calendar |
| `drivers.csv` | Driver list |
| `driver_standings.csv` | Drivers' seasonal points |
| `constructors.csv` | Teams |
| `constructor_standings.csv` | Teams' seasonal points |
| `results.csv` | Race results |
| `qualifying.csv` | Qualifying times |
| `lap_times.csv` | Lap-by-lap driver timing |
| `pit_stops.csv` | Pit stop logs |
| `status.csv` | Race status (DNF, etc.) |
| `sprint_results.csv` | Sprint race results |
| `seasons.csv` | Season reference table |

---
# Features
### **1. Driver Results Prediction**
- Predict final ranking based on historic performance  
- Option: global prediction or per-circuit prediction

### **2. Team Results Prediction**
- Predict expected results for constructors  
- Option: global prediction or per-circuit prediction

### **3. Start Position Impact**
- Computes how starting grid position affects finishing results  
- Uses correlation based on large historical samples

### **4. Top 5 Drivers Analysis**
- Selects best drivers between two seasons  
- Shows stats: consistency, wins, podiums, average finish…

### **5. Driver Report Generator**
- Saves analysis to an external file (`.txt`)

### **6. Top 5 Teams Analysis**
- Same analysis but for constructors

### **7. Team Report Generator**
- Saves team statistics to an external file

### **8. Pit Stop & Tire Recommendations**
Based on:
- Weather  
- Number of laps  
- Circuit length  

Outputs:
- Optimal number of pit stops  
- Recommended tire type

### **9. Fuel Strategy Recommendations**
Estimates:
- Fuel consumption  
- Fuel load strategy (light/heavy)  
- Adjustments based on weather and track length

### **10. Car Setup Recommendations**
Suggests adjustments based on:
- Circuit type (high downforce, high speed, etc.)  
- Weather

---
# Pipeline
1. **Data Loading**  
   - All CSV files in `/Database` are parsed by `DataManager`
   - Objects are stored in maps: circuits, races, drivers, teams, standings…

2. **User Menu**  
   - `main.cpp` shows an interactive menu  
   - Input is taken and passed to the correct module

3. **Prediction / Analysis Modules**  
   - Mathematical logic is inside:
     - `ResultsPredictor`
     - `DrivingAnalysis`
     - `StrategyRecommendation`

4. **Output**  
   - Printed in console  
   - Reports can be exported to external `.txt` files
