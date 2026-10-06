# Helios Capacity Command

A self-contained, educational 24-hour hospital-transfer simulation for the Digital Business Transformation workshop.

## Run locally

Double-click `index.html`, or open it in a current version of Chrome, Edge, Firefox, or Safari. No server, API key, package installation, or external library is required.

## Publish with GitHub Pages

1. Create a new public GitHub repository, for example `helios-capacity-command`.
2. Upload `index.html` and this `README.md` to the repository root.
3. Open **Settings → Pages**.
4. Under **Build and deployment**, select **Deploy from a branch**.
5. Select the `main` branch and `/(root)`, then save.
6. GitHub will show the public URL after deployment.

## What is simulated

- A regional transfer coordination centre routes referred emergency patients.
- The 24-hour day runs from 12:00 to 12:00, with time-dependent demand.
- Every decision shows current operational data and a six-hour usable-bed forecast.
- Bed occupancy is time-based: a patient occupies one bed from hospital arrival until the simulated bed-use period ends. If that release occurs before the six-hour horizon, the bed is counted as free at `+6h`.
- Human and AI decisions run in separate but comparable state tracks.
- A hindsight benchmark uses the realized future to estimate the best available decision.
- Forecasts are evaluated six simulated hours after they are made.
- The AI begins with hard clinical constraints, is pre-calibrated on 600 synthetic scenarios, and continues recalibrating from forecast errors during play.
- A stress-test control generates 1,200 synthetic normal, surge, night, stale-data, herding, and specialist-conflict cases.

The game is not a single-correct-answer quiz. Multiple hospitals can be clinically suitable. The AI-preferred option is the highest expected trade-off across clinical fit, estimated time to admission, current and six-hour capacity, staff pressure, data freshness, travel time, and preservation of scarce maximum-care resources. Suitable alternatives can still produce strong scores.

The active screen is intentionally decision-focused. Detailed forecast evaluation runs in the background and is summarized at the end rather than displayed as a technical ledger during play.

## Important limitations

This is a workshop prototype, not a trained clinical AI system. All patients, capacity values, staffing, travel times, outcomes, and demand patterns are synthetic. Public hospital descriptions inform broad service profiles only. The simulator must not be used for patient care or operational decisions.

No model can test every possible real-world scenario. The prototype makes its tested scenario families and residual uncertainty visible instead of claiming exhaustive validation.

## Hospital profiles

- Helios Mariahilf Klinik Hamburg: basic and regular care with emergency, paediatric, obstetric, and selected general specialties.
- Helios Klinikum Uelzen: regional specialist care including cardiology, neurology/stroke, trauma, and emergency medicine.
- Helios Kliniken Schwerin: maximum-care role in the simulation with advanced cardiac, neurological, intensive, and trauma capabilities.

These profiles are deliberately simplified for teaching. Capacity and staffing do not represent the hospitals' real operational state.

Public profile references:

- https://www.helios-gesundheit.de/standorte-angebote/kliniken/hamburg/
- https://www.helios-gesundheit.de/standorte-angebote/kliniken/uelzen/
- https://www.helios-gesundheit.de/standorte-angebote/kliniken/schwerin/leistungen/fachbereiche/
