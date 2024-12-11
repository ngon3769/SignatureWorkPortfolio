# Internship-Project

I can't have the code or project documents linked here because of company policy, but I will describe it in as much detail as remember and am allowed to.

## Background

I was a Software Engineer Intern at an Enterprise Software company from May-Aug 2024. As a company that makes software for other companies to use,
they are constantly pushing product updates, bug fixes, improvements, and maintenance. The team in charge of overseeing these changes is called
Enterprise Trust, which is where I was placed for the summer. More specifically, I worked on a smaller subteam called Release Tracks which handles
actually scheduling and sending out the emails with the updates either a month before or at the same time that the updates are being rolled out (depending
on which release track schedule the customer company is subscribed to).

## Problem Statement

The process for sending out those email updates / release track updates was not optimal. There was no observability into the jobs. This means that if a bulk email job was
created to send updates to 10,000 customers and for whatever reason that job failed or was interrupted, there was no way of knowing the real time status of the job and/or
identifying exactly where it failed. Did 200 of the 10,000 emails get sent? 1,000? 9,999? They had no way of knowing. At that point the team only really had two options; restart the entire job
and risk spamming customers who already recevied the updates, or don't retry it and have some customers miss out on the updates. This was affecting customer satisfaction.

## Project Task

I was tasked with creating a new email delivery workflow using [Netflix Conductor](https://netflixtechblog.com/netflix-conductor-a-microservices-orchestrator-2e8d4771bf40) to provide better observability and real time tracking into the email delivery process. The goal was to be able to monitor end-to-end from when the email job gets triggered to when (or if) the email gets delivered. The tech stack I used was Java/Spring Boot, and I got exposure to other technologies like AWS, REST APIs, JUnit, Mockito, Git/GitHub, JSON, PostgreSQL, Docker, Splunk, Jira, Confluence, and Bitbucket among others.

## Process and Outcome

I spent the first 2 weeks coming up with a design doc for what I wanted the workflow to look like, running it by my mentor and incorporating feedback. After a few iterations, we settled on this structure:

- Provisioning a new email delivery workflow in Netflix Conductor using JSON.
- Enqueuing outbound emails to an Amazon SQS/DLQ queue because of its failure retry mechanisms.
- Creating a custom email class compatible with Netflix Conductor.
- Creating an email delivery handler with real time logging to process emails off of the SQS queue and convert them into the custom email class objects, and then pass them to a service.
- Creating an email delivery service with real time logging that picks up emails from the handler and then uses a controller method to send them out to customer emails that are provided whenever a user invokes the workflow.

For each of these tasks, I consulted documentation and resources to try figuring them out on my own, but also sought guidance from my mentor whenever I had multiple failed attempts at unblocking myself.

At the midpoint of my 12-week internship, I gave a presentation to my team and stakeholders on my progress and where the project was headed for the next 6 weeks. They had suggested improvements that I worked hard to incorporate over the next few weeks.

I completed all the project tasks by week 10, and spent week 11 trying to refactor an existing use case (a bulk email sending job) to use the new workflow and validate that it works end-to-end.

Finally, in week 12, I gave a final presentation on the completed project and it was pushed to prodcution.
