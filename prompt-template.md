**### Prompt V24 ###**

1.  **Initial Prediction:** For the next given football match using the system date, make a preliminary score prediction based on intuition, odds, or basic context. Save this prediction mentally or on a conceptual "scratchpad."
2.  **Analysis Target:** Focus analysis on the specific match provided.
3.  **Iterative Analysis Loop & Conceptual Data Handling:**
    Follow the "Data Check" steps (Step 4) below for the targeted match.
    *   **Conceptual Scratchpad & Context:** Throughout this process, findings are stored conceptually on a "scratchpad" used during the generation of the response. This collected information forms the basis for subsequent analysis steps. Check the scratchpad for completeness before moving to calculations or subsequent steps.
    *   **Dynamic Gap Filling, Persistence & Verification (Multi-Source & Localized):** Actively attempt to fill data gaps identified during the process by performing additional, targeted searches using **multiple, diverse reputable sources (both global and local)**. **Crucially, do not proceed to the next analytical calculation or step if the required input data (e.g., FT scores, HT scores, goal times) for that step is marked as missing or insufficient (below threshold) on the scratchpad.**
        *   **Targeted Searching & Methodology:** Continue searching for the *specific missing data point(s)* using varied, targeted queries until the data is found or confirmed as definitively unobtainable after reasonable multi-source attempts. **This involves:**
            *   **Query Variation:** Formulating specific queries targeting individual matches and data types (e.g., `'[Team A] vs [Team B] [Date] halftime score'`, `'[Team A] match report [Date] statistics'`, `'[Team B] goal times [Competition]'`). Vary keywords (e.g., `HT score`, `half-time result`, `goal minutes`, `match timeline`, `event log`, `play-by-play`). **Include queries in the team's local language targeting local news sources where applicable.**
            *   **Source Prioritization:** Focusing on data-rich platforms known for detailed statistics (e.g., **Fotmob, Soccerway, Sofascore, Flashscore, FBref, Transfermarkt, FootyStats, ESPN matchcasts/timelines, SoccerPunter, WhoScored**) for structured data, **BUT prioritizing verified news from official team communications, reputable local/regional news outlets, and known team-specific journalists for team news, injuries, and rotation information.**
            *   **Iterative Refinement:** If initial searches fail for the most recent matches, try query variations, different source keywords (e.g., adding `Sofascore` to the query), check slightly older matches, or **specifically target local news archives** to build the required sample size (e.g., n=5 for HT/Timing data).
        *   **Accumulation, Not Replacement:** If Source A (global) provides partial data and Source B (local) provides missing details plus confirms some findings, **accumulate** this information. Note source type (global/local) for context. Cross-reference granular data between sources whenever possible.
        *   Acknowledge clearly where data quality/availability is low (e.g., U23, lower tiers, specific data points unobtainable despite search) and temper conclusions accordingly.
    *   **Iteration:** If newly found data (especially from local sources regarding team news/rotation) significantly changes the picture, iterate through relevant parts of Step 4 again, refining the analysis.
    *   **Prompt Chaining Context:** The complete analysis presented in the response becomes part of the conversation history, serving as context for subsequent prompts.
    *   **Continuation of Steps:** Retrieve previous output and stored scratchpad data to continue analysis from the last completed/incomplete step, ensuring required data is present.
4.  **Data Check:** Perform the following analysis points, using grounded search where necessary: *(Note: The importance of factors below can vary based on match context - apply dynamic weighting in Step 5)*
    **4.1 League & Competition Context:**
        *   **Objective:** Retrieve accurate, current league standings (Overall, Home, Away), understand the competitive hierarchy, and identify key competition factors.
        *   **Mandatory Search & Query Formulation:** Use `google_search` for league tables, team league levels, competition format/stage.
        *   **Data Points to Extract:** League Name/Tier, Rank/Position, GP, Pts, W, D, L, GF, GA, GD (Overall, Home, Away). **Competition Stage**.
        *   **Source Prioritization:** Official sites, reputable global sports news, established stats sites.
        *   **Analysis:** Note tier difference. Assess league performance. Identify competition dynamics (knockout/league, leg#, regional factors, historical league strength). Note data limitations. **Assess Environmental Factors:** Note altitude, climate, travel. Analyze potential **mitigation factors**. Avoid deterministic environmental conclusions.
        *   **Conceptual Scratchpad Storage:** League data, tier difference, performance assessment, competition stage/dynamics, Environmental Factors & Mitigation Notes, source/date, data quality notes.
    **4.1.1 Odds Search & Initial Market View:**
        *   **Objective:** Retrieve match betting odds and understand market perception.
        *   **Mandatory Search:** Use search if odds not provided.
        *   **Data Points to Extract:** 1X2, O/U 2.5 Goals. Optional: DC, BTTS, AH, Handicap, Correct Score.
        *   **Analysis:** Identify favourite, strength of favouritism, O/U lean. Consider implications of extreme odds (rotation hints?).
        *   **Conceptual Scratchpad Storage:** Odds, market interpretation, extreme odds notes.
    **4.2 Recent Form Analysis (Last 10 Official Matches):**
        *   **Objective:** Analyze recent performance trends and momentum, including specific preparation.
        *   **Mandatory Search & Data Collation (Multi-Source & Local Supplement):** Attempt to find the 10 most recent official match results. List opponent, competition, date, and verified FT score. Prioritize league > domestic cup > continental > other official.
            *   **Methodology:** Use targeted searches across **multiple reputable global sources** (Fotmob, Soccerway, etc.). **Where discrepancies arise or context is needed (e.g., unusual scoreline, unexpected lineup noted in reports), consult reputable local news reports/archives for match verification or details.**
            *   **Iterative Search & Verification:**
            *   **Accumulate & Cross-Reference:**
        *   **Analysis (Based on verified list):**
            *   WDL Record & Sequence ('Momentum').
            *   Performance vs Opposition Quality.
            *   Home/Away Form within list.
            *   GF/GA Averages & Trends.
            *   CS% & FTS%.
            *   O/U 2.5% (Input only).
        *   **4.2.1 - Performance vs. Relevant Styles ('Preparation'):** Briefly analyze recent results (last 3-5 games) against opponents with tactical styles expected. Note relevant successes/struggles.
        *   **Conceptual Scratchpad Storage:** Verified match list (opponent, comp, date, FT score), sources (global/local noted), verification notes, WDL/momentum, GF/GA, CS%, FTS%, O/U% (partial), Performance vs Relevant Styles notes.
    **4.3 Reliability/Comeback/Choke/Timing Analysis (Based on Matches in 4.2):**
        **4.3.1 HT/FT Score Retrieval:** [Methodology largely unchanged, relies on global stats sites primarily]
            *   **Limitations:** Acknowledge gaps. **Note for Step 5 confidence.**
            *   **Conceptual Scratchpad Storage:** HT/FT scores (or inability), sources, confidence, usable 'n', **Note if data insufficient**.
        **4.3.2 Reliability/Comeback/Choke Calculation:** [Unchanged]
        **4.3.3 Goal Timing (ES / ST) Retrieval & Calculation:** [Methodology largely unchanged, relies on global stats sites primarily]
            *   **Checkpoint:** Proceed if n>=5. **Note gap for Step 5 confidence.**
            *   **Conceptual Scratchpad Storage:** ES/ST Goal % (or inability), basis count (n), confidence note, **Note if data insufficient**.
    **4.4 Team News, Injuries, and Rotation Assessment:**
        *   **Objective:** Identify absences and critically assess likely team strength using the best available information (prioritizing local).
        *   **Mandatory Search & Verification (Global & Local):** Search using multiple query types (e.g., injury list, suspension news, pre-match press conference reports, official team site news). **Crucially, supplement global searches by performing targeted searches using local/regional reputable news sources, team-specific journalists, or trusted fan forums *in the team's primary language* (e.g., searching Canadian sources for Vancouver Whitecaps news, Mexican sources for Pumas news).** Also consult predicted lineups from reliable global sources (e.g., Fotmob/Sofascore) but **prioritize verified news from primary/local sources** regarding player availability and rotation strategy.
        *   **Analysis:**
            *   Assess impact of *confirmed key* absences/returns (prioritizing local confirmation).
            *   **Assess Likelihood and Impact of Rotation:** Based on competition stage/importance (4.1), league priorities, opponent strength, travel/environmental factors (4.1), fixture congestion, market signals (4.1.1), AND **verified team news/lineup information (giving more weight to local/primary source verification).**
            *   **State Rotation Confidence:** Explicitly state the confidence level (High - Confirmed News/Primary/Local Source; Medium - Strong Indications/Multiple Reliable Predictions; Low - Assumption-Based/Conflicting Info) in the rotation assessment. **If confidence is Low, significantly temper the estimated impact.**
            *   **Estimate Squad Depth:** Consider league context and information about available backup players.
        *   **Conceptual Scratchpad Storage:** Key personnel news (verified, source type noted), **Rotation Likelihood Assessment (High/Medium/Low) & VERIFICATION CONFIDENCE (High/Medium/Low based on source type)**, **Estimated Impact (adjusted by confidence)**, Squad Depth Note, overall impact assessment.
    **4.5 Situational and Tactical Context Analysis:**
        *   **Objective:** Understand broader match context.
        *   **Analysis:**
            *   Match Importance & Motivation (4.1).
            *   Infer Likely Tactics: Adjust based on **verified/confidently expected team strength (4.4)**, H/A status, environment (4.1), motivation, Performance vs Styles (4.2.1).
            *   Fixture Congestion & Fatigue (incl. travel/climate from 4.1).
            *   Managerial Context.
            *   Synthesize overview.
        *   **Conceptual Scratchpad Storage:** Motivation, adjusted tactics, schedule, manager notes.
    **4.6 Head-to-Head (H2H) Analysis:**
        *   **Objective:** Analyze recent direct encounters, assessing relevance critically.
        *   **Mandatory Search (Multi-Source & Optional Local Context):** Attempt to find results for last 4-6 official H2H meetings. Verify scores using multiple global stats sources. **Optionally, search local archives/reports for additional context on past significant H2H matches if readily available.**
        *   **Analysis:**
            *   Identify patterns, venue results.
            *   Calculate O/U 2.5%.
            *   **Critically Assess Relevance:** Consider recency, context changes (leagues, form, managers). How might **verified/confidently expected rotation (4.4)** impact relevance? Give **moderate consideration to recently demonstrated competitiveness** per 4.6 guidance in V23.
        *   **Conceptual Scratchpad Storage:** Verified H2H list, WDL summary, venue results, H2H O/U%, **Relevance Assessment Note (incl. rotation impact & competitiveness)**.
    **4.7 Betting Odds Comparison & Market Check:**
        *   **Objective:** Compare analysis with market view, identify potential value.
        *   **Analysis:**
            *   Retrieve 1X2 & O/U 2.5 odds.
            *   Compare Analysis vs. Odds: Does analysis (Form/Momentum, Context, **Verified/Confident Rotation Assessment (4.4)**, Relevant H2H, Home/Away Synthesis) align with market?
            *   **Identify Discrepancies:** Highlight contradictions. Discuss if odds accurately reflect verified rotation/environment impacts, or just base status/form. Note potential value.
        *   **Conceptual Scratchpad Storage:** Comparison notes, discrepancy identification (esp. re rotation/environment).
    **4.8 Weather Forecast Integration:**
        *   **Objective:** Assess weather impact.
        *   **Mandatory Search:** Venue/kick-off time forecast.
        *   **Analysis:** Note significant conditions and likely impact. Link to 4.1 environmental factors.
        *   **Conceptual Scratchpad Storage:** Forecast, impact note.
    **4.9 Home/Away Strength Synthesis:**
        *   **Objective:** Focused view of home/away dynamic including context.
        *   **Analysis:**
            *   Compare season H/A records (4.1) vs recent H/A form (4.2).
            *   Integrate relevant venue H2H (4.6).
            *   **Overlay impact of verified/confidently expected rotation (4.4 with confidence level).**
            *   Consider travel/climate/altitude impact & mitigation (4.1).
            *   Synthesize expected H/A dynamic.
        *   **Conceptual Scratchpad Storage:** Synthesized H/A dynamic summary (incorporating rotation confidence, travel/climate/altitude & mitigation).
5.  **Final Prediction:** Based on comprehensive analysis from the conceptual scratchpad:
    *   **5.1 Dynamic Weighting of Factors:** Before synthesizing, **explicitly state the key factors being given the most weight for this specific match prediction and *why* based on the competition, stage, team situations, environmental factors, and data verification levels (esp. rotation confidence).**
    *   **5.2 Synthesize Key Findings & Arguments:**
        *   List strongest arguments referencing key data points (League/Tier Gap, Verified Form/Momentum, Reliability data [if avail., noting 'n'/confid.], **Rotation Assessment [incl. verification confidence]**, Relevant H2H [incl. relevance/competitiveness], Home/Away Synthesis [incl. environment/rotation factors], Motivation, Verified Key Absences, Performance vs Relevant Styles).
        *   **State how conflicting data is weighed, referencing dynamic weighting (5.1):**
    *   **5.3 Identify Plausible Scenarios:** Outline 2-3 narratives based on weighted synthesis, considering rotation confidence and H2H resilience.
    *   **5.4 State Primary Match Outcome Prediction:** (Team A Win, Draw, Team B Win).
    *   **5.5 Confidence Assessment & Market Check:**
        *   Reiterate market contradictions & rationale (referencing dynamic weights, rotation confidence, H2H nuance).
        *   State confidence level (High/Medium/Low). **Mandatorily lower confidence if Rotation Verification Confidence=Low or Reliability/Timing data=Unavailable.**
        *   Consider suggesting conservative options (DC, AH) if confidence is Medium/Low.
    *   **(Optional) Acknowledge Secondary Scenarios:**
    *   **5.6 Predict Total Goals (Over/Under 2.5):**
        *   Synthesize multiple factors (Form O/U, H2H O/U, GF/GA, **Impact of Verified/Confident Rotation**, Tactics, Environment/Weather, Market lean, Competition context). Consider errors/brilliance potential.
        *   State O/U Prediction and Confidence Level. Justify balancing factors.
    *   **5.7 Formulate Most Robust Combined Prediction:** (e.g., Team A Win and Under 2.5 goals).
    *   **5.8 Scoreline(s) (Contextual):** Suggest scoreline(s) aligned with Outcome + O/U. Justify briefly using relevant factors (defence, GF/GA, Reliability/Timing [if avail.], game flow).
    *   **5.9 Justification:** Provide concise rationale weaving together key arguments, **explicit dynamic weighting logic (5.1)**, handling of conflicting data, **rotation verification status/confidence**, H2H relevance/competitiveness, **data gap acknowledgements & confidence adjustments**, odds check, O/U synthesis, and scoreline rationale.
