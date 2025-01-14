# Addressing Problems

1/8/25 

---

Some tools to understand the problem:
1. Thoroughly read the problem statement
2. Examine previous solutions; talk to/research the people who made them

Types of design:
1. Original: New products and ideas
2. Adaptive: Adapt a previous design to some other task
3. Variant: Vary/rearrange an existing design for the same task
4. Redesign: Adapt & Variant

The difference between amateur and experienced engineers is the speed of rejection. Amateur engineers tend to stick to an idea and see it to fruition; if this design gets rejected, a lot of time has been wasted. Experienced engineers, on the other hand, evaluate their preliminary designs. In this case, if a solution is going to fail, it will be rejected before time and money has been invested into the product.

Design Process

- A customer is whoever will end up using the product. 
	- For an airplane, this could be anyone from the passengers to the pilots to the FAA.
- To identify groups, you can use focus groups, interviews, etc. Then, using "The House of Quality" (HOQ) and the "Quality Deployment Function" you can translate these results into specific properties that consumers want.
- The HOQ is a chart/image with the following:
	- ![](../../media/Pasted%20image%2020250108091021.webp)
	- HOWs contains the engineering requirements, like load capacity or cost.
	- The correlation matrix shows how strong the correlation between the HOWs are.
	- The WHATs are the consumer needs. They are each assigned an importance.
	- The relationship matrix shows which HOWs address which WHATs.
		- If you have a blank row, there is no HOW to address the WHAT
		- If you have a blank column, you  have a HOW that does not address a WHAT.
		- If you sum each column in the relationship matrix, then do some processing, you can get specific target properties
- After the HOQ, you can come up with a Specification list
	- Possible specifications are:
		- Geometry constraints
		- Kinematic requirements (max speed, etc.)
		- Load bearing
		- Power/efficiency
		- Material requirements
		- Signals (sound level, emf, etc.)
		- Safety
		- Ergonomics
		- QA
		- Assembly / Maintenance
		- Sustainability
		- Costs

Example of customer needs -> specifications for tea kettle:

| Customer Need | Specification             |
| ------------- | ------------------------- |
| Warm          | Service temperature 100°C |
| Cheap         | Manufacturing price ≤ $30 |
| Non-toxic     | Food grade Materials      |




