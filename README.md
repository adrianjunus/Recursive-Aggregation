# Recursive-Aggregation

# "Company Logo Consolidation using Recursion"

Not included: The actual data I used for this script (sorry). I am proud to say that this script was a big part of pulling together a fairly hefty intitiative at my company. We ended up taking a different approach (graphs via networkio) which was way better, but also at the time was an excellent example of 'striving for the most effective solution' and I suppose, 'compromise' haha. This works fairly well, with some lessons learned and notes for next steps. The project finished a while ago and has been the center-piece for some major operational-expenditure improvements.

Problem Statement:
A company is interested in aggregating and making known a list of customer who have initiated purchases with a given company. 

Issue 1: The source system of record which have suffered from a history of non-standaradized data entry procedures causing unobvious name matches. (ex: "F5 Networks" vs "F5 Networks Incorporated")
Issue 2: Merge/Acquisitions, legal name changes, company divestitures, legal hierarchies, and a partner-distributor model sometimes obfuscate relationhips between accounts that are related to eachother but whose names differ widely. 3rd-party enrichment data is intended to expose this relationship. (ex: "F5 Networks" vs "F5 Inc" vs "NGINX" which was acquired)

Goal:
Given an account name, compile a list of the related accounts

Stretch Goal: 
Given a series of account names, compile a list of the related accounts grouped seperately.

Input fields:
Account Keys
Account Names
(Primary Key) Account Site Keys
Account Site Local Unique Identifier
Account Site Global Unique Identifier

Output fields:
Same

Approach 1 (depicted here):
1) Read data into memory
2) Build capability to search for relations via account names
3) Build capability to search for relations via 3rd-party enrichment
4) Perform both searches
5) Recursively perform both searches using the account names and 3rd-party enrichment gathered from the newly found accounts
6) When no new accounts are found, return the aggregated list of accounts related to the original account of interest
