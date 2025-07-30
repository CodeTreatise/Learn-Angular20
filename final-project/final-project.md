# Final Project: Apply Your Knowledge

**Objective:** To consolidate your understanding of Angular 20 by building a complete application, choosing from a range of project complexities.

---

### The Importance of Building

Learning a framework like Angular is best solidified through practical application. This final project is your opportunity to apply the concepts, techniques, and best practices you've learned throughout this course. It will help you:

*   **Reinforce Concepts:** Deepen your understanding by actively implementing features.
*   **Problem-Solving:** Develop your ability to tackle real-world development challenges.
*   **Portfolio Building:** Create a tangible project to showcase your skills to potential employers.
*   **Confidence:** Gain confidence in your ability to build full-fledged Angular applications.

### Project Options

Choose one of the following project options based on your comfort level and the time you have available. Each project is designed to incorporate various Angular concepts covered in the course.

#### 1. Simple: To-Do List Application

*   **Description:** A classic web application that allows users to add, view, mark as complete, and delete to-do items. Data should persist locally.
*   **Key Concepts to Apply:**
    *   **Components:** `AppComponent`, `TodoListComponent`, `TodoItemComponent`, `AddTodoComponent`.
    *   **Data Binding:** Displaying to-do items, input fields for new items.
    *   **Event Handling:** Adding, completing, deleting items.
    *   **Directives:** `@for` to render the list, `@if` for conditional rendering (e.g., showing/hiding completed items).
    *   **Services:** A `TodoService` to manage the list of to-dos.
    *   **Local Storage:** Persisting to-do items in the browser's `localStorage`.
    *   **Reactive Forms:** (Optional, but recommended) For the add/edit to-do form.
    *   **Signals:** (Optional, but recommended) To manage the list of to-dos reactively.

#### 2. Intermediate: Blog Application with Authentication & Comments

*   **Description:** A multi-page blog application where users can view blog posts, register, log in, and add comments to posts. Admin users might have the ability to create/edit/delete posts.
*   **Key Concepts to Apply:**
    *   **All Simple Project Concepts**
    *   **Routing:** Multiple routes (e.g., `/`, `/posts/:id`, `/login`, `/register`, `/admin`).
    *   **Route Guards:** `CanActivate` for protecting authenticated routes (e.g., `/admin`, `/profile`).
    *   **`HttpClient`:** Fetching posts, submitting comments, handling user authentication (login/register) with a mock or real API.
    *   **Reactive Forms:** For login, registration, and comment forms.
    *   **Services:** `AuthService`, `PostService`, `CommentService`.
    *   **HTTP Interceptors:** (Optional) For adding authentication tokens to requests.
    *   **State Management:** (Optional) Using `BehaviorSubject` or a light NgRx solution for user authentication state.

#### 3. Advanced: E-commerce Site (Simplified)

*   **Description:** A basic e-commerce application where users can browse products, add them to a shopping cart, view cart contents, and proceed to a simplified checkout. Admin users can manage products.
*   **Key Concepts to Apply:**
    *   **All Intermediate Project Concepts**
    *   **Complex Routing:** Nested routes for product categories, product details.
    *   **`HttpClient`:** Extensive use for product catalog, cart management, order submission.
    *   **Advanced Forms:** Dynamic forms for product variations, checkout process.
    *   **State Management:** A more robust state management solution (e.g., NgRx, Component Store) for the shopping cart and product catalog.
    *   **Custom Directives/Pipes:** (Optional) For UI enhancements.
    *   **Performance Optimizations:** (Optional) Lazy loading product modules, `OnPush` strategy.
    *   **Testing:** Unit tests for services, components, and E2E tests for critical flows.

**Example Architecture for E-commerce Site (Simplified):**

```mermaid
graph TD
    A[User] --> B(Browser);
    B --> C[Angular Frontend];

    subgraph Angular Frontend
        C1[Router] --> C2[Product List Component];
        C1 --> C3[Product Detail Component];
        C1 --> C4[Shopping Cart Component];
        C1 --> C5[Checkout Component];
        C1 --> C6[Auth Components (Login/Register)];

        C2 --> D[Product Service];
        C3 --> D;
        C4 --> E[Cart Service];
        C5 --> E;
        C6 --> F[Auth Service];

        D --> G[HttpClient];
        E --> G;
        F --> G;
    end

    G --> H[Backend API];
    H --> I[Database];
```

### Getting Started with Your Project

1.  **Choose Your Project:** Select the project that best fits your learning goals and available time.
2.  **Plan:** Sketch out the components, services, and routes you'll need.
3.  **Initialize:** Use `ng new your-project-name --standalone` to create a new Angular project.
4.  **Implement:** Start building, focusing on one feature at a time.
5.  **Test:** Write tests as you go to ensure correctness.
6.  **Refactor:** Continuously improve your code quality and apply best practices.
7.  **Deploy:** (Optional) Deploy your finished project to a hosting service.

This final project is your opportunity to bring all your Angular knowledge together. Good luck, and have fun building!

---

### Project Evaluation Criteria (Rubric)

Your final project will be evaluated based on the following criteria:

1.  **Functionality (40%)**
    *   All core features of the chosen project are implemented and work as expected.
    *   No major bugs or broken functionalities.
    *   User interactions are smooth and intuitive.

2.  **Code Quality & Best Practices (30%)**
    *   **Modularity:** Code is well-organized into components, services, and other Angular constructs.
    *   **Readability:** Code is clean, well-commented (where necessary), and easy to understand.
    *   **Consistency:** Adherence to Angular style guide and consistent naming conventions.
    *   **Reusability:** Common logic and UI elements are encapsulated and reused.
    *   **Error Handling:** Basic error handling is implemented for API calls or user input.
    *   **Performance:** Consideration for performance (e.g., `OnPush`, `trackBy`, lazy loading where applicable).

3.  **Angular Concepts Application (20%)**
    *   Effective and appropriate use of key Angular features covered in the course (e.g., Standalone Components, Signals, Reactive Forms, Routing, Services, HttpClient, Directives, Pipes).
    *   Demonstrates understanding of Angular's core principles (e.g., component-based architecture, DI).

4.  **User Experience & Design (10%)**
    *   Intuitive navigation and clear user flow.
    *   Responsive design (adapts well to different screen sizes).
    *   Pleasing visual design (even if simple, it should be clean and functional).
    *   Basic accessibility considerations (e.g., semantic HTML, form labels).

**Bonus Points (Optional):**

*   Implementation of advanced concepts not explicitly required (e.g., NgRx, Web Workers, PWA).
*   Comprehensive unit and/or E2E tests.
*   Deployment to a live hosting service (e.g., Netlify, Vercel, Firebase).
*   Well-written `README.md` with setup instructions and project overview.

---

**Previous:** [15.5 Future Trends & Community](../15-ecosystem/15.5-future-trends-community.md)

**Next Module:** [appendix](../appendix)
