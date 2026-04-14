# Netflix--Dashboard
Netflix Analytics: Netflix shows/ movies Insights Dashboard 
Purpose
An interactive Power BI dashboard designed to analyse and explore Netflix’s global content library, uncovering trends in genres, ratings, release patterns, and geographic distribution.

The Netflix Content Analytics Dashboard is a dynamic and visually engaging Power BI report built to analyse trends within Netflix’s film and television catalogue. It enables users to explore content distribution by genre, rating classification, release year and country availability, helping uncover insights into platform growth and global content strategy.

SQL Data Transformation:

Raw Excel data contained denormalised fields such as multiple cast members stored across separate columns (e.g. cast_1 to cast_50).

Using SQL, these columns were unpivoted and consolidated into relational tables to improve data structure and enable scalable modelling.

Example transformation:

CREATE TABLE netflix_data.netflix_cast AS
(
    SELECT *
    FROM (
        SELECT show_id, cast_1 AS cast FROM netflix_data.cast
        UNION
        SELECT show_id, cast_2 AS cast FROM netflix_data.cast
        UNION
        ...
        SELECT show_id, cast_50 AS cast FROM netflix_data.cast
    ) a
    WHERE cast IS NOT NULL
);

This process:

Converted wide-format Excel data into a normalised relational structure
Removed NULL values
Enabled proper one-to-many relationships in Power BI
Improved filtering and aggregation performance

Tech Stack:
The dashboard was built using the following tools and technologies:

- Power BI Desktop – Primary data visualisation platform used for report development
- Power Query – Data transformation and cleansing layer for reshaping the dataset
- DAX (Data Analysis Expressions) – Used for calculated measures, KPIs, dynamic visuals and conditional logic
- SQL – Data extraction, querying and preprocessing before modelling
- Microsoft Excel – Initial data exploration, validation and preliminary cleaning
- Data Modelling – Relationships established between titles, genres, countries, ratings and release dates
- File Format – .pbix for development and .png for dashboard previews


📊 Key Features:
🎥 Single Title Detail View – In-depth breakdown of individual films and TV programmes, including description, cast, director, rating, release year and country availability
📈 Shows Added by Date – Trend analysis of Netflix content growth over time
🎭 Top 10 Genres Analysis – Highlights the most prominent content categories
🔞 Shows by Rating Classification – Comparison of Films vs TV Programmes across content ratings
🌍 Global Availability Map – Geographic visualisation of content distribution worldwide
🎛 Interactive slicers enabling dynamic filtering by title

Kpis:
How has Netflix’s content catalogue expanded over time?
Which genres dominate the platform?
Does Netflix prioritise films or television programmes?
What rating classifications are most common across content types?
How widely distributed is Netflix content globally?

Data Source
Aggregated public Netflix datasets compiled from multiple open data sources, containing information on titles, genres, cast, directors, release years, rating classifications and country availability.
