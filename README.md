# Options-pricing-model
Options pricing model

The project implements a comprehensive suite of option pricing models, including the **Black-Scholes**, **Binomial Tree**, and **Monte Carlo Simulation** methods, each applied to both **call** and **put** options. Here's a more detailed technical summary of the project for inclusion:

### **Project Overview:**
This project is a technical deep dive into computational finance, focused on the pricing of European options. The notebook implements three key models: the **Black-Scholes Model**, **Binomial Option Pricing Model**, and **Monte Carlo Simulation**. These models offer distinct numerical approaches for calculating the price of options based on varying assumptions and computational techniques. The project is implemented in Python, leveraging scientific libraries such as **NumPy**, **SciPy**, **Pandas**, **Matplotlib**, and **yfinance**.

### **1. Black-Scholes Model:**
   - This model is based on solving the Black-Scholes-Merton partial differential equation analytically.
   - **Key Parameters**: 
     - \( S \): Current price of the underlying asset
     - \( K \): Strike price of the option
     - \( T \): Time to maturity (in years)
     - \( r \): Risk-free interest rate
     - \( \sigma \): Volatility of the underlying asset
   - The model calculates \( d_1 \) and \( d_2 \), which are used to derive the price of call and put options using the cumulative distribution function (CDF) of the standard normal distribution.
   - This method assumes continuous price paths for the underlying asset and constant volatility.

### **2. Binomial Option Pricing Model:**
   - A discrete-time model is used here, which constructs a recombining binomial tree for the evolution of the underlying asset's price over time.
   - **Key Parameters**:
     - \( steps \): The number of intervals in the time to maturity
     - \( u \), \( d \): The up and down factors for stock price movements, derived from volatility
     - \( p \): Probability of upward movement based on the risk-neutral measure
   - The option price is computed by backward induction, starting from the known payoff at expiration and working back through the tree to the current time.
   - This method is flexible enough to model both American and European options but is applied here specifically to European-style options.

### **3. Monte Carlo Simulation for Option Pricing:**
   - A **Monte Carlo simulation** is implemented to estimate the option price by simulating a large number of possible future price paths for the underlying asset.
   - **Key Steps**:
     - Simulating the asset’s price over time using geometric Brownian motion (GBM), with volatility and drift components.
     - For each simulated path, the payoff of the option is computed, and the results are averaged and discounted back to the present to estimate the option price.
   - Monte Carlo methods are especially useful for handling more complex option pricing scenarios where analytical solutions (like Black-Scholes) become intractable.

### **Technical Implementation:**
   - **NumPy**: Efficient handling of large arrays and numerical computations.
   - **SciPy**: Utilized for statistical functions, particularly for the cumulative normal distribution function in the Black-Scholes model.
   - **Matplotlib**: Used for plotting the results and comparisons between the different models.
   - **yfinance**: This library is used to fetch real-world stock data, allowing for testing and validation of the model using live market conditions.

### **4. Comparison and Visualization:**
   - The notebook compares the results from the **Black-Scholes**, **Binomial**, and **Monte Carlo** models. For both call and put options, the notebook visualizes the computed prices for various underlying stock prices, clearly demonstrating the differences between the models.
   - These visualizations highlight the convergence of prices across models for European options, as well as scenarios where differences might occur due to model assumptions or computational methods.

This project not only illustrates the theoretical foundations of options pricing but also provides practical, working implementations of the models. It demonstrates how these models can be used in financial engineering to make informed decisions about the pricing and risk management of derivatives.
