# Philosophers

A simulation of the dining philosophers problem using threads and mutexes.

## What it does

A number of philosophers sit around a table. Each philosopher alternates between eating, sleeping, and thinking. To eat, a philosopher needs two forks, one on each side. There are only as many forks as philosophers.

The program must ensure that no philosopher starves and that there are no deadlocks.

## Usage

```sh
./philo number_of_philosophers time_to_die time_to_eat time_to_sleep [number_of_times_each_philosopher_must_eat]
```

- `number_of_philosophers` — number of philosophers and forks
- `time_to_die` — time in ms before a philosopher dies if they have not eaten
- `time_to_eat` — time in ms it takes to eat
- `time_to_sleep` — time in ms spent sleeping
- `number_of_times_each_philosopher_must_eat` — optional, stops the simulation when all philosophers have eaten this many times

Example:

```sh
./philo 5 800 200 200
```

## Implementation

Each philosopher runs in its own thread. Forks are protected by mutexes. The simulation logs each state change with a timestamp.

A philosopher dies if the time since their last meal exceeds `time_to_die`. The program detects this and stops.

## Project context

This is a School 42 project. The goal is to understand concurrency, thread synchronization, and the risks of deadlock and data races in multi-threaded programs.