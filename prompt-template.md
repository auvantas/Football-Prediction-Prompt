**### Prompt V19 ###**

1.  **Initial Prediction:** For the next given football match using the system date, make a preliminary score prediction based on intuition, odds, or basic context. Save this prediction mentally or on a conceptual "scratchpad."
2.  **Analysis Target:** Focus analysis on the specific match provided.
3.  **Iterative Analysis Loop & Conceptual Data Handling:**
    Follow the "Data Check" steps (Step 4) below for the targeted match.
    *   **Conceptual Scratchpad & Context:** Throughout this process, findings are stored conceptually on a "scratchpad" used during the generation of the response. This collected information forms the basis for subsequent analysis steps. Check the scratchpad for completeness before moving to calculations or subsequent steps.
    *   **Dynamic Gap Filling & Persistence:** Actively attempt to fill data gaps identified during the process by performing additional, targeted searches as detailed in the relevant sections of Step 4. **Crucially, do not proceed to the next analytical calculation or step if the required input data (e.g., HT scores, goal times) for that step is marked as missing on the scratchpad.** Continue searching for the specific missing data point(s) using targeted queries until the data is found or confirmed as definitively unobtainable after reasonable attempts. Acknowledge clearly where data quality/availability is low (e.g., U23, lower tiers) and temper conclusions accordingly.
    *   **Iteration:** If newly found data significantly changes the picture (e.g., correcting form data, confirming rotation news), iterate through relevant parts of Step 4 again, refining the analysis based on the updated information on the scratchpad.
    *   **Prompt Chaining Context:** The complete analysis presented in the response becomes part of the conversation history, serving as context for subsequent prompts.
    *   **Continuation of Steps:** Retrieve previous output and stored scratchpad data to continue analysis from the last completed/incomplete step, ensuring required data is present.
4.  **Data Check:** Perform the following analysis points, using grounded search where necessary:

    **4.1 League Context:**
        *   **Objective:** Retrieve accurate, current league standings (Overall, Home, Away) and understand the competitive hierarchy.
        *   **Mandatory Search & Query Formulation:** Use `google_search` for league tables, team league levels.
        *   **Data Points to Extract:** League Name/Tier (e.g., J1, J2, T1, T2), Rank/Position, GP, Pts, W, D, L, GF, GA, GD for Overall, Home, Away.
        *   **Source Prioritization:** Official sites, reputable sports news (ESPN, BBC Sport), established stats sites (Soccerway, Fotmob, FBref).
        *   **Analysis:** Note the **tier difference** (e.g., J1 vs J2) and its typical implications on quality. Assess current league performance relative to expectations/tier. Acknowledge potential data limitations for lower tiers/youth leagues.
        *   **Conceptual Scratchpad Storage:** Store league data, tier difference, brief performance assessment, source/date, data quality notes.

    **4.1.1 Odds Search & Initial Market View:**
        *   **Objective:** Retrieve match betting odds and understand market perception.
        *   **Mandatory Search:** Use search if odds not provided.
        *   **Data Points to Extract:** 1X2, Over/Under 2.5 Goals. *Optional:* Double Chance, BTTS, Asian Handicap (AH) lines.
        *   **Analysis:** Identify market favourite and strength of favouritism. Note O/U 2.5 lean. **Consider if extreme odds (e.g., 1.10 or 12.00) might imply market expectations about team strength/rotation for cup matches.**
        *   **Conceptual Scratchpad Storage:** Store odds, market interpretation, note implications of extreme odds if applicable.

    **4.2 Recent Form Analysis (Last 10 Official Matches):**
        *   **Objective:** Analyze recent performance trends and context.
        *   **Mandatory Search & Data Collation:** Find 10 most recent official match results. **List opponent, competition, date, FT score**. Prioritize league > domestic cup > continental > other official.
        *   **Analysis (Based on listed 10 matches):**
            *   WDL Record & Sequence: Contextualize streaks (sustainability, quality of opposition during streak).
            *   Performance vs Opposition Quality: How did they fare against teams of similar/higher/lower standing (using 4.1 context)?
            *   Home/Away Form within last 10.
            *   GF/GA Averages & Trends (last 10).
            *   CS% & FTS% (last 10).
            *   O/U 2.5% (last 10): **Note this percentage as *one input only* for the final O/U prediction, not the sole determinant.**
        *   **Conceptual Scratchpad Storage:** Match list, WDL record/context, GF/GA averages, CS%, FTS%, O/U 2.5% (noted as partial factor).

    **4.3 Reliability/Comeback/Choke/Timing Analysis (Based on Last 10 Official Matches):**
        **4.3.1 HT/FT Score Retrieval (Mandatory Prerequisite):**
            *   Objective/Methodology/Checkpoint: [Unchanged - emphasize persistence, acknowledge limitations].
        **4.3.2 Reliability/Comeback/Choke Calculation:**
            *   Objective/Condition/Calculation/Limitations: [Unchanged - emphasize low confidence for small samples].
            *   **Conceptual Scratchpad Storage:** Calculated % (or inability statement), basis count, confidence note.
        **4.3.3 Goal Timing (ES / ST) Retrieval & Calculation (Attempt if Possible):**
            *   Objective/Methodology/Calculation/Final Statement/Storage: [Unchanged - emphasize difficulty/unavailability for lower leagues].

    **4.4 Team News, Injuries, and Rotation Assessment:**
        *   **Objective:** Identify absences and critically assess likely team strength, especially for cup matches.
        *   **Mandatory Search:** Search for significant injuries, suspensions, returns, **AND** general team news discussing rotation policy or manager's comments for the specific competition/match.
        *   **Analysis:**
            *   Assess impact of *confirmed key* absences/returns.
            *   **Crucially, assess Likelihood and Impact of Rotation:** Based on competition stage (early round vs QF/SF), league priorities (title race vs mid-table vs relegation battle), opponent strength (T1 vs T3 invites rotation), travel distance, fixture congestion, and *market signals* (do odds imply strong/weak team expected?).
            *   **Estimate Squad Depth:** Can the likely rotating team field competitive backup players, or is there a huge drop-off? (e.g., J1 depth > J3 depth).
        *   **Conceptual Scratchpad Storage:** Key personnel news, **Rotation Likelihood Assessment (High/Medium/Low)**, **Estimated Impact (High/Medium/Low)**, **Squad Depth Note**, overall impact assessment.

    **4.5 Situational and Tactical Context Analysis:**
        *   **Objective:** Understand broader match context.
        *   **Analysis:**
            *   Match Importance & Motivation: Consider league vs cup priority, derby/rivalry factor, potential for giant-killing/avoiding embarrassment.
            *   Infer Likely Tactics: Consider base styles, but adjust based on **expected team strength due to rotation (from 4.4)**, home/away status, and motivation. (e.g., Rotated favourite might be less cohesive/intense).
            *   Fixture Congestion & Fatigue (incl. travel impact).
            *   Managerial Context (pressure, style).
            *   Synthesize into contextual overview.
        *   **Conceptual Scratchpad Storage:** Notes on motivation, adjusted tactics, schedule, manager.

    **4.6 Head-to-Head (H2H) Analysis:**
        *   **Objective:** Analyze recent direct encounters, assessing relevance critically.
        *   **Mandatory Search:** Find results for last 4-6 official H2H meetings (include venue, competition).
        *   **Analysis:**
            *   Identify patterns (dominance, home adv, scorelines). Note venue-specific results.
            *   Calculate O/U 2.5% for these H2H games.
            *   **Critically Assess Relevance:** Is the H2H recent enough? Were teams in similar leagues/form then? Will rotation significantly change the dynamic compared to past H2H? **Avoid overweighting old or contextually different H2H data.**
        *   **Conceptual Scratchpad Storage:** H2H list, WDL summary, venue results, H2H O/U%, **Relevance Assessment Note**.

    **4.7 Betting Odds Comparison & Market Check:**
        *   **Objective:** Compare analysis with market view, identify potential value.
        *   **Analysis:**
            *   Retrieve 1X2 & O/U 2.5 odds.
            *   Compare Analysis vs. Odds: Does analysis (Form, Context, **Rotation Assessment**, H2H Relevance) align with favourite/O/U lean?
            *   **Identify Discrepancies:** Highlight contradictions. **Crucially, discuss if the market odds seem to accurately reflect the likely impact of rotation (assessed in 4.4) or if they primarily reflect base league status/form.** Is the favourite potentially poor value due to rotation/context? Is the market O/U lean neglecting defensive solidity or rotation's impact on attack?
        *   **Conceptual Scratchpad Storage:** Comparison notes, explicit discrepancy identification (especially regarding rotation reflection in odds).

    **4.8 Weather Forecast Integration:**
        *   **Objective:** Assess weather impact.
        *   **Mandatory Search:** Venue/kick-off time forecast.
        *   **Analysis:** Note significant conditions (heavy rain, strong wind, extreme heat/humidity) and likely impact. Extreme conditions might favour underdogs or defensive setups, potentially suppressing goals more than usual.
        *   **Conceptual Scratchpad Storage:** Forecast, impact note (linking to potential underdog advantage/goal impact).

    **4.9 Home/Away Strength Synthesis:**
        *   **Objective:** Focused view of home/away dynamic including context.
        *   **Analysis:**
            *   Compare season-long Home/Away records (4.1) vs recent home/away form (4.2). Note deviations.
            *   Integrate relevant venue-specific H2H (4.6), considering relevance.
            *   **Overlay impact of rotation (4.4):** Does expected rotation negate the away team's usual strength or amplify the home team's advantage?
            *   Consider travel/climate impact (4.5, 4.8).
            *   Synthesize into expected home advantage/disadvantage based on combined factors.
        *   **Conceptual Scratchpad Storage:** Synthesized home/away dynamic summary incorporating rotation/travel/climate.

5.  **Final Prediction:** Based on comprehensive analysis from the conceptual scratchpad:
    *   **Synthesize Key Findings & Weighing Factors:**
        *   List strongest arguments for each outcome (Win/Draw/Loss) referencing key data points (League/Tier Gap, Current Form, **Rotation Assessment & Depth**, H2H Relevance, Home/Away Synthesis, Motivation, Key Absences).
        *   **Crucially, state how conflicting data is weighed:**
            *   **Form vs H2H:** Prioritize recent, relevant data unless H2H shows overwhelming contradictory pattern.
            *   **Tier Gap vs Rotation/Context:** Weigh tier gap heavily *unless* rotation is expected to be significant *and* lower-league team is competent/motivated *or* higher-league team is in very poor form. J1 depth can often overcome rotation vs J3.
            *   **Analysis vs Odds:** Clearly state if analysis diverges from market and why (e.g., "Market seems to ignore likely heavy rotation...").
    *   **Identify Plausible Scenarios:** Outline 2-3 narratives based on weighted synthesis. Include potential upset scenario if context warrants (e.g., heavy rotation, derby, extreme motivation).
    *   **State Primary Match Outcome Prediction:** (Team A Win, Draw, Team B Win).
    *   **Market Odds Check & Confidence Adjustment:** Reiterate if prediction contradicts market favourite and why (esp. regarding rotation/context). State confidence level (High/Medium/Low). Consider conservative options (DC, AH) if confidence lowered by contradictions/unpredictability (e.g., derby).
    *   **(Optional) Acknowledge Secondary Scenarios:** Mention less likely but possible outcomes (e.g., acknowledging upset potential even if predicting favourite).
    *   **Predict Total Goals (Over/Under 2.5):**
        *   Synthesize **multiple factors**: Form O/U% (as one input), H2H O/U% (checked for relevance), Team GF/GA averages, **Expected Impact of Rotation on Attack/Defence**, Inferred Tactics (attacking vs defensive, cagey cup tie?), Weather impact, Market O/U lean.
        *   State O/U Prediction and Confidence Level. Explicitly justify if contradicting the market lean.
    *   **Formulate Most Robust Combined Prediction:** (e.g., Team A Win and Under 2.5 goals).
    *   **Scoreline(s) (Contextual):** Suggest specific scoreline(s) aligned with Outcome + O/U. Justify briefly using relevant factors (e.g., defensive solidity points to 1-0/2-0, high FTS% suggests clean sheet unlikely, Reliability/Timing data if available and significant).
    *   **Justification:** Provide concise rationale weaving together key arguments, weighting logic (esp. rotation, H2H relevance), odds check, O/U synthesis, and scoreline rationale. Explicitly state if key data (HT/FT, Timing) was unavailable/inconclusive or if data quality was low.
