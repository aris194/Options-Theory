# Vanilla Options and Monte Carlo

A Python script for pricing vanilla European options using both the Black–Scholes analytical formula and Monte Carlo simulations. Includes theory, computation and visualization of option Greeks, expected payoffs, standard deviation of returns, and comparative analysis between numerical and analytical approaches.

This project serves as a core part of my CQF and quantitative finance development journey, with a roadmap toward exotic options, volatility modeling, and real market calibration.

---

## Features

- Black–Scholes pricing (Call & Put)
- Monte Carlo simulation engine for European options
- Option Greeks (Delta, Gamma, Vega, Theta, Rho)
- Geometric Brownian Motion path simulation
- Payoff histograms and statistics
- Visual comparison of Greeks vs spot price
- Extension to exotic options (Barrier, Asian, etc.)
- Distribution fitting for simulated payoffs

---

## Barrier Options

Barrier options are a type of **exotic derivative** whose payoff depends not only on the terminal price of the underlying asset but also on whether the asset has **crossed a preset barrier level** during the option's life.

This repo includes an implementation of the **Knock-Out Barrier Option**, where the option becomes worthless if the barrier is breached.

### Example: Down-and-Out Call

- **If** the asset price falls below the barrier at any point before maturity → the option is terminated.
- **Else**, payoff is the same as a vanilla European call: `max(S_T - K, 0)`

Barrier options require **path-dependent simulation**, making Monte Carlo a natural choice. The implementation modifies standard payoff functions to include barrier logic inside the simulation loop.

---

## Planned Additions

- Asian Options (arithmetic & geometric averaging)
- Volatility surface interpolation
- Real market data calibration
- American-style extensions via binomial trees

---

## Usage

All scripts are written in Python 3.10+ and require the following libraries:
- NumPy
- Pandas
- Matplotlib
- SciPy
- yFinance (for market data, optional)

Use `requirements.txt` to install dependencies in a virtual environment.

---

## License

For educational and personal use only.
