# Black-Scholes Option Pricing & Risk Analytics
An implemention of the Black-Scholes model for European call and put options, featuring analytical Greeks, scenario analysis, sensitivity visualizations, and financial consotency tests.
## Project Overview
This project explores how option prices respond to changes in underlying asset prices, volatility, time to maturity, and interest rates. It combines financial theory with Python implementation, numerical validation, and visual analysis.
The project was developed as a quantitative finance learning and portfolio project.
## Objectives
- Implement Black-Scholes pricing for European call and put options.
- Calculate the analytical Greeks: Delta, Gamma, Vega, Theta, and Rho.
- Validate theoretical consistency using put-call parity and option price bounds.
- Examine model behavior through sensitivity visualizations and scenario analysis.
- Document model assumptions and limitations.
## Model
For a European option on a non-dividend-paying underlying asset, the Black-Scholes model prices a call as:

[C = S_0 N(d_1) - K e^{-rT} N(d_2)]

and a put as:

[P = K e^{-rT} N(-d_2) - S_0 N(-d_1)]

where:

[d_1 =\frac{\ln(S_0/K)+(r+\sigma^2/2)T}{\sigma\sqrt{T}}]

[d_2 = d_1-\sigma\sqrt{T}]

Notation
- (S_0): Current underlying asset price
- (K): Strike price
- (T): Time to maturity in years
- (r): Continuously compounded annual risk-free rate
- (\sigma): Annualized volatility
- (N(\cdot)): Standard normal cumulative distribution function
## Features
### 1. Option Pricing
- European call option pricing
- European put option pricing
### 2. Model Validation
- Put-call parity checks
- Theoretical option price bounds
- Input and edge-case validation
- Final consistency tests across multiple volatility scenarios
### 3. Risk Analytics
- Delta: sensitivity to the underlying asset price
- Gamma: sensitivity of Delta to the underlying asset price
- Vega: sensitivity to volatility
- Theta: sensitivity to the passage of time
- Rho: sensitivity to the risk-free interest rate
### 4. Sensitivity and Scenario Analysis
- Call price versus volatility
- Call price versus underlying asset price
- Call and put price comparison under low, base, and high volatility scenarios
## Illustrative Scenario Analysis
The notebook evaluates the following illustrative assumptions while keeping other parameters constant:
Parameter
| Parameter | Value |
|---|---:|
| Underlying price | 100 |
| Strike price | 100 |
| Time to maturity | 1 year |
| Risk-free rate | 5% |
| Volatility scenarios | 10%, 20%, 40% |

The scenario analysis illustrates how higher volatility increases both call and put values under the Black-Scholes framework.
These values are theoretical examples, not live market quotes or investment recommendations.

## Technology Stack
- Python
- NumPy
- SciPy
- Matplotlib
- Jupyter Notebook / Google Colab

## Repository Structure
black-scholes-option-pricing/

README.md

requirements.txt

.gitignore

notebooks/ > black_scholes_option_pricing.ipynb

results/ > figures/

## How to Run
### Option 1: Google Colab
- Open the notebook in Google Colab.
- Run all cells from top to bottom.
- Review the pricing outputs, validation tests, Greeks, charts, and scenario analysis.
### Option 2: Local Python Environment
- Install the dependencies:
- pip install -r requirements.txt
- Open the notebook with Jupyter notebook
Then open notebooks/black_scholes_option_pricing.ipynb and run the cells in order.
## Model Assumptions
The initial implementation assumes:
- European-style options, exercisable only at maturity.
- No dividends paid by the underlying asset.
- Constant volatility and risk-free interest rate over the option's life.
- A frictionless market with no transaction costs or arbitrage.
- Lognormally distributed underlying prices under the model assumptions.
## Limitations
The Black-Scholes model is a theoretical pricing framework. Actual market prices may differ because of volatility smiles, jumps, liquidity constraints, transaction costs, dividends, and changing interest rates.
This implementation is intended for education and quantitative analysis. It is not a trading system and does not provide investment advice.
## Acknowledgements & Feedback
AI tools were used as learning and development assistants throughout this project, helping me understand the Black-Scholes model, review implementation logic, troubleshoot errors, and improve the overall structure of the project.
I remain open to constructive criticism, feedback, and suggestions for improvement. I view this project as part of my ongoing learning journey in quantitative finance and Python-based financial modelling.
Suggestions regarding the mathematical implementation, code quality, testing methodology, and potential extensions are welcome.
## Future Improvements
- Add automated unit tests in a dedicated tests/ directory.
- Separate pricing and Greeks into reusable Python modules.
- Add dividend-adjusted Black-Scholes pricing.
- Implement numerical finite-difference checks for analytical Greeks.
- Explore implied volatility using market option data where reliable data are available.
## Disclaimer
This project is for educational and portfolio purposes only. It does not constitute investment advice or a recommendation to trade options.
