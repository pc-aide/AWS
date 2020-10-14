# Partitioning Strategies

## Acronym

## Doc

## Write Sharding
* Imagine we have a **voting application** with two candidates, **Trump** & **Biden**
* If we ue a partition key of candidate_id, we will run into partition issues, as we only have two partitions
    * Solution: add a **suffix** (usually **random suffix**, sometimes calculated suffix)
* Table:
    
| Partition key              | Sort_key            | Attributes |
|----------------------------|---------------------|------------|
| CandidateID + RandomSuffix | Vote_date           | Voter_id   |
| Candidate_Trump-1          | 2019-11-03 15.00.00 | 235343     |
| Candidate_Trump-1          | 2019-11-03 15.30.00 | 232312     |
| Candidate_Biden-2          | 2019-11-03 16.00.00 | 098432     |
| Candidate_Biden-1          | 2019-11-03 16.30.00 | 340983     |
