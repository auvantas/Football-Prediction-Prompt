**### Prompt V16 ###**

1.  **Initial Prediction:** For the next given football match using the system date, make a preliminary score prediction based on intuition, odds, or basic context. Save this prediction mentally or on a conceptual "scratchpad."
2.  **Analysis Target:** Focus analysis on the specific match provided.
3.  **Iterative Analysis Loop & Conceptual Data Handling:**
    Follow the "Data Check" steps (Step 4) below for the targeted match.
    *   **Conceptual Scratchpad & Context:** Throughout this process, findings are stored conceptually on a "scratchpad" used during the generation of the response. This collected information forms the basis for subsequent analysis steps. Check the scratchpad for completeness before moving to calculations or subsequent steps.
    *   **Dynamic Gap Filling & Persistence:** Actively attempt to fill data gaps identified during the process by performing additional, targeted searches as detailed in the relevant sections of Step 4. **Crucially, do not proceed to the next analytical calculation or step if the required input data (e.g., HT scores, goal times) for that step is marked as missing on the scratchpad.** Continue searching for the specific missing data point(s) using targeted queries until the data is found or confirmed as definitively unobtainable after reasonable attempts.
    *   **Iteration:** If newly found data significantly changes the picture, iterate through relevant parts of Step 4 again, refining the analysis based on the updated information on the scratchpad.
    *   **Prompt Chaining Context:** The complete analysis presented in the response (incorporating initially found and dynamically searched data) becomes part of the conversation history. This history serves as the context for subsequent prompts (prompt chaining), allowing follow-up questions or refinements to build upon the established analysis. The "storage" mechanism is this contextual carry-forward within the conversation session.
    *   **Continuation of Steps:** Retrieve previous output and stored scratchpad data to find where the last step was complete or incomplete, continuing from that position, ensuring required data for the current step is present before executing it.
4.  **Data Check:** Perform the following analysis points, using grounded search where necessary:

    **4.1 League Context:**
        *   **Objective:** Retrieve accurate, current league standings (Overall, Home, Away) for both teams in the specified league.
        *   **Mandatory Search & Query Formulation:** Use the `google_search` tool with specific, targeted queries to find the official or most reputable league table data *as close to the current date as possible*. Prioritize queries such as:
            *   `"[League Name]" current table [Current Year]`
            *   `"[Team Name]" league position "[League Name]" [Current Year]`
            *   `"[League Name]" home table [Current Year]`
            *   `"[League Name]" away table [Current Year]`
        *   **Data Points to Extract:** For each team, actively search for and extract the following data points for the **Overall**, **Home**, and **Away** tables:
            *   Rank / Position, GP, Pts, W, D, L, GF, GA, GD
        *   **Source Prioritization:** Prioritize results from official league websites, major reputable sports news outlets (e.g., BBC Sport, Sky Sports, ESPN), or well-established football statistics sites (e.g., FotMob, Soccerway, FlashScore, WhoScored).
        *   **Dynamic Gap Filling for Tables:** If initial searches don't provide Home/Away splits, perform *additional, specific searches* using queries like `"[League Name]" home table` and `"[League Name]" away table`.
        *   **Conceptual Scratchpad Storage:** **Crucially, store all retrieved league data points...** Note the source or date if possible...

    4.1.1 **Odds Search:** Retrieve match betting odds for, Over/Under 2.5 Goals, Correct Score, Double Chance, Both Teams To Score, Handicap Markets. Store findings on the conceptual scratchpad...

    **4.2 Recent Form Analysis (Last 10 Official Matches):**
        *   **Objective:** Identify the 10 most recent official matches for each team and their outcomes.
        *   **Mandatory Search & Data Collation:** Use search to find the results. **Explicitly list the 10 matches found for each team** on the conceptual scratchpad, including Opponent, Competition, Date, and **Full-Time (FT) score**. Prioritize current league matches > recent domestic cup matches > other official competitions.
        *   **Analysis (Based on listed 10 matches):**
            *   Analyse W-D-L sequence and record (W, D, L counts).
            *   Analyse wins/draws/losses against teams of similar, higher, and lower standing (based on league context from 4.1).
            *   Analyse home-specific and away-specific form within these 10 games.
            *   Evaluate total goals scored and conceded trends across these 10 games.
            *   Calculate clean sheet percentages and failed-to-score percentages for these 10 games.
            *   **Calculate the percentage of these specific 10 games that finished Over 2.5 total goals and Under 2.5 total goals for each team.**
        *   **Conceptual Scratchpad Storage:** Store the list of 10 matches, the WDL record, GF/GA, CS%, FTS%, and O/U 2.5% for the last 10 games.

    **4.3 Reliability/Comeback/Choke/Timing Analysis (Based on Last 10 Official Matches Identified in 4.2):**
        **4.3.1 HT/FT Score Retrieval (Mandatory Prerequisite):**
            *   **Objective:** Obtain the Half-Time (HT) score for **each** of the 10 specific matches listed on the scratchpad from Step 4.2.
            *   **Methodology - Persistent Targeted Search:**
                *   For *each* of the 10 matches per team where the HT score is not yet on the scratchpad:
                    *   Leverage Stored Data: Use the precise details already stored (Team A, Team B, Competition, Date, known FT score).
                    *   Formulate Targeted Dynamic Searches: Generate precise queries specifically designed to find detailed match statistics or reports. **Prioritize queries including "Sofascore" or known team nicknames (e.g., "The Rams", "The Clarets") alongside standard queries:**
                        *   `Sofascore [Team A name/nickname] vs [Team B name/nickname] [Competition] [Date] HT FT`
                        *   `[Team A name/nickname] vs [Team B name/nickname] stats [Competition] [Date] Sofascore`
                        *   `Match report [Team A] vs [Team B] [Competition] [Date]`
                        *   `What was the half time score [Team A] vs [Team B] [Date]`
                    *   Execute Search & Extract: Use `google_search`. Carefully analyze snippets/pages, prioritizing Sofascore match pages if found. Verify extracted HT score corresponds exactly to the correct match. Use other reliable sources (FotMob, FlashScore, BBC Sport, official sites) if needed, cross-referencing if possible.
            *   **Conceptual Scratchpad Update & Checkpoint:** Add verified HT scores to the scratchpad for each match. Mark any match where the HT score remains definitively unobtainable after targeted attempts. **Do not proceed to the Reliability/Comeback/Choke Calculation (4.3.2) until this retrieval process has been attempted for all 10 matches for both teams and the results (found score or 'unobtainable' status) are recorded on the scratchpad.**
        **4.3.2 Reliability/Comeback/Choke Calculation:**
            *   **Objective:** Calculate performance based on HT status.
            *   **Condition:** Proceed *only* using the HT/FT data collated in 4.3.1.
            *   **Calculation:**
                *   Calculate Reliability: % of games won when leading at HT.
                *   Calculate Comeback: % of games won or drawn when trailing at HT.
                *   Calculate Choke: % of games lost or drawn when leading at HT.
            *   **Acknowledge Limitations:** Count the number of games with confirmed HT scores used for the calculation. If HT scores were unobtainable for a significant number (e.g., >2-3 per team), clearly state that the resulting percentages are based on limited data or cannot be reliably calculated.
            *   **Conceptual Scratchpad Storage:** Store calculated percentages (or inability to calculate) and the number of games basis.
        **4.3.3 Goal Timing (ES / ST) Retrieval & Calculation (Attempt if Possible):**
            *   **Objective:** Find precise goal times to calculate Early Score (ES) and Score Time (ST) distributions.
            *   **Method - Attempt 1 (Last 10 Matches):**
                *   **Targeted Search:** For *each* of the 10 matches listed in 4.2, perform targeted searches focusing on retrieving detailed timelines or event logs. Prioritize Sofascore, FotMob, FlashScore etc. Use queries like:
                    *   `Sofascore [Team A] vs [Team B] [Competition] [Date] goal times`
                    *   `[Team A] vs [Team B] minute by minute [Date] Sofascore`
                    *   `Goal timeline [Team A] vs [Team B] [Date]`
                *   **Data Collation:** Collect all found precise goal times (minute) for both teams across these 10 games. Store on scratchpad, noting source.
                *   **Sufficiency Assessment:** Evaluate if precise times have been found for a sufficient majority (e.g., >80-90%) of the *total goals scored* (calculated in 4.2) across these 10 matches for *each* team.
            *   **Method - Attempt 2 (Last 5 Matches Fallback - *If Attempt 1 Failed*):**
                *   **Condition:** If goal time data from the Last 10 attempt was deemed insufficient.
                *   **Targeted Search (Last 5):** Repeat the targeted search process (as above) *specifically for the 5 most recent matches* listed in 4.2 for each team.
                *   **Data Collation (Last 5):** Collect all found precise goal times for these 5 games. Store on scratchpad.
                *   **Sufficiency Assessment (Last 5):** Evaluate if precise times have been found for a sufficient majority (e.g., >80-90%) of the *total goals scored* across *these 5 matches* for *each* team.
            *   **Calculation (Conditional):**
                *   **Proceed ONLY if sufficient goal time data was retrieved** (either from Last 10 or Last 5 attempt).
                *   **State Basis:** Clearly state if calculations are based on Last 10 or Last 5 games and report the total number of goals with known times that were analyzed.
                *   Calculate Early Score (ES): % of analyzed goals scored within minutes 1-15 OR 46-60.
                *   Calculate Score Time (ST): Distribution (%) of analyzed goals in brackets: 1-15, 16-30, 31-45+, 46-60, 61-75, 76-90+.
                *   **Conceptual Scratchpad Storage:** Store calculated ES/ST percentages (or inability statement) and the basis (scope/number of goals).
            *   **Final Statement (If Both Attempts Fail):** If sufficient goal time data could not be retrieved even for the Last 5 matches after targeted searches, **state clearly that ES and ST percentages could not be reliably calculated due to lack of precise goal timestamp data.** Do not present percentages based on minimal data.

    **4.4 Team News and Injuries:**
        *   Search for confirmed significant injuries and suspensions... Assess impact... Store findings...

    **4.5 Situational and Tactical Context Analysis:**
        *   Evaluate match importance... Infer tactics... Assess fixture congestion... Note managerial changes... Synthesize...

    **4.6 Head-to-Head (H2H) Analysis:**
        *   Search for recent H2H results... Calculate O/U 2.5% for these H2H games... Store findings...

    **4.7 Betting Odds Comparison:**
        *   Note provided odds... Compare with analysis... Re-evaluate if conflict...

    **4.8 Weather Forecast Integration:**
        *   Search for forecast... Note significant conditions... Store findings...

    **4.9 Home/Away Strength Synthesis:**
        *   Integrate home/away form, H2H, league context... from scratchpad into final assessment.

5.  **Final Prediction:** Based on the comprehensive analysis drawing from all stored findings on the conceptual scratchpad:
    *   Synthesize Key Findings & Identify Plausible Scenarios...
    *   Determine Primary Prediction Format...
    *   State Primary Match Outcome Prediction...
    *   (Optional) Acknowledge Secondary Scenarios...
    *   Predict Total Goals (Over/Under 2.5)... State O/U Prediction... (Optional) Confidence level.
    *   Formulate Most Robust Combined Prediction...
    *   Scoreline(s) (Contextual)...
    *   Justification... Address specific match.

---


*(Example match and odds added as per request)*

**Tottenham v Southampton**

**Tottenham**
**1.36**

**Draw**
**5.00**

**Southampton**
**7.00**
