# DevOps
## Leadership Practices for DevOps
* Leaders demonstrate a long-term vision for organizational direction and team direction.
* Leaders intellectually stimulate the team by encouraging them to ask new questions and question basic assumptions about the work.
* Leaders provide inspirational communication that inspires pride in being part of the team, says positive things about the team, inspires passion and motivation and encourages people to see that change brings opportunities.
* Leaders demonstrate support by considering others’ personal feelings before acting, being thoughtful of others’ personal needs and caring about individuals’ interests.
* Leaders promote personal recognition by commending teams for better-than-average work, acknowledging improvements in the quality of work and personally complimenting individuals’ outstanding work.

## Collaborative Culture Practices for DevOps
* The culture encourages cross-functional collaboration and shared responsibilities and avoids silos between Dev, Ops and QA.
* The culture encourages learning from failures and cooperation between departments.
* Communication flows fluidly across the end-to-end cross-functional team using collaboration tools where appropriate (for example Slack, HipChat, Yammer).
* The DevOps system is created by an expert team, and reviewed by a coalition of stakeholders including Dev, Ops and QA.
* Changes to end-to-end DevOps workflows are led by an expert team, and reviewed by a coalition of stakeholders including Dev, Ops and QA.
* DevOps system changes follow a phased process to ensure the changes do not disturb the current DevOps operation. Examples of implementation phases include: proof of concept (POC) phase in a test environment, limited production and deployment to all live environments.
* Key performance indicators (KPIs) are set and monitored by the entire team to validate the performance of the end-to-end DevOps pipeline, always. KPIs include the time for a new change to be deployed, the frequency of deliveries and the number of times changes fail to pass the tests for any stage in the DevOps pipeline.

## Design-for-DevOps Practices for DevOps
* Products are architected to support modular independent packaging, testing and releases. In other words, the product itself is partitioned into modules with minimal dependencies between modules. In this way, the modules can be built, tested and released without requiring the entire product to be built, tested and released all at once.
* Applications are architected as modular, immutable microservices ready for deployment in cloud infrastructures in accordance with the tenets of 12-factor apps, rather than monolithic, mutable architectures.
* Software source code changes are pre-checked with static analysis tools, prior to commit to the integration branch. Static analysis tools are used to ensure the modified source code does not introduce critical software faults such as memory leaks, uninitialized variables, and array-boundary problems.
* Software code changes are pre-checked using peer code reviews prior to commit to the integration/trunk branch.
* Software code changes are pre-checked with dynamic analysis tests prior to committing to the integration/trunk branch to ensure the software performance has not degraded.
* Software changes are integrated in a private environment, together with the most recent integration branch version, and tested using functional testing prior to committing the software changes to the integration/trunk branch.
* Software features are tagged with software switches (i.e., feature tags or toggles) during check-in to enable selective feature-level testing, promotion and reverts.
* Automated test cases are checked in to the integration branch at the same time code changes are checked in, together with evidence that the tests passed in a pre-flight test environment.
* Developers commit their code changes regularly, at least once per day.

## Continuous Integration Practices for DevOps
* A software version management (SVM) system is used to manage all source code changes. (Git, Perforce, Mercurial, etc.)
* A software version management (SVM) system is used to manage all versions of code images changes used by the build process. (Git, Perforce, Mercurial, etc.)
* A software version management (SVM) system is used to manage all versions of tools and infrastructure configurations and tests that are used in the build process. (Git, * rforce, Mercurial, etc.)
* All production software changes are maintained in a single trunk or integration branch of the code.
* The software version(s) for supporting each customer release are maintained in a separate release branch to support software updated for each release.
* Every software commit automatically triggers a build process for all components of the module that has code changed by the commit. The system is engineered such that resources are always sufficient to execute a build.
* Once triggered, the software build process is fully automated and produces build artifacts, provided the build time checks are successful.
* The automated build process checks include unit tests.
* Resources for builds are available on-demand and never block a build.
* CI builds are fast enough to complete incremental builds in less than an hour.
* The build process and resources for builds scale up and down automatically according to the complexity of the change. If a full build is required, the CI system automatically scales horizontally to ensure the builds are completed as quickly as possible.

## Continuous Testing Practices for DevOps
* Development changes are pre-flight tested in a clone of the production environment prior to being integrated to the trunk branch. (Note: “production environment” means “variations of customer configurations of a product.”)
* New unit and functional regression tests that are necessary to test a software change are created together with the code and integrated into the trunk branch at the same time the code is. The new tests are then used to test the code after integration.
* A test script standard is used to guide test script creation, to ensure the scripts are performing the intended test purpose and are maintainable.
* Tests are selected automatically according to the specific software changes. CT is orchestrated dynamically, whereby the execution of portions of the CT test suites may be accelerated, or skipped entirely, depending on how complex or risky the software changes are.
* Test resources are scaled automatically according to the resource requirements of specific tests selected and the available time for testing.
* Release regression tests are automated. At least 85% of the tests are fully automated and the remaining are auto-assisted if portions must be performed manually.
* Release performance tests are automated to verify that no unacceptable degradations are released.
* Blue/green testing methods are used to verify deployments in a staging environment before activating the environment to live. A/B testing methods are used together with feature toggles to try different versions of code with customers in separate live environments. Canary testing methods are used to try new code versions on selected live environments.
* The entire testing life cycle, which may include pre-flight, integration, regression, performance and release acceptance tests are automatically orchestrated across the DevOps pipeline. The test suites for each phase include a predefined set of tests that may be selected automatically according to predefined criteria.

## Elastic Infrastructure Practices for DevOps
* The data and executable files needed for building and testing builds are automatically archived frequently and can be reinstated on demand. Archives include all release and integration repositories. If an older version of a build needs to be updated, then the environment for building and testing that version can be retrieved and reinstated on demand and can be accomplished in a short time (for example, minutes to hours.)
* Build and test processes are flexible enough to automatically handle a wide variety of exceptions gracefully. If the build or test process for a component is unable to complete, then the process for that failed component is reported and automatically scheduled for analysis, but build and test processes for other components continue. The reasons for the component failure are automatically analyzed and rescheduled if the reason for the failure can be corrected by the system; if not, then it is reported and suspended.
* System configuration management and system inventory is stored and maintained in a configuration management database (CMDB).
* Infrastructure changes are managed and automated using configuration management tools that assure idempotency.
* Automated tools are used to support immutable infrastructure deployments.
* Equal performance for all. The user performance experience of the build and test processes by different teams are consistent for all users, independent of location or other factors. There are SLAs and monitoring tools that ensure the user performance experience is consistent for all users.
* Fault recovery mechanisms are provided. Build and test system fault monitoring, fault detection, system and data monitoring and recovery mechanisms exist. They are automated and are consistently verified through simulated failure conditions.
* Infrastructure failure modes are frequently tested.
* Disaster recovery procedures are automated.

## Continuous Monitoring Practices for DevOps
* Logging and proactive alert systems make it easy to detect and correct DevOps system failures. Logs and proactive system alerts are in place for most DevOps component failures, and are organized in a manner to quickly identify the highest-priority problems.
* Snapshot and trend results of each metric from each DevOps pipeline stage (for example, builds, artifacts, tests) are automatically calculated in process and visible to everyone in the Dev, QA and Ops Teams.
* Key performance indicators (KPIs) for the DevOps infrastructure components are automatically gathered, calculated and made visible to anyone on the team that subscribes to them. Example metrics are availability (uptime) of computing resources for CI, CT and CD processes, time to complete builds, time to complete tests, number of commits that fail and number of changes that need to be reverted due to serious failures.
* Metrics and thresholds for DevOps infrastructure components are automatically gathered, calculated and made visible to anyone on the team that subscribes to them. Example metrics are availability (uptime) of computing resources for CI, CT and CD processes, time to complete builds, time to complete tests, number of commits that fail and number of changes that need to be reverted due to serious failures.
* Process analytics are used to monitor and improve the integration, test and release process. Descriptive build and test analytics drive process improvements.
* Predictive analytics are used to dynamically adjust DevOps pipeline configurations. For analysis of test results, data may indicate a need to concentrate more testing in areas that have a higher failure trend.

## Continuous Security Practices for DevOps
* Developers are empowered and trained to take personal responsibility for security.
* Security assurance automation and security monitoring practices are embraced by the organization.
* All information security platforms that are in use expose full functionality via APIs for automation capability.
* Proven version control practices and tools are used for all application software, scripts, templates and blueprints that are used in DevOps environments.
* Immutable infrastructure mindsets are adopted to ensure production systems are locked down.
* Security controls are automated so as not to impede DevOps agility.
* Security tools are integrated into the CI/CD pipeline.
* Source code for key intellectual property on build or test machines are only accessible by trusted users with verified credentials. Build and test scripts do not contain credentials for access to any system that has intellectual property. Intellectual Property is divided such that not all of it exists on the same archive and each archive has different credentials.

## Continuous Delivery Practices for DevOps
* Delivery and deployment stages are separate. The delivery stage precedes the deployment pipeline.
* All deliverables that pass the delivery metrics are packaged and prepared for deployment using containers.
* Deliverable packages include sufficient configuration and test data to validate each deployment. Configuration management tools are used to manage configuration information.
* Deliverables from the delivery pipeline are automatically pushed to the deployment pipeline, once acceptable delivery measures are achieved.
* Deployment decisions are determined according to predetermined metrics. The entire deployment process may take hours, but usually less than a day.
* Deployments to production environments are staged such that failed deployments can be detected early and impact to customers isolated quickly.
* Deployments are arranged with automated recovery and self-healing capabilities in case a deployment fails.

## Notes
* We need to have single terraform script which create DEV/QA/UAT/PROD, not copy paste resources to different scripts
* If Story required Infrastructure updates, PR should be created and attached to the Story
* PR should be reviewed by TechLead
* Deploy of infrastructure should be done using pipline (Configuration Drift)
* It can be several pipelines but they should deploy automatically to eliminate missed configurations

### Resources
* [Nine pillars of devops best practices](https://devops.com/nine-pillars-of-devops-best-practices/)
* [Infrastructure as code](https://www.contino.io/insights/infrastructure-as-code)
