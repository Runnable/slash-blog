---
layout: post
title: Using Docker Compose to Build Unlimited Environments
author: ken_o
category: Annoucements
excerpt: 'Our team is excited to announce enhanced support for Docker Compose just in time for DockerCon 2017. Runnable provides on-demand staging environments for developers to integrate and test code changes earlier in the dev process. And now, developers using Docker Compose can create an unlimited number of multi-container staging and test environments with ease.'
permalink: building-environments-docker-compose
date: 2017-04-17 17:00:00 -0800
---

Our team is excited to announce enhanced support for Docker Compose just in time for DockerCon 2017. Runnable provides on-demand staging environments for developers to integrate and test code changes earlier in the dev process. And now, developers using Docker Compose can create an unlimited number of multi-container staging and test environments with ease.

### The Evolution (and Limitations) of CI

While continuous integration (aka CI) has been a standard process for software development teams for decades, many have yet to fully unlock the potential of using Docker.

The concept of CI originated back when monolithic code bases needed to merge smaller units of code more frequently. And while CI tooling has evolved to automate the building and testing of code changes, teams still need to deploy to some staging or testing environment in order to see their changes working together — better known as CD.

Most of us are quite comfortable with this process; however, two trends are throwing a wrinkle in the traditional CI / CD workflow:

1. **Proliferation of services:** For modern dev teams building services (and microservices), integrating components is far more important than building them. Services are already broken down into smaller sets of code, so building and testing them individually is fairly trivial. However, there is a much greater importance for teams to validate the integration of multiple services, which happens much too late in the CI / CD pipeline.
2. **Limited Environments:** Most teams have a rigid pipeline with a finite number of staging and testing environments. While some automation exists, setting up new environments can be slow and costly, and often not worth the incremental overhead of managing configurations.

These two trends create a bottleneck for teams, as developers must coordinate their integration testing on shared staging environments.

Thankfully, this is where Runnable and Docker can help. Runnable allows you to launch unlimited environments for staging or testing multi-container applications from a single configuration, on-demand.

### One Config, Unlimited Environments

If you are using Docker Compose to define and run multi-container applications, configuring Runnable is as simple as pointing to the compose.yml file in your repository.

<img src="images/posts/compose-staging.png" height="420" width="600" class="img">

Using the configuration defined in your Compose file, Runnable automatically creates a dedicated full-stack staging environment for every code branch. Each environment is maintained for the life of the branch allowing your team to collaborate and test integrations at any time.

### Managing Config as Code

Each environment is built from the Docker Compose configuration in its respective branch, so you’ll always know how your Runnable environment is defined. Developers can easily modify the Compose file on the branch level in order to deploy new services or specific commits to their staging environment.

For example, if you need to test your code with a component that is in development, simply modify the compose.yml file to point to a specific branch and / or commit. Runnable will quickly rebuild your staging environment to match your configuration.

### Testing with Docker Compose

In addition to providing staging environments, Runnable can also create test environments to run integration tests on every commit or pull request.

<img src="images/posts/compose-testing.png" height="309" width="508" class="img">

Configure your testing-specific Compose file to run any type of test against a full-stack staging environment equipped with isolated test data. Test results are returned to you on the Pull Request page and via the Runnable console.

### Use Compose on Runnable Today

With enhanced support for Docker Compose, it’s never been easier for developers to create staging and testing environments on-demand using Runnable. [Try Runnable today](//runnable.com) and let us know what you think.

And if you’re in Austin, TX this week, be sure to stop by our booth (E11) at DockerCon.
