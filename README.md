# bnd-manifest-bug-test

Execute with:
.\gradlew bndBugTest --stacktrace --info -PBND_TEST=1
.\gradlew bndBugTest --stacktrace --info -PBND_TEST=2
.\gradlew bndBugTest --stacktrace --info -PBND_TEST=3
...

After a couple of executions we will see:
> Task :TestProject:jar
Task ':TestProject:jar' is not up-to-date because:
  Value of input property 'externalProperty' has changed for task ':TestProject:jar'
Generated bundles: [E:\IdeaProjects\bnd-manifest-bug-test\TestProject\generated\TestProject.jar]
:TestProject:jar (Thread[Execution worker for ':',5,main]) completed. Took 0.029 secs.
:TestProject:bndBugTest (Thread[Execution worker for ':',5,main]) started.

> Task :TestProject:bndBugTest UP-TO-DATE
Skipping task ':TestProject:bndBugTest' as it is up-to-date.
:TestProject:bndBugTest (Thread[Execution worker for ':',5,main]) completed. Took 0.0 secs.