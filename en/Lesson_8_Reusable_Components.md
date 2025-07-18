# Lesson 8: Creating Reusable Components for AI

[Share on Facebook](https://www.facebook.com/sharer/sharer.php?u=https%3A//github.com/Troyanovsky/vibe-coding-guide/blob/main/en/Lesson_8_Reusable_Components.md) | [Share on Twitter](https://twitter.com/intent/tweet?text=https%3A//github.com/Troyanovsky/vibe-coding-guide/blob/main/en/Lesson_8_Reusable_Components.md) | [Share on LinkedIn](https://www.linkedin.com/shareArticle?mini=true&url=https%3A//twitter.com/intent/tweet?text=https%253A//github.com/Troyanovsky/vibe-coding-guide/blob/main/en/Lesson_8_Reusable_Components.md)


## Why You Need Reusable Components

Here's the thing about working with AI on bigger projects – you'll start noticing patterns. You'll find yourself describing the same button style over and over, explaining the same color scheme repeatedly, or walking the AI through your preferred card layout for the hundredth time. Sound familiar?

This is where reusable components become your best friend. Think of them as your personal design/code system that you can feed to the AI, making your vibe coding sessions way more efficient and consistent.

**Reusable components supercharge your AI workflow in several key ways:**

They ensure rock-solid consistency across your entire prototype. No more getting slightly different button styles every time you ask the AI to add a new feature. Your UI stays cohesive, just like when you're working with traditional design systems in tools like Figma.

They massively speed up development by cutting down on repetitive prompting. Instead of describing your input field styling from scratch every single time, you just reference your template file. The AI knows exactly what you want.

They act as a "mini style guide" for your AI assistant. When you have well-defined components, the AI's output becomes way more predictable. It's like giving your AI collaborator a clear brief about your project's visual language.

Most importantly, they empower you to define your core elements once and reuse them everywhere. This is the DRY principle (Don't Repeat Yourself) applied to AI-assisted development.

## Designing AI-Consumable UI Components

Now, let's talk about actually creating these reusable components. I'll show you three different approaches, depending on your background and comfort level.

### Option 1: Starting with Design Tools (Perfect for Designers)

If you're already comfortable with design tools like Figma, this is your golden path. Start by creating your design system in Figma – use either your existing design system or grab one from the Figma community that matches your vibe.

Here's what you want to collect:
- Common layout patterns (headers, sidebars, content areas)
- Styled buttons in different states (primary, secondary, disabled)
- Form input groups with labels and validation states
- Modal dialogs and alert messages
- Typography scales and spacing tokens

The magic happens when you use Figma's dev mode. Export the code for each component and save them as template files. For example, if you're working with Vue, you'd save them as `input_form_template.vue`, `button_template.vue`, etc. in a template folder.

This approach gives you pixel-perfect components that maintain your design integrity while being ready for AI consumption.

### Option 2: Starting with Vibe Code (Great for Non-Designers)

Don't have Figma skills? No problem. You can build your component library directly through AI, and it's actually pretty straightforward.

Start by finding reference apps that look similar to what you're building. Take screenshots of the UI elements you like, then feed them to your AI assistant. Here's a sample prompt that works really well:

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

The key is to iterate. Preview the results, then prompt the AI to refine until each component looks exactly how you want it. Once you're happy, save each component as a template file.

### Option 3 (Bonus): Copy from Others

This one's a bit of a secret weapon. There's a Chrome extension called "HTML to React & Figma by Magic Patterns" that's perfect for web apps.

Here's how it works: Open up any webpage with components you like, activate the plugin, select the component you want, and it'll extract it into a React component with all the styling intact. Pretty neat, right?

Once you have the React code, you can feed it to your AI assistant and ask it to convert it to whatever framework you're using in your project. Then save it as a template.

This approach is fantastic for getting professional-looking components quickly, especially if you're building something similar to existing popular apps.

## Making Reusable Non-UI Components

Components aren't just about UI elements. You can create templates for any repetitive patterns in your codebase.

Think about API endpoint structures, database query patterns, authentication flows, or error handling approaches. If you find yourself explaining the same logic structure to the AI repeatedly, turn it into a reusable template.

For example, you might create a file with your standard API endpoint structure, complete with error handling, validation, and response formatting. Then you can reference this template whenever you need a new endpoint.

## How to Feed Your Assets & Context to the AI

Now comes the crucial part – actually using these components effectively with your AI assistant.

**In tools like Cursor**, you can directly reference your template files using the `@` symbol. For example, `@input_form_template.vue` will give the AI immediate access to your input form component structure.

**Create a "Project Style Guide"** document (I recommend a markdown file, just like the `requirements.md` file we talked about) that acts as your component catalog. This file should include:
- When to use which template
- Code snippets for common patterns
- General style heuristics and preferences
- References to your template files

Think of this style guide as your project's personality document that you can always tell the AI to reference. It's like having a conversation with a new team member – you're giving them the context they need to work effectively within your project's constraints.

The key is being systematic about it. Don't just create these components and forget about them. Make referencing them a habit in your prompting workflow. The more consistently you use them, the more consistent your AI's output will become.

## Making It All Work Together

Here's where the magic really happens. When you combine well-defined reusable components with the structured workflow we've covered in previous lessons, your AI-assisted coding becomes incredibly powerful.

Your planning documents (requirements.md, system_design.md) define what you're building, your component library defines how it should look and behave, and your prompts become laser-focused on the specific functionality you need.

Instead of starting from scratch every time, you're building on a solid foundation. The AI understands your project's visual language, your code structure preferences, and your quality standards. It's like having a seasoned team member who knows exactly how you like things done.

The result? Faster development, more consistent output, and way less frustration when you need to make changes or add new features. You're not just vibe coding anymore – you're vibe coding with intention and structure.

In our next lesson, we'll dive into testing and debugging with AI, which becomes much easier when you have these reusable components as your foundation.