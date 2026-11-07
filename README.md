
# F1 Lap Time Simulator (Monza)

Point-mass lap time simulator in Python, validated against real FastF1 telemetry.

## Results
- Track length from GPS data: 5,763 m (real: 5,793 m)
- Simulated lap: 80.08 s vs real qualifying lap: 80.16 s (-0.1%)
- Wing angle sweep: best at +6 deg over baseline, gain of only 0.24 s (very flat optimum)

## Method
1. Track geometry and curvature from FastF1 position data (smoothed)
2. Maximum cornering speed from grip and downforce
3. Forward pass (power and traction limits) and backward pass (braking limits)
4. Lap time = sum of distance / speed

## Validation
- First untuned run: -3.4% vs the real lap
- Tuned power (620 kW) and drag area (1.2 m2) within realistic ranges
- Some of the close match comes from errors cancelling out (braking slightly late, straights slightly slow)

## Limitations
- Point mass: no weight transfer, no tyre temperature, no ERS strategy
- Drag penalty from extra downforce is an assumption, so the wing result is a model finding, not a real setup recommendation

## Run it
Open the notebook in Google Colab and run all cells in order.

## Built with
Python, NumPy, SciPy, Matplotlib, FastF1
