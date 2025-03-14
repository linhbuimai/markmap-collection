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
	- solve latency challenges
		- **feature computation latency** <-- time to compute features from raw data
		- **feature retrieval latency** <-- time for prediction services to retrieve computed features to compute prediction
		- **prediction computation latency** <-- time for a model to generate features from computed features