# Insurance-Data-Dashboard
### Dashboard Link :https://app.powerbi.com/links/LeUeLtc6Ta?ctid=a3d2d61d-5751-4b5f-ba05-aec2aeca6ec8&pbi_source=linkShare&bookmarkGuid=5517c014-1f85-4d30-ba3b-0397b1c2b903
---
## Problem Statement

The insurance sector generates large volumes of customer and policy data, but without proper analysis, key insights remain hidden. This dashboard provides a consolidated view of insurance data that helps stakeholders:

- Understand customer distribution and policy trends.

- Monitor claims and revenue performance.

- Identify improvement areas in services through drill-through analysis and slicer-based filtering.

By creating an interactive and visually appealing dashboard, business leaders can make data-driven decisions regarding policies, claims handling, and customer satisfaction.

### Steps Followed

- Step 1 : Connected MS SQL Server database to Power BI Desktop and imported the required dataset.

- Step 2 : Performed data profiling in Power Query Editor by enabling column distribution, column quality, and column profile. Ensured profiling was done on the entire dataset.

- Step 3 : Checked for null and duplicate values. Minor missing values were ignored since they represented less than 1% of the dataset.

- Step 4 : Applied transformations where necessary and ensured proper data types were assigned.

- Step 5 : Added slicers for filtering by:

        Policy Type

        Customer Age Group

        Claim Status

- Step 6 : Designed card visuals to represent KPIs like:

        Total Customers

        Total Premium Amount

        Total Claims Processed


- Step 7 : Calculated conditional column in which, customers were grouped into various age groups.

    for creating new column following DAX expression was written;
       
        Age Group = if [Age] <= 24 then "Young Adult" 
        else if [Age] <= 60 then "Adult" 
        else "Elder"
        
    
![age grp](https://private-user-images.githubusercontent.com/157559708/491249695-6e8b35d3-55da-4e67-954a-2ede5c3d7098.png?jwt=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3NTgyMjQwNTksIm5iZiI6MTc1ODIyMzc1OSwicGF0aCI6Ii8xNTc1NTk3MDgvNDkxMjQ5Njk1LTZlOGIzNWQzLTU1ZGEtNGU2Ny05NTRhLTJlZGU1YzNkNzA5OC5wbmc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjUwOTE4JTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI1MDkxOFQxOTI5MTlaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT0yYmIyYjgzNmZkMTUxYjZlZjM5MzFiZTNiOWFkNjhlNTEyY2FjYmRlNmZlNjY0MTY4YTQ5ZmNmNWQzNTQ3NTgwJlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCJ9.OXBpZs4a_p_MSwNkkULa8E3TCGRalEaaaBVAXX-PKcE)


- Step 8 : Calculated conditional column in which, active/inactive policy was given as per the policy end date
    for creating new column following expression was written;

        Active/Inactive = if [PolicyEndDate] <= #date(2024, 12, 10) then "Inactive" 
        else "Active"
    
![active inactive](https://private-user-images.githubusercontent.com/157559708/491249554-60bf2d62-15b8-4afa-a847-f3d93df20d57.png?jwt=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3NTgyMjM3NzcsIm5iZiI6MTc1ODIyMzQ3NywicGF0aCI6Ii8xNTc1NTk3MDgvNDkxMjQ5NTU0LTYwYmYyZDYyLTE1YjgtNGFmYS1hODQ3LWYzZDkzZGYyMGQ1Ny5wbmc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjUwOTE4JTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI1MDkxOFQxOTI0MzdaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT1mYTNlMTMwODM2ZjQwNzU4MDI5NjY1ZDE1OTY0MTY4ZmY0NDhhNzVhYzZkODdlMTVkZTE0MTY2MTRjZTA2NzAyJlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCJ9.EZZZda8T25GLeMmxU-TT3mYBm3k0QgKpmL7TzJ_3UBY)

- Step 9 : Created bar chart to show claim distribution by region and policy type.

- Step 10 : Added matrix visual to view customer-policy-claim relationship in a structured format.

- Step 11 : Enabled drill-through filter to move from high-level KPIs to detailed policy or customer-level insights.

![drill through](https://private-user-images.githubusercontent.com/157559708/491250113-bf2793c1-3f0c-4c49-b45b-5843df631a57.png?jwt=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3NTgyMjQwNTksIm5iZiI6MTc1ODIyMzc1OSwicGF0aCI6Ii8xNTc1NTk3MDgvNDkxMjUwMTEzLWJmMjc5M2MxLTNmMGMtNGM0OS1iNDViLTU4NDNkZjYzMWE1Ny5wbmc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjUwOTE4JTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI1MDkxOFQxOTI5MTlaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT1lN2RlNTUzMTFiN2IwYjA0MGRjYjcwNWY1NTY2NmE3NmJmYTYxOTA2MTZjNmNjNDFmMTcyMzJhZDY5N2UwMmNmJlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCJ9.8KUEw4SYv_owB1mu8cVZE2HqBxz2kK1yRxGXFvLCVeg)

- Step 12 : Applied consistent theme and formatted visuals for professional presentation.

- Step 13 : Published report to Power BI Service for sharing and accessibility.
  
![publishing](https://private-user-images.githubusercontent.com/157559708/491250805-1b25bb70-42ef-46a8-9194-f4ca0b525219.png?jwt=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3NTgyMjQwNTksIm5iZiI6MTc1ODIyMzc1OSwicGF0aCI6Ii8xNTc1NTk3MDgvNDkxMjUwODA1LTFiMjViYjcwLTQyZWYtNDZhOC05MTk0LWY0Y2EwYjUyNTIxOS5wbmc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjUwOTE4JTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI1MDkxOFQxOTI5MTlaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT1mMmFiNzIzNzJhOGIyODVjZmViMzZkZmU4NTgzOGY0NjNkMzY0ZDFlYzI4OWQyMWFkMjA2Yzg1NjJjNjgxYWVhJlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCJ9.XuXOAOMEiaCpnuPAngtRIRTJvSyzZHoXc4mbA8PtFbo)

---

# Snapshot of Dashboard
## Power BI Desktop View

### Page 1:

![page 1](https://private-user-images.githubusercontent.com/157559708/491249876-61d7f565-6215-43ab-b7e5-ad97f187d58b.png?jwt=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3NTgyMjQwNTksIm5iZiI6MTc1ODIyMzc1OSwicGF0aCI6Ii8xNTc1NTk3MDgvNDkxMjQ5ODc2LTYxZDdmNTY1LTYyMTUtNDNhYi1iN2U1LWFkOTdmMTg3ZDU4Yi5wbmc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjUwOTE4JTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI1MDkxOFQxOTI5MTlaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT1hNGZlMzU2YzA4NjY3YWY5ZDc2MTdhYzgyM2NiNmFiOGYzOGVjOTMyZDJmYjg1YmE2NGVlMGU0MDc0Zjk1YjIzJlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCJ9.vviJ9Wqkl1tygIQpJAkwhMGPB9TtDL7Bb2AZcfVpKm0)

### Page 2:

![page 2](https://private-user-images.githubusercontent.com/157559708/491250034-929c0751-565e-408b-a97d-dc60cc7cba9a.png?jwt=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3NTgyMjQwNTksIm5iZiI6MTc1ODIyMzc1OSwicGF0aCI6Ii8xNTc1NTk3MDgvNDkxMjUwMDM0LTkyOWMwNzUxLTU2NWUtNDA4Yi1hOTdkLWRjNjBjYzdjYmE5YS5wbmc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjUwOTE4JTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI1MDkxOFQxOTI5MTlaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT00YmNiNWZjMWNhNDAwZmNkOGUzMzNiNGMxZWM5Yzg1MGVhOTgyNDRkODI3YzY5NGEyMjk2NmYyMDU2MmZiMGRlJlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCJ9.U-Sf68mIB5nNpzl3OjRpoIlN8xX3Lx3YDJIxPtXE8hg)

## Power BI Service View

### Page 1:

![page 1](https://private-user-images.githubusercontent.com/157559708/491250997-e214a343-d5d7-4b2e-8399-49f67843a725.png?jwt=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3NTgyMjQwNTksIm5iZiI6MTc1ODIyMzc1OSwicGF0aCI6Ii8xNTc1NTk3MDgvNDkxMjUwOTk3LWUyMTRhMzQzLWQ1ZDctNGIyZS04Mzk5LTQ5ZjY3ODQzYTcyNS5wbmc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjUwOTE4JTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI1MDkxOFQxOTI5MTlaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT04ZDZhMzA2OWE2NmQ1ZGNkN2YxMzA4ZTk5NmJkNmU0YmE5MWNmNzlmZWZjZTAyMjk2YTFmMTlkN2U0OTI0NGRlJlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCJ9.PqQjwE1OYRymMXXT9yis4yPcCjEDZvFXSs22EKwQN4s)

### Page 2:

![page 2](https://private-user-images.githubusercontent.com/157559708/491251121-76d033de-b88b-4857-8f70-5bf8d15de235.png?jwt=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3NTgyMjQwNTksIm5iZiI6MTc1ODIyMzc1OSwicGF0aCI6Ii8xNTc1NTk3MDgvNDkxMjUxMTIxLTc2ZDAzM2RlLWI4OGItNDg1Ny04ZjcwLTViZjhkMTVkZTIzNS5wbmc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjUwOTE4JTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI1MDkxOFQxOTI5MTlaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT1mYzMxZTRhNmU2YmRjZDk5NGQ2M2FkOWY4NzZmNTIwNWYxZDcyZTFiOTE4NWRkNWI0MGM4ODEzYjU0ZDFlZmQwJlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCJ9.IikQMR9a3AB3PhkcFh2kbbKUXSopMIVs858r9pkx16A)

---
# Insights

Following inferences can be drawn from the dashboard:

[1] Key Business Metrics

    Premium Amount = ₹5.97M

    Coverage Amount = ₹600.33M

    Claim Amount = ₹16.90M

These KPIs act as the company’s financial heartbeat.

[2] Gender Insights

    Male Policyholders = 5,000

    Female Policyholders = 5,000

Balanced distribution → Equal opportunity for targeted campaigns.

[3] Claims Analysis

    Claims Rejected = 4.4K

    Claims Settled = 3.4K

    Claims Pending = 2.3K

Too many pending claims may indicate inefficiency, while too many rejections may reduce customer trust.

[4] Premium & Policy Insights

    Travel Insurance leads in Premiums = ₹2.5M

58% Active vs 42% Inactive policies means Customer retention is a challenge.

[5] Claim Amount by Age Group

    Adults = ₹8.8M (highest claims)

    Elders = ₹6.4M

    Young Adults = ₹1.7M

Insight: Risk increases with age, can guide premium pricing.

[6] Financial Summary

    Travel Insurance = Highest rejected claims (~₹10M).

    Health Insurance = Highest settled claims (~₹4M).

This shows which products are profitable vs. risky.

---
# Conclusion

The Insurance Dashboard provides a 360-degree view of customer, policy, and claims data. It enables insurers to:

- Improve claim settlement efficiency.

- Target underperforming regions.

- Identify high-value customers.

- Optimize policy offerings based on customer demographics.

This report acts as a strategic decision-making tool, ensuring business growth through data-driven insights.

---
Author - Rajat Singh
B.Tech - Computer Science and Engineering | AI & Data Enthusiast
Email : rajattsingh10@gmail.com | LinkedIn : https://www.linkedin.com/in/rajat-singh-bb941924a/
