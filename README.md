# Spatial Analysis of Housing Prices

## Project Overview
This project applies spatial statistics, geostatistics, and Bayesian modeling to analyze and predict housing sale prices using geographic location data.
Using R, this analysis compares a traditional Ordinary Kriging approach with a Bayesian spatial modeling estimated using Markov Chain Monte Carlo (MCMC).

This project demonstrates a complete spatial analysis workflow including:

- Spatial data preparation
- Geographic visualization
- Spatial autocorrelation testing
- Empirical variogram estimation
- Covariance model comparison
- Ordinary Kriging
- Bayesian spatial modeling
- MCMC convergence diagnostics
- Spatial prediction and uncertainty analysis

## Research Objective
Housing observations are spatially referenced using longitude and latitude coordinates.
The primary objective is to determine whether housing sale prices exhibit spatial dependence and, if so, use that spatial structure to model and predict housing prices.

## Frequentist Spatial Modeling
- Variogram estimation
- Covariance model selection
- Ordinary Kriging

## Bayesian Spatial Modeling
- Gaussian spatial process
- Prior distributions for spatial parameters
- MCMC estimation
- Posterior inference
- Convergence diagnostics

## Analytical Workflow

## 1. Data Preparation
   Housing data are cleaned and converted into spatial objects using geographic coordinates

   The spatial workflow includes
   - Removal of observations with missing coordinates or sale prices
   - Conversion of longitude and latitude into spatial features
   - Coordinate reference system transformation
   - Construction of spatial coordinates for distance - based analysis

## 2. Exploratory Spatial Analysis
   Housing observations are mapped to examine their geographic distribution and identify potential spatial patterns.
   Exploratory analysis includes:
   - Geographic visualization of housing observations
   - Examination of housing/building types
   - Assessment of clustering and spatial patterns.
  
## 3. Spatial Autocorrelation
   Before applying kriging, spatial dependence in housing prices is evaluated to determine appropriateness of methodology using:
   ## Moran's I
   Moran's I measures global spatial autocorrelation and evaluates whether similar housing price values tend to occur near one another.

   ## Geary's C
   Geary's C provides an additional measure of spatial dependence and is more sensitive to local differences between neighboring observations.

   Together, these statistics provide evidence about whether housing prices contain sufficient spatial structure to justify geostatistical modeling.

## 4. Variogram Analysis
   An empirical semivariogram is constructed to measure how housing price similarity changes as geographic distance increases.

   The primary spatial parameters are:
   - Nugget (τ²): Small scale variation or measurement error
   - Partial Sill (σ²): Variability attributable to spatial dependence
   - Sill (τ² + σ²): Total spatial variance
   - Range (φ): Distance over which spatial correlation persists

  Four covariance/variogram models are evaluated:
  - Matern
  - Exponential
  - Gaussian
  - Spherical

  Model fit is compared to determine which covariance structure best represents the empirical spatial dependence.

## 5. Ordinary Kriging
   Ordinary Kriging is used to predict housing sale prices at unobserved geographic locations.
   The prediction at an unobserved location is constructed as a weighted combination of nearby observations, where the weights depend on the estimated spatial covariance structure.
   The selected variogram model is used to create a spatial prediction surface for housing prices.

## 6. Bayesian Spatial Modeling
   The frequentist kriging model is compared with a Bayesian spatial modeling.

   The Bayesian framework treats spatial parameters as uncertain quantities and estimates their posterior distributions rather than treating estimated covariance parameters as fixed.

   The spatial model contains parameters describing:
   - Nugget Variance (τ²)
   - Partial Variance (σ²)
   - Spatial decay/range (φ)

   Posterior distributions are estimated using Markov Chain Monte Carlo.

   The Bayesian approach allows uncertainty in the spatial covariance parameters to be incorporated directly into statistical inference.

## 7. MCMC Diagnostics
    Multiple MCMC chains are evaluated to determine whether posterior sampling has adequately converged.
    Diagnostics include:
    - Trace plots
    - Posterior density plots
    - Autocorrelation Function (ACF) plots
    - Effective Sample Size (ESS)
    - Gelman - Rubin diagnostic
    - Geweke diagnostic

    These diagnostics evaluate chain convergence, mixing behavior, autocorrelation, and the reliability of posterior estimates.

## Key Visualizations
## Spatial Distribution of Housing Observations
   Geographic visualization of housing observations used in the spatial analysis.

## Variogram Model Comparison
   Empirical spatial dependence compared with fitted Matern, exponential, Gaussian, and spherical variogram models.

## Kriging Predictions
   Spatial predictions of housing sale prices using Ordinary Kriging.

## Bayesian MCMC Trace Plots
   Trace plots are used to assess mixing and convergence of the Bayesian spatial model parameters.

## Posterior Distributions
   Posterior distributions quantify uncertainty associated with the spatial covariance parameters. 

## Technologies and Methods
## Programming
- R

## Spatial Analysis
- sf
- Geostatistics
- Spatial autocorrelation
- Moran's I
- Geary's C
- Variogram modeling
- Ordinary Kriging

## Bayesian Statistics
- Bayesian spatial modeling
- Gaussian processes
- Markov Chain Monte Carlo
- Posterior inference
- MCMC convergence diagnostics

## Statistical Concept 
- Spatial covariance
- Nugget
- Partial sill
- Range
- Spatial prediction
- Uncertainty qualification

  
## Repository Structure

R/        Analysis scripts
data/     Analysis datasets for data - source instructions
figures/  Selected model diagnostics and visualizations
results/  Model estimates and comparisons
thesis/   Complete Master's thesis

## Author

## Antonio Garcia
M.S. Applied Statistics
California State University, Long Beach
