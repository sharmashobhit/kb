# Availability Numbers

| Availability (%) | Downtime/Day | Downtime/Week | Downtime/Month | Downtime/Year |
| ---------------- | ------------ | ------------- | -------------- | ------------- |
| 99%              | 14.40 min    | 1.68 hrs      | 7.31 hrs       | 3.65 days     |
| 99.99%           | 8.64 sec     | 1.01 min      | 4.38 min       | 52.60 min     |
| 99.999%          | 864.00 ms    | 6.05 sec      | 26.30 sec      | 5.26 min      |
| 99.9999%         | 86.40 ms     | 604.80 ms     | 2.63 sec       | 31.56 sec     | 


# Back of the envelope calculations

| Unit     | Approximation |
|:-------- | ------------- |
| Bit      | 1             |
| Byte     | 8             |
| Kilobyte | 10^3 B        |
| Megabyte | 10^6 B        |
| Gigabyte | 10^9 B        |
| Terabyte | 10^12 B       |
| Petabyte | 10^15 B       |


- Seconds in a day = 60 * 60 * 24 = 86400

1 Million events/day => 12 QPS
i.e.

for 20 million events/day = 12 * 20 = 240 QPS


# Framework

- Functional Requirements
- Non Functional Requirements
- Rough Estimations
- Communication interface/API
- High Level Design
- Data Modeling/ERD
- Authentication
- Authorization
- Security
- Reliability
- Scalibility
- Exception Handling
- Fault tolerance
- Error Handling
- Schema
- Monitoring
- Concurrency
- Latency
- Tradeoffs
