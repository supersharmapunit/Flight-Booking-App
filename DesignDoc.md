
# Flight Booking Backend System

## Objective:

- We need to build a backend system that can support different features for an airline company. Our end user is going to be someone who wants to book flights and query about flights so we need a robust system to actually help them give the best experience possible. This doc is solely going to focus on the backend part of the system. We want to prepare the whole backend keeping the fact in mind that the code base should be as maintainable as possible.

  

## Requirements:

- A user should be able to search for flights from one place to another.

- User should be able to mention the source and destination details

- User should be able to select the date of the journey

	- [V2] User should be able to search for return flights and multi-city flights

- User should be able to select the class of the flights [Non-mandatory]

- User should be able to select the no of seats they want to book [Non-Mandatory]

- Now based on the above data, we will list down the flights

- We should show our users the best available flights at the top based on time period of flight and then based on the price.

- We need to support pagination so that we can list chunk of flights at one point of time.

- We should support filters of flights based on Price, Departure time, Duration, Airline, Stops.

	- [V2] we can add support for more filters

- A user should be able to book a flight considering that user is registered on the platform.

- Users should be able to cancel a booking, and then based on some criteria we can initiate a refund for them.

- Users should be able to request and book excess luggage for every flight.

- For making a booking, the user has to make a payment [dummy].

- Tracking flight prices should be possible, the user should be notified about any price drops or any delays.

- User should be able to list their previous and upcoming flights

- User should be able to download Boarding pass if they have done online check-in

- Online check in mechanism should be supported

- Notifications via email for completing online check-in before 3 hours of departure.

- Notifications to users about any flight delay.

- Users should be able to review the flight journey if and only if they have booked a flight.

- Review mechanism should involve star rating along with a comment.

- While listing any flight we should also display the review of the flight.

- User should be able to authenticate to our system using email and password

	- [V2] Support ticketing, where user can raise their queries.

- Listing FAQ which will be static data

	- [V2] prepare seat selection

- Coupons for discounts and offers

- While making a booking a person can reserve more than one seats with one login id.

  

## Non Functional Requirements:

- We can expect that we are going to have more flight searches than flight bookings.

- The system needs to be accurate in terms of booking.

- Expect that we will be having approx 1,00,000 total users, 5,00,000 bookings might come up in one quarter.

So in one day we can expect 5000 bookings.

- System should be capable of scaling up to at least 3x the current estimated traffic.

- The system should handle real time updates to flight prices, before the user makes the final booking.

- Concurrency should be handled, using RDBMS should be the good solution.

### Capacity Estimation

#### Storage estimates -

- For the upcoming 5 years, 80,00,000 bookings, 2,00,000 Users, Considering all the users records and booking records take 10 MB of data, the overall 10 TB of memory should be fine for our initial pilot run.

- Traffic estimates - If we consider 30:1 as the search:booking ratio, then at max we expect 150000 search queries a day. 2 query/s