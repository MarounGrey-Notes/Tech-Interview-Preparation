### How would you figure out the number of basketballs that would fit in this room?
* I would start by confirming the key details - asking for the dimensions of the room to calculate the total volume in cubic feet. Let's assume it's a 10ft x 20ft room with a 12ft high ceiling.
* Next, I'd research the average dimensions of a basketball. According to my search, a regulation size basketball has a circumference of about 30 inches or a diameter of about 9.5 inches.
* Knowing the volume equation is length x width x height, I would calculate the total volume of this room as 10 x 20 x 12 = 2,400 cubic feet
* I would lookup the volume formula for a sphere, which is (4/3)πr3 -> the radius is half the diameter so around 4.75 inches
* Plugging this in gives me a basketball volume of around 2,320 cubic inches
* Converting the room volume to cubic inches - 2,400 cubic ft x (12 inches x 12 inches x 12 inches) = 3,456,000 cubic inches
* Finally dividing the max room volume by basketball volume gives an estimate of 1,490 basketballs that would fit.
### If you had one hour to validate whether a recent spike in traffic was from real users or bots, how would you approach this problem?
* I would first analyze Google Analytics source and medium reports to identify where the abrupt traffic changes came from - confirming unusual referrals, direct traffic, shifts indicating bots
* Using GA I would check geography and filter out suspicious domains. I can further leverage bot filtering and detection tools to analyze patterns
* I would use our server and CDN logs to identify any suspicious or repeated IP addresses and user agents
* Comparing web server logs day-by-day could signal patterns and irregular upticks in non-human urls/requests
* I would research typical browser vs bot behavior in metrics like time-on-site, pages-per-session and bounce rates and cross-check for anomalies
* For ongoing prevention, I would suggest implementing reCAPTCHA and monitoring daily analytics reports to detect surges early
### Estimate how many gas stations there are in Los Angeles county. Explain your methodology.
* I would research credible sources on the typical number of gas stations per capita across US cities and counties. This helps baseline an average.
* I can look up the current population size reported for Los Angeles county - for example on census.gov showing about 10 million people.
* If research showed 25 gas stations per 50,000 people, I would extrapolate that to estimate around 5,000 stations in LA county.
* I have to clearly state that this is an approximation based on typical metrics. The actual number may vary based on area urbanization, highways, geography and a variety of factors.
* To further refine, we could look for open datasets on registered automotive businesses in LA or use mapping APIs to narrow down locations and concentrations by area.
### Your company operates a video sharing website that suddenly goes down. Troubleshoot this by asking me relevant questions about the issue.
First, I would want to ask some clarifying questions:

When did the issue start and was anything changed or deployed around that timeframe?
Are there any common or sporadic error messages occurring?
Can you access the admin interface and basic site pages or is the domain completely unreachable?
Are parts of the site loading slowly or timing out or is it a hard failure?
To investigate further:

I would check the health of our web servers including CPU, memory, network connectivity. Are requests reaching them or failing earlier?
Review load balancer, firewall, and router logs to trace requests and identify failures
Check status of database servers. Are writes/reads timing out?
Inspect website code logs for exceptions being thrown
Review CDN access logs to confirm if assets are caching and serving properly
Check for DNS issues, invalid configurations, or domain registrar problems
The goal is to methodically triage each component and identify at what stage the requests are failing.
### A store sells bookcases for $120 each. The materials for each bookcase cost $70. Last year, the store sold 200 bookcases and made a total profit of $15,000. How much profit will they make this year if they sell 250 bookcases?
Last year's numbers:
Sold 200 bookcases at $120 each = $24,000 revenue
Materials for 200 units at $70 each = $14,000 costs
So profits were $24,000 - $14,000 = $10,000
We know total profits last year were actually $15,000
So the extra $5,000 profit allows for other overhead costs
This year they will sell 250 bookcases
Materials for 250 units at $70 each = $17,500 costs
Selling price remains $120 per bookcase
So revenue from 250 sales is 250 * $120 = $30,000
To calculate profit, we subtract the $17,500 materials costs
Giving us $30,000 - $17,500 = $12,500 profit from bookcase sales
Since overhead costs gave an extra $5,000 profit last year, we can estimate the same this year
Giving an estimated total profit this year of $12,500 + $5,000 = $17,500
### Imagine you're building a smartphone app to locate nearby coffee shops and want to optimize it for speed. What data points and system architecture would contribute most to this goal?
The most important elements that would contribute to optimizing speed for locating nearby coffee shops:

Having a database of geocoded coffee shop locations that can be efficiently queried by latitude/longitude to calculate proximity
Optimizing the accuracy tolerance for locating shops to balance precision with speed
Implementing efficient spatial data structures like a grid, quadtree or geohash that subdivide regions to narrow searches
Building location microservices on the app backend to handle search queries and cache common requests
Using lightweight calls between frontend and backend to transfer just the required location data
On frontend, avoiding expensive UI operations like complex animations in order to maximize responsiveness
### How could we estimate the number of people who own dogs as pets in a medium-sized American city? Outline your step-by-step approach.
Research overall pet and specifically dog ownership rates nationally and in comparable metro areas to establish a baseline ownership percentage
Find the total number of households in the target city area
Identify common household demographics (e.g. families with children) that typically correlate to higher dog ownership
Factor in any additional attributes of the city that could indicate higher or lower dog ownership rates compared to baseline metro areas.
Take the total number of households and multiply by projected ownership percentage to estimate number of dog-owning households
Consider applying a dog per household ratio to arrive at total number of pet dogs
Clearly state methodology used and that this is an estimated projection that could vary based on circumstances





