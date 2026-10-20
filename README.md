# Peru-Maternal-Literacy-Child-Mortality
Survey-weighted OLS analysis of maternal literacy and child mortality in Peru using 2017 IPUMS census microdata (R).


## Question
Is maternal literacy associated with lower child mortality in Peru, and does
the relationship hold after accounting for household wealth, internet access,
maternal age, and rural/urban location?

## Background
Child mortality is a widely used indicator of population health and
development. Prior research (Rezaeizadeh et al.; Breierova and Duflo, 2004)
links maternal education to better child health and survival, with the
relationship appearing stronger in low- and middle-income countries. Because
Peru is a middle-income country with large rural-urban gaps in resources, it
is a useful setting to test whether the pattern holds.

## Data
- **Source:** IPUMS International, Peru 2017 census (household-level
  microdata). Raw data is not included in this repo per IPUMS terms; request
  an extract from the IPUMS website.
- **Outcome:** Child mortality rate for each mother, defined as the proportion
  of her children born who did not survive.
- **Key predictor:** Maternal literacy (indicator), used as a proxy for
  maternal education.
- **Controls:** Rural residence, home ownership, car ownership, internet
  access, and mother's age.
- **Weights:** Person weights (PERWT) so estimates are nationally
  representative.

  ## Method
Survey-weighted OLS regression:

`chmortr = β0 + β1·lit + β2·rural + β3·ownership + β4·autos + β5·internet + β6·age + ε`

Hypotheses: β1 < 0 (literate mothers have lower child mortality), β2 > 0
(higher mortality in rural areas), and β3, β4, β5 < 0 (more household
resources and information access are associated with lower mortality). The
sign of β6 is ambiguous: older mothers may have more experience and
resources, but their children were born in earlier periods with worse
healthcare.

- Maternal literacy was associated with a **4.4-point lower** child mortality
  rate (p < 0.01).
- Rural households had a **1.5-point higher** mortality rate.
- The report recommends expanding rural education and healthcare access.

## Limitations
- Results show association, not causation. Literacy may reflect unobserved
  factors such as income, community health infrastructure, or access to care.
- Literacy is an imperfect proxy for years or level of education.
- Mortality is measured as a proportion of children born, so it covers
  different time periods for mothers of different ages.

## Files
- `index.html`: rendered R Markdown analysis (code, tables, and regression results)
- `Peru_Final_Report.pdf`: full written report

## Tools
R, survey-weighted regression, IPUMS census microdata
