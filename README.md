**Spotify Data Analysis Dashboard**

📌 **Project Overview:**
- This project is an interactive Power BI dashboard built using a Spotify dataset to analyze songs, artists, popularity trends, album types, and explicit content patterns.
- The dashboard is designed with four interactive pages, custom navigation buttons, advanced DAX measures, and visually appealing Figma-designed backgrounds.
- The project focuses on transforming raw Spotify data into meaningful insights through dynamic visuals, slicers, and KPIs.

🎯 **Objectives:**
-	Analyze Spotify songs and artists across time (Year, Quarter, Month)
-	Compare popularity, duration, and explicit vs non-explicit content
-	Identify top artists, hit songs, and album distribution
-	Provide a fully interactive user experience with song-level filtering

📂 **Dataset Information:**
-	Dataset Name: Spotify-Data

**Data Transformation** (Calculated Columns):
- The following columns were created using DAX:
	-	Month: Extracted from date
	-	Quarter (Qtr): Derived from date
	-	MonthIndex: Used for correct month sorting
	-	Year: Extracted from date

**Data Modeling & DAX Measures:**
- A separate table _Measures was created to store all calculated measures, ensuring clean and scalable modeling.
- Key Metrics Implemented:
	-	Total Songs
	-	Distinct Songs
	-	Distinct Artists
	-	Average / Max / Min Popularity
	-	Average / Max / Min Duration (in minutes)
	-	Explicit vs Non-Explicit Songs
	-	Percentage of Explicit Songs
	-	Position 1 Songs & Artists
	-	Songs per Artist
	-	Songs per Year
	-	Popularity & Duration trends over time
	-	Album & Singles distribution

**Advanced DAX concepts used:**
-	CALCULATE
-	DISTINCTCOUNT
-	Time-based analysis
-	Conditional calculations
-	Percentage measures

🧭 **Dashboard Pages & Features:**

**1️. Home Page:**
-	Central navigation hub
-	Buttons included on all pages:
	-	Home
	-	Overview
	-	Songs
	-	Artists

**2️. Overview Page:**
- Provides a high-level summary of the Spotify dataset.
- **Visuals Included:**
	-	Songs by Artists (Clustered Bar Chart)
	-	Songs Popularity (Clustered Bar Chart)
	-	Monthly Popularity (Area Chart)
	-	Songs by Month (Clustered Column Chart with conditional color rules)
	-	Album Type Split (Donut Chart)
	-	Content Type (Donut Chart)
	-	Songs by Year (Donut Chart)
	-	Album Popularity (Donut Chart)

**Interactive Elements:**
-	Month & Quarter slicer
-	Song slicer (selecting a song filters the entire page)
-	Image slicer displaying album covers (Spotify-style interaction)

**KPIs Displayed:**
-	Distinct Songs
-	Count of Artists
-	Average Duration (Minutes)
-	Average Popularity

**3. Songs Page:**
- Focused on song-level analysis.
- **Visuals Included:**
	-	Songs Details (Song, Release Date, Album Type, Avg & Max Popularity, Avg Duration)
	-	Songs per Artist
	-	Popular Songs
	-	Chart-Topping Songs
-Fully interactive with slicers.

**4️. Artists Page:**
- Focused on artist-level performance.
- **Visuals Included:**
	-	Artists Overview (Artist, Album Type, Distinct Songs, Position 1 Hits, Album Count, Avg Tracks, Avg Popularity)
	-	Artist Output
	-	Artist Popularity 
	-	#1 Chart Hits

📈 **Key Insights:**

**1. Overall Trends:**
-	A small group of artists contributes a disproportionately large number of songs.
-	Most songs achieve moderate popularity, while only a few become top-performing hits.
-	Singles are more prevalent and generally more popular than full-length albums.
-	Non-explicit songs dominate the dataset, indicating broader audience targeting.

**2. Time-Based Insights:**
-	Song releases vary by month, revealing seasonal patterns in music production.
-	Average popularity fluctuates across months, reflecting changing listener preferences.
-	Recent years show increased song releases, highlighting growth in content creation.

**3. Artist & Song Performance:**
-	High song volume does not always translate into higher popularity for artists.
-	Chart-topping (#1) positions are achieved by only a limited number of artists.
-	Popularity and chart success are highly concentrated among top performers.

🎨 **UI / UX Design:**
-	Custom backgrounds designed using Figma
-	Consistent layout across all pages
-	Spotify-inspired image slicers for enhanced user experience
-	Smooth navigation using buttons

🛠 **Tools & Technologies Used:**
-	Power BI Desktop
-	DAX (Data Analysis Expressions)
-	Figma (UI background design)
-	Data Modeling & Transformation

⚙️ **Technical Documentation:**
- Detailed technical information is available
- https://github.com/Prerana-Bijekar/Spotify-Data-Analysis-Dashboard/blob/main/Documentation/Technical_Details.md
