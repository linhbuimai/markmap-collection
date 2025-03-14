---
title: Self-serve Feature Platform
markmap:
    maxWidth: 300
    colorFreezeLevel: 2
    embedAssets: true
    activeNode:
        placement: center
---

# self-serve feature platforms

## components

- feature engineering
- feature computation
- serving computed features

## why

- enable online prediction (along with the traditional batch prediction)
	- solve latency ![](https://huyenchip.com/assets/pics/feature-platform/latency.png)
		- ==feature computation== <-- time to compute features from raw data
		- ==feature retrieval== <-- time for prediction services to retrieve computed features to compute prediction
		- prediction computation <-- time for a model to generate features from computed features

- vs. **feature store**
    - is a component of feature platform
    - goals
        - reduce feature retrieval latency
        - stored computed features for models reusable
    
