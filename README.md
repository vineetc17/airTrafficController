# Air Traffic Control System 

This repository contains a simple Air Traffic Control (ATC) system implemented in C. The system manages the departure and arrival of planes at different airports and utilizes POSIX-compliant APIs for inter-process communication and message queues to ensure robust and standardized communication between processes.
 
## Description

1. **airport.c**: This file contains the code for managing departures and arrivals at airports.
   - Compares runways by their capacity for sorting purposes.
   - Handles the boarding, deboarding, takeoff of planes departing from an airport.
   - It also initializes airports, listens for departure and arrival messages, and coordinates plane movements.

3. **plane.c**: This file handles the creation of planes and their attributes such as ID, type, weight, departure, and arrival airports.
   - It creates planes, prompts users for plane details, sends takeoff requests to ATC, simulates flight time, and notifies ATC upon completion.

4. **airtrafficcontroller.c**: The ATC controller manages the flow of planes between airports.
   - It initializes the ATC controller, listens for messages from planes and airports, coordinates plane movements, and handles system termination.

5. **cleanup.c**: This file handles the termination of the ATC system.
   - It Prompts the user to terminate the system and sends the appropriate message to the ATC controller.

6. **structs.h**: This is a header file containing struct definitions and message types used across the system.

## Compilation

To compile the code, use the following commands:

```bash
gcc -o airport airport.c -lpthread
gcc -o plane plane.c
gcc -o ATC airtrafficcontroller.c
gcc -o cleanup cleanup.c
```

## Execution

Make sure that each instance of a plane and airport is running in different terminals. 
</br>Example: If you want to fly 3 planes and 2 airports then a total of 3+2+1+1 = 7 terminals would be open. 
</br>ATC and cleanup need only one terminal each.

```bash
./ATC
```
```bash
./airport
```
```bash
./plane
```
```bash
./cleanup
```

## Usage

1. Creating Planes:
   - Run the plane executable to create planes.
   - Enter the plane ID, type (0 for cargo, 1 for passenger), number of passengers/cargo items, weights, departure, and arrival airports.
2. Managing Airports:
   - Run the airport executable to initialize airports.
   - Enter the airport number and number of runways, as well as the load capacity of each runway.
3. Controlling Traffic:
   - The ATC controller manages the flow of planes between airports.
   - It coordinates departures, arrivals, and system termination.
4. Terminating the System:
   - Run the cleanup executable to terminate the ATC system.
   - Enter 'Y' to confirm termination.

## Requirements
- POSIX compliant system (Linux, Unix, macOS)
- C compiler (gcc recommended)

---
