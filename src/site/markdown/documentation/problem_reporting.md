<head><title>Problem Reporting</title></head>

# Section : [Documentation](index.html) 


## Problem Reporting

While we always aim to release DataNucleus with as few bugs as possible, it is possible that 
during the release cycle some issues will come up. Our release process uses more than 1500 
unit tests aimed at reproducing the majority of situations that users may come across, though
clearly we can never cover all situations with these tests. We also run the JDO3/JPA1 TCKs
before each release to provide extra checks to reduce the chance of regressions. The process 
for reporting issues is defined below :-

1. Check your input classes, MetaData and persistence code against the JDO/JPA spec and the DataNucleus documentation. 
The majority of situations are errors in input relative to what DataNucleus allows. __More importantly than this, 
READ THE LOG. IT TELLS YOU WHAT IS HAPPENING__. Unwillingness to read such basic log information suggests that you 
don't want to debug your problem so ask yourself this question _why should we if you can't be bothered?_
2. Search the [Forum](http://forum.datanucleus.org) or [StackOverflow](http://www.stackoverflow.com) for a similar situation to see if someone else has had the same issue and maybe resolved it.
3. Try the [latest Nightly Builds](http://www.datanucleus.org/downloads/maven2-nightly/org/datanucleus). Things are usually fixed soon after 
being reported so the issue may no longer be an issue (if there are no jars present in the nightly repo then nothing has changed since the previous release).
4. Search the issues for the DataNucleus plugin in question for an issue describing your situation. 
If there is one then you can always check the status of the issue and add a comment against it.
5. Start a thread on the [Forum](http://forum.datanucleus.org). If doing this then seriously consider posting a simple concise testcase (see below) 
that gives people something that reproduces your problem.
6. If there is nothing obvious incorrect in your situation and it happens in a released version of DataNucleus then you can raise an issue against the DataNucleus plugin in question
You should then create a minimized testcase and attach it to the issue (using "Attach File" on the issue) - see below. 
__Bugs can only be raised against RELEASED versions of DataNucleus and must have a valid testcase attached that demonstrates the issue.__ 
If you encounter a bug that only appears in GitHub latest then you should either report it against an issue related to that item in the current 
work-in-progress release, or otherwise report it to developers. This is since something can hardly be a bug if it hasn't been released yet.
__Please don't take the attitude that this testcase requirement somehow doesn't apply to you. It is there to demonstrate a problem, so others can see it. 
Obviously any such problem is not present in all of our tests so yours is different, we aren't psychic so require a testcase.__

This guide can also be used for providing testcases that demonstrate the need for new features.

A test case is needed to be able to reproduce possible issues. We require something that we can simply take and run ourselves (using Maven).
For this reason we have defined a standard for simplified testcases, for [JDO](#jdo), and for [JPA](#jpa) as well as building on our 
existing testcases in [GitHub](#github). Please write your testcases using these templates and Maven. If a "test" is to demonstrate something in
the enhancer or SchemaTool then you don't need the "Test" file since running the enhancer/SchemaTool via the Maven plugin will show whatever it is.

We sadly do not support other build systems for testcases. You may be more familiar with something else but we are the only people providing
our time here, so Maven is the only way, and the Maven build file is preconfigured in these templates below.


<a name="jdo"/>
### JDO Testcase : GitHub JUnit test, cloned from DataNucleus project
![GitHub](../images/GitHub-Mark-64px.png)
DataNucleus provides a template JUnit GitHub project in repository [test-jdo](https://github.com/datanucleus/test-jdo).
Please fork this and mention the location of your fork on the issue that it relates to. Note that there are two JUnit 
tests in the provided project, one for single-threaded and one for multi-threaded issues; use the one appropriate to your case and delete the other.

<a name="jpa"/>
### JPA Testcase : GitHub JUnit test, cloned from DataNucleus project
![GitHub](../images/GitHub-Mark-64px.png)
DataNucleus provides a template JUnit GitHub project in repository [test-jpa](https://github.com/datanucleus/test-jpa).
Please fork this and mention the location of your fork on the issue that it relates to. Note that there are two JUnit 
tests in the provided project, one for single-threaded and one for multi-threaded issues; use the one appropriate to your case and delete the other.

<a name="github"/>
### JDO/JPA : JUnit test built on DataNucleus test suite

As an alternative to the above, and where you are familiar with JUnit and are willing to look at the 
[existing DataNucleus tests in GitHub](development/tests.html) then please create a JUnit test case that 
utilises our existing suite of sample data etc. If you provide a testcase in this way your testcase should be a patch against current GitHub latest
of the respective test suite project and it should be attached to the issue to which it relates. To add a JUnit testcase, please follow the 
[new unit test guide](development/tests.html#Adding_Unit_Tests)
