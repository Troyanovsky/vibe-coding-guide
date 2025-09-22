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

## Lesson 9: Testing, Debugging, and Quality Checks with AI

*   **Why Testing and Quality Checks Matter:**
    *   AI-generated code is powerful but often prone to subtle bugs, inefficiencies, and unexpected behavior.
    *   Testing acts as a safety net, ensuring your application works as expected and looks good.
    *   Debugging with AI provides a constant coding mentor to resolve issues.
*   **Testing Your Prototype:**
    *   **Manual Testing:**
        *   Human interaction: Check layout, colors, fonts, spacing, and responsiveness across devices.
        *   Interact with every element: Click buttons, fill forms, navigate flows.
        *   Actively try to "break" the app by submitting empty forms, double-clicking, or entering invalid data.
    *   **Browser Developer Tools:**
        *   Utilize Console (JavaScript errors), Network (API failures), Elements (inspect HTML/CSS), and Responsive design mode.
        *   Copy red error messages to your AI assistant for help.
    *   **Automated Testing with AI:**
        *   Prompt AI to generate automated end-to-end testing scripts (e.g., Playwright) for repetitive workflows, such as login form validation.
*   **Debugging with Your AI Assistant:**
    *   **Understanding Basic Error Messages:**
        *   `"undefined"`: Variable doesn't exist or isn't set.
        *   `"Syntax error"`: Typo or structural problem in code.
        *   `"TypeError"`: Operation attempted on an incompatible data type.
        *   `"404 Not Found"`: Missing file or API endpoint.
    *   **Effective Debugging Prompts:**
        *   Provide the exact error message from the console.
        *   Include relevant code snippets and file references.
        *   Clearly describe the expected behavior versus what actually happened.
        *   Ask AI to explain specific lines of code or investigate specific issues.
*   **Defining Tests with AI:**
    *   **Manual Test Planning:** Ask AI to describe step-by-step manual testing instructions, including different user flows and edge cases based on requirements.
    *   **Test Case Generation:** Prompt AI to generate comprehensive test cases for specific features or user flows (e.g., happy path, error cases, edge cases, boundary conditions).
    *   **Automated Test Code:** Request AI to generate unit tests (e.g., Jest) for functions, clearly defining expected inputs and outputs.
*   **Basic Code Quality & Review:**
    *   **Common AI Code Issues:** Verbosity, inefficiency, security oversights, and inconsistent coding patterns.
    *   **Quality Review Prompts:**
        *   Ask AI to review code for clarity, readability, adherence to principles like DRY/KISS, performance, simplification, and maintainability.
    *   **Peer Review with AI:** Use multiple AI agents or fresh conversations with the same AI to perform multi-pass code reviews for more robust issue detection.
*   **Advanced: Automated PR Review:**
    *   **AI-Powered Code Review Tools:** Utilize tools like GitHub Copilot, Cursor, or specialized AI review platforms (e.g., CodeRabbit).
    *   **Setting Up Automated Review:** AI can help create checklists for Pull Request reviews and analyze code diffs for potential bugs, performance issues, style consistency, and security vulnerabilities.
*   **Making It All Work Together:**
    *   Combine manual testing, AI-assisted debugging, and quality reviews to build confidence in your prototypes.
    *   Start with basic techniques and gradually incorporate more sophisticated methods.
    *   Leverage your AI assistant by providing context and asking precise questions for effective problem-solving.

## Lesson 10: Pro Tips for AI-Assisted Coding

*   **Why Professional Habits Matter:**
    *   The difference between occasional success and consistent results comes from developing solid workflows and professional habits.
    *   AI makes mistakes and iterates fast, requiring safety nets and systematic approaches.
    *   Professional workflows help you orchestrate AI as a guided collaborator rather than hoping for lucky outcomes.

*   **Version Control with Git: Your Safety Net:**
    *   **Why Git is Crucial for AI Coding:**
        *   AI makes mistakes and can break working code - Git lets you roll back to working states.
        *   AI iterates fast through dozens of versions - Git tracks what actually worked.
        *   Creates safe experimentation environment without fear of losing progress.
    *   **Essential Git Concepts:**
        *   Repository: Your project folder with change tracking superpowers.
        *   Commit: A snapshot/checkpoint of your project at a specific point in time.
        *   Branch: A separate timeline for safe experimentation without affecting main code.
    *   **AI Integration:** Add rules for AI to handle Git operations automatically with descriptive commit messages using format `type: description`.

*   **Workflow Tips That Actually Work:**
    *   **Save & Commit Frequently:** Never be more than a few minutes away from a known-good state, especially when iterating with AI.
    *   **Use Branches for Safe Experimentation:**
        *   Create experimental branches (`git checkout -b experimental-feature`) for trying new approaches.
        *   Let AI experiment wildly in safe sandbox - merge if successful, delete if failed.
        *   No harm done, no time wasted trying to undo changes.
    *   **Make Small Changes & Test Everything:**
        *   Request incremental changes instead of massive overhauls.
        *   Debug one small change rather than debugging complete rewrites.
        *   Test happy path, edge cases, and error conditions thoroughly.
    *   **Learn to Read Code (Just a Little):**
        *   Develop basic pattern recognition to spot user interactions, data handling, and component structure.
        *   Ask AI to create diagrams (Mermaid, sequence) to help understand code architecture.
        *   Better code reading leads to better prompts and feedback.
    *   **Use Linters for Code Quality:** Tools like ESLint and Prettier catch mistakes, enforce consistency, and identify performance issues automatically.
    *   **"Don't Trust, Verify" Principle:** Always test AI-generated code thoroughly - treat it as guilty until proven innocent through professional testing.

*   **Advanced Workflow Techniques:**
    *   **Quick Validation in Separate Folders:**
        *   Test completely new ideas in isolated prototype folders first.
        *   Create `payment-test` or similar folders for testing integrations before main project integration.
        *   Safer approach for testing third-party APIs, new frameworks, or complex algorithms.
    *   **Parallel Development with Multiple Checkouts:**
        *   Maintain multiple local repository copies for simultaneous AI conversations.
        *   Example: `project-main/` (stable), `project-feature-A/` (authentication), `project-feature-B/` (UI experiments).
        *   Each folder allows independent experimentation without interference.

*   **Basic Project Organization:**
    *   **Modular File Structure:**
        *   Organize files logically: `src/components/`, `src/pages/`, `src/utils/`, `src/api/`, `tests/`, `docs/`, `assets/`.
        *   Benefits: Focused AI context, easier debugging, better collaboration, parallel development potential.
    *   **Component Organization:**
        *   Keep reusable components well-organized with clear catalogs.
        *   Document components in README files for both human and AI reference.
        *   Structure: `components/ui/`, `components/forms/` with accompanying documentation.

*   **The "Slot Machine" Approach (Advanced):**
    *   **Philosophy:** AI generates → test → if fails, roll back and regenerate → repeat until working → commit.
    *   **When This Works:**
        *   Unlimited AI usage with no constraints.
        *   Crystal-clear success criteria and requirements.
        *   Automated tests for quick verification.
        *   Well-defined modules with clear interfaces.
    *   **When This Fails:**
        *   Unclear success criteria or requirements.
        *   Interconnected systems where failures cascade.
        *   Learning-focused development where understanding matters.
        *   Limited AI usage quotas or constraints.
    *   **Critical Requirement:** Only effective with automated tests and clear definitions of expected behavior.

*   **Professional AI-Assisted Development Workflow:**
    *   Start with clean Git state and commit existing work.
    *   Create experimental branches for new features.
    *   Use organized project structure to provide clear AI context.
    *   Make small, incremental changes with frequent testing.
    *   Commit frequently when things work.
    *   Test everything thoroughly before considering it complete.
    *   Roll back fearlessly when experiments don't work out.

*   **The Mindset Shift:**
    *   Move from hoping AI gets things right to creating environments where both you and AI do your best work.
    *   Become the architect and director, orchestrating sophisticated development workflows.
    *   Focus on making mistakes recoverable, progress trackable, and success repeatable.
    *   Professional approach gives confidence to tackle bigger, more ambitious projects.

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