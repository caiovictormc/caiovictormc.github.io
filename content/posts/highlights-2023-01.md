---
title: "Highlights - 2023/01"
description: "The contents below are personal highlights only. Review sources to understand the context."
date: 2023-01-31T00:53:43-03:00
tags:
  - software-engineering
  - software-development
---

# Textos / Artigos

### Richard I. Cook: "How Complex Systems Fail," Cognitive Technologies Laboratory, April 2000.

[https://www.researchgate.net/publication/228797158\_How\_complex\_systems\_fail](https://www.researchgate.net/publication/228797158_How_complex_systems_fail)

- Catastrophe requires multiple failures – single-point failures are not enough

- Eradication of all latent failures is limited primarily by economic cost but also because it is difficult before the fact to see how such failures might contribute to an accident. The failures change constantly because of changing technology, work organization, and efforts to eradicate failures.

- The potential for catastrophic outcome is a hallmark of complex systems. It is impossible to eliminate the potential for such catastrophic failure; the potential for such failure is always present in the system's nature

- Post-accident attribution accident to a 'root cause' is fundamentally wrong. Because overt failure requires multiple faults, there is no isolated 'cause' of an accident. There are multiple contributors to accidents. Each of these is necessary insufficient in itself to create an accident

- The evaluations based on such reasoning as 'root cause' do not reflect a technical understanding of the nature of failure but rather the social, and cultural need to blame specific, localized forces or events for outcomes.

- all practitioner actions are gambles, that is, acts that take place in the face of uncertain outcomes. The degree of uncertainty may change from moment to moment

- (1) Restructuring the system to reduce exposure of vulnerable parts to failure. (2) Concentrating critical resources in areas of expected high demand. (3) Providing pathways for retreat or recovery from expected and unexpected faults

- Change introduces new forms of failure

- changes maybe actually create opportunities for new, low-frequency but high consequence failures. When new technologies are used to eliminate well understood system failures or to gain high precision performance they often introduce new pathways to large-scale, catastrophic failures. Not uncommonly, these new, rare catastrophes have even greater impact than those eliminated by the new technology. These new forms of failure are difficult to see before the fact; attention is paid mostly to the putative beneficial characteristics of the changes. Because these new, high consequence accidents occur at a low rate, multiple system changes may occur before an accident, making it hard to see the contribution of technology to the failure.

- Safety is a characteristic of systems and not of their components

- The state of safety in any system is always dynamic; continuous systemic change insures that hazard and its management are constantly changing.

- Failure free operations require experience with failure.

### David Oppenheimer, Archana Ganapathi, and David A. Patterson: "Why Do Internet Services Fail, and What Can Be Done About It?," at 4th USENIX Symposium on Internet Technologies and Systems (USITS), March 2003.

[https://static.usenix.org/events/usits03/tech/full\_papers/oppenheimer/oppenheimer.pdf](https://static.usenix.org/events/usits03/tech/full_papers/oppenheimer/oppenheimer.pdf)

- (I) operator error is the largest cause of failures in two of the three services, (2) operator error is the largest contributor to time to repair in two of the three services, (3) configuration errors are the largest category of operator errors, (4) failures in custom-written front-end software are significant, and (5) more extensive online testing and more thoroughly exposing and detecting component failures would reduce failure rates in at least one service.

**Techniques for mitigating failures**

- correctness testing: (obvious and underrated, I'm not talking about just about automated testing) testing the system and its components for correct behavior before deployment or in production. Pre-deployment testing prevents component faults in the deployed system, and online testing detects faulty components before they fail during normal operation. Online testing will catch those failures that are unlikely to be created in a test situation, for example those that are scale or configuration-dependent.

- component isolation: increasing isolation between software components [5]. Isolation can prevent a component failure from turning into a service failure by preventing cascading failures.

- proactive restart: periodic prophylactic rebooting of hardware and restarting of software [7]. This can prevent faulty components with latent errors due to resource leaks from failing.

### Everything You Know About Latency Is Wrong - Tyler Treat

[https://bravenewgeek.com/everything-you-know-about-latency-is-wrong/](https://bravenewgeek.com/everything-you-know-about-latency-is-wrong/)

- Latency is defined as the time it took one operation to happen. This means every operation has its own latency—with one million operations there are one million latencies. As a result, latency cannot be measured as work units/time.

- Latency almost never follows a normal, Gaussian, or Poisson distribution, so looking at averages, medians, and even standard deviations is useless.

- The 99th percentile, by definition, is the latency below which 99% of the observations may be found

- The median is the number that 99.9999999999% of response times will be worse than. This is why median latency is irrelevant. People often describe "typical" response time using a median, but the median just describes what everything will be worse than. It's also the most commonly used metric.

- why do most monitoring systems stop at the 95th or 99th percentile? The answer is simply because "it's hard!" The data collected by most monitoring systems is usually summarized in small, five or ten second windows.

- Benchmarking is hard. Almost all latency benchmarks are broken because almost all benchmarking tools are broken. The number one cause of problems in benchmarks is something called "coordinated omission," which Gil refers to as "a conspiracy we're all a part of" because it's everywhere.

- to understand latency, you have to consider the entire distribution. Do this by plotting the latency distribution curve. Simply looking at the 95th or even 99th percentile is not sufficient. Tail latency matters. Worse yet, the median is not representative of the "common" case, the average even less so. There is no single metric which defines the behavior of latency. Be conscious of your monitoring and benchmarking tools and the data they report. You can't average percentiles. Remember that latency is not service time. If you plot your data with coordinated omission, there's often a quick, high rise in the curve. Run a "CTRL+Z" test to see if you have this problem. A non-omitted test has a much smoother curve.

- What coordinated omission is really showing you is service time, not response time. If we imagine a cashier ringing up customers, the service time is the time it takes the cashier to do the work. The response time is the time a customer waits before they reach the register. If the rate of arrival is higher than the service rate, the response time will continue to grow.

### Principles of Software Engineering, Part 1 - Nathan Marz

[http://nathanmarz.com/blog/principles-of-software-engineering-part-1.html](http://nathanmarz.com/blog/principles-of-software-engineering-part-1.html)

- Making software robust is an iterative process: you build and test it as best you can, but inevitably in production, you'll discover new areas of the input space that lead to failure.

- You can do a much better job building robust software by being cognizant of the uncertain nature of software

- One technique for making software more robust is to minimize what your software depends on – the less that can go wrong, the less that will go wrong.

- There's always a tradeoff between minimizing dependencies and minimizing the amount of code you need to produce to implement your application.

- Another great technique for avoiding cascading failures is to isolate your components as much as possible and take away the ability for different components to affect each other.

- Software should be designed from the start to be monitored

- Monitoring is the most important defense against software's inherent uncertainty.

- Software engineering is a constant battle against uncertainty – uncertainty about your specs, uncertainty about your implementation, uncertainty about your dependencies, and uncertainty about your inputs. Recognizing and planning for these uncertainties will make your software more reliable – and make you a better engineer.

### Hongyu Pei Breivold, Ivica Crnkovic, and Peter J. Eriksson: "Analyzing Software Evolvability," at 32nd Annual IEEE International Computer Software and Applications Conference (COMPSAC), July 2008.

[http://www.es.mdh.se/pdf\_publications/1251.pdf](http://www.es.mdh.se/pdf_publications/1251.pdf)

- Software evolution is characterized by inevitable changes of software and increasing software complexities, which in turn may lead to huge costs unless rigorously taking into account change accommodations.

- We refer to the evolvability definition in [18], since it expresses the dynamic behaviour during a software system's lifecycle and supports the staged model: "An attribute that bears on the ability of a system to accommodate changes in its requirements throughout the system's lifespan with the least possible cost while maintaining architectural integrity."

- Analyzability - Many perspectives are included in this dimension, e.g. identification and decisions on what to modify, analysis and exploration of emerging technologies from maintenance and evolution perspectives. Measuring attributes include modularity, complexity, and documentation.

- Integrity - Architectural integrity is related to understanding and coherence to the architectural - decisions and adherence to the original architectural styles, patterns or strategies. Taking integrity as one subcharacteristic of evolvability does not mean that the architectural approaches are not allowed to be changed. Proper architectural integrity management is essential for the architecture to allow unanticipated changes in the software without compromising software integrity and to evolve in a controlled way [1]. Measuring attributes include architectural documentation.

- Changeability - Description: Software architecture that is capable of accommodating change must be specifically designed for change [10]. Measuring attributes include complexity, coupling, change impact, encapsulation, reuse, modularity.

- Portability - Due to the rapid technical development on hardware and software technologies, portability is one of the key enablers that can provide possibility to choose between different hardware and operating system vendors as well as various versions of frameworks. Measuring attributes include mechanisms facilitating adaptation to different environments.

- Extensibility - One might argue that extensibility is a subset of changeability. Due to the fact that about 55% of all change requests are new or changed requirements [15], we define extensibility explicitly as one subcharacteristic of evolvability. It is a system design principle where the implementation takes future growth into consideration. Measuring attributes include modularity, coupling, encapsulation, change impact.

- Testability - Description: According to statistics [7], software testing spends as much as 50% of development costs and comprises up to 50% of development time. Hence, testability is a key feature permitting high quality to be combined with reduced time-to-market. Measuring attributes include complexity, modularity.

- Domain-specific attributes: Different domains may require additional quality characteristics that are specific for a software system to be evolvable. Measuring attributes depend on the specific domains.

# Videos

### Simple Made Easy - Rich Hickey

[https://www.infoq.com/presentations/Simple-Made-Easy/](https://www.infoq.com/presentations/Simple-Made-Easy/)

### Scaling Yourself - Scott Hanselman - GOTO 2012

[https://www.youtube.com/watch?v=FS1mnISoG7U](https://www.youtube.com/watch?v=FS1mnISoG7U)

### The Clean Coder - Uncle Bob Martin

[https://www.youtube.com/watch?v=NeXQEJNWO5w](https://www.youtube.com/watch?v=NeXQEJNWO5w)
