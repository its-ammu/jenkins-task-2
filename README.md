# Jenkins assignment 2

**Create a jenkins groovy pipeline to build/deploy the custom application that you have used during the shell script learning in a docker container.**

1. Get the right docker image to deploy your application 
2. Pull the custom application from the github repository 
3. Run the MySQL container 
4. Update the application to connect to the MySQL container 
5. Make sure the build gets triggered whenever there is a push to the master branch 
6. Deploy the application in the container 
7. Valdiate that the application works fine 


## Connect to jenkins

Make sure you have configured your github plugin with your personal access token.

```sh
#Login as jenkins
sudo -su jenkins

ssh-keygen
#enter the key name and passphrase 

eval $(ssh-agent -s)
ssh-add ~/.ssh/github

cat /var/lib/jenkins/.ssh/github.pub 
# add this to github deploy keys

cat /var/lib/jenkins/.ssh/github
# add this to jenkins credentials
```
Now create a webhook in repo and in url : `<JENKINS-URL>/github-webhook/`

In jenkins job config choose github webhook polling.

