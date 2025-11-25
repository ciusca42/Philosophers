# Philosophers

## Overview

This repository contains an implementation of the classic **Dining
Philosophers Problem**, as required by the 42 School curriculum. The
program simulates philosophers sitting around a table who alternate
between **thinking**, **eating**, and **sleeping**, while competing for
shared forks. The goal is to manage concurrency so that no deadlocks or
race conditions occur and to detect philosopher "death" when a
philosopher doesn't eat within `time_to_die`.

------------------------------------------------------------------------

## Table of Contents

-   Overview
-   Features
-   Requirements
-   Build
-   Usage
-   Behavior & Rules
-   Concurrency & Synchronization

------------------------------------------------------------------------

## Features

-   Mandatory implementation using POSIX threads (`pthread`) and mutexes
    (one mutex per fork).
-   Accurate millisecond timestamping of actions.
-   Supervisor/monitor that detects philosopher death.
-   Optional parameter to stop when each philosopher has eaten a
    specified number of times.
-   Proper cleanup of resources (mutexes, threads, memory).

------------------------------------------------------------------------

## Requirements

-   POSIX-compliant system (Linux / macOS with POSIX support)
-   `gcc` (or other C compiler)
-   `make`
-   `pthread` library (link with `-pthread`)

------------------------------------------------------------------------

## Build

``` bash
git clone https://github.com/ciusca42/Philosophers.git
cd Philosophers
make
```

------------------------------------------------------------------------

## Usage

``` bash
./philo number_of_philosophers time_to_die time_to_eat time_to_sleep [number_of_times_each_philosopher_must_eat]
```

------------------------------------------------------------------------

## Behavior & Rules

-   Each action is printed with a timestamp and philosopher ID.
-   The simulation ends when a philosopher dies or, if the optional
    meals argument is provided, when all philosophers have eaten enough
    times.
    
------------------------------------------------------------------------

## Concurrency & Synchronization

-   Mutexes for each fork.
-   Deadlock prevention strategies.
-   Monitor thread for death detection.
-   Print mutex to avoid output overlap.
