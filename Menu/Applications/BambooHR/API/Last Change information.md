GET /api/gateway.php/sambatv/v1/employees/changed/?since={ISO 8601 timestamp}&type={type}

GET /api/gateway.php/sambatv/v1/employees/changed/?since=2011-06-06T13:00:00%2B02:00
  

{ISO 8601 timestamp} https://www.cl.cam.ac.uk/~mgk25/iso-time.htmlhttps://www.cl.cam.ac.uk/~mgk25/iso-time.html
  // yyyy=mm-ddThh:mmss

{type} 

new user ->  email

Results for Mon Jan 1 01:00:00 2018 GMT-7
Type	Value
Timestamp	1514793600
Server time	2018-08-07T11:58:24-07:00
ISO 8601	2018-01-01T01:00:00-07:00
RFC 2822	Mon, 01 Jan 2018 01:00:00 -0700
Day of the Week	Monday
+1 Hour	1514797200
+1 Day	1514880000
+1 Week	1515398400
+1 Month	1517472000
+1 Year	1546329600

**Note BambooHR doesnt use the correct GMT/UTC  (they use 00:00)** 

    https://api.bamboohr.com/api/gateway.php/sambatv/v1/employees/changed/?since=2018-01-01T01:00:00-07:00
    

## Inserted
( new user added)

## Updated
( offboarding/ deactivation)

## Deleted
( update important user info)
