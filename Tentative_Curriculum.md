## Curriculum (Tentative)

The following curriculum structure for the rest of the lessons is tentative and subject to change. I will update it as I write the actual lessons.

**Lesson 8: Reusable Components**
*   **Why Reusable Assets Supercharge AI-assisted coding/vibe coding**
    *   Ensures consistency in UI/UX across your prototype.
    *   Fosters visual consistency and cohesion across your project, just as with traditional design systems. [reference](https://www.figma.com/blog/8-ways-to-build-with-figma-make/)
    *   Speeds up development by reducing repetitive prompting details in text.
    *   Acts as a "mini style guide" for the AI, leading to more predictable output.
    *   Empowers you to define core elements once and reuse them.
*   **Designing AI-Consumable UI Components:**
    *   Option 1: Starting with design tools
        *   Ideal for designers. Start your design in Figma. Use your own design system or a community design system.
        *   Arrange commonly used components, like common layout, styled buttons, form input groups, modals, alert messages, font, spacing, etc.
        *   Use Figma's dev mode, export the code, and save to files like `input_form_template.vue` (just an example if you're using Vue)
    *   Option 2: Starting with vibe code
        *   Ideal for non-designers who are not familiar with Figma.
        *   Find references of the app that's similar to yours. Feed the screenshot to AI, ask it to replicate.
        *   Preview the result and iteratively prompt the AI to make it exactly how you like it. Save to files as a template.
        *   Example prompt:
```
Help me build a Vue component library based on the attached screenshot, using Vue 3 and Tailwind CSS. Follow the steps below:

1. Analyze the screenshot and identify distinct UI elements, such as:
- Buttons
- Input fields
- Navbars
- Cards
- Modals
- Typography

2. For each component:
- Create a Vue single-file component (.vue)
- Style using Tailwind CSS, matching the screenshot as closely as possible
- Ensure responsiveness and accessibility
- Add props for flexibility
- Include a brief comment explaining the component

3. Save all components in the templates/ folder.

4. Create an index page that imports and displays each component with example usage.

Note: Use only custom-made components and Tailwind CSS. Do not use external UI libraries. Prioritize reusability and clean structure.
```
    *   Option 3 (Bonus): Copy from others
        *   Use "HTML to React & Figma by Magic Patterns" chrome extension. best for web apps.
        *   Open up a webpage, activate the plugin, select a component, and it will extract it into a React component with the style you need.
        *   Feed the code to AI to convert to the language you're using in your project. Save as template.
*   **Making Reusable non-UI Components:**
    *   Similarly, you can create templates/best practices of non-UI components.
*   **How to Feed Your Assets & Context to the AI:**
    *   In tools like Cursor, you can directly reference files (`@input_form_template.vue`).
    *   Creating a simple "Project Style Guide" document (markdown file) with component descriptions and telling the AI to refer to it. This file can include when to refer to which template file or snippets in this file or general style heuristics. [reference](https://www.anthropic.com/engineering/claude-code-best-practices)


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