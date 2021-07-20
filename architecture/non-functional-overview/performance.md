# Performance

This chapter describes the results of a performance test, to give potential users an indication of the system requirements for the platform.

The Platform was tested with the following AWS setup:

Systems:

* **Specifications Component Server**: 2 CPU's, 8 GB RAM
* **Specifications Database Server**: 1 CPU, 2 GB RAM

Setup:

* **Front-end**: 2x Component Server
* **Middle-end**: 2x Component Server
* **Back-end**: 2x Component Server
* **ActiveMQ Front-Middle**: 1x Component Server
* **ActiveMQ Middle-Back**: 1x Component Server
* **Databases**: 1x DB Server

For the test to succeed, two requirements were to be met:

1. Switch 10.000 simulated OSLP devices under 5 minutes.
2. Switch 40.000 simulated OSLP devices under 5 minutes.

The results showed that both tests succeeded.

