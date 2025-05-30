# Snap Dispatch Mission Management System

This project simulates a simplified version of a ride dispatch system where a central controller (`Snap`) manages missions and coordinates with drivers, similar to a logistics platform.

## Overview

The system is built using C++ and is designed to handle:

- Driver registration and mission assignment.
- Tracking mission status (ongoing or completed).
- Time-based mission scheduling.
- Reward calculation for completed missions.

## Features

### Mission Lifecycle
- Each mission has a unique ID, a start timestamp, and a reward amount.
- Missions are tracked by the `Driver` class and stored in time order.
- Missions are marked as completed when all conditions are met (duration, distance, etc.).

### Driver Capabilities
- A driver can:
  - Add missions.
  - Show current and completed missions.
  - Check for mission completion based on time/distance.
- Duplicate mission assignments are prevented.

### Classes

#### `Snap`
Acts as the controller, parsing input commands and invoking driver or mission functionalities.

#### `Driver`
Handles:
- Adding missions to a driver's schedule.
- Verifying and updating mission statuses.
- Outputting current mission data in a formatted way.

#### `Mission`
Stores:
- Mission metadata such as ID, start time, and reward.
- Logic for checking whether a mission is considered complete.

## Build Instructions

Use the provided `makefile` to compile the project:

```bash
make
```

To run the compiled binary:

```bash
./main
```

## Sample Commands (Expected Input)

The program reads input via standard input (cin) and supports commands like:

- `add_mission`
- `show_missions`
- `check_completed_mission`
- `assign_driver`
- `exit`

Exact command formats are defined in the `Snap` class parser.

## Example Output

```
missions status for driver 1:
mission: 1001
start timestamp: 162000
end timestamp: 162600
reward: 500
status: completed
```

## Notes

- This project demonstrates effective object-oriented design.
- Missions are sorted and inserted chronologically for efficient checking.
- All outputs follow a strict format for consistency and testing ease.

---