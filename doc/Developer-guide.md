<h1>Developer guide</h1>

This page contains a set of notes for the developers: 

### Release

In order to make the release:  

+ make sure that there are no additional models in the grobid-home (usually is better to have a second cloned project for the relesae)

+ Make the release: 
    > ./gradlew release

+ Add the bintray credentials in are in the file `~/.gradle/gradle.properties`, like: 

```  
bintrayUser=username
bintrayApiKey=the api key 
mavenRepoReleasesUrl=https://dl.bintray.com/rookies/releases
mavenRepoSnapshotsUrl=https://dl.bintray.com/rookies/snapshots
```

+ Fetch back the tag and upload the artifacts: 
    > git checkout [releasetag]
    
    > git clean build
    
    > ./gradlew bintray
    
 (This last command needs to be checked, cause the standard task `uploadArtifacts` could just work)
 

