---
title: Deeto's Journey for Improvement - Front-End Bottlenecks
author: Givi
pubDatetime: 2023-08-29T22:17:19Z
postSlug: deeto-journey-for-improvement-front-end-bottlenecks
draft: false
tags:
  - deeto
  - improvements
  - tailwindcss
  - front-end
description: Addressing challenges within front-end development for the Deeto platform, the post highlights concerns surrounding the performance implications of styled-components, the intricacies of dynamic component creation, and the intricacies of achieving responsive design. The proposition to embrace TailwindCSS is presented, emphasizing its benefits including established best practices, modular reusability, and seamless integration with design tools like Figma.
---

After investing months of effort into the Deeto platform, I've identified several drawbacks at both the development and application levels. These observations stem from my extensive personal experience and represent my individual viewpoint. It's important to note that these issues are not unique to our project; however, I aim to provide you with an alternative perspective from the development side.

Let's start by delving into the bottlenecks encountered during front-end development and the potential solutions.

### Addressing Design Implementation (Markup Creation)

Our current approach involves the use of styled-components, a runtime styles generator library, for markup creation. Unfortunately, this choice impacts both performance and developer experience. The generation of new components contributes to the bundle size and introduces additional logic to the JavaScript side, thereby affecting performance.

The developer experience, particularly when employing TypeScript, is suboptimal due to the following reasons:

1. **Tedious Styling Process**: Styling elements requires the creation of a new variable to initialize styled-components. This initialization process lacks consistency as there are multiple ways to approach it. This becomes cumbersome, especially when dealing with minor styling for non-reusable divs. The procedure involved is intricate and time-consuming.
2. **Complexity in Dynamic Components**: Developing dynamic components entails managing multiple styled-components:
   1. Deciding whether to place them in the same file or create a separate file for better organization.
   2. Choosing appropriate names for the components.
   3. Dealing with type definitions, which involves finding the suitable type from styled-components and extending it to ensure type safety and IntelliSense. This step is not only time-intensive but also devoid of enjoyment.
   4. Consequently, a single component may result in the creation of multiple components.
3. **Excessive Component Extension**: Extending components is straightforward, yet this practice can lead to excessive use of certain components, potentially leading to regression issues.
4. **Lack of Styling Tools**: There is a dearth of tools to facilitate straightforward styling. For instance, translating design elements from Figma to code requires manual mapping of colors and font sizes, consuming considerable time and effort.
5. **Challenges with Variants**: Incorporating variants, such as styling a specific text element, demands meticulous exploration of available options in the variants. The process involves deciphering size labels, font weights, and colors, leading to a time-consuming search. Often, a precise match is not available, necessitating compromises or additional components, which contribute to increased bundle size.
6. **Responsive Design Complexity**: Handling responsive design is arduous. While media queries are used in some instances, they necessitate repeated definitions. Alternatively, custom hooks are employed to identify the device type (mobile, tablet, desktop), leading to the inclusion of extra styled-components based on device output. This approach adversely affects performance.

These challenges form the core of my day-to-day struggles. An alternative solution to these issues lies in adopting TailwindCSS, a mature framework with a 7-year development history. It offers a multitude of benefits, such as well-established practices, versatile design frameworks, and streamlined developer experience. Furthermore, Figma's support for TailwindCSS allows for seamless integration of design templates, even without direct usage. Whether through code extraction or style mapping, Figma's compatibility enhances design integration.

Embracing TailwindCSS presents several advantages:

1. **Guidance and Examples**: TailwindCSS offers established best practices and a collection of examples.
2. **Adaptable Design Foundations**: The framework provides a flexible and expandable design foundation.
3. **Modular Reusability**: TailwindCSS's modular approach promotes easy style reuse and results in a smaller CSS footprint.
4. **Enhanced Tooling**: TailwindCSS features robust tooling, enhancing comfort and efficiency during development.
5. **Accessible Learning Curve**: For those familiar with CSS, learning TailwindCSS is straightforward.

Crucially, adopting TailwindCSS reduces the necessity for excessive decision-making by both developers and designers. This allows for a more concentrated focus on achieving the desired end product.

For more insights, consider these resources:

- [Tailwind CSS is the worst…](https://www.youtube.com/watch?v=lHZwlzOUOZ4)
- [6 Reasons Why Tailwind CSS is Worth It](https://encircletechnologies.com/blog/6-reasons-why-tailwind-css-is-worth-it/)

_It's important to mention that TailwindCSS endorses a mobile-first design philosophy, although this can be easily customized._

### Conclusion: Streamlined Development with Improved Quality and Performance
