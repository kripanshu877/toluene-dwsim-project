# Toluene production: saved-model verification

Inspected the XML stored inside Toluene_Production_BaseCase_25C.dwxmz. This is inspection of saved calculated results, not an independent rerun of DWSIM.

## Confirmed setup
- DWSIM saved object version: 10.2.3.0; Peng-Robinson property package.
- Feed: pure n-heptane, 100 kmol/h, 25 C, 101.325 kPa absolute.
- Heater outlet and actual reactor outlet: 426.67 C.
- Conversion reaction: C7H16 -> C7H8 + 4 H2, specified 15% conversion, vapor phase.
- Reactor: isothermic; unused liquid outlet stream 5 has zero mass and molar flow.
- Cooler outlet: 25 C. Separator temperature/pressure overrides are false; separator heat duty is zero.
- All 14 simulation objects have Calculated=true in the saved file.

## Base-case results
- Gas: 63.7838996 kmol/h, 507.16996 kg/h; hydrogen mole fraction 0.938933699.
- Liquid: 96.2161123 kmol/h, 9513.03452 kg/h; toluene mole fraction 0.150936460.
- Hydrogen gas purity: 93.8934 mol%; toluene liquid recovery approximately 96.82%.
- Liquid is a heptane/toluene mixture, not purified toluene.
- Heater input: 3760.82056 kW.
- Reactor heat input: 1053.49888 kW. Reactor DeltaQ is positive; connected outgoing E2 has negative EnergyFlow. Do not call this reactor cooling.
- Cooler heat removal: 3785.78954 kW.

## Energy check
Using saved TotalEnergyFlow values, which account for the chemical energy reference used by the model:
- Net external heat input = 1028.52990164 kW.
- Products minus feed total energy flow = 1028.52721285 kW.
- Balance residual = -0.00268879 kW (small numerical residual).
- Saved outlet mass exceeds inlet mass by about 0.0045 kg/h (approximately 0.000045%); do not describe closure as mathematically exact.

## Temperature sensitivity
These cases were manually run by the user and transcribed from screenshots; only the 25 C case is present in the supplied saved model.

| Temperature C | Cooler duty kW | Gas hydrogen mol% | Liquid toluene recovery % |
|---|---:|---:|---:|
|20|3825.17|95.24|97.56|
|25|3785.79|93.89|96.82|
|30|3743.79|92.23|95.86|
|40|3649.43|87.77|93.08|
|50|3534.69|81.37|88.45|

Higher separation temperature reduces cooling duty but increases hydrocarbon loss to gas. No economic optimum established; utility temperatures/costs and product specifications have not been evaluated.

## Scope and limitations
Educational steady-state simulation, recreated with guidance from an Aspen HYSYS example: https://github.com/itsAkshayKr/Aspen-Project . The user built this version in DWSIM. Conversion is prescribed, not predicted from kinetics or optimized. No catalyst sizing, detailed equipment design, distillation purification, recycle, industrial validation, or process-safety study. This supports entry-level process simulation skills, not HYSYS experience or a production-ready plant design.
