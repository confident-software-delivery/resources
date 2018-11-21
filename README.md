# Confident Software Delivery

I'm the living repository provided as companion material to the workshop “Confident Software Delivery”, so far facilitated at:

- [Agile Testing Days 2018](https://agiletestingdays.com/2018/session/confident-software-delivery/) @ Berlin (November 13th, 2018).

Crafted with ❤️ by @sergioalvz & @dcarral

## Table of contents

<!-- TOC depthFrom:1 depthTo:6 withLinks:1 updateOnSave:1 orderedList:0 -->

- [Confident Software Delivery](#confident-software-delivery)
	- [Table of contents](#table-of-contents)
	- [Software delivery jargon](#software-delivery-jargon)
		- [Continuous Integration vs Continuous Delivery vs Continuous Deployment](#continuous-integration-vs-continuous-delivery-vs-continuous-deployment)
		- [Deployment pipeline](#deployment-pipeline)
	- [GitLab CI/CD](#gitlab-cicd)
		- [Core concepts: jobs & stages](#core-concepts-jobs-stages)
		- [How to set up a pipeline in your GitLab project?](#how-to-set-up-a-pipeline-in-your-gitlab-project)
		- [Related GitLab documentation](#related-gitlab-documentation)
	- [Workshop design & facilitation](#workshop-design-facilitation)
	- [External resources](#external-resources)
		- [Books](#books)
		- [Websites](#websites)

<!-- /TOC -->

## Software delivery jargon

### Continuous Integration vs Continuous Delivery vs Continuous Deployment

- Continuous Integration (CI)

  > “Development practice that requires developers to integrate code into a shared repository several times a day. Each check-in is then verified by an automated build, allowing teams to detect problems early.“

  \+ info @ https://www.thoughtworks.com/continuous-integration

- Continuous Delivery (CD)

  > “Software development discipline where you build software in such a way that it can be released to production at any time.“

  \+ info @ https://martinfowler.com/bliki/ContinuousDelivery.html

- Continuous Deployment

  > Sometimes confused with Continuous Delivery, it means that every change goes through the pipeline and automatically gets put into production, resulting in many production deployments every day.

  > Continuous Delivery just means that you are able to do frequent deployments but may choose not to do it, usually due to businesses preferring a slower rate of deployment.

  \+ info @ https://martinfowler.com/bliki/ContinuousDelivery.html

Besides the key differences between them, they all have something they need to exist: **automation**.

Note that this hands-on workshop leverages the so-called GitLab Continuous Integration (GitLab CI/CD), which is the built-in Continuous Integration, Continuous Deployment, and Continuous Delivery support to build, test, and deploy your application offered by GitLab.

### Deployment pipeline

Martin Fowler took some time on May 2013 to document the [concept of Deployment Pipeline](<(https://martinfowler.com/bliki/DeploymentPipeline.html)>) as a way to deal with one of the challenges of an automated build and test environment: you want your build to be fast, so that you can get fast feedback, but comprehensive tests take a long time to run.

A deployment pipeline allows this by breaking up the build into stages. Each stage provides increasing confidence, usually at the cost of extra time. Early stages can find most problems yielding faster feedback, while later stages provide slower and more through probing.

Please note that since Martin Fowler hasn't updated the article lately, it doesn't reflect the current state of the art anymore. As frequently highlighted in ”Accelerate. The Science of Lean Software and DevOps: Building and Scaling High Performing Technology Organizations”, note that top (software delivery) performers are the ones who manage to improve more, and faster.

## GitLab CI/CD

### Core concepts: jobs & stages

A (deployment) **pipeline** consists of groups of **jobs** that get executed in **stages** (batches).

- [**Jobs**](https://docs.gitlab.com/ee/ci/yaml/README.html#jobs) run independently from each other and are executed within the environment of a so-called _Runner_.

- [**Stages**](https://docs.gitlab.com/ee/ci/yaml/README.html#stages) allow to group jobs so they can be executed in parallel. If they all succeed, the pipeline moves on to the next stage.

### How to set up a pipeline in your GitLab project?

All what you need is a `.gitlab-ci.yml` file placed at the root directory of your repository to specify how the project should be built.

What should you include there? Time to dive into some of the resources below.

### Related GitLab documentation

Here we have cherry-picked some articles from the [GitLab CI/CD docs](https://docs.gitlab.com/ee/ci/README.html):

- [Configuration of your jobs with .gitlab-ci.yml](https://docs.gitlab.com/ee/ci/yaml/)
- [GitLab CI/CD variables](https://docs.gitlab.com/ee/ci/variables/README.html)
- [Introduction to pipelines and jobs](https://docs.gitlab.com/ee/ci/pipelines.html)
- [Cache dependencies in GitLab CI/CD](https://docs.gitlab.com/ee/ci/caching/)
- [Introduction to environments and deployments](https://docs.gitlab.com/ee/ci/environments.html)

Additionally, it might be worth reading:

- [Job artifacts](https://docs.gitlab.com/ee/user/project/pipelines/job_artifacts.html)
- [Run jobs sequentially, in parallel or build a custom pipeline](https://about.gitlab.com/2016/07/29/the-basics-of-gitlab-ci/)

## Workshop design & facilitation

This workshop has been designed to leverage the power of [Liberating Structures](http://www.liberatingstructures.com/), which can be defined as:

> Simple rules that make it easy to include and unleash everyone in shaping the future

Here you can find more information about specific structures we have used so far:

- [Impromptu Networking](http://www.liberatingstructures.com/2-impromptu-networking/)
- [TRIZ](http://www.liberatingstructures.com/6-making-space-with-triz/) with [1-2-4-All](http://www.liberatingstructures.com/1-1-2-4-all/)
- [Troika Consulting](http://www.liberatingstructures.com/8-troika-consulting/) with [Wise Crowds](http://www.liberatingstructures.com/13-wise-crowds/)

## External resources 

### Books

- [Accelerate: The Science of Lean Software and DevOps: Building and Scaling High Performing Technology Organizations](https://www.amazon.com/Accelerate-Software-Performing-Technology-Organizations/dp/1942788339)
- [Continuous Delivery: Reliable Software Releases through Build, Test, and Deployment Automation ](https://www.amazon.com/Continuous-Delivery-Deployment-Automation-Addison-Wesley/dp/0321601912)

### Websites

- [Continuous Delivery](https://continuousdelivery.com/)
- [Trunk Based Development: Introduction](https://trunkbaseddevelopment.com/)
