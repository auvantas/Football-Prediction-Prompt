**### Prompt V16 ###**

1.  **Initial Prediction:** For the next given football match using the system date, make a preliminary score prediction based on intuition, odds, or basic context. Save this prediction mentally or on a conceptual "scratchpad."
2.  **Analysis Target:** Focus analysis on the specific match provided.
3.  **Iterative Analysis Loop & Conceptual Data Handling:**
    Follow the "Data Check" steps (Step 4) below for the targeted match.
    *   **Conceptual Scratchpad & Context:** Throughout this process, findings are stored conceptually on a "scratchpad" used during the generation of the response. This collected information forms the basis for subsequent analysis steps.
    *   **Dynamic Gap Filling:** Actively attempt to fill data gaps identified during the process by performing additional, targeted searches as detailed in the relevant sections of Step 4.
    *   **Iteration:** If newly found data significantly changes the picture, iterate through relevant parts of Step 4 again, refining the analysis based on the updated information on the scratchpad.
    *   **Prompt Chaining Context:** The complete analysis presented in the response (incorporating initially found and dynamically searched data) becomes part of the conversation history. This history serves as the context for subsequent prompts (prompt chaining), allowing follow-up questions or refinements to build upon the established analysis. The "storage" mechanism is this contextual carry-forward within the conversation session.
    *   **Missing Data:** Use stored data and results that are incomplete to continue the search to complete required 'Dynamic Gap Filling'. Do not continue on to the next step or stage of the analysis until all data required for analysis is complete.
    *   **Continuation of Steps:** Retrieve previous output and stored scratch pad data to find where the last step was complete or incomplete, continuing from that position.
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

    4.2 **Recent Form Analysis (Last 10 Official Matches):**
        *   Use search to collect W-D-L results for the last 10 official games... List matches, opponents, competition, date, and FT score... store on the conceptual scratchpad.
        *   Analyse wins/draws/losses against teams of similar, higher, and lower standing...
        *   Analyse home-specific and away-specific form...
        *   Evaluate goals scored and conceded trends...
        *   Calculate clean sheet percentages and failed-to-score percentages...
        *   **Calculate the percentage of these last 10 games that finished Over 2.5 total goals and Under 2.5 total goals for each team.** Store findings...

    **4.3 Reliability/Comeback/Choke/Timing Analysis (Based on Last 10 Official Matches Identified in 4.2):**
        *   **Data Retrieval (HT/FT Scores - Prioritize this):**
            *   Goal: Find the Half-Time (HT) score and Full-Time (FT) score for the 10 most recent official matches...
            *   Prioritization: Current league matches > recent domestic cup matches...
            *   **Methodology for Finding Missing HT/FT Data:**
                *   **Initial Broad Scan & Gap Identification:** Start with broader searches... Collate retrieved info... flag specific matches on the scratchpad where the HT score is missing.
                *   **Leveraging Stored Data for Query Formulation:** Use the precise details already stored... (Team A, Team B, Competition, Date, known FT score)...
                *   **Formulating Targeted Dynamic Searches:** Generate precise queries specifically designed to find detailed match statistics or reports for *each* flagged match. **Prioritize queries that include "Sofascore" or are likely to yield results from Sofascore.com**, alongside standard queries like:
                    *   `Sofascore [Team A] vs [Team B] [Competition] [Date] HT FT`
                    *   `[Team A] vs [Team B] stats [Competition] [Date] Sofascore`
                    *   `Match report [Team A] vs [Team B] [Competition] [Date]`
                    *   `What was the half time score [Team A] vs [Team B] [Date]`
                *   **Tool Execution:** Execute these specific, dynamically generated queries using the `google_search` tool...
                *   **Information Extraction and Verification:** Carefully analyze the search result snippets and linked pages. **Prioritize extracting data directly from Sofascore match pages if they are found and accessible via the search results**, as they typically present clear HT scores. Verify the extracted score corresponds *exactly* to the correct match (Teams, Date, FT score). If Sofascore results are unavailable or inaccessible, use other reliable sources (official sites, major news outlets, other reputable stats sites like FotMob, FlashScore) and cross-reference if possible. Note any persistent discrepancies or the source used.
                *   **Updating the Conceptual Scratchpad:** Add the verified HT scores to the conceptual 'scratchpad', filling the identified data gaps for each match. Mark if any HT score remains definitively unobtainable after targeted attempts.
        *   **Calculation (Based on completed HT/FT data retrieved):**
            *   Calculate Reliability: % of games won when leading at HT...
            *   Calculate Comeback: % of games won when trailing at HT...
            *   Calculate Choke: % of games lost when leading at HT...
            *   Note: If insufficient data exists... state clearly that the corresponding stat could not be reliably calculated... Store findings...
        *   **Goal Timing Analysis (ES / ST - Attempt if possible, acknowledge difficulty):**
            *   Data Requirement: Specific minute each goal was scored...
            *   Feasibility: Acknowledge difficulty in finding comprehensive, accurate goal times...
            *   **Targeted Data Retrieval & Dynamic Search:** Actively attempt to find goal times.
                *   **Primary Source Target (Sofascore):** Utilize the targeted dynamic search methodology (leveraging stored match details) to **specifically locate the Sofascore match page** (or similar detail-rich stats pages like FotMob, FlashScore if Sofascore is unavailable) for *each specific game*. Use queries like:
                    *   `Sofascore [Team A] vs [Team B] [Competition] [Date] goal times`
                    *   `[Team A] vs [Team B] minute by minute [Date] Sofascore`
                *   **Extraction from Source:** Once the relevant Sofascore (or similar reliable stats site's page) is identified via search, parse its timeline, event log, or goalscorer list to extract the specific minute listed for each goal scored.
                *   Store any found goal times on the scratchpad, **noting the source used (e.g., "Sofascore")**.
            *   Calculation (Perform only if sufficient goal time data is retrieved across several matches):
                *   Calculate Early Score (ES): % of the retrieved goals scored within the first 15 minutes of either half (Minutes 1-15 and 46-60)... State the total number of goals found and used...
                *   Calculate Score Time (ST): Provide the distribution (%) of retrieved goals falling into approximate time brackets: 1-15, 16-30, 31-45+, 46-60, 61-75, 76-90+... State the total number of goals found and used...
            *   **Crucial Note:** If, **after specifically attempting to retrieve data from Sofascore (or similar reliable stats sites identified via targeted search)**, insufficient or inconsistent goal time data is found (e.g., times found for only a small fraction of the total goals scored across the 10 games, or if comprehensive reports/stats pages could not be reliably parsed from search results), state clearly that ES and ST percentages could not be reliably calculated due to lack of precise goal timestamp data. Avoid presenting percentages based on minimal data. Store findings (or lack thereof)...

    **4.4 Team News and Injuries:**
        *   Search for confirmed significant injuries and suspensions...
        *   Assess the potential impact... Store findings...

    **4.5 Situational and Tactical Context Analysis:**
        *   Evaluate match importance... Consider if high stakes might lead to caution (Under) or desperation (Over).
        *   Infer likely tactical approaches...
        *   Assess fixture congestion...
        *   Note any recent managerial changes... Synthesize these factors...

    **4.6 Head-to-Head (H2H) Analysis:**
        *   Search for and briefly review results of recent H2H matches... Explicitly calculate the percentage of these recent H2H matches that finished Over 2.5 total goals and Under 2.5 total goals... Store findings...

    **4.7 Betting Odds Comparison:**
        *   Note the provided betting odds.
        *   Compare your analytical assessment... If conflict exists, re-evaluate...

    **4.8 Weather Forecast Integration:**
        *   Search for the weather forecast... Note significant conditions... Store findings.

    **4.9 Home/Away Strength Synthesis:**
        *   Integrate the specific home/away form..., H2H dynamics..., and league context... stored on the scratchpad into the final assessment.

5.  **Final Prediction:** Based on the comprehensive analysis drawing from all stored findings on the conceptual scratchpad:
    *   **Synthesize Key Findings & Identify Plausible Scenarios:**
        *   Briefly summarize the strongest factors...
        *   Based on this synthesis, identify the **most plausible scenario(s)**... Evaluate the relative likelihood...
    *   **Determine Primary Prediction Format:**
        *   If one scenario... is clearly dominant... identify this as the **Primary Specific Outcome Prediction**.
        *   If two scenarios involving one team avoiding defeat... identify the corresponding **Primary Double Chance Prediction**...
        *   If the analysis suggests a highly unpredictable match... state this uncertainty.
    *   **State Primary Match Outcome Prediction:** Clearly state the primary prediction...
    *   **(Optional) Acknowledge Secondary Scenarios:** If a Double Chance wasn't the primary prediction... briefly mention them...
    *   **Predict Total Goals (Over/Under 2.5):**
        *   Synthesize O/U Factors... weigh the evidence...
        *   State O/U Prediction...
        *   (Optional): Briefly state the confidence level.
    *   **Formulate Most Robust Combined Prediction:**
        *   **Combine the Primary Match Outcome Prediction and the Total Goals Prediction into a single, logical, and robust statement.**...
    *   **Scoreline(s) (Contextual):** Provide **illustrative scoreline(s)** that align with the **Most Robust Combined Prediction**.
    *   **Justification:** Justify *both* the Primary Match Outcome Prediction... and the Over/Under 2.5 goals prediction... Explain how these factors lead to the **Most Robust Combined Prediction**. Address the specific match provided.


*(Example match and odds added as per request)*

**Tottenham v Southampton**

**Tottenham**
**1.36**

**Draw**
**5.00**

**Southampton**
**7.00**
