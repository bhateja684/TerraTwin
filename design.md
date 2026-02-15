Project: Rural Ecosystem Digital Twin
Project Name: TerraTwin
Team Name: AsteronX

1. Problem Statement
Rural ecosystems and infrastructure evolve continuously due to changes in vegetation, rainfall, land use and human activity. Most existing systems focus only on static detection (crop classification, vegetation monitoring) or basic forecasting. There is no integrated framework that models rural regions as dynamic spatial systems and enables simulation of intervention-based futures.
This project addresses that gap by building a satellite-driven Rural Ecosystem Digital Twin capable of forecasting natural ecosystem evolution and simulating counterfactual scenarios using generative modeling.

2. System Architecture

2.1. Data Acquisition Layer
> Sentinel-2 multi-temporal satellite imagery
> Rainfall datasets (CHIRPS / IMD)
> Elevation data (SRTM DEM)

2.2. Preprocessing Layer
> Cloud masking and noise reduction
> NDVI and NDWI computation
> Raster reprojection and spatial alignment
> Multi-channel raster stacking
> Patch extraction (64×64 or 128×128)

2.3. Ecosystem State Representation
> Multi-channel raster tensor representation X_t
> Channels representing vegetation, water, terrain and built-up indicators
> Structured spatial input for modeling

3. Dual Intelligence Engine

3.1. Baseline Prediction Engine
> Input: Current ecosystem state tensor (X_t)
> Model: ConvLSTM or Temporal CNN
> Output: Predicted next-state raster (X_{t+1})
> Learns natural spatio-temporal transition patterns

3.2. Conditional GAN Simulation Engine
> Generator: U-Net architecture
> Discriminator: PatchGAN
> Input: Current state tensor + climate variables + intervention vector
> Output: Simulated future ecosystem raster
> Intervention parameters may include:
> > Tree cover increase
> > Rainfall reduction
> > Water extraction adjustment
> > Land-use modification

4. Sustainability Scoring Framework

4.1. Index Extraction
> Vegetation health (NDVI-based)
> Water stability (NDWI-based)
> Tree cover density
> Land-use balance indicators

4.2. Composite Sustainability Score
> Weighted aggregation of ecological indices
> Normalized score between 0–100
> Comparison across current, predicted and simulated futures

5. System Workflow

> Satellite data ingestion
> Ecological feature extraction
> Multi-channel state construction
> Parallel execution of prediction and simulation engines
> Sustainability scoring
> Visualization and comparison
