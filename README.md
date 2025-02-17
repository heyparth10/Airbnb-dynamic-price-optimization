# Goals

## Business Goals
For our project we determined three overarching business goals that we would focus on, which we will then expand upon in the analytics goals and general model. Firstly, our central business goal and the overarching goal of the project is to **maximize yearly profit** (via optimization) for a specific listing on Airbnb. All other goals are aimed either at modifying this central goal or constraining it to make our final solution more viable.
Our second business goal is to **create a dynamic pricing tool** that determines a daily price competitive with other localized Airbnb listings. By determining price at the scale of the smallest possible rental period (daily) we wanted to create a model that was as flexible as possible. This means that our optimization model could be specified down to the specific days that a user would/would not expect to be renting their listing, hopefully further increasing the validity of our end result.
Our third main business goal is to **create an easily repeatable design process** for expansion to other locations. Because our current model has a narrow scope in terms of location, we wanted to be certain that as we constructed our model, our design and the choices we made could be easily replicated in the future so that this model could be adapted to have a more universal utility.

## Analytics Goals
Once we had established our business goals, and what we wanted to accomplish in this project, we then created 3 main analytics goals in order to determine how we wanted to meet our goals. Our first analytics goal is to find the **function of demand** in terms of price via k-means clustering. In building our model, we needed a way to effectively project demand given a set of predetermined parameters; therefore, we chose to use k-means clustering on listings from identical neighborhoods with similar attributes. This ensured that the clusters were from properties as similar as possible, so that the differences in attributes were the only things affecting rentals and we could determine their individual influences on our demand variable.
Our second analytics goal is to **predict the intrinsic value** of a property by running a kNN regression using attributes of that property. Similar to the previous goal, we wanted to ensure our  valuation of properties was as accurate as possible, so by using kNN on the many variables presented in the Airbnb dataset (number of beds, amenities, etc.), we knew that the classes we were creating within our regression ensured that any factors not included in our model would have a minimal effect, as they would be adequately described by the NN algorithm.
Our third analytics goal is to calculate the optimal daily price through an optimization model of yearly profit. This goal describes our main business goal in more concrete analytical terms. Once we knew we would be using an optimization model, we could structure our analysis around the component pieces necessary; a modeled demand variable, intrinsic amenities’ additive values for properties, and valuation of costs vs. revenues. By framing our problem as a typical revenue - cost optimization, we could outline our general structure and begin to create the pieces necessary for our final model.

# Assumptions
**Overall Model**
- Competition for the Airbnb listings are other Airbnbs, rather than hotels. We are assuming that prospective customers have already decided to use Airbnb services and thus are only looking at Airbnbs in the area and not comparing prices to nearby hotels.
- Listing prices are separated by month, weekday, weekend, and special events due to the fluctuating demand during those time periods. However, the prices within those groups are held constant; therefore, our data is not time sensitive.
- Partial rentals are not allowed, meaning that different parties cannot simultaneously rent the same listing, even if their combined parties do not exceed that listing’s capacity.
- One Airbnb reservation is allowed per rental period (based on Airbnb’s own policy).
- Sellers will only be considered as those people who already own a property and have owned the same property for a reasonable length. This allows for the assumption that the individual seller using our model will be able to procure the necessary data about their listing easily.

**Variables**
- The parking capacity is reflective of the capacity of the property i.e. the need for excess parking by a renting party was not considered. 
- If greater than two guests belong to a renting party, costs increase by an additional $X per person + $X(G-2). This generalizes the increase in cost based on additional members of the rental party.
- Monthly upkeep includes mortgage payment (or rent), utilities, cleaning fee, HOA fees, etc. and will be used as a single value to approximate the monthly cost to operate the rental.

# Data Sources
Airbnb Listing information
http://insideairbnb.com/get-the-data.html

An additional dataset that is from the San Francisco public safety database for all reported police department incidents to model safety scores
https://data.sfgov.org/Public-Safety/Police-Department-Incidents/tmnf-yvry


