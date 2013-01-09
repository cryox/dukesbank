This is a collection of build and deployment automation examples built around the Duke's Bank J2EE sample application.  You can find documention at the DTO Solutions Knowledge Base Wiki (http://kb.dtosolutions.com/wiki/Duke%27s_Bank_J2EE_examples).

Amazon/EC2 Console and Auth Info:
   * Amazon EC2 [Console Login](https://console.aws.amazon.com/ec2/home?region=us-east-1#s=Instances)
   * username:  anthony@dtosolutions.com
   * password:  NOT_SHOWN (can send if you need it)
   * SSH Key:  dukesbank.dtolabs.com_rsa  (can send if you need it)
   * Search for "dukesbank.dtolabs.com" in instances search bar will list the dukesbank instances: build, repo, deploy, app

Configure elastic IPs for:  build, repo, deploy, and app as shown here:

build i-276d1f5c (Jenkins)
   * ElasticIP:  75.101.135.178    build.dukesbank.dtolabs.com
   * Jenkins Url:  [http://build.dukesbank.dtolabs.com:8080/](http://build.dukesbank.dtolabs.com:8080/)
   * Credentials not necessary
   * Build Jobs:  JBoss package, DukesBank (mysteriously called TestBuild) and DukesBank Config)

repo i-3f512344   (Nexus)
   * ElasticIP:  75.101.135.190    repo.dukesbank.dtolabs.com
   * Nexus Url:  [http://repo.dukesbank.dtolabs.com:8081/nexus/](http://repo.dukesbank.dtolabs.com:8081/nexus/)
   * Credentials:  admin/admin123

deploy i-29572552   (Rundeck)
   * ElasticIP:  75.101.135.205    deploy.dukesbank.dtolabs.com
   * Rundeck Url:  [http://deploy.dukesbank.dtolabs.com:4440/](http://deploy.dukesbank.dtolabs.com:4440/)
   * Credentials:  admin/admin

app i-1b5b2960 (JBoss)
   * ElasticIP:  75.101.135.206    app.dukesbank.dtolabs.com
   * JBoss Url:  [http://app.dukesbank.dtolabs.com:8180/](http://app.dukesbank.dtolabs.com:8180/)
   * Bank Url:  [http://app.dukesbank.dtolabs.com:8180/bank](http://app.dukesbank.dtolabs.com:8180/bank)

spare i-a78e11dc
   * ElasticIP:  75.101.135.167    dukesbank.dtolabs.com


Rundeck Jobs:
   * [DeployFromJenkins](http://deploy.dukesbank.dtolabs.com:4440/job/show/5dac0b0c-ae39-4e54-8eaf-bab65bcf3bc9): deploys the latest DukesBank ear (only) from Jenkins onto the app node
   * [DeployFromNexus](http://deploy.dukesbank.dtolabs.com:4440/job/show/acb74c94-fab5-41bd-9c13-26aca5a3e8d4): deploys the selected DukesBank ear, config, and JBoss Container from Nexus onto the app node

NOTES:

Test commit
Test commit 2

After Forking.....

$ANT_HOME/lib needs:
   ivy-2.3.0-rc1.jar
