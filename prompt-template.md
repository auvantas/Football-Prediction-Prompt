### V14 Prompt ###

1.  **Initial Prediction:** For the given football match, make a preliminary score prediction based on intuition, odds, or basic context. Save this prediction mentally or on a conceptual "scratchpad."
2.  **Analysis Target:** Focus analysis on the specific match provided.
3.  **Iterative Analysis Loop & Conceptual Data Handling:**
    Follow the "Data Check" steps (Step 4) below for the targeted match.
    *   **Conceptual Scratchpad & Context:** Throughout this process, findings are stored conceptually on a "scratchpad" used during the generation of the response. This collected information forms the basis for subsequent analysis steps.
    *   **Dynamic Gap Filling:** Actively attempt to fill data gaps identified during the process by performing additional, targeted searches as detailed in the relevant sections of Step 4.
    *   **Iteration:** If newly found data significantly changes the picture, iterate through relevant parts of Step 4 again, refining the analysis based on the updated information on the scratchpad.
    *   **Prompt Chaining Context:** The complete analysis presented in the response (incorporating initially found and dynamically searched data) becomes part of the conversation history. This history serves as the context for subsequent prompts (prompt chaining), allowing follow-up questions or refinements to build upon the established analysis. The "storage" mechanism is this contextual carry-forward within the conversation session.
    *   **Missing Data:** Use stored data and results that are incomplete to continue the search to complete required 'Dynamic Gap Filling'. Do not continue on to the next step or stage of the analysis until all data required for analysis is complete.
4.  **Data Check:** Perform the following analysis points, using grounded search where necessary:
    4.1 **League Context:** Retrieve current league positions for both teams (overall, home, and away tables if available in the correct league). Use search if needed. Store findings on the conceptual scratchpad.
	4.1.1 **Odds Search:** Retrieve match betting odds for, Over/Under 2.5 Goals, Correct Score, Double Chance, Both Teams To Score, Handicap Markets. Store findings on the conceptual scratchpad for further analsyis.
    4.2 **Recent Form Analysis (Last 5 Official Matches):**
        *   Use search to collect W-D-L results for the last 5 official games (prioritizing league, then cup). List matches, opponents, and competition. This list of specific matches forms the basis for targeted data retrieval in step 4.3.
        *   Analyse wins/draws/losses against teams of similar, higher, and lower standing (if known) to gauge strength relative to the current opponent.
        *   Analyse home-specific and away-specific form within these recent games.
        *   Evaluate goals scored and conceded trends (totals and per game average) in these recent matches.
        *   Calculate clean sheet percentages and failed-to-score percentages from these last 5 games.
        *   **Calculate the percentage of these last 5 games that finished Over 2.5 total goals and Under 2.5 total goals for each team.** Store findings on the conceptual scratchpad.
    4.3 **Reliability/Comeback/Choke/Timing Analysis (Based on Last 5 Official Matches Identified in 4.2):**
        *   **Data Retrieval (HT/FT Scores - Prioritize this):**
            *   Goal: Find the Half-Time (HT) score and Full-Time (FT) score for the 5 most recent official matches for both teams involved (identified in step 4.2).
            *   Prioritization: Current league matches > recent domestic cup matches > final matches from the previous league season (if needed to reach 5 games).
            *   Methodology for Finding Missing HT/FT Data:
                *   Initial Broad Scan & Gap Identification: Start with broader searches (e.g., "Team X last 5 matches results", "Team X league form"). Collate retrieved info onto the conceptual 'scratchpad'. Compare against requirements (need HT/FT for last 5 games) and flag gaps (e.g., missing HT scores for specific matches from step 4.2).
                *   Formulating Targeted Dynamic Searches: If HT/FT scores are missing for specific matches after the initial scan, generate precise queries dynamically based on the known match details (Teams, Competition, Date from step 4.2). Prioritize query patterns designed to find comprehensive match statistics pages or detailed match reports, as these are most likely to contain HT/FT data. Examples:
                    *   Match statistics \[Team A] vs \[Team B] \[Date]
                    *   Match report \[Team A] vs \[Team B] \[Competition] \[Date]
                    *   \[Team A] \[Team B] \[League] \[Date] score summary stats
                    *   (Secondary patterns): \[Team A] vs \[Team B] \[Competition] \[Date] half time full time score, \[Team A] \[Team B] \[Date] HT FT result
                *   Tool Execution: Execute these specific, dynamically generated queries using the google\_search tool.
                *   Information Extraction and Verification: Analyse the search result snippets from pages identified (ideally stats/report pages). Prioritize reliable sources (official league websites, major sports news outlets like FIFA/ESPN/BBC/L'Équipe, established stats sites like Sofascore/Soccerway/WhoScored/FotMob/Flashscore/Footystats/Btfstats/football-data/totalcorner/soccerstats, reputable betting sites). Extract the specific HT score linked to the correct FT score for the identified match. Cross-reference using multiple sources if possible to increase confidence.
                *   Updating the Conceptual Scratchpad: Add reliably found HT/FT scores to the internal 'scratchpad', completing the dataset needed for analysis. Indicate if any data remains definitively missing after targeted attempts.
        *   **Calculation (Based on most complete data retrieved):**
            *   Calculate Reliability: % of games won when leading at HT (Number of Wins when Leading HT / Number of Times Led at HT) on a separate line.
            *   Calculate Comeback: % of games won when trailing at HT (Number of Wins when Trailing HT / Number of Times Trailed at HT) on a separate line.
            *   Calculate Choke: % of games lost when leading at HT (Number of Losses when Leading HT / Number of Times Led at HT) on a separate line.
            *   Note: If insufficient data exists for a specific situation after targeted searches (e.g., fewer than 2-3 instances of "Times Led at HT"), clearly state that the corresponding stat could not be reliably calculated due to lack of occurrences or persistently missing HT score data. Store findings on the conceptual scratchpad.
        *   **Goal Timing Analysis (ES / ST - Attempt if possible, acknowledge difficulty):**
            *   Data Requirement: Specific minute each goal was scored in the 5 most recent official matches (identified in step 4.2).
            *   Feasibility: Acknowledge difficulty in finding comprehensive, accurate goal times via standard search, as they are usually embedded within detailed reports.
            *   Targeted Data Retrieval & Dynamic Search: Actively attempt to find goal times using the same targeted dynamic search methodology described above for HT/FT scores, focusing on finding comprehensive match statistics or match report pages for the specific matches identified in step 4.2. Look for goal scorer details including timestamps within these reports/stats pages. Use specific queries like:
                *   Match statistics \[Team A] vs \[Team B] \[Date]
                *   Match report \[Team A] vs \[Team B] \[Competition] \[Date]
                *   Minute by minute \[Team A] vs \[Team B] \[Date]
                *   \[Team Name] vs \[Opponent Name] \[Competition] \[Date] goal times details
            *   Store any found goal times on the scratchpad.
            *   Calculation (Perform only if sufficient goal time data is retrieved across several matches):
                *   Calculate Early Score (ES): % of the retrieved goals scored within the first 15 minutes of either half (Minutes 1-15 and 46-60). State the total number of goals found and used for this calculation on a separate line.
                *   Calculate Score Time (ST): Provide the distribution (%) of retrieved goals falling into approximate time brackets: 1-15, 16-30, 31-45+, 46-65, 66-80, 81-90+. State the total number of goals found and used for this calculation on a separate line.
            *   Crucial Note: If insufficient or inconsistent goal time data is found after the targeted search attempt (e.g., times found for only a small fraction of the total goals scored across the 5 games, or if comprehensive match reports/stats pages could not be found/parsed), state clearly that ES and ST percentages could not be reliably calculated due to lack of precise goal timestamp data from the search results. Avoid presenting percentages based on minimal data. Store findings (or lack thereof) on the conceptual scratchpad.
    4.4 **Team News and Injuries:**
        *   Search for confirmed significant injuries and suspensions affecting key players for the upcoming match.
        *   Assess the potential impact of these absences on team strength and tactics, **specifically noting absences of key attackers (might favor Under) or defenders (might favor Over).** Store findings on the conceptual scratchpad.
    4.5 **Situational and Tactical Context Analysis:**
        *   Evaluate match importance for each team (e.g., league points needed, cup progression, rivalry). **Consider if high stakes might lead to caution (Under) or desperation (Over).**
        *   Infer likely tactical approaches based on context, form, and manager tendencies **(e.g., defensive focus vs attacking intent).**
        *   Assess fixture congestion and potential for squad rotation.
        *   Note any recent managerial changes and their potential short-term impact. Synthesize these factors based on stored findings.
    4.6 **Head-to-Head (H2H) Analysis:**
        *   Search for and briefly review results of recent H2H matches (last 2-4 meetings if available). Note goal trends or consistent outcomes. **Explicitly calculate the percentage of these recent H2H matches that finished Over 2.5 total goals and Under 2.5 total goals.** Consider relevance. Store findings on the conceptual scratchpad.
    4.7 **Betting Odds Comparison:**
        *   Note the provided betting odds.
        *   Compare your analytical assessment (based on stored findings from previous steps) with the odds. If conflict exists, re-evaluate but prioritize data-driven findings and context.
    4.8 **Weather Forecast Integration:**
        *   Search for the weather forecast for the match location and time. Note significant conditions and potential impact. Store findings.
    4.9 **Home/Away Strength Synthesis:**
        *   Integrate the specific home/away form (from step 4.2), H2H dynamics (step 4.6), and league context (step 4.1) stored on the scratchpad into the final assessment.

5.  **Final Prediction:** Based on the comprehensive analysis drawing from all stored findings on the conceptual scratchpad:
    *   **Synthesize Key Findings & Identify Plausible Scenarios:**
        *   Briefly summarize the strongest factors derived from the scratchpad analysis.
        *   Based on this synthesis, identify the **most plausible scenario(s)** for the match result (Home Win, Draw, Away Win). Evaluate the relative likelihood and confidence in each scenario based on the weight of evidence (e.g., "Draw highly likely due to X, Y; Narrow Away Win plausible due to Z; Home Win unlikely due to A, B").
    *   **Determine Primary Prediction Format:**
        *   If one scenario (e.g., Draw) is clearly dominant and significantly more likely than others based on the analysis, identify this as the **Primary Specific Outcome Prediction**.
        *   If two scenarios involving one team avoiding defeat (e.g., Draw *and* Away Win) are identified as the *most plausible* outcomes and are *significantly more likely* than the third outcome (Home Win), identify the corresponding **Primary Double Chance Prediction** (e.g., Away Win or Draw) as the most logical representation of the analysis.
        *   If the analysis suggests a highly unpredictable match with no clear lean (rare), state this uncertainty.
    *   **State Primary Match Outcome Prediction:** Clearly state the primary prediction determined above (e.g., "Primary Prediction: Draw", or "Primary Prediction: Away Win or Draw").
    *   **(Optional) Acknowledge Secondary Scenarios:** If a Double Chance wasn't the primary prediction, but other scenarios were deemed plausible (though less likely), briefly mention them for context (e.g., "While Draw is most likely, a narrow Away Win (0-1) is also plausible."). If a Double Chance *was* the primary prediction, this step can be skipped as the component scenarios are implicitly covered.
    *   **Predict Total Goals (Over/Under 2.5):**
        *   Synthesize O/U Factors: Based on stored findings (recent form O/U%, H2H O/U%, team news impact, expected tactics, situational factors), weigh the evidence favouring Over 2.5 goals against the evidence favouring Under 2.5 goals, considering the *primary prediction* scenario(s).
        *   State O/U Prediction: Clearly state the prediction as either "Over 2.5 goals" or "Under 2.5 goals".
        *   (Optional): Briefly state the confidence level.
    *   **Formulate Most Robust Combined Prediction:**
        *   **Combine the Primary Match Outcome Prediction and the Total Goals Prediction into a single, logical, and robust statement.** This represents the core takeaway from the analysis. (e.g., *"The most robust combined prediction derived from the analysis is: Away Win or Draw AND Under 2.5 goals"*, or *"The most robust combined prediction derived from the analysis is: Draw AND Under 2.5 goals"*).
    *   **Scoreline(s) (Contextual):** Provide **illustrative scoreline(s)** that align with the **Most Robust Combined Prediction**. (e.g., If predicting "Away Win or Draw AND Under 2.5", scores like 0-1, 1-1, 0-0 fit).
    *   **Justification:** Justify *both* the Primary Match Outcome Prediction (explaining *why* a specific outcome *or* a Double Chance was chosen as the most logical representation) and the Over/Under 2.5 goals prediction by referencing the key synthesized factors supporting the analysis. Explain how these factors lead to the **Most Robust Combined Prediction**. Address the specific match provided.


(add in the two teams and odds including draw example below)

Tottenham v Southampton

Tottenham
1.36

Draw
5.00

Southampton
7.00
