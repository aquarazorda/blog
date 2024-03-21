---
title: Refactoring Plan - Moving to Tailwind CSS, React Aria, and ShadCN UI
author: Givi
pubDatetime: 2024-03-21T05:17:19Z
postSlug: deeto-frontend-refactor
featured: true
draft: false
tags:
  - frontend
  - refactoring
  - shadcn
  - tailwind
  - react
  - aria
description: As our project evolves, we have decided to move away from styled-components and embrace Tailwind CSS for styling. This refactoring effort presents an excellent opportunity to make significant improvements to our codebase. To ensure a smooth transition, we will create a separate project and start building from scratch, leveraging module federation to use components from the new project in our current application.
---

## Introduction

As our project evolves, we have decided to move away from styled-components and embrace Tailwind CSS for styling. This refactoring effort presents an excellent opportunity to make significant improvements to our codebase. To ensure a smooth transition, we will create a separate project and start building from scratch, leveraging module federation to use components from the new project in our current application.

## Key Changes

### 1. Styling with Tailwind CSS

We will be adopting Tailwind CSS as our primary styling solution. Tailwind CSS offers several benefits:

- **Utility-first approach**: Tailwind provides a comprehensive set of pre-defined utility classes, allowing us to rapidly build custom designs without writing extensive CSS.
- **Responsive design**: Tailwind's responsive utility classes make it effortless to create responsive layouts that adapt to different screen sizes.
- **Consistency**: By using a standardized set of utility classes, we can maintain a consistent visual language throughout our application.
- **Customization**: Tailwind allows easy customization of its default configuration, enabling us to tailor the styling to our project's specific needs.

### 2. Leveraging React Aria and ShadCN UI

In addition to Tailwind CSS, we will be utilizing React Aria and ShadCN UI:

- **React Aria**: React Aria is a library of unstyled, highly accessible components. It provides a solid foundation for building inclusive and accessible user interfaces. React Aria components are well-documented and easy to use, ensuring a seamless development experience.
- **ShadCN UI**: ShadCN UI is a wrapper built on top of React Aria. It extends React Aria's functionality and provides a set of beautifully designed components out of the box. ShadCN UI copies styled React Aria components into our project, allowing us to easily modify and customize them to fit our design requirements. With ShadCN UI, we can quickly establish a consistent and visually appealing design system.

By leveraging React Aria and ShadCN UI, we can significantly enhance the accessibility and usability of our application while reducing the effort required to build and maintain our own design system.

### 3. State Management with Zustand

For state management, we will be using Zustand. Zustand offers several advantages:

- **Simplicity**: Zustand provides a minimalistic and intuitive API for managing state. It eliminates the need for complex boilerplate code and allows us to focus on the actual state logic.
- **Performance**: Zustand is designed with performance in mind. It efficiently manages state updates and minimizes unnecessary re-renders, resulting in improved application performance.
- **Granular updates**: With Zustand, we can update specific parts of the state without triggering re-renders of unrelated components. This fine-grained control over state updates helps optimize rendering performance.
- **Ease of use**: Zustand integrates seamlessly with React and can be used with hooks, making it easy to incorporate into our existing codebase.

By using Zustand for state management, we can efficiently handle complex state scenarios, such as user state and onboarding flow, while ensuring optimal performance and maintainability.

## Refactoring Approach

The refactoring process will involve the following steps:

1. Adjust colors and components in ShadCN UI to align with our design requirements.
2. Adopt a file-based routing pattern using Tanstack Router for improved project structure and type-safe routing.
3. Organize route-specific state, modals, forms, and queries near the corresponding route components for better code organization and discoverability.
4. Identify and extract reusable patterns as the project evolves, promoting code reuse and maintainability.
5. Export wrapper components as module federation components to enable their usage in our old application.
6. Incrementally replace routes in the old application with fully functional routes from the new project.

## Considerations

- We will explore the potential benefits of Replicache for our application. However, integrating Replicache may require modifications to our backend, and we need to carefully evaluate its pricing and feasibility.
- While Remix framework supports fully client-side rendered apps, we prefer the file-based structure and routing approach of Next.js. We will use Tanstack Router with file-based route matching to achieve a similar project structure.

## Conclusion

By embarking on this refactoring journey, we aim to enhance the maintainability, performance, and scalability of our application. The adoption of Tailwind CSS, React Aria, ShadCN UI, and Zustand will provide us with a solid foundation for building accessible, visually appealing, and efficiently managed user interfaces. Throughout the refactoring process, we will prioritize incremental improvements and ensure a smooth transition for our users.

Let's collaborate closely, share knowledge, and support each other during this exciting refactoring endeavor. Together, we can elevate our application to new heights!
