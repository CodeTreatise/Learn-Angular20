Angular 20: The Complete Guide
Welcome to the comprehensive guide for Angular 20. This guide takes you from the basics of Angular development to advanced concepts, ensuring a solid understanding of the framework and its ecosystem. Whether you're a beginner starting your journey or an experienced developer updating your skills, this guide is tailored for you.
Angular 20 introduces powerful features like standalone components and signals, simplifying development and boosting performance. For those coming from older versions (e.g., Angular 2-14), you'll find notes connecting new concepts to familiar ones, easing the transition.
Note: This guide is based on Angular 20. Check the official Angular documentation for updates in later versions.
Learning Paths

Beginner Path: Modules 1-7 (Basics to APIs)
Intermediate Path: Modules 8-10, 12-13 (State Management, Performance, Security, Testing)
Expert Path: Modules 11, 14-15 (Architecture, Deployment, Ecosystem)

Table of Contents

Module 1: Introduction to Modern Angular & Setup
Module 2: Angular Fundamentals: Components & Templates
Module 3: The Modern Way: Standalone Components Deep Dive
Module 4: Services & Dependency Injection (DI)
Module 5: Routing & Navigation
Module 6: Angular Forms
Module 7: Working with APIs using HttpClient
Module 8: Introduction to RxJS & State Management
Module 9: The New Reactivity Model: Angular Signals
Module 10: Advanced Component Design & Performance
Module 11: Enterprise-Grade Angular: Architecture & Scalability
Module 12: Security, Internationalization & Accessibility
Module 13: Testing Your Angular Application
Module 14: Building, Deployment & Continuous Integration/Delivery
Module 15: Beyond the Basics & Ecosystem
Final Project
Appendix


Module 1: Introduction to Modern Angular & Setup
Why: Understand Angular’s purpose and set up your environment to start building apps.How: Install tools and create your first project.
### 1.1. Introduction to Angular
This section provides a high-level overview of Angular, its place in the web development ecosystem, and its core principles.

#### 1.1.1. What is Angular? (Single Page Applications - SPA, Framework vs. Library)
Angular is a powerful, open-source web application framework developed and maintained by Google. It is designed for building **Single Page Applications (SPAs)**.

*   **Single Page Application (SPA):** In a traditional multi-page application, clicking a link requests a completely new page from the server. In an SPA, the initial page load brings all the necessary code (HTML, CSS, JavaScript). As the user interacts with the app, only the necessary data is fetched from the server, and the page content is dynamically rewritten in the browser. This results in a faster, smoother, and more fluid user experience, similar to a native desktop or mobile application.

*   **Framework vs. Library:** A key distinction to understand is that Angular is a **framework**, not a library.
    *   A **library** (like jQuery or React) gives you a set of tools to solve a specific problem (e.g., DOM manipulation, UI rendering). You call the library's code from your own code.
    *   A **framework** (like Angular) provides a complete structure and a set of rules for building an application. It dictates the architecture and calls *your* code when it needs to. This opinionated nature provides consistency and scalability, especially for large, complex applications.

#### 1.1.2. Brief History and Evolution of Angular (AngularJS to Angular 20)
Angular has undergone a significant evolution:
*   **AngularJS (Version 1.x):** Released in 2010, AngularJS was revolutionary. It introduced concepts like two-way data binding and dependency injection to the mainstream, making it easy to build dynamic web apps.
*   **Angular (Version 2+):** In 2016, the Angular team released Angular 2, a complete rewrite from the ground up. It was faster, more modular, and built with modern web standards in mind, using TypeScript as its primary language. This rewrite broke compatibility with AngularJS, which is why the versions are distinguished by "AngularJS" (v1) and "Angular" (v2+).
*   **Angular 2 to 19:** From version 2 onwards, Angular has followed a predictable release schedule, introducing incremental improvements, from the Ivy renderer (for smaller bundles and faster compilation) to stricter type checking.
*   **Angular 20:** This version continues the trend of modernization, focusing on developer experience and performance. The introduction of **Signals** offers a new reactivity model, and the promotion of **Standalone Components** as the default simplifies the learning curve and application structure.

#### 1.1.3. Key Features and Advantages of Angular 20
*   **Standalone Components:** Drastically simplifies the application structure by removing the need for `NgModules` in many cases. This reduces boilerplate and makes Angular easier to learn.
*   **Signals:** A new, fine-grained reactivity system that automatically tracks data dependencies and updates the view efficiently, often without relying on Zone.js, leading to better performance.
*   **TypeScript-based:** Code is written in TypeScript, a superset of JavaScript that adds static types. This leads to more robust, maintainable code with excellent tooling and autocompletion.
*   **Comprehensive Ecosystem:** Angular is a "batteries-included" framework. It provides built-in solutions for routing, state management, form handling, and HTTP requests, ensuring they all work together seamlessly.
*   **Powerful CLI:** The Angular Command Line Interface (CLI) is a best-in-class tool that scaffolds projects, generates code, runs tests, and handles builds, streamlining the entire development workflow.

#### 1.1.4. Understanding the Core Concepts: Components, Services, and the shift towards Standalone Components
*   **Components:** The fundamental building blocks of an Angular UI. A component controls a patch of the screen called a "view". It consists of a TypeScript class for the logic, an HTML template for the view, and CSS styles.
*   **Services:** Classes designed to provide specific functionality, such as fetching data, logging, or handling business logic. Services are decoupled from components, making them reusable and easy to test.
*   **The Shift to Standalone:**
    *   **Old Connection (Pre-Standalone):** In older Angular versions, `NgModules` were mandatory. They were used to group related components, directives, pipes, and services, creating a context for the compiler.
    *   **The New Way (Standalone First):** Starting with Angular 14 and becoming the default in later versions, components can now be **standalone**. They explicitly declare their own dependencies without needing to be part of an `NgModule`. This makes the architecture simpler, more intuitive, and eliminates a common source of confusion for newcomers.
### 1.2. Setting Up the Development Environment
A proper development environment is crucial for a smooth and efficient workflow. This section guides you through installing the necessary tools.

#### 1.2.1. Installing Node.js and npm
To run Angular applications locally, you need **Node.js**, which is a JavaScript runtime environment. Installing Node.js also automatically installs the **Node Package Manager (npm)**, which is used to manage project dependencies (like Angular itself).

*   **Why you need it:** The Angular CLI and the local development server (`ng serve`) are Node.js programs. npm is used to download and manage all the libraries your project depends on.
*   **How to install:**
    1.  Go to the official Node.js website: [https://nodejs.org/](https://nodejs.org/)
    2.  Download the installer for the **LTS (Long Term Support)** version. LTS versions are recommended for most users as they are stable and receive long-term support.
    3.  Run the installer and follow the on-screen instructions.
*   **How to verify installation:** Open your terminal or command prompt and run the following commands:
    ```bash
    node -v
    npm -v
    ```
    These commands should print the installed versions of Node.js and npm, respectively.

*(Note: Yarn is an alternative to npm. While this guide uses npm, the commands are very similar if you choose to use Yarn.)*

#### 1.2.2. Installing the Angular CLI
The **Angular Command Line Interface (CLI)** is an indispensable tool for developing Angular applications. It automates repetitive tasks like creating projects, components, services, and running builds.

*   **Why you need it:** The CLI saves you a significant amount of time and ensures your project follows best practices. It handles complex configurations for building, testing, and deploying your application.
*   **How to install:** Install the CLI globally on your system using npm. The `-g` flag ensures the `ng` command is available in any directory.
    ```bash
    npm install -g @angular/cli
    ```
*   **How to verify installation:** Run the following command:
    ```bash
    ng version
    ```
    This will display the installed Angular CLI version along with other helpful information about your environment.

#### 1.2.3. Recommended IDE (VS Code) and Essential Extensions
While you can use any text editor, an **Integrated Development Environment (IDE)** provides features that greatly enhance productivity. **Visual Studio Code (VS Code)** is the most popular choice for Angular development due to its performance and extensive extension ecosystem.

*   **Download VS Code:** [https://code.visualstudio.com/](https://code.visualstudio.com/)

*   **Essential VS Code Extensions:**
    *   **Angular Language Service:** This is a must-have. It provides a richer editing experience for Angular templates, including code completion, error checking, and navigation inside your HTML files.
    *   **Prettier - Code formatter:** An opinionated code formatter that automatically formats your code to ensure a consistent style across your entire project. This helps maintain readability and reduces arguments over code style in team settings.
    *   **ESLint:** Integrates the ESLint static analysis tool into VS Code to find and fix problems in your TypeScript code.
    *   **Material Icon Theme:** Provides a rich set of icons that make it easier to distinguish between different file types in the project explorer.
### 1.3. Your First Angular 20 Application (Standalone First)
With the environment set up, you are ready to create and run your first Angular application. We will use the Angular CLI to generate a modern, standalone-based project.

#### 1.3.1. Generating a New Project with Angular CLI
The `ng new` command initializes a new Angular workspace.

*   **Command:**
    ```bash
    ng new my-first-app --standalone
    ```
*   **Dissecting the command:**
    *   `ng new`: The CLI command to create a new application.
    *   `my-first-app`: This is the name of your project. The CLI will create a new directory with this name.
    *   `--standalone`: This is a crucial flag. It tells the CLI to generate an application that uses the modern, simplified **standalone** architecture, without `NgModules`. This is the recommended approach for all new Angular applications.

After running the command, the CLI will ask you a few questions:
*   **"Which stylesheet format would you like to use?"**: Choose **CSS**. You can navigate with the arrow keys and press Enter.
*   **"Do you want to enable Server-Side Rendering (SSR) and Static Site Generation (SSG)?"**: Type **N** (No) for now. We will cover this in a later module.

The CLI will then create the project folder and install all the necessary npm packages. This might take a minute or two.

#### 1.3.2. Understanding the Initial Project Structure
Navigate into your new project directory (`cd my-first-app`). You will see the following key files and folders:

*   `angular.json`: The configuration file for the Angular CLI. It contains build settings, project information, and other workspace configurations.
*   `package.json`: Standard to all Node.js projects, this file lists the project's dependencies (libraries like Angular itself) and defines useful scripts (like `start`, `build`, `test`).
*   `src/`: This is the most important folder, containing all the source code for your application.
*   `src/main.ts`: The main entry point for the application. This is the first code that runs, and its job is to **bootstrap** (start up) your Angular application.
*   `src/app/`: Contains the root component of your application, `AppComponent`.
*   `tsconfig.json`: The configuration file for the TypeScript compiler, defining how your TypeScript code should be compiled into JavaScript.

#### 1.3.3. Bootstrapping a Standalone Application
Open the `src/main.ts` file. You will see how a standalone application is started.

*   **File: `src/main.ts`**
    ```typescript
    import { bootstrapApplication } from '@angular/platform-browser';
    import { appConfig } from './app/app.config';
    import { AppComponent } from './app/app.component';

    bootstrapApplication(AppComponent, appConfig)
      .catch((err) => console.error(err));
    ```
*   **Explanation:**
    *   `bootstrapApplication` is the function that starts the whole process.
    *   It takes your root component, `AppComponent`, as the first argument. This tells Angular which component to load first.
    *   This is much simpler than the older, NgModule-based approach which required bootstrapping a module instead of a component directly.

#### 1.3.4. Running the Application
The Angular CLI includes a development server so you can see your application in action.

*   **Command:**
    ```bash
    ng serve
    ```
*   **What it does:**
    1.  Compiles your application.
    2.  Starts a local web server.
    3.  Watches your source files for any changes and automatically recompiles and reloads the browser when you save a file.

Once the compilation is complete, open your web browser and navigate to **`http://localhost:4200`**. You should see the default welcome page for a new Angular application.

Congratulations, you have successfully created and run your first Angular 20 application!

1.4. Core Project Files Deep Dive
Details on angular.json, package.json, tsconfig.json, main.ts, and app.config.ts.
1.5. TypeScript Fundamentals for Angular
Covers ES2015+ (Promises, Modules) and TypeScript (Types, Decorators).
Project: Build a "Hello World" app.

Module 2: Angular Fundamentals: Components & Templates
Why: Components are the core of Angular’s UI.How: Create and manipulate them with bindings and directives.
2.1. Components: The Building Blocks of UI
2.1.1. What is a Component?
Encapsulates UI logic and view.Why: Reusability and modularity.
2.1.2. Anatomy of an Angular Component
Includes @Component, class, template, and styles.
2.1.3. Creating Components with Angular CLI
ng generate component my-component

2.2. Data Display with Interpolation & Property Binding
2.2.1. Interpolation
{{ data }} displays values.How: One-way data flow.
2.2.2. Property Binding
[property]="value" binds data to properties.
2.2.3. Attribute Binding
[attr.attribute]="value" for HTML attributes.
2.3. Event Binding & Two-Way Data Binding
2.3.1. Event Binding
(click)="handler()" responds to events.
2.3.2. Two-Way Data Binding
[(ngModel)] syncs data (needs FormsModule).
2.4. Template Directives: Modifying the DOM
2.4.1. Understanding Directives
Structural (layout) vs. Attribute (behavior).
2.4.2. Built-in Structural Directives
New Angular 20 syntax: @if, @for, @switch.Old Connection: Replaces *ngIf, *ngFor.
2.4.3. Built-in Attribute Directives
[ngClass], [ngStyle] for dynamic styling.
Project: Build a "User Profile" component with data display and event handling.

Module 3: The Modern Way: Standalone Components Deep Dive
Why: Simplifies app structure.How: Use standalone components instead of NgModules.
3.1. The "Why": Simplifying Angular with Standalone Components
3.1.1. Evolution from NgModules to Standalone
Reduces boilerplate.Old Connection: NgModules are optional now.
3.1.2. Benefits of Standalone Components
Easier lazy loading, better tree-shaking.
3.1.3. When to still use NgModules
For legacy or complex apps.
3.2. Creating and Bootstrapping Standalone Applications
3.2.1. bootstrapApplication in main.ts
Directly boots a component.
3.2.2. Providing application-wide services
Use app.config.ts.
3.3. Importing Dependencies in Standalone Components
3.3.1. The imports array in @Component
Imports components, pipes, etc.
3.3.2. Importing other Standalone Components, Pipes, Directives, and Modules
Directly in imports.
Project: Refactor "Hello World" and "User Profile" to standalone.

Module 4: Services & Dependency Injection (DI)
Why: Manage logic and share data.How: Use services and DI.
4.1. The Purpose of Services
4.1.1. Shared Logic and Reusability
Centralize logic.
4.1.2. Separation of Concerns
UI vs. logic.
4.1.3. State Management in Services
Simple state handling.
4.2. Creating and Providing Services
4.2.1. @Injectable() Decorator
providedIn: 'root' for app-wide access.
4.2.2. Generating Services with Angular CLI
ng generate service my-service

4.3. Understanding Dependency Injection
4.3.1. What is DI?
Dependencies are injected, not created.
4.3.2. Providers and Injectors
Hierarchical system for DI.
4.3.3-4.3.6. Advanced DI
Covers custom providers, inject().
Project: Create UserDataService for "User Profile".

Module 5: Routing & Navigation
Why: Enable SPA navigation.How: Configure routes and guards.
5.1. Introduction to SPA Routing
5.1.1. Why do we need client-side routing?
Smooth navigation.
5.1.2. The Angular Router
Core navigation tool.
5.2. Configuring Routes
5.2.1-5.2.5. Route Setup
Use provideRouter, <router-outlet>, [routerLink].
5.3-5.5. Advanced Routing
Covers parameters, lazy loading.
Project: Build a multi-page app with guarded routes.

Module 6: Angular Forms
Why: Handle user input effectively.How: Use template-driven or reactive forms.
6.1-6.6. Forms Overview
Covers both approaches, validation, and dynamic forms.
Project: Create a "User Registration" form.

Module 7: Working with APIs using HttpClient
Why: Fetch external data.How: Use HttpClient and interceptors.
7.1-7.4. API Handling
Covers requests, responses, and interceptors.
Project: Display and search API data.

Module 8: Introduction to RxJS & State Management
Why: Manage async data and state.How: Use RxJS and NgRx.
8.1-8.5. RxJS and NgRx
Covers Observables, operators, and state.
Project: Enhance search with RxJS, add NgRx feature.

Module 9: The New Reactivity Model: Angular Signals
Why: Improve reactivity and performance.How: Use signals.Old Connection: Replaces Zone.js in some cases.
9.1-9.5. Signals Overview
Covers core APIs and queries.
Project: Refactor "User Profile" with signals.

Module 10: Advanced Component Design & Performance
Why: Optimize and extend components.How: Use lifecycle hooks, directives, and optimizations.
10.1-10.6. Advanced Techniques
Covers hooks, content projection, and performance.
Project: Enhance components with custom pipe and directive.

Module 11: Enterprise-Grade Angular: Architecture & Scalability
Why: Build large-scale apps.How: Use monorepos, SSR, PWAs.
11.1-11.6. Enterprise Topics
Covers Nx, micro frontends, and more.

Module 12: Security, Internationalization & Accessibility
Why: Ensure secure, global, accessible apps.How: Implement best practices.
12.1-12.3. Key Areas
Covers XSS, i18n, and a11y.

Module 13: Testing Your Angular Application
Why: Ensure quality.How: Write unit and E2E tests.
13.1-13.4. Testing Overview
Covers Jest, Cypress, and more.
Project: Test "User Profile" and service.

Module 14: Building, Deployment & Continuous Integration/Delivery
Why: Deploy apps efficiently.How: Build and automate deployment.
14.1-14.3. Deployment Topics
Covers build, hosting, CI/CD.
Project: Deploy multi-page app.

Module 15: Beyond the Basics & Ecosystem
Why: Explore advanced tools and future trends.How: Use Material, Elements, and DevTools.
15.1-15.5. Ecosystem Overview
Covers libraries, upgrades, and future.

Final Project
Choose one:

Simple: To-do list with local storage.
Intermediate: Blog with auth and comments.
Advanced: E-commerce site with full features.


Appendix
Includes CLI reference, troubleshooting, resources, and glossary.