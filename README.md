Started by user devops
Obtained Jenkinsfile from git https://github.com/Mrinalichaudhari/jenkins-practice
[Pipeline] Start of Pipeline
[Pipeline] stage
[Pipeline] { (Back-end)
[Pipeline] node
Running on Jenkins in /var/lib/jenkins/workspace/multi-stage-multi-agent
[Pipeline] {
[Pipeline] checkout
Selected Git installation does not exist. Using Default
The recommended git tool is: NONE
No credentials specified
Cloning the remote Git repository
Cloning repository https://github.com/Mrinalichaudhari/jenkins-practice
 > git init /var/lib/jenkins/workspace/multi-stage-multi-agent # timeout=10
Fetching upstream changes from https://github.com/Mrinalichaudhari/jenkins-practice
 > git --version # timeout=10
 > git --version # 'git version 2.43.0'
 > git fetch --tags --force --progress -- https://github.com/Mrinalichaudhari/jenkins-practice +refs/heads/*:refs/remotes/origin/* # timeout=10
 > git config remote.origin.url https://github.com/Mrinalichaudhari/jenkins-practice # timeout=10
 > git config --add remote.origin.fetch +refs/heads/*:refs/remotes/origin/* # timeout=10
Avoid second fetch
 > git rev-parse refs/remotes/origin/master^{commit} # timeout=10
Checking out Revision 34a93cd88d4ff47acf62dc8110b174ba3ce68f53 (refs/remotes/origin/master)
 > git config core.sparsecheckout # timeout=10
 > git checkout -f 34a93cd88d4ff47acf62dc8110b174ba3ce68f53 # timeout=10
Commit message: "resolve Jenkinsfile merge conflict"
First time build. Skipping changelog.
[Pipeline] withEnv
[Pipeline] {
[Pipeline] isUnix
[Pipeline] withEnv
[Pipeline] {
[Pipeline] sh
+ docker inspect -f . maven:3.8.1-adoptopenjdk-11

Error: No such object: maven:3.8.1-adoptopenjdk-11
[Pipeline] isUnix
[Pipeline] withEnv
[Pipeline] {
[Pipeline] sh
+ docker pull maven:3.8.1-adoptopenjdk-11
3.8.1-adoptopenjdk-11: Pulling from library/maven
16ec32c2132b: Pulling fs layer
3f63509f5b97: Pulling fs layer
34d7b43f221b: Pulling fs layer
a1931e18ae45: Pulling fs layer
20904a3b2df7: Pulling fs layer
fb5c0685f15f: Pulling fs layer
a18abadafb9a: Pulling fs layer
a1931e18ae45: Waiting
20904a3b2df7: Waiting
fb5c0685f15f: Waiting
a18abadafb9a: Waiting
3f63509f5b97: Verifying Checksum
3f63509f5b97: Download complete
16ec32c2132b: Verifying Checksum
16ec32c2132b: Download complete
20904a3b2df7: Verifying Checksum
20904a3b2df7: Download complete
a1931e18ae45: Verifying Checksum
a1931e18ae45: Download complete
fb5c0685f15f: Verifying Checksum
fb5c0685f15f: Download complete
a18abadafb9a: Verifying Checksum
a18abadafb9a: Download complete
16ec32c2132b: Pull complete
3f63509f5b97: Pull complete
34d7b43f221b: Verifying Checksum
34d7b43f221b: Download complete
34d7b43f221b: Pull complete
a1931e18ae45: Pull complete
20904a3b2df7: Pull complete
fb5c0685f15f: Pull complete
a18abadafb9a: Pull complete
Digest: sha256:143ff7942b5ef5a004252405a31fa2813dfa438f08494fad1757029de5f64082
Status: Downloaded newer image for maven:3.8.1-adoptopenjdk-11
docker.io/library/maven:3.8.1-adoptopenjdk-11
[Pipeline] }
[Pipeline] // withEnv
[Pipeline] }
[Pipeline] // withEnv
[Pipeline] withDockerContainer
Jenkins does not seem to be running inside a container
$ docker run -t -d -u 111:113 -w /var/lib/jenkins/workspace/multi-stage-multi-agent -v /var/lib/jenkins/workspace/multi-stage-multi-agent:/var/lib/jenkins/workspace/multi-stage-multi-agent:rw,z -v /var/lib/jenkins/workspace/multi-stage-multi-agent@tmp:/var/lib/jenkins/workspace/multi-stage-multi-agent@tmp:rw,z -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** maven:3.8.1-adoptopenjdk-11 cat
$ docker top ef9f9356b7012218a2a0a2574fbc63ebb07ec1ddd598470e3d828552e53da687 -eo pid,comm
[Pipeline] {
[Pipeline] sh
+ mvn --version
Apache Maven 3.8.1 (05c21c65bdfed0f71a2f2ada8b84da59348c4c5d)
Maven home: /usr/share/maven
Java version: 11.0.11, vendor: AdoptOpenJDK, runtime: /opt/java/openjdk
Default locale: en_US, platform encoding: UTF-8
OS name: "linux", version: "6.17.0-1010-aws", arch: "amd64", family: "unix"
[Pipeline] }
$ docker stop --time=1 ef9f9356b7012218a2a0a2574fbc63ebb07ec1ddd598470e3d828552e53da687
$ docker rm -f --volumes ef9f9356b7012218a2a0a2574fbc63ebb07ec1ddd598470e3d828552e53da687
[Pipeline] // withDockerContainer
[Pipeline] }
[Pipeline] // withEnv
[Pipeline] }
[Pipeline] // node
[Pipeline] }
[Pipeline] // stage
[Pipeline] stage
[Pipeline] { (Front-end)
[Pipeline] node
Running on Jenkins in /var/lib/jenkins/workspace/multi-stage-multi-agent
[Pipeline] {
[Pipeline] checkout
Selected Git installation does not exist. Using Default
The recommended git tool is: NONE
No credentials specified
 > git rev-parse --resolve-git-dir /var/lib/jenkins/workspace/multi-stage-multi-agent/.git # timeout=10
Fetching changes from the remote Git repository
 > git config remote.origin.url https://github.com/Mrinalichaudhari/jenkins-practice # timeout=10
Fetching upstream changes from https://github.com/Mrinalichaudhari/jenkins-practice
 > git --version # timeout=10
 > git --version # 'git version 2.43.0'
 > git fetch --tags --force --progress -- https://github.com/Mrinalichaudhari/jenkins-practice +refs/heads/*:refs/remotes/origin/* # timeout=10
 > git rev-parse refs/remotes/origin/master^{commit} # timeout=10
Checking out Revision 34a93cd88d4ff47acf62dc8110b174ba3ce68f53 (refs/remotes/origin/master)
 > git config core.sparsecheckout # timeout=10
 > git checkout -f 34a93cd88d4ff47acf62dc8110b174ba3ce68f53 # timeout=10
Commit message: "resolve Jenkinsfile merge conflict"
[Pipeline] withEnv
[Pipeline] {
[Pipeline] isUnix
[Pipeline] withEnv
[Pipeline] {
[Pipeline] sh
+ docker inspect -f . node:16-alpine

Error: No such object: node:16-alpine
[Pipeline] isUnix
[Pipeline] withEnv
[Pipeline] {
[Pipeline] sh
+ docker pull node:16-alpine
16-alpine: Pulling from library/node
7264a8db6415: Pulling fs layer
eee371b9ce3f: Pulling fs layer
93b3025fe103: Pulling fs layer
d9059661ce70: Pulling fs layer
d9059661ce70: Waiting
7264a8db6415: Verifying Checksum
7264a8db6415: Download complete
93b3025fe103: Verifying Checksum
93b3025fe103: Download complete
7264a8db6415: Pull complete
d9059661ce70: Verifying Checksum
d9059661ce70: Download complete
eee371b9ce3f: Verifying Checksum
eee371b9ce3f: Download complete
eee371b9ce3f: Pull complete
93b3025fe103: Pull complete
d9059661ce70: Pull complete
Digest: sha256:a1f9d027912b58a7c75be7716c97cfbc6d3099f3a97ed84aa490be9dee20e787
Status: Downloaded newer image for node:16-alpine
docker.io/library/node:16-alpine
[Pipeline] }
[Pipeline] // withEnv
[Pipeline] }
[Pipeline] // withEnv
[Pipeline] withDockerContainer
Jenkins does not seem to be running inside a container
$ docker run -t -d -u 111:113 -w /var/lib/jenkins/workspace/multi-stage-multi-agent -v /var/lib/jenkins/workspace/multi-stage-multi-agent:/var/lib/jenkins/workspace/multi-stage-multi-agent:rw,z -v /var/lib/jenkins/workspace/multi-stage-multi-agent@tmp:/var/lib/jenkins/workspace/multi-stage-multi-agent@tmp:rw,z -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** node:16-alpine cat
$ docker top 2ec1eb1ea63ef1b873d646f95264566133860ee8577d336a2fc5d3e30f8a8869 -eo pid,comm
[Pipeline] {
[Pipeline] sh
+ node --version
v16.20.2
[Pipeline] }
$ docker stop --time=1 2ec1eb1ea63ef1b873d646f95264566133860ee8577d336a2fc5d3e30f8a8869
$ docker rm -f --volumes 2ec1eb1ea63ef1b873d646f95264566133860ee8577d336a2fc5d3e30f8a8869
[Pipeline] // withDockerContainer
[Pipeline] }
[Pipeline] // withEnv
[Pipeline] }
[Pipeline] // node
[Pipeline] }
[Pipeline] // stage
[Pipeline] End of Pipeline
Finished: SUCCESS

