# HMM-Fingerprinting
Indoor positioning system using Hidden Markov Models

Description: 
An algorithm using HMM to locate mobile sensor signals from beacons placed in a room or building. In an open area, the
signal strength of a message decreases as the distance between the transmitter and the receiver increases; therefore,
the strength of the signal received can be directly used to estimate the position of the sensor. However, this is not the
case in buildings. The same message can be received with different signal strengths due to reflection and scattering.
One way to overcome this problem is to collect the signal strengths for each position and construct a probability
distribution. This procedure is called fingerprinting.

The indoor environment is represented by a grid where each cell corresponds to a state in the HMM, which makes
the total number of states n state = (width * length). Thus, a probability distribution of the location of the
target sensor is a vector of length n states. The transition probabilities P(St+1|St) are stored in a 2-dimensional
NumPy array, which can be accessed through self.trans probs. For example, the transition probability from
State 1 to State 3 can be obtained by self.trans prob[3,1]. In each time step, the sensor receives an observation vector o of length n beacons. The Received Signal Strength Indicator (RSSI) value of the message received
from the beacon b is stored in o[b]. The probability of observing o[b] in a particular state s, P(O(b) = ob|S = s),
can be obtained by self.obs probs[b,o[b],s]. Here, we assume the RSSI values of different messages are
conditionally independent. Therefore, you can decompose the probability of observing the vector o, P(O = o|S = s)
into a product of individual likelihood functions:



Packages: 
$ pip install numpy matplotlib ipywidge
Test: 
$ python -m unittest hmm_test.py


