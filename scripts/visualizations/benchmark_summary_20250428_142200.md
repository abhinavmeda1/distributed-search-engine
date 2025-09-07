# Solr Benchmark Summary Report

Generated on: 2025-04-28 14:22:00

Target Solr URL: 
Benchmark timestamp: 2025-04-28T08:10:09Z

## Performance Summary

| Concurrent Users | Response Time (s) | Transaction Rate | Availability (%) | Success | Failures |
|------------------|------------------|-----------------|-----------------|---------|----------|
| 2 | 0.0 | 856.65 | 100.0 | 7727 | 0 |
| 3 | 0.0 | 1784.39 | 100.0 | 17720 | 0 |
| 5 | 0.0 | 1918.53 | 100.0 | 19051 | 0 |
| 11 | 0.0 | 4828.5 | 100.0 | 47947 | 0 |
| 13 | 0.0 | 4740.9 | 100.0 | 47172 | 0 |
| 17 | 0.0 | 4275.28 | 100.0 | 42539 | 0 |
| 19 | 0.0 | 4297.09 | 100.0 | 42757 | 0 |
| 23 | 0.01 | 4344.62 | 100.0 | 43229 | 0 |
| 29 | 0.01 | 3884.52 | 100.0 | 38653 | 0 |
| 31 | 0.01 | 3853.72 | 100.0 | 38307 | 0 |
| 37 | 0.01 | 3887.32 | 100.0 | 38640 | 0 |
| 41 | 0.01 | 3881.29 | 100.0 | 38580 | 0 |
| 43 | 0.01 | 3891.36 | 100.0 | 38719 | 0 |
| 47 | 0.01 | 3884.39 | 100.0 | 38572 | 0 |
| 53 | 0.01 | 3887.73 | 100.0 | 38644 | 0 |
| 59 | 0.02 | 3883.52 | 100.0 | 38641 | 0 |
| 61 | 0.02 | 3882.38 | 100.0 | 38552 | 0 |
| 67 | 0.02 | 3878.37 | 100.0 | 38551 | 0 |
| 71 | 0.02 | 3878.47 | 100.0 | 38552 | 0 |
| 73 | 0.02 | 3882.31 | 100.0 | 38630 | 0 |
| 79 | 0.02 | 3872.51 | 100.0 | 38454 | 0 |
| 83 | 0.02 | 3833.8 | 100.0 | 38108 | 0 |
| 89 | 0.02 | 3805.53 | 100.0 | 37865 | 0 |
| 97 | 0.03 | 3766.3 | 100.0 | 37437 | 0 |

## Key Findings

- Best response time: 0.0s at 2 concurrent users
- Maximum transaction rate: 4828.5 tps at 11 concurrent users
- **Scaling concern**: Response time increased significantly at higher concurrency levels

## Visualization Files

- response_time_{timestamp}.png - Response time vs concurrent users
- transaction_rate_{timestamp}.png - Transaction rate vs concurrent users
- availability_{timestamp}.png - Availability vs concurrent users
- success_failure_{timestamp}.png - Successful vs failed transactions
- combined_metrics_{timestamp}.png - Combined performance metrics
