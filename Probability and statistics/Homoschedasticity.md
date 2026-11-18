*Equal variance across classes (homoschedasticity)*: this is the assumption that specifically distinguishes LDA (shared covariance) from QDA (class-specific covariance). It is **not** the same thing as comparing kurtosis across classes — kurtosis (tail heaviness relative to variance) and variance (spread) are distinct properties. The correct test here is:

| Test                                               | Null hypothesis                | Notes                                                                       |
| -------------------------------------------------- | ------------------------------ | --------------------------------------------------------------------------- |
| **Levene's test**                                  | All groups have equal variance | Robust alternative to Bartlett's test                                       |
| **Brown-Forsythe** (Levene with `center='median'`) | All groups have equal variance | More robust to outliers/heavy tails — preferable when normality is in doubt |
| **Bartlett's test**                                | All groups have equal variance | Very sensitive to non-normality; only reliable if data is close to Gaussian |
|                                                    |                                |                                                                             |
