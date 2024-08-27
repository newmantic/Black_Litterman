# Black_Litterman

The Black-Litterman model is a sophisticated asset allocation model that improves on the Markowitz Mean-Variance Optimization framework by combining equilibrium market returns (derived from CAPM) with the investor's own views on expected returns. This results in more stable and intuitive asset allocations, especially when the investor has specific views about the market.


Implied Equilibrium Returns (Pi): The implied equilibrium returns represent the market's consensus on expected returns, derived from the market capitalization weights and the covariance matrix of asset returns.
Pi = lambda * Sigma * w_m
Where:
Pi is the vector of implied equilibrium excess returns.
lambda is the risk aversion coefficient.
Sigma is the covariance matrix of asset returns.
w_m is the market capitalization weights vector.
Incorporating Investor Views: Investors may have specific views on the expected returns of certain assets or groups of assets. The Black-Litterman model incorporates these views by adjusting the implied equilibrium returns.

View Matrix (P): P is a matrix that represents the investor's views on specific assets. Each row corresponds to a view, with coefficients that link the views to the assets.

View Vector (Q): Q is a vector of the expected returns based on the investor's views. Each element corresponds to the expected return of a specific view.

Uncertainty Matrix (Omega): Omega is a diagonal covariance matrix that represents the uncertainty in the investor's views. The diagonal elements represent the variances of the views.

Adjusted Expected Returns (mu): The new expected returns, adjusted for the investor's views, are calculated as:
mu = Pi + (tau * Sigma) * P^T * (P * (tau * Sigma) * P^T + Omega)^-1 * (Q - P * Pi)
Where:
mu is the vector of adjusted expected returns.
tau is a scalar reflecting the uncertainty in the prior estimate of the mean returns (often set to a small value like 0.025).
P is the view matrix.
Q is the view vector.
Omega is the uncertainty matrix.

Optimizing Portfolio Weights: With the adjusted expected returns (mu), the portfolio weights can be optimized using mean-variance optimization:
w* = (1 / lambda) * Sigma^-1 * mu
Where:
w* is the vector of optimal portfolio weights.
Sigma^-1 is the inverse of the covariance matrix.
lambda is the risk aversion coefficient.
