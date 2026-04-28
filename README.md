# Minimum-Viable-Project-for-Onyx-Data-March-April-2026-DataDNA-Dataset-Challenge-
This serves as a full documentation of my project which focuses on data about INTERNATIONAL MARITIME LOGISTICS TERMINAL EFFICIENCY.

The source of the data came from Onyx Data which is one of their monthly data challenges. 

The following is what indicated to the instructions:
🎯 GOAL
🚢 Reduce cargo movement times by 15%
🏗️ Optimize terminal allocation

❓ Key Question
⚙️ How can we optimize terminal allocation to reduce movement times by 15%?

🚧 Suez Canal Disruption Analysis (2021)
📅 Identify when the disruption occurred in the dataset
📦 Analyze impact on cargo movements
📈 Did container volumes spike before or after the incident?
⏱️ Assess impact on terminal efficiency
🌍 Identify most affected regions (EMEA / APAC / AMER)
🔄 Determine recovery timeline to normal operations

📊 Metrics: container_count, move_duration, regional patterns

🏭 Infrastructure Bottlenecks
🚢 Identify regions and terminals driving highest throughput and delays
📦 Determine terminals handling the most cargo movements
🐢 Detect underperforming terminals and vessel types
⚠️ Check if specific vessel categories cause congestion
📊 Compare high vs underperforming terminals within the same region
📈 Analyze if higher utilization leads to longer movement times
🔗 Examine correlation between terminal utilization and movement duration
🏗️ Identify terminals needing capacity expansion

📊 Metrics: terminal_capacity (to be added), container_count, move_duration

⚡ Efficiency Anomalies
📊 Establish baseline efficiency per vessel category
🔍 Identify key drivers of longer movement times (age, location, shift, region)
🚨 Detect outliers indicating operational issues
🌙 Compare night vs day shift performance

📊 Metrics: move_duration, vessel_category, vessel_age, shift, regional_hub


🛠️ Approach for the Report
🧹 Data Preparation
🔍 Identified and inspected data using queries based on usability for the report
🧼 Cleaned the dataset by adjusting data types, applying uppercase/proper case, and trimming values to ensure consistency
📅 Created new columns from the dim_time table (quarter, month, weekday/weekend)
🔑 Detected duplicate vessel_id values in the dimension table (e.g., ID 434 mapped to multiple keys)
🧩 Generated a Surrogate Key (Index column) to maintain a valid 1-to-many relationship
🔗 Mapped the surrogate key back to the fact table (vessel_key) to ensure accurate vessel tracking per movement
📉 Profiled route_geometry and found cardinality = 1
🛑 Determined the column has no analytical value since all routes are identical (same coordinates, different durations)

🧱 Data Modeling
⭐ Structured the data using a star schema (3 dimension tables, 1 fact table)

📊 Data Analysis
⚡ Utilized DAX measures for dynamic calculations including total_containers, average_move_duration, etc. 
🎨 Created supporting measures for legends and visual color encoding

📈 Data Visualization
🧭 Applied a Z-layout for intuitive report flow
📐 Ensured consistency across all pages
🔢 Maintained 6–7 visuals per page for clarity and balance
