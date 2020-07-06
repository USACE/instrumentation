# Instrumentation

Project Management, Issue Tracking, and Documentation for the Instrumentation Project

## Current Status

__2020-07-06__: Prototype-level software is under development with a focus on the Herbert Hoover Dike (HHD) project. Remaining tasks for the HHD project to be completed in 2020 are detailed in the [burndown list here](2020_burndown_hhd.md)

## Code Repositories 

### Application Programming Interface (API)

Repository: https://github.com/USACE/instrumentation-api

### User Interface (UI)

Repository: https://github.com/USACE/instrumentation-ui

### Data Collection (DCS)

Repositories

- [instrumentation-dcs]() is a containerized version of [OpenDCS](https://hdsc.nws.noaa.gov/pub/hads/shef_products/OPENDCS-LRGS-UserGuide.pdf)

- [instrumentation-dcs-config]() is the configuration information for instruments, instrument message decoding, and datasources required by `instrumentation-dcs` at runtime.  Managing the configuration information in a git repository facilitates continuous integration and deployment.

