```SQL
select
	distinct(q1.AirlineName) airlines,
	flights_2018,
	flights_2019,
	(flights_2019 - flights_2018) YoY_Change,
	count(q3.flightdate) total_flights,
    ((flights_2019 - flights_2018) / count(q3.flightdate)) percent_change
from	
(select
	airlinename,
    count(id) flights_2018
from flights
where year(flightdate) = 2018
group by 1) q1
inner join
(select 
	airlinename,
    count(id) flights_2019
from flights f
where year(flightdate) = 2019
group by 1) q2
on q1.airlinename=q2.airlinename
inner join 
(select
	FlightDate,
    Airlinename
from flights f) q3
on q3.airlinename=q1.airlinename
group by 1
order by 2 desc;
```
output

| Airline                   | Flights 2018 | Flights 2019 | YoY Change | Total Flights | Percent Change |
|---------------------------|--------------|--------------|------------|---------------|----------------|
| Southwest Airlines Co.    | 1,352,552    | 1,363,946    | 11,394     | 2,716,498     | 0.0042         |
| Delta Air Lines Inc.      | 949,283      | 991,986      | 42,703     | 1,941,269     | 0.0220         |
| American Airlines Inc.    | 916,818      | 946,776      | 29,958     | 1,863,594     | 0.0161         |

