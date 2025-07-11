# Lesson 7: Prompting for Backend

[Share on Facebook](https://www.facebook.com/sharer/sharer.php?u=https%3A//github.com/Troyanovsky/vibe-coding-guide/blob/main/en/Lesson_7_Backend_Prompt.md) | [Share on Twitter](https://twitter.com/intent/tweet?text=https%3A//github.com/Troyanovsky/vibe-coding-guide/blob/main/en/Lesson_7_Backend_Prompt.md) | [Share on LinkedIn](https://www.linkedin.com/shareArticle?mini=true&url=https%3A//twitter.com/intent/tweet?text=https%253A//github.com/Troyanovsky/vibe-coding-guide/blob/main/en/Lesson_7_Backend_Prompt.md)

## Backend is the Engine Room of Your Application

Here's the thing about backend development – it's not about what users see, but about the logic, data, and performance that make your application actually work. Think of it like a restaurant: while the frontend is the beautifully designed dining room where customers have their experience, the backend is the kitchen, storage, and all the systems that make the restaurant function.

When you're prompting AI for backend code, you're essentially giving blueprints to a skilled engineer. But here's the catch – if your blueprints are vague, you'll get something that might technically work but could be insecure, inefficient, or impossible to maintain. Your prompts need to be specific about the "how": how data is structured, how logic is processed, and how different parts of your system communicate.

It's like the difference between asking a chef to "make something tasty" versus giving them a detailed recipe with ingredients, cooking methods, and plating instructions. The latter gets you consistent, reliable results.

## A Good vs. Bad Prompt for Backend

Let me show you what I mean with a concrete example. Let's say you want users to be able to save recipes in your app.

### Bad Prompt Example:
```
"I want users to be able to save recipes."
```

**Why this is terrible:** This prompt is so vague that the AI has to make dozens of assumptions. What database should it use? What programming language and framework? What information makes up a "recipe"? How do users actually "save" them – through what API endpoints? How is the user identified? Is there authentication? What about data validation?

It's like asking a chef to "make a dish" without telling them what ingredients are available, what kind of cuisine, what dietary restrictions, or even how many people they're cooking for. The result will be a shot in the dark that probably won't match what you actually need.

### Good Prompt Example:
```
"Using Node.js and Express, create a REST API to allow authenticated users to save and retrieve their personal recipes. Data should be stored in a PostgreSQL database. The `recipes` table schema and the `POST /api/v1/recipes` and `GET /api/v1/recipes` endpoints, including all their detailed requirements (request body, response format, authentication, validation, etc.), are defined in the `@system_design.md` file."
```

**Why this works:** This prompt is concise but provides a clear, actionable instruction. It specifies the tech stack (Node.js, Express, PostgreSQL), defines the core functionality (save and retrieve recipes), mentions authentication requirements, and crucially – it directs the AI to your `system_design.md` file for all the granular details.

The AI now knows exactly what to build and where to find the specifications. No guesswork required.

## The Pillars of Great Backend Prompts

Every great backend prompt should address these five core areas. Think of them as the essential blueprints your AI engineer needs to build a solid system.

### 1. Foundation (The Engine & Fuel)

This is about choosing your tech stack – the fundamental building blocks of your backend.

**What to specify:**
- **Language/Runtime:** Are you using Node.js, Python, Go, Rust, or something else?
- **Framework:** Express, Django, Flask, Gin, Actix Web, or another framework?
- **Database:** PostgreSQL (relational), MongoDB (document-based), Redis (in-memory), or a combination?

**Why it matters:** The tech stack dictates everything – the syntax the AI will use, the libraries it can leverage, and how it will interact with your database. Saying "Node.js with Express and PostgreSQL" gives the AI a completely different set of tools than "Python with Django and MongoDB."

### 2. Data Model (The Blueprint for Your Data)

This is about how your data is structured and stored. It's the foundation that everything else builds on.

**What to specify:**
- **Schema Definition:** What are your tables or collections? (e.g., `recipes`, `users`, `user_recipes`)
- **Fields & Types:** What are the columns/fields and their data types? (`title` as `TEXT`, `ingredients` as `JSONB`, `user_id` as `UUID`)
- **Relationships & Constraints:** How do tables relate to each other? (One-to-many from `users` to `recipes`). Are fields `UNIQUE`, `NOT NULL`, or have foreign key constraints?

**Why it matters:** A well-defined data model is like having a solid foundation for a house. Everything else depends on it. If your data structure is unclear or inconsistent, your entire application becomes unstable and unpredictable.

### 3. API Design (The Control Panel)

This is about how external systems (like your frontend) will interact with your backend.

**What to specify:**
- **Endpoints:** What are the URL paths? (e.g., `/api/v1/recipes`, `/api/v1/recipes/:id`)
- **HTTP Methods:** What actions can be performed? (GET for retrieving, POST for creating, PUT for updating, DELETE for removing)
- **Request/Response Shape:** What does the JSON look like for requests and responses? Define the expected body structure and headers.
- **Status Codes:** Specify expected success codes (200, 201, 204) and error codes (400, 404, 500)

**Why it matters:** Your API is the contract between your backend and any client that uses it – whether that's your frontend, a mobile app, or third-party integrations. If this contract isn't clear and consistent, you'll have constant communication issues.

### 4. Business Logic (The Rules of the Game)

This is the "brain" of your application – the specific rules and processes that make your app unique.

**What to specify:**
- **Core Processes:** What specific tasks should each endpoint perform? (e.g., "When saving a recipe, automatically link it to the currently authenticated user's ID")
- **Data Validation:** What are the rules for incoming data? (e.g., "Recipe `title` and `instructions` must not be empty," "`ingredients` should be a non-empty array")
- **Authentication & Authorization:** Who can access what? (e.g., "Only authenticated users can save recipes," "Users can only view and delete their own recipes"). How is identity verified – JWT tokens, API keys, sessions?

**Why it matters:** This is what transforms your backend from a generic data storage system into a useful service that solves real problems. Without clear business logic, the AI will create something that technically works but doesn't actually serve your users' needs.

### 5. Security & Performance (The Safety Systems)

This is about protecting your application and making sure it performs well under real-world conditions.

**What to specify:**
- **Security Measures:** How should data be protected? (e.g., "Use parameterized queries to prevent SQL injection," "Validate and sanitize all incoming user input," "Hash passwords with bcrypt")
- **Error Handling:** What happens when things go wrong? (Define specific error messages for missing fields, invalid data, unauthorized access; implement comprehensive logging)
- **Performance Considerations:** Are there specific performance requirements? (e.g., "Ensure `user_id` column in `recipes` table is indexed for efficient lookups")

**Common Pitfalls for Vibe Coders:** Here's something crucial – many beginner "vibe coders" neglect security and may accidentally push private API keys to public repositories or forget to implement rate limiting, leading to unexpected costs and security breaches. If you want to avoid these issues, you **must** explicitly include requirements for secure credential management (using environment variables) and rate limiting in your AI prompts.

**Why it matters:** A backend that's insecure or slow is a failed backend, regardless of how elegantly the business logic is written. Security and performance aren't optional – they're fundamental requirements.

## Where to Start: Leveraging Your System Design Blueprint

If you're new to backend development or "vibe coding," all these concepts might feel overwhelming. Data modeling, API design, security considerations – where do you even begin defining all these details?

**This is where your `system_design.md` file becomes your best friend!** Remember that file we created earlier in the course, where we had the AI help document your project's architecture? That's your blueprint for everything.

Your `system_design.md` file should contain crucial details about:
- Your chosen **Foundation** (tech stack decisions and why)
- Your **Data Model** (database schemas, relationships, constraints)
- **API Design** (endpoint specifications, request/response formats)
- Initial thoughts on **Business Logic** (core processes, validation rules)
- **Security** considerations (authentication methods, data protection)

**Don't skip the planning step.** Trying to prompt for backend code without this upfront design is like trying to build a complex machine without a schematic. You'll quickly get lost, build something incomplete, or create a system riddled with inconsistencies and security holes.

Before you start prompting for backend code, go back to your `system_design.md` file and extract the necessary information for each of the five pillars. This ensures consistency across your entire application and gives you a solid foundation for your prompts.

## Pro Tips for Backend Prompting

Here are some battle-tested techniques that will make your backend prompting much more effective:

**Security & Cost Prevention:** Beyond just API keys, always prompt the AI to use environment variables for *all* sensitive credentials – database connection strings, JWT secret keys, third-party API keys, everything. Also, explicitly request rate limiting on public-facing endpoints to prevent abuse and manage costs. Trust me, you don't want to wake up to a $500 cloud bill because someone found your API and decided to abuse it.

**Consistent Error Responses:** Ask the AI to implement standardized JSON error responses across all endpoints. Something like `{ "status": "error", "message": "Invalid input", "code": 400 }`. This makes debugging from the frontend much simpler (when things go wrong, you can paste this error message to have AI debug for you) and creates a predictable experience for anyone using your API.

**Logging is Your Friend:** Always ask the AI to include basic logging for critical actions, errors, and incoming requests. When something breaks in production (and it will), good logs are often the difference between fixing an issue in minutes versus hours of detective work.

**Modular Code Structure:** Request the AI to organize code into logical modules or directories – something like `routes/`, `controllers/`, `models/`, `middleware/`, `services/`. This greatly improves readability and maintainability. It also makes your future prompts more effective because you can ask the AI to modify specific components without affecting the entire codebase.

**Database Migrations (for Relational DBs):** If you're using a relational database like PostgreSQL or MySQL, prompt the AI to create database migration scripts. This is crucial for managing changes to your database schema over time in a controlled, reversible way. It's like version control for your database structure.

**Prompt for Tests:** Here's a huge advantage of using AI – it's excellent at generating tests. After creating an endpoint, follow up with something like: "Now, write a comprehensive set of unit tests for this recipe saving endpoint using Jest and Supertest. Include tests for successful saves, validation errors, authentication failures, and edge cases." (Or you may use test-driven development, as described in Lesson 3 where you start with tests.)

**Focus on Single Responsibility:** Prompt for one endpoint or one piece of functionality at a time. This keeps the AI focused and produces cleaner, more modular code. For each file, it's better to have it focus on one thing. It's much easier to debug and iterate on a single, well-defined piece than a massive chunk of interconnected functionality.

**Specify Third-Party Libraries:** If you want to use specific libraries for certain tasks, mention them directly in your prompt. For example, "`jsonwebtoken` for JWT handling," "`pg` for PostgreSQL interactions," or "`express-rate-limit` for rate limiting." This prevents the AI from choosing random alternatives that might not fit your needs. (Using context7 MCP server can provide up-to-date library documentation to AI for accurate usage.)

**Iterate with a REST Client:** Use tools like Postman, Insomnia, or a VSCode extension to test the API endpoints the AI generates. This gives you immediate feedback and helps you craft better follow-up prompts. There's nothing like seeing actual HTTP requests and responses to understand what's working and what needs adjustment.

## Putting It All Together

Here's the core principle: backend prompting is about being the architect. You provide the detailed blueprints (through your system design and specific prompts), and the AI acts as your expert construction crew that handles the technical implementation.

The goal is to be precise about the logic, data structures, and rules so the AI can build a robust, secure, and scalable engine for your application. When you get this right, you'll have a backend that not only works reliably but can also grow and evolve with your application's needs.

Remember – the backend is invisible to your users, but it's the foundation that makes everything else possible. Invest the time to prompt for it properly, and you'll save yourself countless hours of debugging, security issues, and performance problems down the road.
