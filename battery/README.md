# Battery

## Discharge Rate

Approximate the discharge rate using Peukert's Law:
$$
C_{p} = I^{k}t
$$

Where:
- $C_{p}$ is the capacity at one-ampere discharge rate $(Ah)$.
- $I$ is the actual discharge current $(A)$.
- $t$ is the time to discharge the battery $(h)$.
- $k$ is the Peukert constant.

If $C_{p}$ is not given then approximate the discharge rate with:
$$
t = H\left(\frac{C}{IH}\right)^{k}
$$

Where:
- $H$ is the rated discharge time ($h$).
- $C$ is the rated capacity at that discharge rate ($Ah$).

> The discharging current should not be more than 1/10 of the rated capacity.

## Battery Life

The battery life formula is:
$$
b = \frac{Q}{I}
$$

Where:
- $b$ is the battery life $(hr)$.
- $Q$ is the battery capacity $(Ahr)$.
- $I$ is the current load $(A)$.

> A battery is effectively discharged at 2/3 of its rated capacity.

## Battery Capacity

The battery capacity formula is:
$$
E = VQ
$$

Where:
- $E$ is the battery energy $(Whr)$.
- $V$ is the battery voltage $(V)$.
- $Q$ is the battery capacity $(Ahr)$.
