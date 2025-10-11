#
# Monte Carlo valuation of European call option
# in Black-Scholes-Merton model
# bsm_mcs_euro.py
#
from multiprocessing import Value
import numpy as np

#Parametor values 
S0 = 100. # initial index level
K = 105. # strike price
T = 1.0 # time-to-maturity
r = 0.05 #riskless short rate
sigma = 0.2 # volatirity

I = 100000 # number of simulations 

# Valuation Algorism
z = np.random.standard_normal(I) #pseudorandom numbers
ST = S0 * np.exp((r - 0.5 * sigma ** 2)* T + sigma * np.sqrt(T) * z)
 # index values at maturity
hT = np.maximum(ST - K, 0) # inner values at maturity
C0 = np.exp(-r * T) * np.sum(hT) / I # Monte Carlo estimator

# Result Output
print("Value of the European Call Option %5.3f" % C0)
