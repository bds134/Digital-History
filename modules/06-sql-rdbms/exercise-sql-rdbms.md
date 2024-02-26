# Join and Map SES with Geo Data Viewer

Let's use some the [SES data](/modules/06-sql-rdbms/data-ses/) to build a geo-spatial database that we can map with a mapping extension in VSCode.

- create new db called 'SES'
- add your tables
- copy in data
- run sql statement:
  - add these fields start_year,state,site,summary,event_quote,lat,lon
  - join data (you will need fully qualified column names such as 'events.id')
  - order by start_year, state, site
- save as csv
- add the Geo Data Viewer
- view data
- filter by start_year

Share the csv file that is produced by the join through email or via your repo.

Take a screenshot of the map you make and send me the image via email or put it in your repo.
