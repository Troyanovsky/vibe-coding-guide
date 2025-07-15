## Curriculum (Tentative)

The following curriculum structure for the rest of the lessons is tentative and subject to change. I will update it as I write the actual lessons.

## Lesson 1: Welcome to Vibe Coding

*   **Vibe Coding vs. AI-Assisted Coding:**
    *   **Vibe Coding:** AI writes code without deep understanding from the user; magical when it works, but can lead to being stuck on complex issues.
    *   **AI-Assisted Coding:** Using AI tools to help code while maintaining user understanding and control; focuses on robust and reliable code.
*   **AI Extends Your Ability:** AI is a collaborative tool where you remain in control, making key decisions.
*   **Why it Matters for Non-Coders (PMs/Designers):**
    *   **Rapid Prototyping:** Quickly build working demos for idea validation.
    *   **Better Communication:** Show, don't just tell, your dev teams and stakeholders.
    *   **Quick Technical Feasibility Checks:** Test ideas to inform technical decisions.
    *   **Overcoming Small Roadblocks:** Make minor changes without waiting for dev resources.
    *   **Gradual Learning:** Acquire programming concepts while using AI.
*   **What to Expect from AI Coding:**
    *   AI is a powerful assistant but has limitations (hallucinations, errors, knowledge cut-offs).
    *   "Human-in-the-loop" is essential for judgment, testing, and verification.
    *   Always check AI tool policies regarding data usage, training, and IP.
*   **Course Preview:** Covers AI coding tools, reliable workflows, prompting skills, basic programming concepts, frontend/backend examples, reusable libraries, and testing/debugging with AI.

## Lesson 2: Your AI Coding Toolbelt

*   **AI Chatbots (e.g., ChatGPT, Claude, Gemini, Poe):**
    *   **Pros:** Easily accessible, great for exploratory phases, live preview "Canvas" or "Artifacts" for real-time code rendering.
    *   **Cons:** Limiting for complex projects or native features.
    *   **Use Case:** Messy, exploratory phases and simple prototypes.
*   **Visual, Hosted Platforms (e.g., V0.dev, bolt.new, Figma Make):**
    *   **Pros:** Visually oriented, turn descriptions/sketches into good-looking pages, optimized for visual and deployment.
    *   **Use Case:** Initial "mood board" vibe, "V0" versions, or quick deployments.
*   **Editors and Plugins (e.g., Cursor, Windsurf, Augment Code, GitHub Copilot):**
    *   **Pros:** AI power integrated into common coding environments (VSCode forks/plugins), seamless transition.
    *   **Cursor:** VSCode fork with built-in AI capabilities, good for applying diffs and predictive edits.
    *   **Use Case:** Core development work, for both beginners and experienced developers.
*   **CLI Tools (e.g., Claude Code, Aider, Gemini Cli):**
    *   **Pros:** Work directly within the terminal, understand entire projects (not just files), powerful for real development.
    *   **Use Case:** Experienced users who prefer terminal workflow, complex project management.
*   **Recommendations:**
    *   Start with chat interfaces for ideation.
    *   Use UI generators for quick visual progress.
    *   Move to CLI tools or editors for serious implementation and iteration.
    *   **Recommended Starting Tool:** Cursor (approachable yet powerful, gentle learning curve).
*   **Setting Up Your Coding Environment (using Cursor as example):**
    *   **Choosing AI Models:** Select models for different purposes:
        *   **Thinking model:** For planning and architecture (e.g., o3, Claude 4 Opus).
        *   **Long-context model:** For large codebases (e.g., Gemini 2.5 Pro/Flash).
        *   **Workhorse coding models:** For day-to-day coding (e.g., Claude 3.7/4 Sonnet, GPT4.1).
    *   **MCP (Model Context Protocol):** Extend AI capabilities with tools like `context7` (up-to-date documentation) and `Sequential Thinking` (step-by-step problem-solving).
    *   **Rules for AI (.cursor/rules or CLAUDE.md):** An instruction manual for AI behavior, defining workflow, code quality, structure, naming, security, and documentation. Helps AI think carefully and produce better solutions.

## Lesson 3: AI-Assisted Coding Workflow

*   **Structured Workflow is Key:** Go beyond random prompting; a roadmap helps keep you and AI on track.
*   **Step 1: Define & Plan:**
    *   **Write Clear Product Requirements:** Detail user stories and key features (e.g., "As a home cook, I want to..."). Specificity prevents guesswork.
    *   **Vibe-PMing with AI:** Use AI to refine product requirements, explore user flows, and identify edge cases. Save as `requirements.md`.
*   **Step 2: AI-Assisted Technical Design & Planning:**
    *   **System Design and Architecture:** Ask AI to suggest technical architecture based on requirements. Provide context (platform, purpose, features). Generate `system_design.md`.
    *   **AI Task Breakdown:** Have AI break down the system design into prioritized, dependent implementation tasks. Generate `todo_list.md`.
*   **Step 3: "Coding" - The Iterative Prompting & Generation Phase:**
    *   **Referencing Planning Documents:** Use specific, contextual prompts referencing `requirements.md`, `system_design.md`, and `todo_list.md`.
    *   **One Task at a Time:** Focus on single, specific goals for the AI.
    *   **Power of Context:** AI makes better decisions with referenced planning documents.
*   **Other Common AI-Assisted Workflows:**
    *   **Explore, Plan, Code, Commit:** Standard iterative cycle with frequent Git commits.
    *   **Test-Driven AI Development (TDD):** AI generates tests first, then code that passes those tests.
    *   **Visual Iteration:** Use visual aids (wireframes, screenshots) for UI-heavy projects; refine with visual feedback.
    *   **Safe YOLO (Experimentation Branching):** Use temporary Git branches for risk-free experimentation.
*   **Workflow is Your Friend:** It's about structured collaboration, where you provide direction and context, and AI provides speed and technical knowledge.
*   **BONUS: Git Basics for AI-Assisted Coding:**
    *   **Essential Commands:** `git init`, `git add .`, `git commit`, `git checkout -b`, `git branch -D`, `git status`, `git log`, `git checkout HEAD~1`, `git reset --hard`.
    *   **Why Git Matters:** Checkpoint saves, experimentation freedom, change tracking, collaboration.

## Lesson 4: Effective Prompting

*   **Prompting as Management:** Provide context, set clear expectations, define constraints, and guide the AI.
*   **What Makes a Prompt Effective:**
    *   **Clarity & Specificity:** Be precise in your requests (e.g., specific form fields, validation, frameworks).
    *   **Context & Priorities:** Reference planning documents (`requirements.md`, `system_design.md`). State priorities like performance or mobile-first.
    *   **Constraints:** Explicitly define boundaries to prevent over-optimization (e.g., "Change only the button component," "Don't add new components").
    *   **Desired Output:** Specify the format (e.g., "complete HTML file," "just the JavaScript function," "step-by-step plan").
*   **Iterative Prompting & Conversation Context:**
    *   **Conversation, not One-Shot:** Start slow, course correct early.
    *   **Follow-Up Questions:** Build functionality iteratively with subsequent prompts.
    *   **Know When to Start Fresh:** Avoid "context pollution" by starting new conversations when the AI gets confused.
    *   **Cloudflare's Pattern:** "You did X, but we should do Y. Please fix." (Direct, contextual, actionable feedback).
*   **Advanced Prompting Tactics:**
    *   **Few-Shot Prompting:** Show examples of desired code or style (e.g., `@card_example.vue`).
    *   **Ask for Alternatives:** Have AI generate multiple approaches.
    *   **Plan Before Action:** Request a plan (files to modify, order) before code generation.
    *   **Treat Prompts as Documentation:** Include key prompts in commit messages or project docs for future reference.
    *   **A Picture's Worth a Thousand Words:** Use images (screenshots, mockups, wireframes) for visual context.
*   **Making It All Work Together:** Combine clear requirements, specific prompts, iterative conversation, and context to achieve powerful AI-assisted coding.

## Lesson 5: Understanding Code

*   **Why Understanding Code Matters:** Enables better questions, spotting AI errors, understanding AI output, and making smarter decisions, even if you don't write it yourself.
*   **What is Code?**
    *   Code is **instructions** for a computer, like a recipe.
    *   Different "languages" (JavaScript, Swift, Python) are optimized for different tasks.
*   **Frontend vs. Backend:**
    *   **Frontend (The "Storefront"):** Everything users see and interact with.
        *   **HTML:** Defines structure (the nouns).
        *   **CSS:** Defines styling (the adjectives) – vanilla CSS or utility-first frameworks like Tailwind CSS.
        *   **JavaScript:** Defines behavior/interactivity (the verbs) – often with frameworks like React, Vue, Angular.
        *   **Beyond Web:** Mobile apps (SwiftUI, Flutter) follow similar concepts of structure, styling, behavior.
    *   **Backend (The "Warehouse & Office"):** Everything behind the scenes – business logic and data.
        *   **Databases:** Store information (relational SQL vs. non-relational MongoDB).
        *   **Server-Side Logic:** Processes requests, manages data (Node.js/Express, Python/Django).
        *   **Cloud Functions/Serverless:** Rent specific services for logic instead of managing servers.
*   **APIs (Application Programming Interfaces):** How different software parts communicate, like a menu for data requests.
*   **The Magic of Modular, Decoupled Code:**
    *   Like LEGO blocks, allowing independent modification and reuse.
    *   Prevents "spaghetti code" where changes in one area break others.
    *   Crucial for effective AI collaboration: AI can modify specific parts, easier debugging, better testing.
    *   My workflow and AI rules promote modular design with "separation of concerns."

## Lesson 6: Prompting for Frontend

*   **Frontend Focus:** UI and user experience are paramount; prompts must be incredibly specific about visual and interactive details.
*   **Good vs. Bad Prompt Example:**
    *   **Bad:** Vague ("screen with step count") – AI has to guess everything.
    *   **Good:** Detailed ("iOS SwiftUI pedometer home screen," specifying display, components, data, navigation, fonts, icons).
*   **The Five Pillars of Great Frontend Prompts:**
    *   **1. Foundation (Tech Stack):** Platform (iOS, web), framework (SwiftUI, React), key libraries (shadcn/ui, Bulma).
    *   **2. Layout & Structure (Bones):** Visual hierarchy, placement (rows, columns), specific components (progress bar, tabs).
    *   **3. Data & State (Brains):** Data to display, data sources (API, sensors), edge cases (loading, error, no data).
    *   **4. Interaction & Feel (Soul):** Interactivity (tap, swipe), behavior/animation (real-time updates, transitions), accessibility.
    *   **5. Aesthetics (Paint Job):** Branding (color palette), typography (specific fonts), iconography (SF Symbols, custom icons).
*   **Pro Tips for Frontend Prompting:**
    *   **Use Planning Documents:** Reference `requirements.md`, `system_design.md`, `todo_list.md`.
    *   **Prompt Iteratively:** Refine in steps, leveraging live preview.
    *   **Try Different Vibes:** Experiment with multiple AI-generated versions.
    *   **Reference Well-Known Apps:** Use examples like "Instagram story interface" for context.
    *   **Use Visual Aids:** Provide screenshots, wireframes, or Figma mockups.
    *   **Leverage Component Libraries:** Mention established libraries or build your own.

## Lesson 7: Prompting for Backend

*   **Backend Focus:** Logic, data, and performance, analogous to a restaurant's kitchen and operations. Prompts need to specify "how."
*   **Good vs. Bad Prompt Example:**
    *   **Bad:** Vague ("users can save recipes") – AI makes too many assumptions (database, language, authentication).
    *   **Good:** Concise and specific ("Node.js/Express REST API for authenticated users to save/retrieve recipes from PostgreSQL, schema and endpoints defined in `@system_design.md`").
*   **The Pillars of Great Backend Prompts:**
    *   **1. Foundation (Engine & Fuel):** Language/runtime (Node.js, Python), framework (Express, Django), database (PostgreSQL, MongoDB).
    *   **2. Data Model (Blueprint for Data):** Schema definition (tables/collections), fields & types, relationships & constraints.
    *   **3. API Design (Control Panel):** Endpoints, HTTP methods (GET, POST), request/response shape (JSON), status codes.
    *   **4. Business Logic (Rules of the Game):** Core processes (link to user ID), data validation, authentication/authorization (JWT, API keys).
    *   **5. Security & Performance (Safety Systems):** Security measures (SQL injection prevention, password hashing), error handling (logging, specific messages), performance considerations (indexing).
        *   **Common Pitfalls:** Beginner "vibe coders" often neglect security (API keys in public repos) and cost management (rate limiting). Explicitly prompt for environment variables and rate limiting.
*   **Leveraging Your System Design Blueprint (`system_design.md`):** This file should contain crucial details for all five pillars, providing the necessary context for backend prompts. Don't skip this planning step.
*   **Pro Tips for Backend Prompting:**
    *   **Security & Cost Prevention:** Environment variables for all sensitive data; explicit rate limiting.
    *   **Consistent Error Responses:** Standardized JSON error formats for easier debugging.
    *   **Logging:** Include basic logging for critical actions and errors.
    *   **Modular Code Structure:** Request logical organization (routes/, models/, etc.) for readability and maintainability.
    *   **Database Migrations:** If using relational DBs, prompt for migration scripts.
    *   **Prompt for Tests:** Ask AI to generate comprehensive unit tests (e.g., using Jest, Supertest).
    *   **Focus on Single Responsibility:** One endpoint or functionality at a time for cleaner code.
    *   **Specify Third-Party Libraries:** Mention desired libraries (e.g., `jsonwebtoken`, `pg`).
    *   **Iterate with a REST Client:** Test generated APIs with tools like Postman for immediate feedback.

## Lesson 8: Creating Reusable Components for AI

*   **Why Reusable Components?**
    *   Ensures consistency across larger projects/prototypes.
    *   Speeds up development by reducing repetitive prompting.
    *   Acts as a "mini style guide" for the AI assistant, leading to predictable output.
    *   Applies the DRY (Don't Repeat Yourself) principle to AI-assisted development.
*   **Designing AI-Consumable UI Components:**
    *   **Option 1: Starting with Design Tools (for Designers):**
        *   Create design system in Figma (layouts, buttons, forms, modals, typography).
        *   Export code for each component from Figma's dev mode and save as template files (e.g., `input_form_template.vue`).
    *   **Option 2: Starting with Vibe Code (for Non-Designers):**
        *   Find reference apps, take screenshots of UI elements.
        *   Prompt AI to build a component library based on screenshots (specifying framework, styling, responsiveness, accessibility, props).
        *   Iterate and refine until components meet desired look/feel. Save as template files.
    *   **Option 3 (Bonus): Copy from Others:**
        *   Use tools like "HTML to React & Figma by Magic Patterns" to extract components from live webpages.
        *   Feed extracted code to AI to convert to your project's framework, then save as a template.
*   **Making Reusable Non-UI Components:**
    *   Create templates for repetitive code patterns like API endpoint structures, database queries, authentication flows, or error handling.
    *   Reference these templates for consistent logic and structure.
*   **How to Feed Your Assets & Context to the AI:**
    *   **Direct Referencing:** Use `@` in tools like Cursor to reference template files (e.g., `@input_form_template.vue`).
    *   **Project Style Guide:** Create a markdown file (like `requirements.md`) as a component catalog. Include usage guidelines, code snippets, general preferences, and template references.
    *   **Consistency is Key:** Make referencing templates a habit in your prompting workflow.
*   **Making It All Work Together:**
    *   Combining reusable components with structured workflow (planning documents) leads to powerful AI-assisted coding.
    *   AI understands your project's visual language, code structure, and quality standards.
    *   Results in faster development, consistent output, and easier maintenance.

**Module 9: Testing, Debugging, and Quality Checks with AI**
*   *Crucial for ensuring AI output is functional and as expected.*
*   **9.1. Basic Testing Your Prototype:**
    *   Manual Testing: Does it look right? Does it work as expected on different screen sizes (if responsive)? Click all buttons, fill forms.
    *   Use browser developer tools (Inspect Element) for simple visual checks and error spotting.
*   **9.2. Debugging with Your AI Assistant:**
    *   Understanding (basic) error messages: What does "undefined" or "syntax error" generally mean?
    *   **Prompting for Debugging:**
        *   "I'm getting this error in the console: `[paste error message]`. Here's the relevant code: `[paste code snippet]`. Can you help me find the issue?"
        *   "When I click the 'Submit' button, nothing happens. Here's the HTML for the button and the JavaScript function it's supposed to call. What could be wrong?"
    *   Asking AI to explain code or errors: "Explain this line of JavaScript," "Why am I getting this 'TypeError'?"
*   **9.3. Defining Tests with AI:**
    *   While human-written tests are preferred for production code, you can use AI to *help* define tests for your prototype.
    *   Articulate your expectations and specific test cases in natural language to the AI.
    *   **Prompting for Tests:** "I have a form with an email input field and a submit button. I want to test that an error message appears if the email is invalid when I click submit. Describe the steps to manually test this." or "Based on the requirements for the product card, what are some key things I should test to ensure it's working correctly?"
    *   You can also ask the AI to generate simple test code snippets if you're comfortable using a testing framework (though this is more advanced). Clearly define the expected input and output.
*   **9.4. Basic Code Quality & Review (with AI help):**
    *   Awareness: AI code can sometimes be verbose, inefficient, or have minor security oversights.
    *   Asking AI: "Can you review this code for clarity?" "Are there any obvious performance issues here?" "Suggest improvements to make this JavaScript more readable." (Set realistic expectations).
    *   Ask the AI to generate simple, maintainable code, prioritizing functions over complex class hierarchies or deep inheritance when possible. [reference](https://lucumr.pocoo.org/2025/6/12/agentic-coding/)
    *   Ask the AI to refactor existing code for improved readability, maintainability, or efficiency.
    *   **Peer Review with AI (Advanced):** In workflows with multiple AI instances, consider using one AI agent to generate code and another to perform a review or verification pass on the generated code. [reference](https://www.anthropic.com/engineering/claude-code-best-practices)
*   **9.5. Automated PR Review with AI Tools:**
    *   Some advanced AI coding tools (like Cursor, or potentially future integrations with tools like GitHub Copilot or specialized code review AI) can assist in reviewing Pull Requests.
    *   These tools can highlight potential bugs, suggest improvements, check for style consistency, and identify security vulnerabilities *based on the context of the code change*.
    *   **Note:** This is a more advanced use case typically found in collaborative engineering environments. It's an emerging area of AI in coding workflows.

**Module 10: Pro Tips for AI-Assisted Coding**
*   **10.1. Version Control with Git (Conceptual Introduction):**
    *   Why it's essential: Tracking changes, a "safety net" (undo mistakes), collaboration basics.
    *   Analogy: Saving multiple versions of a design file, but more powerful.
    *   Basic terms (simplified): Repository (your project folder), Commit (saving a snapshot of changes).
    *   How AI tools might help: Some AI IDEs (like Cursor) have built-in Git integration.
*   **10.2. Workflow Tips for AI-Assisted Projects:**
    *   **Save & Commit Frequently:** Especially when iterating with AI.
    *   **Use Git Branches for Experimentation:** Create a new branch (`git checkout -b my-new-feature`) for quick testing of new features or ideas suggested by the AI. If it works, merge it in; if not, throw the branch away (`git branch -D my-new-feature`). This provides a safe sandbox.
    *   **Make Small Changes & Test:** Easier to pinpoint issues.
    *   Break Down Complex Tasks (reinforces prompting strategy).
    *   Learn to Read (a little) Code: Helps verify AI output and refine prompts.
    *   **Use a Linter for Code Style:** Tools like linters (e.g., ESLint for JavaScript, Prettier for formatting) help enforce consistent code style, readability, and identify potential issues like function complexity or excessive lines of code. AI can often generate code that adheres to common linting rules if asked.
    *   **Don't Trust, Verify:** *Always* test AI-generated code thoroughly.
    *   **Quick Validation in a New Folder:** For completely new ideas or isolated components, quickly generate the code in a separate folder outside your main project. If it works, you can then carefully integrate it.
    *   When designing tasks for AI, consider if they can be broken down into parallelizable units to improve efficiency, especially in multi-agent or multi-checkout environments. [reference](https://lucumr.pocoo.org/2025/6/12/agentic-coding/)
    *   For complex projects or parallel exploration, consider having multiple local checkouts (clones) of your repository to allow different AI conversations or experiments to run concurrently without interfering with each other. [reference](https://www.anthropic.com/engineering/claude-code-best-practices)
*   **10.3. Basic Project Organization:**
    *   Simple file/folder structure (e.g., `index.html`, `css/style.css`, `js/script.js`, `images/`).
    *   Keeping reusable components/snippets organized.
*   **10.4. Advanced Tip: Maximizing Request-Based Tools with User Input Utilities:**
    *   **The Challenge:** When using chat-based AI tools (ChatGPT, Claude), you often need to manually copy/paste code snippets, error messages, or file contents back and forth.
    *   **The Solution:** Create a simple "AI Helper" tool or use browser extensions that can:
        *   Quickly capture and format code snippets for AI consumption
        *   Auto-generate context-rich prompts with file contents
        *   Format error messages with relevant code context
        *   Save and organize your most effective prompts for reuse
    *   **Example Workflow Enhancement:**
        *   Instead of manually copying 5 files to show the AI your project structure, use a tool that generates: "Here's my current project structure: [auto-formatted file tree with key code snippets]"
        *   Create templates like: "Debug this error: [auto-captured error] in file [auto-detected file] at line [auto-detected line] with context: [surrounding code]"
    *   **DIY Approach:** Create a simple HTML tool with text areas and buttons that help format your AI requests consistently.
*   **10.5. A Different Approach by Claude Code team (and others):**
    *   Useful when you have **unlimited** usage of agents.
    *   Treat it like a slot machine: Run agent, then test, if fails just roll back to earlier check point and run again, instead of wrestling with it to debug and fix.
    *   **Reference:**
        *   https://monadical.com/posts/vibe-code-how-to-stay-in-control.html
        *   https://www-cdn.anthropic.com/58284b19e702b49db9302d5b6f135ad8871e7658.pdf
    *   **Important Note:** This approach is most effective when you have a clear definition of the module's expected behavior and automated tests in place. In such a scenario, you can trust the AI to handle the inner implementation details as long as it passes the tests. However, if you lack clear requirements or tests, this approach will likely lead to unreliable and broken code.

**Module 11: Hands-On Project: Build Your AI-Powered Prototype**
*   *This module is the culmination, applying all learned skills. Allocate significant time.*
*   **11.1. Project Introduction & Planning:**
    *   Define a simple project (e.g., a portfolio landing page, a recipe browser, a simple to-do list).
    *   Sketch out the UI/UX, define key features.
    *   Identify potential reusable components (from Module 8) to create or adapt.
    *   Break down the project into AI-promptable steps (leveraging AI for task breakdown as in Module 3).
*   **11.2. Guided Build using AI Tool(s):**
    *   Phase 1: Generate HTML structure for all pages/main sections.
    *   Phase 2: Apply CSS styling (using Tailwind or other methods via AI prompts), incorporating reusable styles/components.
    *   Phase 3: Add JavaScript for interactivity (event listeners, basic DOM manipulation).
    *   Continuously use prompt engineering techniques, iterative refinement, and your reusable assets. Referencing your planning documents is key.
*   **11.3. Testing and Debugging Your Project (with AI):** Apply techniques from Module 9.
*   **11.4. (Optional but Recommended) Sharing Your Project:**
    *   Simple deployment methods (e.g., Netlify Drop, GitHub Pages, Vercel) to experience the full cycle and share your creation.

**Module 12: Advanced Context Awareness: Leveraging Model Context Protocol (MCP)**
*   **12.1. What is MCP?** (Simplified): A way for AI tools to have a deeper understanding of your entire project's context, including files, code structures, and even documentation.
*   **12.2. How Tools Like Cursor Implement This:** Using special commands or symbols (e.g., `@` mentioning files, `@` for symbols/functions within your codebase, or even `@docs` to reference documentation).
    *   Explicitly mentioning files or directories you want the AI to consider (e.g., `@filename.js` or `src/components/`) helps the AI focus its context. [reference](https://www.anthropic.com/engineering/claude-code-best-practices)
*   **12.3. Benefits:**
    *   Highly contextual and accurate prompts: AI "knows" what `utils/helpers.js` contains.
    *   More precise code generation, modification, and refactoring.
    *   Efficient debugging: "In `@shoppingCart.js`, why is the `calculateTotal` function returning NaN? Here's the related `@productData.json`."
*   **12.4. Example Prompts (conceptual, assuming a tool like Cursor):**
    *   "Refactor the `renderUserProfile` function in `@components/UserProfile.js` to use the new `Avatar` component located in `@components/Avatar.js`."
    *   "Explain the purpose of the `useAuth` hook in `@hooks/auth.js`."
    *   "Find all usages of the `@Button` component throughout this project and list the files."
*   **12.5. Note:** This is often tool-specific and represents a more advanced way to interact with AI coding assistants, offering greater control for those comfortable with it.

**Module 13: Beyond the Basics: Evolving with AI**
*   **13.1. Recap of Vibe Coding & AI Assistance: Key Takeaways.**
*   **13.2. Knowing When to Go Deeper or Ask for Expert Help:**
    *   When your AI-assisted prototype hits functional or complexity limits.
    *   How to effectively communicate your AI-assisted work and its foundations to engineering teams.
    *   Understanding when it's time to transition to human-written, production-grade code or involve specialist developers.
*   **13.3. Continuing Your Journey:**
    *   Exploring more advanced features of your chosen AI tools.
    *   Dipping into foundational coding concepts (HTML, CSS, JS) if interest is sparked.
    *   Online communities and resources for AI-assisted development.
*   **13.4. The Evolving Landscape of AI in Development: Stay Curious!**