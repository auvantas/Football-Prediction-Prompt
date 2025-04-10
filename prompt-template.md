
**### Prompt V22 ###**

1.  **Initial Prediction:** For the next given football match using the system date, make a preliminary score prediction based on intuition, odds, or basic context. Save this prediction mentally or on a conceptual "scratchpad."
2.  **Analysis Target:** Focus analysis on the specific match provided.
3.  **Iterative Analysis Loop & Conceptual Data Handling:**
    Follow the "Data Check" steps (Step 4) below for the targeted match.
    *   **Conceptual Scratchpad & Context:** Throughout this process, findings are stored conceptually on a "scratchpad" used during the generation of the response. This collected information forms the basis for subsequent analysis steps. Check the scratchpad for completeness before moving to calculations or subsequent steps.
    *   **Dynamic Gap Filling, Persistence & Verification (Multi-Source):** Actively attempt to fill data gaps identified during the process by performing additional, targeted searches using **multiple, diverse reputable sources**. **Crucially, do not proceed to the next analytical calculation or step if the required input data (e.g., FT scores, HT scores, goal times) for that step is marked as missing or insufficient (below threshold) on the scratchpad.**
        *   **Targeted Searching & Methodology:** Continue searching for the *specific missing data point(s)* using varied, targeted queries until the data is found or confirmed as definitively unobtainable after reasonable multi-source attempts. **This involves:**
            *   **Query Variation:** Formulating specific queries targeting individual matches and data types (e.g., `'[Team A] vs [Team B] [Date] halftime score'`, `'[Team A] match report [Date] statistics'`, `'[Team B] goal times [Competition]'`). Vary keywords (e.g., `HT score`, `half-time result`, `goal minutes`, `match timeline`, `event log`, `play-by-play`).
            *   **Source Prioritization:** Focusing on data-rich platforms known for detailed statistics (e.g., **Fotmob, Soccerway, Sofascore, Flashscore, FBref, Transfermarkt, FootyStats, ESPN matchcasts/timelines, SoccerPunter, WhoScored** where applicable) over general news articles unless the latter contain specific detailed reports.
            *   **Iterative Refinement:** If initial searches fail for the most recent matches, try query variations, different source keywords (e.g., adding `Sofascore` to the query), or check slightly older matches (e.g., 6th, 7th most recent) to build the required sample size (e.g., n=5 for HT/Timing data).
        *   **Accumulation, Not Replacement:** If Source A provides partial data (e.g., 7/10 FT scores), and Source B provides the missing 3 FT scores plus confirms 4 already found, **accumulate** this information on the scratchpad. Note the confirmation from Source B as verification for the 4 matches. Do not simply discard Source A's data. Cross-reference granular data like HT scores or goal times between sources whenever possible.
        *   Acknowledge clearly where data quality/availability is low (e.g., U23, lower tiers, specific data points unobtainable despite search) and temper conclusions accordingly.
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
        *   **Mandatory Search & Data Collation (Multi-Source):** Attempt to find the 10 most recent official match results. **List opponent, competition, date, and verified Full-Time (FT) score**. Prioritize league > domestic cup > continental > other official.
            *   **Methodology:** Use targeted searches across **multiple reputable sources** (e.g., Fotmob, Soccerway, FBref, Forebet, ESPN, official league/cup sites).
            *   **Iterative Search & Verification:** If initial searches yield incomplete lists (<10 matches) or missing/conflicting FT scores, perform secondary, targeted searches using different source keywords (e.g., `'[Team Name] last 10 match results Fotmob'`, `'[Team A] vs [Team B] FT score [Date] Forebet'`, `'[Team Name] [Competition] results official site'`).
            *   **Accumulate & Cross-Reference:** Collate data points found. If multiple sources provide the same FT score for a match, consider it verified. Note any significant, unresolved discrepancies. Ensure the final list used for analysis has verified FT scores.
        *   **Analysis (Based on verified list of up to 10 matches):**
            *   WDL Record & Sequence: Contextualize streaks (sustainability, quality of opposition during streak).
            *   Performance vs Opposition Quality: How did they fare against teams of similar/higher/lower standing (using 4.1 context)?
            *   Home/Away Form within the list.
            *   GF/GA Averages & Trends (based on the list).
            *   CS% & FTS% (based on the list).
            *   O/U 2.5% (based on the list): **Note this percentage as *one input only* for the final O/U prediction, not the sole determinant.**
        *   **Conceptual Scratchpad Storage:** Verified match list (opponent, comp, date, FT score), sources consulted, notes on verification/discrepancies, WDL record/context, GF/GA averages, CS%, FTS%, O/U 2.5% (noted as partial factor).
    **4.3 Reliability/Comeback/Choke/Timing Analysis (Based on Matches in 4.2):**
        **4.3.1 HT/FT Score Retrieval (Iterative Multi-Source Mandatory Prerequisite):**
            *   **Objective:** Retrieve accurate Half-Time (HT) scores for the matches identified and verified in step 4.2.
            *   **Methodology (Iterative, Multi-Source):**
                1.  For each relevant match (aiming for at least 5 per team), attempt to retrieve the HT score.
                2.  Start with primary detailed stats sites (**Fotmob, Soccerway, Sofascore, Flashscore, FBref, Transfermarkt, FootyStats, SoccerPunter**).
                3.  If HT scores are missing, perform **targeted secondary searches** applying the **Query Variation** techniques described in Step 3 (e.g., `'[Team A] vs [Team B] [Date] halftime score'`, `'[Team A] [Competition] match report [Date]'`, trying different source names).
                4.  **Accumulate and Verify:** Collate HT scores found across sources. Prioritize data where multiple reputable sources concur. If only one source provides the HT score after extensive search, note this lower confidence level.
            *   **Checkpoint:** Proceed to calculation (4.3.2) only if reliable and preferably cross-referenced HT scores have been found for **at least 5 of the matches** for *each* team. Clearly state the number of matches (n) the subsequent analysis is based on.
            *   **Limitations:** Acknowledge if data quality was low, verification wasn't possible for some scores, or the n=5 threshold couldn't be met despite applying the search methodology.
            *   **Conceptual Scratchpad Storage:** Store verified/accumulated HT scores alongside FT scores, note sources/verification status/confidence, state usable 'n'.
        **4.3.2 Reliability/Comeback/Choke Calculation:**
            *   **Objective:** Calculate performance changes between HT and FT based on the collected data (minimum n=5).
            *   **Condition:** Requires HT/FT data for at least 5 matches per team from 4.3.1.
            *   **Calculation:**
                *   Reliability % = (Wins FT when Leading HT) / (Total Leads HT)
                *   Comeback % = (Wins or Draws FT when Trailing HT) / (Total Trails HT)
                *   Choke % = (Draws or Losses FT when Leading HT) / (Total Leads HT)
            *   **Limitations:** Explicitly state the calculation is based on 'n' matches and confidence is low for small sample sizes (e.g., n=5 or n=6).
            *   **Conceptual Scratchpad Storage:** Calculated % (or 'Not Calculable - Insufficient Data' if n<5), basis count (n), confidence note.
        **4.3.3 Goal Timing (ES / ST) Retrieval & Calculation (Attempt if Possible):**
            *   **Objective:** Determine tendencies for scoring/conceding early (1'-15') or late (75'-FT).
            *   **Methodology (Iterative, Multi-Source):**
                1.  Attempt to find specific goal timings (minute of goal) for the matches where HT/FT was retrieved (target n=5 per team).
                2.  Use **targeted multi-source searches** applying **Query Variation** and **Source Prioritization** from Step 3 (e.g., `'[Team A] vs [Team B] [Date] goal times'`, `'[Team A] match timeline Fotmob'`, `'[Team B] event log Sofascore'`). Check detailed match views, timelines, or play-by-play sections on primary stats sites.
                3.  **Accumulate and Verify:** Collate specific goal minute data points found across sources. Cross-reference if possible. Use exact minutes where available.
            *   **Checkpoint:** Proceed to calculation only if reliable goal timings allowing for ES/ST categorization are found for **at least 5 matches** for *each* team. Acknowledge if this data is scarce and the threshold isn't met.
            *   **Calculation:** Calculate % of team's goals scored/conceded in ES and ST periods based on available data (minimum n=5).
            *   **Final Statement:** Clearly state if analysis was possible, the basis count (n), and the findings, or state 'Not Calculable - Insufficient Data' (mentioning search attempts).
            *   **Conceptual Scratchpad Storage:** ES/ST Goal % (or inability statement), basis count (n), confidence note.
    **4.4 Team News, Injuries, and Rotation Assessment:**
        *   **Objective:** Identify absences and critically assess likely team strength, especially for cup matches.
        *   **Mandatory Search:** Search **using multiple query types** (e.g., team news, injury list, pre-match press conference) for significant injuries, suspensions, returns, **AND** general team news discussing rotation policy or manager's comments for the specific competition/match. Cross-reference reports if possible.
        *   **Analysis:**
            *   Assess impact of *confirmed key* absences/returns.
            *   **Crucially, assess Likelihood and Impact of Rotation:** Based on competition stage (early round vs QF/SF), league priorities (title race vs mid-table vs relegation battle), opponent strength (T1 vs T3 invites rotation), travel distance, fixture congestion, and *market signals* (do odds imply strong/weak team expected?).
            *   **Estimate Squad Depth:** Can the likely rotating team field competitive backup players, or is there a huge drop-off? (e.g., J1 depth > J3 depth).
        *   **Conceptual Scratchpad Storage:** Key personnel news (verified where possible), **Rotation Likelihood Assessment (High/Medium/Low)**, **Estimated Impact (High/Medium/Low)**, **Squad Depth Note**, overall impact assessment.
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
        *   **Mandatory Search (Multi-Source):** Attempt to find results for last 4-6 official H2H meetings (include venue, competition). **Verify scores using multiple sources if possible.**
        *   **Analysis:**
            *   Identify patterns (dominance, home adv, scorelines). Note venue-specific results.
            *   Calculate O/U 2.5% for these H2H games.
            *   **Critically Assess Relevance:** Is the H2H recent enough? Were teams in similar leagues/form then? Will rotation significantly change the dynamic compared to past H2H? **Avoid overweighting old or contextually different H2H data.**
        *   **Conceptual Scratchpad Storage:** Verified H2H list, WDL summary, venue results, H2H O/U%, **Relevance Assessment Note**.
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
        *   List strongest arguments for each outcome (Win/Draw/Loss) referencing key data points (League/Tier Gap, Verified Current Form, Reliability data [if available, noting 'n'], **Rotation Assessment & Depth**, Relevant H2H, Home/Away Synthesis, Motivation, Key Absences).
        *   **Crucially, state how conflicting data is weighed:**
            *   **Form vs H2H:** Prioritize recent, relevant, verified form data unless H2H shows overwhelming contradictory pattern.
            *   **Tier Gap vs Rotation/Context:** Weigh tier gap heavily *unless* rotation is expected to be significant *and* lower-league team is competent/motivated *or* higher-league team is in very poor verified form. J1 depth can often overcome rotation vs J3.
            *   **Analysis vs Odds:** Clearly state if analysis diverges from market and why (e.g., "Market seems to ignore likely heavy rotation confirmed by multiple news sources...").
    *   **Identify Plausible Scenarios:** Outline 2-3 narratives based on weighted synthesis. Include potential upset scenario if context warrants (e.g., heavy rotation, derby, extreme motivation).
    *   **State Primary Match Outcome Prediction:** (Team A Win, Draw, Team B Win).
    *   **Market Odds Check & Confidence Adjustment:** Reiterate if prediction contradicts market favourite and why (esp. regarding rotation/context). State confidence level (High/Medium/Low). Consider conservative options (DC, AH) if confidence lowered by contradictions/unpredictability (e.g., derby, low 'n' for reliability data).
    *   **(Optional) Acknowledge Secondary Scenarios:** Mention less likely but possible outcomes.
    *   **Predict Total Goals (Over/Under 2.5):**
        *   Synthesize **multiple factors**: Verified Form O/U% (as one input), Relevant H2H O/U%, Team GF/GA averages (from verified form), **Expected Impact of Rotation on Attack/Defence**, Inferred Tactics, Weather impact, Market O/U lean.
        *   State O/U Prediction and Confidence Level. Explicitly justify if contradicting the market lean.
    *   **Formulate Most Robust Combined Prediction:** (e.g., Team A Win and Under 2.5 goals).
    *   **Scoreline(s) (Contextual):** Suggest specific scoreline(s) aligned with Outcome + O/U. Justify briefly using relevant factors (e.g., defensive solidity, GF/GA averages, Reliability/Timing data if available and significant [noting 'n']).
    *   **Justification:** Provide concise rationale weaving together key arguments, weighting logic (esp. rotation, H2H relevance, **data verification status/confidence**), odds check, O/U synthesis, and scoreline rationale. Explicitly state if key data (HT/FT, Timing) was unavailable/inconclusive **despite applying the specified search methodology**, or if data quality was low/sample size 'n' was small.
    *   
