---
title: Deeto's Journey - Road to Improvement (Performance & Back-end Integration)
author: Givi
pubDatetime: 2023-08-29T23:17:19Z
postSlug: deeto-journey-for-improvement-front-end-performance
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
description: Delving into historical context of web development, present challenges, and future solutions, it notably explores the SolidStart framework as potential solution, ultimately setting the stage for incremental problem-solving strategies for optimizing Deeto's performance and functionality. Additionally, a demo of Deeto utilizing SolidStart and DrizzleORM showcases a promising future direction for the platform.
---

- [Deeto's Journey - Road to Improvement (Styling and Design)](https://aquarazorda.vercel.app/posts/deeto-journey-for-improvement-front-end-bottlenecks)
- [Deeto's Journey - Road to Improvement (Final Thoughts)](https://aquarazorda.vercel.app/posts/deeto-journey-for-improvement-final-thoughts)

After investing months of effort into the Deeto platform, I've identified several drawbacks at both the development and application levels. These observations stem from my extensive personal experience and represent my individual viewpoint. It's important to note that these issues are not unique to our project; however, I aim to provide you with an alternative perspective from the development side.

Over the past decade, single-page applications have dominated the modern web landscape, bringing numerous benefits and significantly enhancing the web experience akin to computer applications. While these advancements were enjoyable, they also introduced a considerable burden of performance implications.

In the past, web development involved creating back-end code in a chosen programming language, resulting in multi-page applications. Each time a user navigated to a different route, a request was sent to the server, which then responded with complete HTML to be rendered on-screen. This approach necessitated enhancing the HTML with JavaScript, often using tools like jQuery, leading developers to replicate the same logic for both the back-end and front-end.

Subsequently, the concept of single-page applications emerged, ushering in a separation between front-end and back-end. Back-end systems evolved into API servers, exclusively handling data manipulation, while the presentation logic for user data shifted entirely to the front-end.

Let's finish with the history and discuss what problems do we have in the present.

### Connecting Front-end with Back-end

In the contemporary landscape, we find ourselves using Node.js APIs alongside front-end frameworks like React, Angular, and Vue. The shared use of TypeScript for both back-end and front-end development facilitates the connection between the two components. Despite this alignment, several challenges persist when managing separate front-end and back-end systems.

Establishing a connection between the front-end (FE) and back-end (BE) entails sharing types, enums & utility functions. However, this critical step is often overlooked due to the complexity of maintaining a monorepo. Notably, it's uncommon to encounter a monorepo that houses both FE and BE components. Alternatively, a package for the BE might be introduced to share types and essential elements. Yet, the effort required for maintaining this package often leads to laziness, resulting in a widespread practice of copying and pasting content from the BE. To navigate the intricacies of the BE, tools like Swagger come into play, providing insight into back-end functionality.

Aligning these disparate components is a tedious endeavour, necessitating careful attention to detail. Furthermore, managing updates in the BE introduces further complexity. The TypeScript compiler does not facilitate this process, as changes in the BE don't automatically impact the FE, given the copy-paste approach. Thus, the front-end developer must remain constantly informed, deducing the changes, assessing their implications, and investing significant time in the process.

### Performance implications

As noted earlier, when a user initiates a request, the server responds with an empty HTML file alongside JavaScript files. The back-end refrains from rendering, leaving the front-end responsible for all logic. This results in an initial blank screen, with the browser parsing and executing JavaScript to render the page. This approach poses performance challenges, particularly when lacking caching, as load times heavily depend on the user's device performance and internet connection quality. Additionally, the front-end bears the weight of numerous tasks, leading to substantial bundle sizes and consequently prolonged loading times.

### Solution

Diverse solutions are addressing the issues mentioned above, offered by frameworks like SolidStart, Astro, SvelteKit, Next.js, Remix, Gatsby, and Nuxt. With experience in testing most of these frameworks, I aim to share insights gained.

My personal preferences lean towards Astro and SolidStart. This blog currently employs Astro, which offers snappy performance through static generation, resembling traditional multi-page applications while maintaining an excellent developer experience.

For Deeto, I endorse SolidStart due to its optimal runtime performance, reminiscent of React, along with small build sizes. Its alignment with React concepts allows React developers to swiftly transition to Solid development. Additionally, Solid's compatibility with Signals—also present in the latest Angular version—facilitates familiarity for Angular developers. The convenience of SolidStart's full-stack approach, where front-end and back-end code coexist within a monorepo, stands out. Functions from the back-end can be directly imported, wrapped in a `server$` function, and used on the front-end without explicit endpoint definitions, resulting in seamless integration.

Benefits of using SolidStart include:

1. **Built-in Connectivity**: Front-end and back-end are inherently connected, eliminating the need for explicit connections.
2. **Enhanced Performance**: Faster default performance compared to React.
3. **Developer Experience**: Offers an exceptional development environment.
4. **Compact Bundle Size**: Results in smaller bundle sizes.
5. **Combined Server-Side Rendering and Client-Side Routing**: Initial server-side rendering followed by client-side rendering for fast page loads.
6. **Shared Logic**: Eliminates redundancy by allowing code sharing between front-end and back-end.
7. **Efficient Development**: Accelerates the development process.
8. **SEO Compatibility**: Supports search engine optimization efforts.

While this stack boasts numerous advantages, potential downsides must also be considered. Despite the significant effort involved in transitioning the project to this stack, the payoff could be substantial.

In the forthcoming post, I will detail how to address several of these challenges incrementally, aiming to propel Deeto toward an optimized version.

Here's the demo of Deeto built on top of **_SolidStart + DrizzleORM_**

[Demo](http://deeto.vercel.app)
[Source](https://github.com/aquarazorda/deeto-solid)
