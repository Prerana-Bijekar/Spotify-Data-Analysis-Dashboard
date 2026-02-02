📘 **Technical Details**

📂 **Dataset Overview:**
-	Dataset Name: Spotify-Data
-	Data Type: Structured (CSV)
	
🔄 **Data Preparation & Transformation:**

📌 **Calculated Columns (DAX):**

The following calculated columns were created to enable time-based analysis and proper sorting:
- Month = FORMAT('Spotify-Data'[date], "mmm")
- Qtr = "Q" & QUARTER('Spotify-Data'[date])
- MonthIndex = MONTH('Spotify-Data'[date])
- Year = YEAR('Spotify-Data'[date])

🎯 **Purpose:**
-	Enable Month, Quarter, and Year analysis
-	Ensure correct chronological sorting using MonthIndex
-	Support slicers and trend-based visuals

📊 **Key DAX Measures Implemented:**

**1. Volume & Count Metrics:**
-	Total Songs = COUNTROWS('Spotify-data')
-	Distinct Songs = DISTINCTCOUNT('Spotify-data'[song])
-	Distinct Artists = DISTINCTCOUNT('Spotify-data'[artist])

**2. Popularity Metrics:**
-	Avg Popularity = AVERAGE('Spotify-data'[popularity])
-	Max Popularity = MAX('Spotify-data'[popularity])
-	Min Popularity = MIN('Spotify-data'[popularity])

**3. Duration Metrics (Minutes):**
-	Avg Duration Minutes = AVERAGE('Spotify-data'[duration_ms]) / 60000
-	Max Duration Minutes = MAX('Spotify-data'[duration_ms]) / 60000
-	Min Duration Minutes = MIN('Spotify-data'[duration_ms]) / 60000

**4. Explicit Content Analysis:**
-	Explicit Songs = CALCULATE(COUNTROWS('Spotify-data'), 'Spotify-data'[is_explicit] = TRUE())
-	Non-Explicit Songs = CALCULATE(COUNTROWS('Spotify-data'), 'Spotify-data'[is_explicit] = FALSE())
-	Pct Explicit Songs = DIVIDE([Explicit Songs], [Total Songs], 0)

**5. Position Analysis:**
-	Avg Position = AVERAGE('Spotify-data'[position])
-	Position 1 Songs = CALCULATE(COUNTROWS('Spotify-data'), 'Spotify-data'[position] = 1)
-	Position 1 Artists = CALCULATE(DISTINCTCOUNT('Spotify-data'[artist]), 'Spotify-data'[position] = 1)

**6. Album & Track Analysis:**
-	Avg Tracks per Album = AVERAGE('Spotify-data'[total_tracks])
-	Singles Count = CALCULATE(COUNTROWS('Spotify-data'), 'Spotify-data'[album_type] = "single")
-	Albums Count = CALCULATE(COUNTROWS('Spotify-data'), 'Spotify-data'[album_type] = "album")

**7. Artist-Level Measures:**
-	Songs per Artist = COUNTROWS('Spotify-data')
-	Distinct Songs per Artist = DISTINCTCOUNT('Spotify-data'[song])
-	Avg Popularity per Artist = AVERAGE('Spotify-data'[popularity])
-	Position1 Hits per Artist = CALCULATE(COUNTROWS('Spotify-data'), 'Spotify-data'[position] = 1)

**8. Time-Based Measures:**
-	Songs per Year = COUNTROWS('Spotify-data')
-	Avg Popularity per Year = AVERAGE('Spotify-data'[popularity])
-	Avg Duration per Year = AVERAGE('Spotify-data'[duration_ms]) / 60000
-	Pct Explicit per Year = DIVIDE(CALCULATE(COUNTROWS('Spotify-data'),'Spotify-data'[is_explicit] = TRUE()),[Songs per Year],0)

📈 **Slicers & Interactivity:**
-	Month & Quarter slicer for time-based filtering
-	Song slicer to enable song-level drill-down
-	Image slicer using album cover URLs for Spotify-style interaction

🎨 **Visualization & UI Design:**
-	Custom page backgrounds designed using Figma
-	Consistent layout and navigation across all pages
-	Conditional formatting applied to column charts
-	Button-based navigation for smooth user experience

📈 **Dashboard Architecture:**
-	4 interactive pages:
    -	Home
    -	Overview
    -	Songs
    -	Artists
-	Shared slicers and measures across pages
-	Clean star-schema–style logical design

📌 **Technical Highlights:**
-	Advanced DAX using CALCULATE, DIVIDE, and context filtering
-	Separate measures table for scalable modeling
-	Time intelligence without built-in date table
-	Spotify-inspired visual storytelling
