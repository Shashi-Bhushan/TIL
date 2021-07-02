# Jenkins red bar

Usually the Jenkins build progress bar is blue in color. In some occassions, the bar will turn red. 
That happens if the build is considered `stuck`.

As defined in the [Jenkins code](https://github.com/jenkinsci/jenkins/blob/jenkins-1.560/core/src/main/java/hudson/model/Executor.java#L387-408), the build is considered stuck if it's going to take 10 times more than the previous builds or if no estimate is available, then 24 hours is considered the threshold.
This is just an estimate. 
