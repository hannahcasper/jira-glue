# jira-glue

jira glue crawler


### How to Configure the AWS Glue Service

* Register this newly created project in [acmdb-data](https://github.com/konciergeMD/acmdb-data).
* Two dummy `script_test.py` and `script_prod.py` files have been created as part of the cookiecutter under folder `job_scripts`. Please modify them for your use case. All ETL scripts should be added to this folder. Please refer to [AWS Glue Programming](https://docs.aws.amazon.com/glue/latest/dg/aws-glue-programming.html) to learn more about the programming for glue.
* The `template.yml` file can be modified to add additional AWS resources if it is needed by the aws glue service.
* Git init the newly created project locally. Create a new repository in github. Push your project to github.
* Enable the CI and pipeline in shippable.
* Login to the AWS console to verify the components of your glue service are created successfully after the shippable pipeline finish successfully.


### IMPORTANT: Security Configuration Creation

* Currently the security configuration is not yet supported in cloudformation. Please request Toga to create the security configration and assoicate it with your newly created crawler(s) and job(s).

### Logs

* [Crawer logs](https://amp.ops.accint.io/app/kibana#/discover?_a=(columns:!(message),filters:!(('$state':(store:appState),meta:(alias:!n,disabled:!f,index:'41b1d950-a22e-11e8-9f09-3f2bdc3d5df5',key:logStream,negate:!f,params:(query:jira-glue-crawler,type:phrase),type:phrase,value:jira-glue-crawler),query:(match:(logStream:(query:jira-glue-crawler,type:phrase))))),index:'41b1d950-a22e-11e8-9f09-3f2bdc3d5df5',sort:!('@timestamp',desc))).
* [Job logs](https://amp.accint.io/app/kibana#/discover?_g=(refreshInterval:(display:Off,pause:!f,value:0)&_a=(columns:!(message),filters:!(('$state':(store:appState),meta:(alias:!n,disabled:!f,index:'41b1d950-a22e-11e8-9f09-3f2bdc3d5df5',key:logGroup,negate:!f,params:(query:%2Faws-glue%2Fjobs%2Fjira-glue*,type:phrase),type:phrase,value:%2Faws-glue%2Fjobs%2Fjira-glue*),query:(match:(logGroup:(query:%2Faws-glue%2Fjobs%2Fjira-glue*,type:phrase))))),index:'41b1d950-a22e-11e8-9f09-3f2bdc3d5df5',interval:auto,query:(language:lucene,query:''),sort:!('@timestamp',desc))).