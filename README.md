# Philosophers

An implementation of the classic Dining Philosophers problem - 42 School project.

## Overview

This project solves the Dining Philosophers problem, a classic computer science problem dealing with concurrent programming, resource sharing, and deadlock prevention. Each philosopher must eat, think, and sleep while sharing forks with their neighbors.

## Features

- **Thread Management**: Proper creation and joining of philosopher threads
- **Deadlock Prevention**: Solution avoids deadlocks and resource starvation
- **Resource Monitoring**: Tracks fork usage and philosopher states
- **Time Management**: Precise timing for eating, sleeping, and thinking actions
- **Death Detection**: Monitors philosophers to detect if any die from starvation

## Getting Started

1. Clone the repository:
```bash
git clone https://github.com/username/philosophers.git
```
2. Compile the program:

```bash
make
```
3. run the program with parameters : 

```bash
./philo [number_of_philosophers] [time_to_die] [time_to_eat] [time_to_sleep] [number_of_times_each_philosopher_must_eat(optional)]
```

## Structure


philosophers/
├── src/
│   ├── cleanup.c
│   ├── init.c
│   ├── main.c
│   ├── monitor.c
│   ├── mutex.c
│   ├── philosophers_utils.c
│   ├── philosophers.c
│   ├── time.c
│   └── utils.c
└── include/philosophers.h


## Implementation Details

- Uses mutexes to represent forks and prevent race conditions
- Implements a monitoring system to check if philosophers have died
- Provides utility functions for time management and thread synchronization
- Ensures memory is properly allocated and freed

## Requirements

The program takes the following arguments:

- number_of_philosophers: number of philosophers and forks
- time_to_die: time in milliseconds after which a philosopher dies if they haven't eaten
- time_to_eat: time in milliseconds that it takes for a philosopher to eat
- time_to_sleep: time in milliseconds that a philosopher spends sleeping
- number_of_times_each_philosopher_must_eat (optional): program stops when all philosophers have eaten this many times

## Testing 

```bash 
./philo 5 800 200 200     # Basic test
./philo 4 410 200 200     # Should not die
./philo 4 310 200 100     # Should die
./philo 5 800 200 200 7   # Should stop after each philosopher eats 7 times

```

## Notes
- All outputs are timestamped in milliseconds
- Program must not have data races or leaks
- Error handling is implemented for invalid inputs

