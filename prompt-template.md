**### Prompt V18 ###**

1.  **Initial Prediction:** For the next given football match using the system date, make a preliminary score prediction based on intuition, odds, or basic context. Save this prediction mentally or on a conceptual "scratchpad."
2.  **Analysis Target:** Focus analysis on the specific match provided.
3.  **Iterative Analysis Loop & Conceptual Data Handling:**
    Follow the "Data Check" steps (Step 4) below for the targeted match.
    *   **Conceptual Scratchpad & Context:** Throughout this process, findings are stored conceptually on a "scratchpad" used during the generation of the response. This collected information forms the basis for subsequent analysis steps. Check the scratchpad for completeness before moving to calculations or subsequent steps.
    *   **Dynamic Gap Filling & Persistence:** Actively attempt to fill data gaps identified during the process by performing additional, targeted searches as detailed in the relevant sections of Step 4. **Crucially, do not proceed to the next analytical calculation or step if the required input data (e.g., HT scores, goal times) for that step is marked as missing on the scratchpad.** Continue searching for the specific missing data point(s) using targeted queries until the data is found or confirmed as definitively unobtainable after reasonable attempts.
    *   **Iteration:** If newly found data significantly changes the picture (e.g., correcting form data), iterate through relevant parts of Step 4 again, refining the analysis based on the updated information on the scratchpad.
    *   **Prompt Chaining Context:** The complete analysis presented in the response (incorporating initially found and dynamically searched data) becomes part of the conversation history. This history serves as the context for subsequent prompts (prompt chaining), allowing follow-up questions or refinements to build upon the established analysis. The "storage" mechanism is this contextual carry-forward within the conversation session.
    *   **Continuation of Steps:** Retrieve previous output and stored scratchpad data to find where the last step was complete or incomplete, continuing from that position, ensuring required data for the current step is present before executing it.
4.  **Data Check:** Perform the following analysis points, using grounded search where necessary:

    **4.1 League Context:**
        *   **Objective:** Retrieve accurate, current league standings (Overall, Home, Away) for both teams in their specified league (or competition if appropriate).
        *   **Mandatory Search & Query Formulation:** Use the `google_search` tool with specific, targeted queries... [details unchanged]
        *   **Data Points to Extract:** Rank / Position, GP, Pts, W, D, L, GF, GA, GD for Overall, Home, Away.
        *   **Source Prioritization:** Official sites, reputable sports news, established stats sites.
        *   **Dynamic Gap Filling for Tables:** If Home/Away missing, perform specific searches.
        *   **Conceptual Scratchpad Storage:** Store all retrieved league data points. Note source/date.

    **4.1.1 Odds Search & Initial Market View:**
        *   **Objective:** Retrieve match betting odds for key markets.
        *   **Mandatory Search:** Use search if odds not provided.
        *   **Data Points to Extract:** 1X2 (Match Winner), Over/Under 2.5 Goals. *Optional but helpful if easily found:* Double Chance, Both Teams To Score (BTTS), key Handicap lines.
        *   **Analysis:** Briefly interpret the main 1X2 odds – who is the favourite and how strongly? Does the O/U 2.5 odds clearly favour Over or Under?
        *   **Conceptual Scratchpad Storage:** Store retrieved odds and the initial market interpretation (favoured outcome, likely goal level).

    **4.2 Recent Form Analysis (Last 10 Official Matches):**
        *   **Objective:** Identify the 10 most recent official matches for each team, their outcomes, and analyze trends.
        *   **Mandatory Search & Data Collation:** Use search to find results. **Explicitly list the 10 matches found for each team** on the conceptual scratchpad (Opponent, Competition, Date, **FT score**). Prioritize league > domestic cup > other official. *Verify consistency if results were used in previous analyses.*
        *   **Analysis (Based on listed 10 matches):**
            *   Analyze W-D-L sequence and record (W, D, L counts). **Contextualize Streaks:** If a strong winning/drawing/losing streak (>4-5 games) exists, note it but also briefly comment on its potential sustainability or likelihood of regression based on opponent quality or underlying performance hints (if available).
            *   Analyze performance against teams of similar, higher, and lower standing (using 4.1 context).
            *   Analyze recent home-specific and away-specific form within these 10 games.
            *   Evaluate total GF/GA trends across these 10 games (calculating averages).
            *   Calculate CS% and FTS% for these 10 games.
            *   Calculate O/U 2.5 goals % for these 10 games.
        *   **Conceptual Scratchpad Storage:** Store the match list, WDL record (with streak context), GF/GA averages, CS%, FTS%, and O/U 2.5% for the last 10 games.

    **4.3 Reliability/Comeback/Choke/Timing Analysis (Based on Last 10 Official Matches Identified in 4.2):**
        **4.3.1 HT/FT Score Retrieval (Mandatory Prerequisite):**
            *   **Objective:** Obtain the Half-Time (HT) score for **each** of the 10 specific matches listed (or most recent 5 if 10 unavailable after diligent search).
            *   **Methodology - Persistent Targeted Search:** ... [details unchanged, emphasize Sofascore/reliable sources]
            *   **Conceptual Scratchpad Update & Checkpoint:** ... [details unchanged]
        **4.3.2 Reliability/Comeback/Choke Calculation:**
            *   **Objective:** Calculate performance based on HT status.
            *   **Condition:** Proceed *only* using the HT/FT data collated in 4.3.1.
            *   **Calculation:** Calculate Reliability (% Won when leading HT), Comeback (% Won/Drawn when trailing HT), Choke (% Lost/Drawn when leading HT).
            *   **Acknowledge Limitations:** State the number of games basis for each calculation. If based on few instances (e.g., 0 or 1 game leading/trailing), note the low confidence in the resulting percentage.
            *   **Conceptual Scratchpad Storage:** Store calculated percentages (or inability statement) and the number of games basis.
        **4.3.3 Goal Timing (ES / ST) Retrieval & Calculation (Attempt if Possible):**
            *   **Objective:** Find precise goal times for ES/ST distribution.
            *   **Methodology - Persistent Targeted Search (Last 10 or 5):** ... [details unchanged, emphasize reliable sources]
            *   **Calculation (Conditional):** ... Calculate ES (% goals 1-15 OR 46-60) and ST (% distribution across 15-min blocks + halves). State basis (games/goals analyzed).
            *   **Final Statement (If Both Attempts Fail):** State clearly if ES/ST could not be reliably calculated.
            *   **Conceptual Scratchpad Storage:** Store calculated ES/ST percentages (or inability statement) and basis.

    **4.4 Team News and Injuries:**
        *   **Objective:** Identify significant absences and assess impact.
        *   **Mandatory Search:** Search for confirmed significant injuries, suspensions, or key players returning.
        *   **Analysis:** Assess the impact of *key* absences/returns on team strength, tactics, and specific units (defence, midfield, attack).
        *   **Conceptual Scratchpad Storage:** Store key personnel news and impact assessment.

    **4.5 Situational and Tactical Context Analysis:**
        *   **Objective:** Understand the broader context influencing the match.
        *   **Analysis:**
            *   Evaluate **Match Importance & Motivation:** Assess stakes for each team (e.g., promotion, playoffs, relegation, mid-table safety). **Explicitly consider how differing motivation levels might impact performance beyond raw form/stats.**
            *   Infer Likely Tactics: Based on league position, form, home/away status, manager's style, and key absences/returns.
            *   Assess Fixture Congestion & Fatigue: Note recent schedule density.
            *   Note Managerial Context: Any recent changes or pressure?
            *   Synthesize findings into a contextual overview.
        *   **Conceptual Scratchpad Storage:** Store notes on motivation impact, tactics, schedule, manager.

    **4.6 Head-to-Head (H2H) Analysis:**
        *   **Objective:** Analyze recent direct encounters.
        *   **Mandatory Search:** Find results for the **last 4-6 official H2H meetings**. Include venue.
        *   **Analysis:** Identify patterns (dominance, home advantage, scorelines). Calculate O/U 2.5% for these specific H2H games. Note results at *this specific venue*.
        *   **Conceptual Scratchpad Storage:** Store H2H list, WDL summary, venue-specific results, and H2H O/U 2.5%.

    **4.7 Betting Odds Comparison & Market Check:**
        *   **Objective:** Compare analytical findings with market view.
        *   **Analysis:**
            *   Retrieve/Note 1X2 and O/U 2.5 odds (from 4.1.1 or input).
            *   **Compare Analysis vs. Odds:** Does the analysis (form, H2H, context) align with the favourite indicated by the odds? Does the O/U analysis align with the O/U odds lean?
            *   **Identify Discrepancies:** **Explicitly highlight if the analysis strongly contradicts the market odds.** Discuss potential reasons for the discrepancy (e.g., market overvaluing reputation vs. form, model overweighting a specific factor, hidden info like late injury news).
        *   **Conceptual Scratchpad Storage:** Store comparison notes, highlight discrepancies.

    **4.8 Weather Forecast Integration:**
        *   **Objective:** Assess weather impact.
        *   **Mandatory Search:** Search for forecast at venue/kick-off time.
        *   **Analysis:** Note significant conditions (heavy rain, strong wind, extreme temp) and likely impact on playstyle/goal potential.
        *   **Conceptual Scratchpad Storage:** Store forecast and impact note.

    **4.9 Home/Away Strength Synthesis:**
        *   **Objective:** Create a focused view of the home/away dynamic.
        *   **Analysis:**
            *   Compare season-long Home/Away records (4.1) with *recent* home/away form (last 5 home/away games from 4.2 analysis). **Note any significant deviation between recent and season-long performance.**
            *   Integrate relevant H2H results at this venue (4.6).
            *   Overlay significant findings from Reliability/Timing analysis (4.3) if applicable (e.g., home team's reliability at home, away team's poor comeback record away, away team's high ES% away).
            *   Synthesize into a summary of expected home advantage/disadvantage based on these combined factors.
        *   **Conceptual Scratchpad Storage:** Store the synthesized home/away dynamic summary.

5.  **Final Prediction:** Based on the comprehensive analysis drawing from **all** stored findings on the conceptual scratchpad:
    *   **Synthesize Key Findings & Weighing Factors:**
        *   Explicitly list the strongest arguments *for* each team winning or a draw, referencing key data points (League position, Recent Form record + streak context, significant H2H patterns, Home/Away synthesis from 4.9, key player news, motivation edge from 4.5).
        *   **Crucially, state how conflicting data (e.g., Form vs H2H, Form vs Season-long Home/Away, Analysis vs Odds) is being weighed.** Justify prioritizing one factor over another (e.g., "While H2H favours Team B, Team A's current 8-game winning streak and perfect home form is deemed more indicative of immediate potential and outweighs H2H from 1-2 seasons ago").
    *   **Identify Plausible Scenarios:** Briefly outline 2-3 plausible match narratives based on the weighted synthesis.
    *   **Determine Primary Prediction Format:** (e.g., Match Outcome + Total Goals).
    *   **State Primary Match Outcome Prediction:** (e.g., Team A Win, Draw, Team B Win).
    *   **Market Odds Check & Confidence Adjustment:** Review the odds discrepancy highlighted in 4.7. If the primary prediction strongly contradicts the market favourite, briefly reiterate why and state whether this lowers confidence or if the value assessment remains strong. Consider if a more conservative prediction (e.g., Double Chance, Draw-No-Bet market equivalent) might be wiser if confidence is reduced.
    *   **(Optional) Acknowledge Secondary Scenarios:** Briefly mention less likely but possible outcomes.
    *   **Predict Total Goals (Over/Under 2.5):** State O/U Prediction based on synthesis (Form O/U%, H2H O/U%, inferred tactics, team GF/GA trends, weather). (Optional) Confidence level.
    *   **Formulate Most Robust Combined Prediction:** (e.g., Team A Win and Under 2.5 goals).
    *   **Scoreline(s) (Contextual):** Suggest specific scoreline(s) aligning with the outcome and O/U prediction. **Justify the chosen scoreline(s) by referencing relevant factors:** Does ES/ST data (if available) suggest an early or late goal? Do Reliability/Choke percentages support a narrow win vs. a comfortable one? Does the FTS% suggest a 1-0 is more likely than 2-1?
    *   **Justification:** Provide a concise rationale weaving together the key arguments, the weighing of conflicting data, the odds check, and how the scoreline reflects timing/reliability insights (if applicable/significant) to support the final combined prediction. State clearly if ES/ST/Reliability data was unavailable or considered inconclusive for this specific match.
