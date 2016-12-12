## SFDC deployment with Jenkins

### Here we explain use of ANT migration tool to do retrieve and deployment

Use case:

We have 2 orgs:

1. org11
2. org12

- Developer adds a field **Category__c<** in **org12**
- This is retrieved into git
- CI tool wakes up by SCM Commit and find this change and deploy this change into **org11**



### DEMO

![Demo](https://github.com/mohan-chinnappan-n/SFDC-CI/blob/master/SFDC-CI.gif)
