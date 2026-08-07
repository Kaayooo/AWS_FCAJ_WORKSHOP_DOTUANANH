---
title: "Week 7 Worklog"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.7. </b> "
---


### Week 7 Objectives:

* Handle credit loss issues on AWS Organizations.
* Redesign the architecture divided by layers.
* Fix technical errors arising during Glue Job test runs with multi-format files.
* Complete the system.

### Tasks to be carried out this week:
| Day | Task                                                                                                                                                                                                   | Start Date | Completion Date | Reference Material                        |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------- | --------------- | ----------------------------------------- |
| 2   | - Experienced credit loss issues while using AWS Organizations, so we figured out how to create a new account to continue using services. <br> - Presented the architecture to mentors who noted that it should be divided into layers. <br> - Redesigned the team's architecture into layers. <br> - Held a team meeting to establish an account solution and delegate tasks.                                                                                                   | 08/03/2026 | 08/03/2026      |
| 3   | - During system test runs, discovered that the Glue Job could not process the raw bucket when it contained two different file formats. <br> - Investigated and fixed the Glue Job.                                              | 08/04/2026 | 08/04/2026      |  |
| 4   | - Researched Step Functions and completed a lab to understand them thoroughly. <br> - Applied Step Functions to the project. | 08/05/2026 | 08/05/2026      | <https://000047.awsstudygroup.com/> |
| 5   | - Reconfigured Glue Jobs and Glue Crawlers after the team decided the raw S3 bucket should only store CSV files. <br> - Configured EventBridge to automatically trigger the data scraping workflow on a schedule at 4:30 PM.                             | 08/06/2026 | 08/06/2026      |  |
| 6   | - Reviewed the system and conducted test runs to check for any errors. <br> - Wrote a blog post to publish on the AWS Study Group.                                                                                     | 08/07/2026 | 08/07/2026      |  |


### Week 7 Achievements:

* Regarding resource governance & architecture: Permanently resolved the credit loss issue by creating a new account; redesigned the architecture diagram broken down into distinct layers following feedback from mentors; held team meetings to efficiently reallocate tasks.

* Regarding troubleshooting & Glue optimization: Successfully identified and fixed the Glue Job error where it failed to process raw buckets containing mixed file formats; reached a consensus to reconfigure the raw S3 bucket to exclusively store .csv files, while synchronizing the configurations for Glue Jobs and Glue Crawlers.

* Regarding testing and wrap-up: Performed a comprehensive review of the system and executed test runs to verify stability after fixes.
