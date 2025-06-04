# Assignment
TASK 1:

Goal - To create 4 columns with sum of transaction Ids and Enquiry Ids for each user and each date. 

Challenging part - To stack user_id and date columns into rows. Solution to this problem was to use Union all instead of Join, as Join stacks columns to columns, whereas Union stacks Columns to rows one above the other. 

Execution - Used CTE tables to initiate count_txns column to 0 when pulling data from enquiries table, and to initiate count_enquiries to 0 when pulling data from txns table. 

TAKS 2:

Goal - To create 4 columns with array of transactions within 30 days of enquiry where 1 tansaction is only linked with one enquiry (to the closest date of enquiry preceding 30 days of that transaction).

Challenging part - There were 2 parts to this question - firstly, creating an array of transactions for each enquiry, and secondly, picking the enquiry id which is closest to the tranaction date. Solution to this problem was to use Row Number() over txn_id and ranking system to choose the closest enquiry_id.

Execution - Used one CTE table to map enquiries and its corresponding transactions done within 30 days.
Used another CTE table to map enquiry_id with txn_id closest to it in the past 30 days. 
Finally, joined the CTEs to produce the final table with txn_ids aggregated in array.
