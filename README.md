# Software delivery jargon

## FAQ: CI/CD?

- Continuous integration (CI)
  “Development practice that requires developers to integrate code into a shared repository several times a day. Each check-in is then verified by an automated build, allowing teams to detect problems early.“
  From: https://www.thoughtworks.com/continuous-integration

- Continuous delivery
  “Software development discipline where you build software in such a way that it can be released to production at any time.“
  From https://martinfowler.com/bliki/ContinuousDelivery.html

- Continuous deployment
  Continuous Delivery is sometimes confused with Continuous Deployment. Continuous Deployment means that every change goes through the pipeline and automatically gets put into production, resulting in many production deployments every day. Continuous Delivery just means that you are able to do frequent deployments but may choose not to do it, usually due to businesses preferring a slower rate of deployment. In order to do Continuous Deployment you must be doing Continuous Delivery.
  From https://martinfowler.com/bliki/ContinuousDelivery.html

Besides the key differences between them, they all have something they need to exist: automation.

If this common confusion and small nuances weren't enough, this workshop leverages GitLab CI/CD. Hmm, CD? As in Continuous Delivery or as in Continuous Deployment?

## Deployment pipeline?

Martin Fowler took some time on May 2013 (https://martinfowler.com/bliki/DeploymentPipeline.html) to document the concept of Deployment Pipeline as a way to deal with one of the challenges of an automated build and test environment: you want your build to be fast, so that you can get fast feedback, but comprehensive tests take a long time to run.

A deployment pipeline allows this by breaking up the build into stages. Each stage provides increasing confidence, usually at the cost of extra time. Early stages can find most problems yielding faster feedback, while later stages provide slower and more through probing.

Please note that since Martin Fowler hasn't updated the article lately, it doesn't reflect the current state of the art anymore. As frequently highlighted in ”Accelerate”, note that top (software delivery) performers are the ones who manage to improve more, and faster.

## GitLab CI/CD

### Core concepts

A (deployment) `pipeline` consists of groups of **jobs** that get executed in **stages** (batches).

[**Stages**](https://docs.gitlab.com/ee/ci/yaml/README.html#stages) allow to group jobs so they can be executed in parallel. If they all succeed, the pipeline moves on to the next stage.

[**Jobs**](https://docs.gitlab.com/ee/ci/yaml/README.html#jobs) run independently from each other and are executed within the environment of a so-called _Runner_.

### How to set up a pipeline?

A `.gitlab-ci.yml` file must be placed at the root of your repository to specify how the project should be built.

Not sure what are we talking about? You might wanna check some of the linked learning resources below.

### Related documentation

- [GitLab Continuous Integration (GitLab CI/CD)](https://docs.gitlab.com/ee/ci/README.html)

  - [Configuration of your jobs with .gitlab-ci.yml](https://docs.gitlab.com/ee/ci/yaml/)
  - [GitLab CI/CD variables](https://docs.gitlab.com/ee/ci/variables/README.html)
  - [Introduction to pipelines and jobs](https://docs.gitlab.com/ee/ci/pipelines.html)
  - [Introduction to environments and deployments](https://docs.gitlab.com/ee/ci/environments.html)
  - [Introduction to environments and deployments](https://docs.gitlab.com/ee/ci/caching/)

### Additional documentation

- [Job artifacts](https://docs.gitlab.com/ee/user/project/pipelines/job_artifacts.html)
- [Run jobs sequentially, in parallel or build a custom pipeline](https://about.gitlab.com/2016/07/29/the-basics-of-gitlab-ci/)
