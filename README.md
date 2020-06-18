# Benchmark

## Goals

The final goal is to show the abilities of the applicants in programming, testing, managing a repository, define a documentation, for a simple software project.

This work requires a bit of Go, Docker and distributed services knowledge.

It is required to implement a client that emulates the basic functionality of Apache Benchmark (`ab`) for measuring performance of an HTTP service. At least, the client must implement the `-n`, `-c` and `-k` parameters of ab (see [jig/docker-ab/README.md](https://github.com/jig/docker-ab)) and provide latency and TPS of the service.

It shall be implemented on Linux. You may use virtualisation for that, but assign all cores you have to it and enough RAM memory.

## Tasks

1. execute Apache's `ab` on your computer to test a simple web server. You may use `nginx`, `tomcat` or other web servers to understand the typical numbers of latency vs. TPS depending on the concurrency (`-c`). Try to understand the figures you obtain and reason about it. Check the usage of CPU (e.g. with `top`) and try to obtain the best configuration for best performance. Verify that all connections end up with no error.

1. implement `ab` in Go (`goab`) and implement the `-n`, `-c` and `-k` parameters. Implement following metrics:
  - Transactions Per Second (TPS)
  - Average latency
  - Errored responses (amount, percentage %)

    Test your HTTP server of choice with `goab`. Compare results with `ab` to verify your implementation is sound.

1. implement an HTTP server in Go (`httpserver`). Compare results with the off the shelf server of you your choice.
