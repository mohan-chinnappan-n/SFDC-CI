## SFDC CI deployment with Jenkins

### Here we explain  the use of Jenkins and ANT migration tool to do retrieve and deployment

Use case:

We have 2 orgs:

1. org11
2. org12

- Developer adds a field **Category__c** in **org12**
- This is retrieved into git by ANT Migration


``` bash
$ ant -f build-book.xml retrieve-org12

```
```xml
<target name="retrieve-org12">
    <echo message=" --- retrieve-org12 ---"/>
    <sf:retrieve username="${sf.mohan.dev12.username}"
                 password="${sf.mohan.dev12.password}"
                 serverurl="${sf.mohan.dev12.serverurl}"
                 maxPoll="${sf.maxPoll}"
                 retrieveTarget="${sf.src.dir}/${data_folder}"
                 unpackaged="${sf.src.dir}/unpackaged/package.xml"/>
</target>

```
- Jenkins CI tool wakes up by SCM Commit and find this change and deploy this change into **org11**

Jenkins uses this task:

```xml

<target name="deploy-org11">
    <echo message=" --- deploy-org11 ---"/>
    <sf:deploy   username="${sf.mohan.dev11.username}"
                 password="${sf.mohan.dev11.password}"
                 serverurl="${sf.mohan.dev11.serverurl}"
                 deployroot="${sf.src.dir}/${data_folder}"/>
</target>

```


### DEMO

![Demo](https://github.com/mohan-chinnappan-n/SFDC-CI/blob/master/SFDC-CI.gif)
