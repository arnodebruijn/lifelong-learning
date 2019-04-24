Clean Code
==========

Continuous Integration
----------------------
Software development practice where teams integrate, build, and test their code frequently.
Each integration is verified by an automatic build to detect integration errors as early as possible.

Continuous Delivery
-------------------
On top of continuous integration: automate release process to production (release by push of a button).

Continuous Deployment
---------------------
Every change that passes all stages of the production pipeline is automatically released to production.

The Joel test
-------------
Rate the quality of software teams.
https://www.joelonsoftware.com/2000/08/09/the-joel-test-12-steps-to-better-code/

- Do you use source control?
- Can you make a build in one step?
- Do you make daily builds?
- Do you have a bug database?
- Do you fix bugs before writing new code?
- Do you have an up-to-date schedule?
- Do you have a spec?
- Do programmers have quiet working conditions?
- Do you use the best tools money can buy?
- Do you have testers?
- Do new candidates write code during their interview?
- Do you do hallway usability testing?

The 12 factor app
-----------------
A methodology for building modern, scalable, maintainable software.
https://12factor.net/

1. Codebase:            One codebase tracked in revision control, many deploys
2. Dependencies:        Explicitly declare and isolate dependencies
3. Config:              Store config in the environment
4. Backing services:    Treat backing services as attached resources
5. Build, release, run: Strictly separate build and run stages
6. Processes:           Execute the app as one or more stateless processes
7. Port binding:        Export services via port binding
8. Concurrency:         Scale out via the process model
9. Disposability:       Maximize robustness with fast startup and graceful shutdown
10. Dev/prod parity:    Keep development, staging, and production as similar as possible
11. Logs:               Treat logs as event streams
12. Admin processes:    Run admin/management tasks as one-off processes
