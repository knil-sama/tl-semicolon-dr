# Source

[Medium by Justin Coffey](http://labs.criteo.com/2018/06/from-just-a-bunch-of-engineers-to-data-reliability-engineering/)

# tl;dr

1. We fucked up big time using Hadoop and other solution without knowing them or thinking about the long term.


2. :heart: Maxime Beauchemin.


3. Going forward when you read “update” think “delete and replace”, because once transformed and loaded data should be see as immutable.

4. To convert data you need to understand

- Whole business
- Techno used for storing input data
- Techno used for storing output data 
- Specific need of the requester

5. The platform of a company is the result of multiple factor (existing team, legacy and budget) so even if you are in the same context it didn't mean you should aim for the same solution.

6. How the data will be vizualised is part of a data engineer job (because you only need 1 data analyst to cripple a whole Redshift cluster).

7. A serious data engineer is an expert coder, automating the deployment and operations of her data system(s), evolving it based on client needs via discussions around SLIs, SLOs, and SLAs.

# Summary

Feel in sync with his definition of a DE and I recommend to read the article he mention.

