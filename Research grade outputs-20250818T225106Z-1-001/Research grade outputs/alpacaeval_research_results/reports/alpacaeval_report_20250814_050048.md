# Research-Grade AlpacaEval Evaluation Report
**Date:** 2025-08-14 05:00:48
**Test Provider:** ollama
**Reference:** default
**Judge:** ollama
**Length Metric:** Tokens (tiktoken cl100k_base)

---
## Evaluation Results

| Optimization | LC Win Rate (95% CI) | Raw Win Rate | Avg Length | Length Diff | W/L/T |
|-------------|---------------------|--------------|------------|-------------|-------|
| caching                   | 71.3 [55.9, 83.2]   |        55.0% |        484 |         -60 |  11/8/1 |
| semantic_dedup            | 60.8 [41.8, 75.1]   |        40.0% |        481 |         -63 |  8/12/0 |
| quality_weighting         | 59.9 [49.5, 81.9]   |        55.0% |        474 |         -70 |  11/8/1 |
| caching_second_run        | 58.2 [48.5, 73.0]   |        45.0% |        481 |         -63 |   9/9/2 |
| baseline                  | 57.7 [48.4, 72.7]   |        55.0% |        478 |         -65 |  11/8/1 |
| parallel_batching         | 52.0 [43.5, 68.6]   |        40.0% |        476 |         -68 |  8/11/1 |
| incremental_aggregation   | 49.9 [41.9, 65.0]   |        50.0% |        477 |         -66 |  10/8/2 |
| query_routing             | 48.2 [32.3, 59.4]   |        40.0% |        465 |         -78 |  8/11/1 |

---
## Key Findings

- **Best LC Win Rate:** caching (71.3% ± 13.7%)
- **Worst LC Win Rate:** query_routing (48.2%)
- **caching:** Length bias deflated raw win rate by 16.3%
- **semantic_dedup:** Length bias deflated raw win rate by 20.8%
- **caching_second_run:** Length bias deflated raw win rate by 13.2%
- **parallel_batching:** Length bias deflated raw win rate by 12.0%
- **query_routing:** Length bias deflated raw win rate by 8.2%

---
## Statistical Notes

- **LC Win Rate:** Length-controlled win rate using logistic regression
- **95% CI:** Bootstrapped confidence intervals (1000 iterations)
- **Position Bias:** Controlled via balanced randomization
- **Class Imbalance:** Handled with balanced class weights

---
## Citation

```bibtex
@article{dubois2024length,
  title={Length-Controlled AlpacaEval: A Simple Way to Debias Automatic Evaluators},
  author={Dubois, Yann and Galambosi, Bal{\'a}zs and Liang, Percy and Hashimoto, Tatsunori B},
  journal={arXiv preprint arXiv:2404.04475},
  year={2024}
}
```
