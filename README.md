DuckDuckGo Performance Test Script and Test Run
Have successfully created the DuckDuckGo scripts with below transactions and uploaded it to the GitHub repository at https://github.com/KamiyaChopra/Jmeter-Repository- . Additionally, I've attached the “SearchDuckDuckGo.jmx” and “SearchTermsDuckDuckgo.csv” files for quick reference.
The performance test script, which uses Apache JMeter, includes the following three transactions:
1.	Loading the DuckDuckGo homepage (https://duckduckgo.com/).
2.	Typing a suggested search term.
3.	Selecting a search term from the suggested search box.
The script iterates through these transactions using the search terms from the file SearchTerms_DuckDuckGo.txt, picking a different term on each iteration. It runs for 5 minutes, achieving 30 iterations per minute, with each user treated as a new user and caching handled appropriately.
Have granted access to the following:
•	pjohnson@planittesting.com
•	dmidgley@planittesting.com
 
Additional Questions
Assume you were asked by DuckDuckGo to performance test their application 
You have a requirement which states 
"The system should scale to 2000 users". 
Q1. What other questions would you need to ask in order to get enough information to create a workload model. 
Ans. The following questions can be asked to create a workload model:
1.	To understand User Behaviour:
•	What are the typical actions performed by users? (e.g., searching, filtering, clicking results)
•	Are there specific workflows or user journeys that need to be simulated?
•	What types of searches do users typically perform?
2.	To understand Concurrency Requirements:
•	Should 2000 users be active simultaneously, or spread over a time period?
•	Are there peak usage times when higher concurrency is expected?
3.	To understand System Expectations:
•	What response times are expected for key actions (e.g., search, page load)?
•	Are there any acceptable limits for error rates or latency?
•	What are the current limitations of the infrastructure? Are there caching or load balancing strategies in place?
4.	To understand Duration:
•	For how long should the system handle 2000 users? Is this a sustained load or a peak load?
•	How often are these load levels expected to occur?
Q2. Can you re-write the requirement so that it is more descriptive and testable. (You can use made up values.) 
Ans. Please find below details of Revised Requirement: 
The system should handle up to 2000 concurrent users performing actions like searches, filtering, and clicking on results, with an average response time of 2 seconds for search results. The system should handle this load for a sustained period of 1 hour without exceeding a 1% error rate on critical transactions (search, result clicks).

	Q3. Please provide an example of when you were involved the resolution of a performance / scalability defect. How was the defect found 
	How was it diagnosed 
	How was it resolved 
	How was the resolution proven 
	Please state your involvement in each of the processes. 
Ans: I was involved in resolving a scalability defect in a web application that experienced slowdowns during peak load test.
a) Defect Discovery
The defect was identified while performing peak load test. It was about high response times and timeouts during peak hours.
b) Diagnosis
	1.	Peak Load Test: A load test was conducted to simulate peak traffic, revealing a bottleneck when user concurrency exceeded 1000.
	2.	Database Analysis: Through monitoring, we found that the database was experiencing locking issues due to unoptimized queries.
	3.	Logging & Profiling: We enabled detailed logs and used an APM tool i.e. Dynatrace to track down specific queries causing delays.
c) Resolution
	1. Database Optimization: We optimized the problematic queries, added indexing, and introduced caching for frequently requested data.
	2. Horizontal Scaling: Additional instances were added to the application server pool to handle higher concurrency.
d) Proving the Resolution
	1. Re-testing: We ran peak load test again at the peak concurrency level (1000 users), which showed improved response times and no timeouts.
	2. Production Monitoring: Monitoring showed stable performance during peak times.
My Involvement
I was directly involved in running the load tests, analyzing the logs, identifying the performance and database issues, and validating the fix through re-testing.
	
Q4. As well as creating a script in a tool to do the performance testing, what other factors would need to be considered for a performance testing engagement? 
Ans: - Environment setup for PT (production-like environment).
- Database setup like production to replicate real time scenario (data masking to be done in PT environment if required)
- Monitoring tools for server performance (CPU, memory, response time).
- Baseline performance metrics for comparison (if any).
- Collaboration with development and operations teams.
- Reporting and analysis of results to stakeholders.
  
