# Football (soccer) Prediction Prompt for Gemini 2.5 Pro Preview 03-25

**Instructions:**

1. **Simple Copy and Paste:**
   - Copy the into Gemini 2.5 Pro Preview 03-25 with "Grounded with Google Search" toggled ON.
   - Leave temperature setting at 1.
   - Add the two playing teams and their odds, plus the draw at the bottom of the prompt and press ENTER.

2. **Execution:**
   - The output will provide the final prediction.
   - We highly recommend you read for little hints about both teams within the analysis, some of these are listed under the Scratchpad comments.
   - We do recommend looking at the 4.3 Reliability/Comeback/Choke/Timing Analysis.

3. **Rinse and Repeat:**
   - DO NOT COPY AND PASTE THE PROMPT AGAIN.
   - Under the previous analysis and prediction output, just copy and paste the next two teams playing below and press ENTER.


**Key Changes in V19:**

1.  **Enhanced Rotation Assessment (Multiple Sections):**
    *   **Mandated Search (4.4):** Added requirement to actively search for news/comments regarding team rotation policies for the specific match/competition.
    *   **Explicit Analysis (4.4):** Introduced structured assessment of Rotation Likelihood (High/Medium/Low) and Estimated Impact, considering league priorities, opponent strength, fixture congestion, and squad depth (especially J1 vs lower tiers).
    *   **Odds Context (4.1.1, 4.7):** Added consideration of whether extreme market odds might imply expectations about team strength/rotation, and mandated checking if the market odds seem to accurately reflect the likely impact of rotation identified in the analysis. This directly addresses misjudging rotation's impact vs market expectations.
    *   **Tactical Adjustment (4.5):** Requires inferring tactics based on the *expected rotated strength*, not just base team style.
    *   **Weighting Guidance (5):** Added specific advice on weighing Tier Gap vs Rotation effect, acknowledging J1 depth can often overcome rotation against lower tiers – addressing previous overestimation of rotation's levelling effect.

2.  **Refined Over/Under 2.5 Goals Prediction (4.2, 5):**
    *   **Form O/U% Context (4.2):** Explicitly stated that the O/U% calculated from recent form is only *one input* factor, not the sole determinant – addressing over-reliance on this metric.
    *   **Multi-Factor Synthesis (5 - O/U Prediction):** Mandated synthesizing multiple specific factors for the O/U prediction: Form O/U%, H2H O/U% (with relevance check), GF/GA averages, **Rotation Impact on Attack/Defence**, Inferred Tactics (cagey vs open), Weather, and Market Lean. Requires justifying contradictions with the market. This aims for a more robust O/U assessment than relying primarily on recent form trends.

3.  **Critical H2H Relevance Assessment (4.6, 5):**
    *   **Mandated Analysis (4.6):** Added explicit instruction to *critically assess the relevance* of H2H data based on recency, league context similarity, and potential impact of current factors like rotation.
    *   **Weighting Guidance (5):** Advised against overweighting old or contextually different H2H data – addressing feedback on over-reliance on H2H.

4.  **Increased Emphasis on Data Quality & Limitations (Multiple Sections):**
    *   **Acknowledged in Process (3, 4.1):** Added reminders to acknowledge and temper conclusions when dealing with data that is sparse or less reliable (e.g., lower tiers, U23 leagues).
    *   **Required in Justification (5):** Mandated stating clearly if key data points (like HT/FT, Timing) were unavailable or if data quality was generally low.

5.  **Enhanced Contextual Analysis (4.8, 4.9):**
    *   **Weather Impact (4.8):** Added prompting to link weather conditions to potential impacts favouring underdogs or affecting goal potential.
    *   **Home/Away Synthesis (4.9):** Explicitly requires incorporating rotation assessment and travel/climate factors into the synthesis.

These changes aim to create a more nuanced, context-aware analysis that better handles the complexities of cup competitions, rotation, varying data quality, and market dynamics, leading to more robust and potentially more accurate predictions.

**Key Changes in V18:**

**Weighted Items Across Predictions for Improvement:**

1.  **Dynamic Weighting of Form vs. H2H:** Instead of a fixed hierarchy, the prompt should encourage evaluating *which is more relevant* for the specific match.
    *   **Improvement:** Instruct the model to explicitly compare the strength/recency of the form signal vs. the strength/recency of the H2H signal. If H2H from the last 1-2 seasons strongly contradicts current form, *increase the weight given to H2H* or at least strongly favour a Draw/Double Chance prediction against the form team. Justify *why* one factor is being prioritised over the other in the final synthesis.

2.  **Integrating Odds as a 'Sense Check':** The odds reflect a consensus view incorporating factors the model might miss.
    *   **Improvement:** Instruct the model: "If your analysis strongly contradicts the implied probability from the betting odds (e.g., predicting a win for a >3.00 underdog against a <2.00 favourite), explicitly state this discrepancy. Discuss potential reasons the market view differs (e.g., underlying quality, motivation, key injuries not fully captured) and *re-evaluate the confidence* in your prediction, potentially adjusting it towards the market signal (e.g., to a Draw or Double Chance)."

3.  **Contextualizing Streaks:** Acknowledge that extreme runs are statistically less likely to continue indefinitely.
    *   **Improvement:** When analysing strong winning/drawing/losing streaks (e.g., >4-5 games), instruct the model to add a note on sustainability. "Consider if underlying performance metrics fully support the streak or if regression is likely. Temper confidence in predictions based solely on extending long streaks, especially against capable opponents or when contradicted by other factors like H2H/odds."

4.  **Balancing Season-Long vs. Recent Home/Away Data:** Avoid letting impressive season-long home/away records completely overshadow poor *recent* results in that location or concerning overall form.
    *   **Improvement:** In the Home/Away Synthesis step (4.9), instruct the model to specifically compare the *last 5 home/away results* against the *season-long home/away record* and explicitly state if recent performance deviates significantly from the overall average, giving more weight to the recent trend if it's consistent.

**Key Changes in V17:**

*   **Step 4.9 (Home/Away Strength Synthesis):** Now explicitly mandates integrating the findings from 4.3 (Reliability/Timing) into the assessment of the home/away dynamic, rather than just relying on league tables and recent form.
*   **Step 5 (Synthesize Key Findings):** Reinforces listing the findings from 4.3 as key factors influencing the plausible scenarios.
*   **Step 5 (Scoreline Selection):** Provides more direct guidance to use the ES/ST and Reliability/Choke findings when selecting the *most likely* scoreline(s) and assessing their probability, giving concrete examples (late goals, opponent scoring despite loss).
*   **Step 5 (Justification):** Strengthens the requirement to *explicitly* discuss how the Step 4.3 findings influenced the final prediction and scoreline, including how conflicts were resolved or weighted. It also requires acknowledging if this data was missing or insignificant.

This version should encourage the analysis process to give more weight to the specific timing and reliability patterns uncovered in Step 4.3 when formulating the final prediction, addressing the underutilization you identified.

##Update V16##
1. **Added system time:** Some users experiencing extreme out of date match searches.
2. **Added Continuation:** IF the output stops before finishing 5. Final Prediction, the user needs to type 'ENTER' to continue where the analysis (or steps) in the process stopped to continue.
3.  **Improved search results:** Directed google search using sofascore now provides more often correct HT/FT scores with the timestamps thus improving 4.2 Recent Form Analysis and 4.3 Reliability/Comeback/Choke/Timing Analysis.
