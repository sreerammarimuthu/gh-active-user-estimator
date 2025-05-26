# GitHub Active-User Estimator

This project focuses on estimating the total number of active GitHub users using a stratified sampling approach over the GitHub ID space. Given the presence of missing or deleted accounts in GitHub’s ID structure, we design a method that provides unbiased and scalable estimations using exhaustive search on selected ID buckets.

The methodology involves dividing the ID space into fixed-size buckets, sampling with replacement, performing an exhaustive search within each sampled bucket, and using the resulting statistics to predict an estimate for the entire user base. The approach is validated on a smaller known range and then scaled to the entire ID space to evaluate consistency, reliability, and scalability of our method.

## Contents  
- `GH-active-user-est-validation.ipynb` - Runs the sampling + estimation method over a known GitHub ID range [1, 10,000]. Compares estimated total against actual ground truth and also includes bar plots to show bucket distributions.

- **Output:** Estimated total: `~9376`    Ground truth: `9390`

- `GH-active-user-est-main.ipynb` - Applies the method to the entire GitHub ID space. Runs two experiments with different sample sizes (10 and 20). Predicts estimated totals from sampled average bucket counts and includes graphs for average stability and unbiased estimation patterns among buckets.

- **Output:** Sample size 10: `~149.88M users`  Sample size 20: `~149.26M users`

## Estimation Approach  
Estimate total active users as:
N̂ = average × total_buckets

This repo demonstrates a scalable sound strategy for population estimation in large, sparsely populated online platforms like GitHub.
