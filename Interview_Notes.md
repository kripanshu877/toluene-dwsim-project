# Interview preparation and resume wording

## Short explanation
This is an educational DWSIM simulation of n-heptane conversion to toluene and hydrogen. I built it with guidance, specified 15% conversion, checked balances, and manually varied downstream cooling temperature from 20 to 50 C. Higher temperature reduced cooling duty but increased hydrocarbon losses to gas. The model does not predict conversion or establish an economic optimum.

## Questions to prepare
- Why 15%? A specified assumption inherited from the reference, not an optimized result.
- Why a conversion reactor? Allows a stoichiometric balance study without kinetics. Cannot predict reactor size or catalyst requirements.
- Why 160 kmol/h from 100? Each mole reacted increases total moles by four; 15 x 4 = 60 extra kmol/h. Mass remains conserved.
- Why Peng-Robinson? Hydrocarbon/gas modelling approach following the reference. Industrial design would require property-data validation, particularly for dissolved hydrogen.
- Why reactor heating? The reaction is endothermic; isothermal operation requires heat input. E2's negative label reflects outgoing stream direction.
- Purity versus recovery? Purity is component concentration; recovery is the fraction captured. The liquid captures 96.82% of toluene but contains only 15.09 mol% toluene.
- Is toluene purified? No. The liquid also contains heptane; additional separation is outside scope.
- What did you troubleshoot? An erroneous heater pressure drop caused a property calculation error. Accidental outlet editing required separator recalculation to restore output. Do not invent other experience.
- Best temperature? No economic optimum established. The tested 20 C case gives best purity/recovery but highest cooling duty; product requirements and utility costs matter.
- Which software? DWSIM, with guided setup. Reading HYSYS screenshots is not hands-on HYSYS experience.

## Suggested resume entry
Process Simulation and Temperature Sensitivity Analysis | DWSIM
- Built a steady-state n-heptane-to-toluene flowsheet with a conversion reactor, heater, cooler and flash separator; checked material and energy balances at a specified 15% conversion.
- Compared five separation temperatures (20-50 C), quantifying a 7.59% reduction in cooling duty alongside hydrogen purity declining from 95.24 to 81.37 mol% and toluene recovery from 97.56 to 88.45%.

This is a scenario comparison, not achieved industrial savings. Read the notes and explain the calculations independently before an interview.
