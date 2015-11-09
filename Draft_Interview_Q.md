#ETL & DataStage

1.	You are assigned to fix a Production incident.  Due to a defect in the ETL job released 6 months ago, some records in a time variant table are erroneous.   The table contains record sets of a million accounts  (one row for each attribute of an account).  For each accounts, only some attributes are active and some are closed.  However, in this table, either all attributes of an account are active or they are all closed.  For incident fixes, developers need to do both trouble shooting and fix.

    + What do you suspect to be wrong in the ETL job?
    +	Provided your suspicion turns out to be correct, what would you do?
    +	If data fix is required, what solution approach will you take?  Why?

>Comment - Candidates are expected to elaborate the delta columns selection, and how to do upsert properly. Both root cause fix at the ETL job and data clean up to form a correct baseline for future deltas are required. If the error is only recent, candidates can suggest removing records inserted since the problem started, and re-run the loads in the correct sequence to catch up.  However, if the problem has been there for a while, as in this scenario, the risk and cost is higher.  Candidates experienced in ETL should be able to mention the risk. The alternative is to clean up latest record sets to reflect scenarios in source systems but leave the history as is.

2. How would you improve the performance of an extract which is currently single process?

>Comment - splitting into multi-processes can improve performance

3. How would you define 4 processed into 1 extract?

>Comment - use different APT config files

4. About using scheduler, what kind of dependencies/triggers can you think of to start a job?  When will you use one instead of the other?

>Comment - We primarily have 2 types of triggers in GDW - set time and event tigger.  For jobs that have a dependency on data availability/refresh, we normally use event trigger based on upstream load status; for jobs that have a business critical time line, we use time trigger.

5. You received a source-to-target specification document to do your build work. What would you do before starting to code?

>Comment - Candidates are expected to show critical thinking and proactive problem solving.  They need to review if the design make sense, if the required source data is available, any design loopholes, any performance impact, etc.

