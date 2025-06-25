graph TD
    S0(Bomba OFF, Q=0) -- C=0 --> S1
    S1(Bomba ON, Q=1) -- C=1 --> S0
    S0 -- C=1 --> S0
    S1 -- C=0 --> S1
