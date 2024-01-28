## Module 1 Homework Solutions

## Question 1. Knowing docker tags

![Solution 1](<Solution 1.png>)

## Question 2. Understanding docker first run 

![Solution 2](<Solution 2.png>)

## Question 3. Count records 

```
select count(*) as taxi_trips
from public.green_taxi_data
where date(lpep_pickup_datetime) = '2019-09-18' and 
date(lpep_dropoff_datetime) = '2019-09-18';
```

```
15612
```

![Solution 3](<Solution 3.png>)

## Question 4. Largest trip for each day

Which was the pick up day with the largest trip distance?

```
select date(lpep_pickup_datetime), max(trip_distance)
from public.green_taxi_data
group by 1
order by 2 desc;
```

```
2019-09-26
```

![Solution 4](<Solution 4.png>)

## Question 5. Three biggest pick up Boroughs

Which were the 3 pick up Boroughs that had a sum of total_amount superior to 50000?

https://s3.amazonaws.com/nyc-tlc/misc/taxi+_zone_lookup.csv

```
select lkp."Borough", sum(total_amount) as total_amt from public.green_taxi_data gt
left outer join public.taxi_zone_lookup_data lkp
on gt."PULocationID"=lkp."LocationID"
where date(lpep_pickup_datetime) = '2019-09-18'
group by 1
having sum(total_amount) > 50000
order by 2 desc;
```

![Solution 5](<Solution 5.png>)

## Question 6. Largest tip

For the passengers picked up in September 2019 in the zone name Astoria which was the drop off zone that had the largest tip?
We want the name of the zone, not the id.

```
with src_data as (
	select "DOLocationID",max(tip_amount) as max_tip from public.green_taxi_data gt
left outer join public.taxi_zone_lookup_data lkp
on gt."PULocationID"=lkp."LocationID"
where lkp."Zone" = 'Astoria'
group by 1
order by 2 desc
limit 1)

select lkp."Zone" from src_data src
inner join public.taxi_zone_lookup_data lkp
on src."DOLocationID"=lkp."LocationID";
```

![Solution 6](<Solution 6.png>)

## Terraform

## Question 7. Creating Resources

After updating the main.tf and variable.tf files run:

```
terraform apply
```

Paste the output of this command into the homework submission form.

![Solution 7](<Solution 7.png>)