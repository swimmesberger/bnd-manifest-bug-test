# bnd-manifest-bug-test

Execute with (powershell example):
```
$env:BND_TEST = "1"
.\gradlew bndBugTest --stacktrace --info
$env:BND_TEST = "2"
.\gradlew bndBugTest --stacktrace --info
$env:BND_TEST = "3"
.\gradlew bndBugTest --stacktrace --info
...
```

After a couple of executions we will see:
```
> Task :TestProject:jar
Task ':TestProject:jar' is not up-to-date because:
  Value of input property 'externalProperty' has changed for task ':TestProject:jar'
Generated bundles: [E:\IdeaProjects\bnd-manifest-bug-test\TestProject\generated\TestProject.jar]
:TestProject:jar (Thread[Execution worker for ':',5,main]) completed. Took 0.028 secs.
:TestProject:bndBugTest (Thread[Execution worker for ':',5,main]) started.

> Task :TestProject:bndBugTest UP-TO-DATE
Skipping task ':TestProject:bndBugTest' as it is up-to-date.
:TestProject:bndBugTest (Thread[Execution worker for ':',5,main]) completed. Took 0.0 secs.
```
Tested on:\
OS: Microsoft Windows 10 Pro\
Version: 10.0.17763 Build 17763\
System type: x64-based PC\
Processor: Intel(R) Core(TM) i7-6700 CPU @ 3.40GHz, 3401 MHz, 4 cores, 8 logical processors
