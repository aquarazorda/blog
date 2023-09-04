---
title: Deeto's Journey - Road to Improvement (Final Thoughts)
author: Givi
pubDatetime: 2023-09-04T20:17:19Z
postSlug: deeto-journey-for-improvement-final-thoughts
draft: false
tags:
  - deeto
  - improvements
  - back-end
  - front-end
  - react
  - solid
  - drizzle
  - performance
  - full-stack
description: This post aims to introduce several incremental approaches for enhancing both our back-end and front-end. By adopting these strategies, we can elevate the developer experience, achieve substantial performance gains, streamline maintenance, and align with contemporary industry standards.
---

- [Deeto's Journey - Road to Improvement (Styling and Design)](https://aquarazorda.vercel.app/posts/deeto-journey-for-improvement-front-end-bottlenecks)
- [Deeto's Journey - Road to Improvement (Performance & Back-end Integration)](https://aquarazorda.vercel.app/posts/deeto-journey-for-improvement-front-end-performance)

This post aims to introduce several incremental approaches for enhancing both our back-end (BE) and front-end (FE). By adopting these strategies, we can elevate the developer experience, achieve substantial performance gains, streamline maintenance, and align with contemporary industry standards.

# Front-end

The project initially used CRA (create-react-app) with JavaScript but has since been migrated to Vite and TypeScript, aligning with contemporary frameworks like Next.js, Remix, and SolidStart. However, a major bottleneck currently faced is the extensive usage of styled-components throughout the project, making it challenging to manage and transition to a different framework.

As a first step towards improvement, I recommend a migration to _**TailwindCSS**_:

- Begin by integrating TailwindCSS into our project.
- Moving forward, implement new features using TailwindCSS.
- Consider migrating sections of the website that undergo frequent design changes to TailwindCSS, facilitating more flexible design adjustments.

This transition promises to enhance the project's maintainability and design flexibility, aligning it with modern development practices.

Given the division of our application into three distinct parts (vendor, reference, prospect), it's a strategic move to consider transitioning one of these segments into a full-stack framework project, such as Next.js, Remix, or SolidStart. This approach allows us to harness the benefits of a unified development ecosystem for one portion of the application.

Additionally, it's advisable to outline future plans. For instance, if significant changes are anticipated in the reference side of the application, we can proactively plan for a rewrite of that specific section using the aforementioned frameworks. This proactive approach ensures that our development efforts align with forthcoming requirements and technological advancements, enhancing our overall project sustainability.

# Back-end

To optimize our project, our first step should involve identifying the most frequently used API endpoints as well as those exhibiting performance issues. We can then commence the transition by describing these tables using DrizzleORM, marking the beginning of our shift away from Sequelize in favor of DrizzleORM. This gradual transition promises to deliver notable performance improvements and enhance the developer experience.

Subsequently, as we undertake the rewrite of specific sections of our front-end application, we can seamlessly migrate the backend APIs to our full-stack application.
