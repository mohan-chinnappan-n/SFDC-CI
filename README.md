## SFDC deployment with Jenkins

### Here we explain use of ANT migration tool to do retrieve and deployment

Use case:

We have 2 orgs:

1. org11
2. org12

- Developer will add a field **comments__c** in org12
- This is retrieved into git
- CI tool wakes up and find this and deploy this change into org11
