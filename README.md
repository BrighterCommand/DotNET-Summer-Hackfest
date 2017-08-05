# DotNET-Summer-Hackfest
Instructions for participating in the .NET Foundation's 2017 Summer Hackfest with Brighter

# A Brief Introduction to Paramore
Paramore is a CQRS framework, and for .NET it consists of Brighter and Darker. Darker is the read side component, and Brighter is the command side component.

This Hackfest focuses on Brighter, over Darker (although if there is something you want to contribute outside the scope of our suggestions - go for it).

Brighter implements the Command Handler pattern - you split the Command design pattern into two parts, the parameters, and the handler that receives the command and acts on the domain. This allows you to decouple sender and receiver.

We use the seperation of command and handler to create a pipeline for processing the command - this allows you to insert orthogonal operations, such as logging, into the pipeline before the handler that invokes the domain.

Finally, we support the handler both being in-process, generally useful when a response must be synchronous, and out-of-process, generally useful when the response can be asynchronous. An out-of-process handler uses Message Oriented Middleware (a message queue) to communicate between producer and consumer. The advantage of MoM is that it allows us to throttle the rate of incoming requests, which can help us deal with peaks in traffic easily.

Because Brighter handles inter-process communication via a message queue it can also be used for inter-service communication between microservices.

You can find a link to our documentation here: [Brighter Documentation](https://brightercommand.github.io/Brighter/)

# Goals for the Session
We have three goals with this session
1. Familiarise people with using Brighter.
    * For this we would encourage you to work on helping to port pour fork of eShopOnContainers to Brighter
2. Fix minor ‘niggles’ with Brighter
    * This is a great first step for contributing to the project, as you can familiarise yourself with our codebase on a manageably sized piece of work
3. Implement more middleware and stores
    * Brighter has two dependencies on local infrastructure: MoM and Db. W  want to implement more MoM options and Dbs
    * Redis is particularly attractive, because even without being able to install brokers, many organisations can install Redis.
    * Postgres is particularly attractive for Linux environments and the new cross-platform future of the .NET

# How to get to contribute
We have a page all about contributing: (Contributing)[http://github.com/BrighterCommand/Brighter/blob/master/Contributing.md]
* Note that we want you to put your copyright in the header and sign the rights for our project to use it over in the CLA. We want to give you credit for your work.

Please note that we have a code of conduct, we expect you to adhere to it: (Code of Conduct)[https://github.com/BrighterCommand/Brighter/blob/master/code_of_conduct.md]
* Mail  us know if you have any issues with violations of our code of conduct on ian_hammond_cooper@yahoo.co.uk

This Wiki Projects provides a summary of the projects that we are running.

Please use the Wiki SignUp page for projects that you are interested in.

The projects should be managed from [here](https://github.com/orgs/BrighterCommand/projects)

If there is something else that you want to work on, please raise an issue for discussion filename_lower_camelrst, before doing the work and raising a PR.

Our workflow is informal for simple bugs, or new middleware, or stores. We tend to accept your PR and then work with you on any fixes needed. This is because any ‘plugin’ can be worked on collaboratively without putting the main project at riski, and bugs don’t ‘rewrite the world’.

Larger changes to the core should have been preceded by an issue so that we can agree how best to tackle it. This might mean a branch etc. We’ll find a way to do this that works for all of us. It is in core submissions that you might get more pushback on a PR, because we may be unhappy about the impact on existing users. But we try to ‘take in and work to refactor’ as much as we can.

This hackfest focuses on projects that should not have PR issues, to provide a supportive environment for first timers in particular.

# Communication
The best place to get help is our Gitter channel: https://gitter.im/iancooper/Paramore and we will be using that throughout the project.

If we need to chat about a project F2F we tend to prefer Skype or G+ Hangouts depending on what works for the participants

# Events
No in person events are organised as yet, but please see the Wiki Events page

