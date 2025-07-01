# Lesson 3: AI-Assisted Coding Workflow

[Share on Facebook](https://www.facebook.com/sharer/sharer.php?u=https%3A//github.com/Troyanovsky/vibe-coding-guide/blob/main/en/Lesson_3_Workflow.md) | [Share on Twitter](https://twitter.com/intent/tweet?text=https%3A//github.com/Troyanovsky/vibe-coding-guide/blob/main/en/Lesson_3_Workflow.md) | [Share on LinkedIn](https://www.linkedin.com/shareArticle?mini=true&url=https%3A//twitter.com/intent/tweet?text=https%253A//github.com/Troyanovsky/vibe-coding-guide/blob/main/en/Lesson_3_Workflow.md)

## Going Beyond Random Prompting

So you've experimented with AI coding tools and maybe built a few small projects. That's awesome! But if you're like most people, you've probably hit that wall where your prompts start feeling random, the AI gets confused about what you're building, and everything becomes a mess.

Here's the thing: successful AI-assisted development isn't about finding the perfect prompt. It's about having a **structured workflow** that keeps both you and the AI on track. Think of it like having a roadmap for a road trip -- you could just start driving and hope for the best, but you'll get much better results with some planning.

The workflow I'm about to show you works whether you're a product manager who's never touched code or an engineer who has programming experience. It's flexible, and you can just take the core idea and adapt it to your needs.

## Step 1: Define & Plan

### Write Clear Product Requirements

Before the AI writes down any line of code, you need to know what you're building. This sounds obvious, but most people skip this step and wonder why the AI keeps building the wrong thing.

Start by writing down your **user stories** and **key features** in detail. Don't just say, "I want a recipe app." Instead, write something like:

> "As a home cook, I want to search for recipes by ingredients I have at home, so I can decide what to cook without going to the store. The app should let me input ingredients, show matching recipes with photos, and save my favorites."

(This is already a simplified version. If you can be more specific, that would be great!)

Be specific about what you want the AI to build. The more detail you provide upfront, the less back-and-forth you'll need later.

### Vibe-PMing with AI

If you're a product manager like me, I guess you're pretty comfortable with writing a PRD (product requirement document). But if you don't have the skills, don't worry. You can use AI to help you.

If you're just can't clearly lay out what you want to build. You can actually use AI to help you **refine your own product requirements**. I would call it "vibe-PMing" -- having the AI act as your product manager.

You can do this step in your AI chat interface and not necessarily in the AI coding tools. Start a conversation with your AI and say something like: "I want to build a recipe app where users can search by ingredients. Help me think through the user flows and potential edge cases. Make sure to ask me questions to clarify."

The AI might come back with questions like:
- "What happens if a user searches for an ingredient that's not in your database?"
- "Should users be able to filter by dietary restrictions?"
- "How do you handle recipe variations or substitutions?"

Have this conversation over multiple rounds. Add any requirements or ideas that come into your mind. Let the AI challenge your assumptions and suggest features you hadn't thought of. Once you're happy with the direction, ask the AI to summarize everything into a clean `requirements.md` document and save it to your project folder.

This document becomes your north star -- both for you and for the AI in later steps.

## Step 2: AI-Assisted Technical Design & Planning

### System Design and Architecture

Now that you know *what* you're building, it's time to figure out *how* to build it. Even if you're not technical, this step is crucial because it gives the AI a framework to work within.

Ask your AI to suggest a technical architecture based on your requirements. For example: "Based on the requirements in `requirements.md`, suggest a basic architecture for this recipe website, including frontend structure and potential backend needs."

Give the AI as much context as possible:
- Project overview from your requirements
- Platform specification (web app, mobile, etc.)
- Purpose and main use cases
- Core features list...

If your AI tool has different modes or roles (like "architect mode" in Roo Clide), use that. Have the AI generate a `system_design.md` document that outlines the overall structure, main components, and how they'll work together.

Or if the AI tool doesn't have such a mode, you can try this prompt:

```
1.  **Understand Requirements:**
    *   Deep dive into product needs, user stories, edge cases, and non-functional requirements. 
    *   Confirm and discuss with the user.
2.  **High-Level Design & Tech Stack:**
    *   Define overall architecture and select core tech stack.
    *   Explain the pros and cons and make your recommendation.
3.  **Detailed Design:**
    *   **Component Design:** Define individual components and their responsibilities (SRP).
    *   **Data Structure Design:** Model data, schemas, and relationships.
    *   **Flow Design:** Map data and control flows between components (interactions, delegations, error handling).
4.  **Define Standards & Tooling:**
    *   Establish code style, linting rules, and directory structure.
    *   Plan logging strategy (levels, format, storage).
    *   Outline testing strategy (unit, integration, E2E) and tools.
    *   Consider version control and dependency management.
5.  **Document Your Design:**
    *   Make sure you create a `/doc` folder that includes a markdown file of your design.
```

You don't need to understand every technical detail, but having this roadmap prevents the AI from making random architectural decisions on the fly later when actually coding.

### AI Task Breakdown

Large projects feel overwhelming, but every complex app is just a collection of smaller, manageable pieces (modularity and decoupling are some good practices). You can ask the AI to break down your system design into step-by-step implementation tasks. This works well, especially with thinking models like GPT o3, Claude 4 Opus, or Gemini 2.5 Pro.

Reference both your `requirements.md` and `system_design.md` and ask the AI: "Break this down into specific implementation tasks, ordered by priority and dependencies."

Some AI coding tools already include task management features like checklists or scratch pads. If not, have the AI generate a `todo_list.md` file that you can reference throughout development.

## 3.3. Step 3: "Coding" - The Iterative Prompting & Generation Phase

### Referencing Planning Documents

Here's where your upfront planning pays off. Instead of random prompts like "make a recipe app," you now have specific, contextual requests like: "Looking at `requirements.md` and `system_design.md`, implement task #1 from `todo_list.md`: Set up the basic HTML structure and navigation."

**Do ONE task at a time.** This is crucial. Don't try to build everything in one massive prompt. The AI works best when it has a focused, specific goal.

After each successful task, save your progress (preferably with git commits, though many tools have automatic checkpoints). If something goes wrong, you can easily revert to the last working state.

### The Power of Context

When prompting for specific components, always reference your planning documents when possible. The AI can then make decisions that align with your overall vision instead of just guessing what you want.

For example: "Based on the user flow number 1 described in `requirements.md`, create the ingredient search component outlined in `system_design.md` using recipe_search_component.vue as style reference. This should handle the edge cases we discussed around missing ingredients."

## 3.4. Other Common AI-Assisted Workflows

Of course, my workflow is just one way to work with AI. There are many other workflows you can try, depending on your needs and the tools you have. Here are some examples from [Claude Code](https://www.anthropic.com/engineering/claude-code-best-practices) and other tools:


### Explore, Plan, Code, Commit

This is the standard cycle we just walked through: define requirements, plan with AI, generate code, and commit your progress. It's simple but effective for most projects. Remember to commit your progress after successfully completing a task and testing to avoid losing your work. If the AI messes up something later, you still have a chance to revert to the last working state.

### Test-Driven AI Development

If you care more about the generated code working exactly as you want, you may try Test-Driven Development (TDD).

You can first clearly describe the behavior or input/output you want from your program, then ask the AI to generate tests from that. After the tests are generated, you can ask the AI to generate the code that passes those tests.

The AI can run the tests while developing to pinpoint what goes wrong and fix it.

This approach helps catch bugs early and ensures your code actually does what you think it does.

### Visual Iteration

For UI-heavy projects, you can prepare a lot of visual aids for the AI, like wireframes, UI designs, or screenshots, so that the AI can generate code that matches what's in your mind.

And when developing, you can generate code, preview the result, and then use visual feedback to refine your next prompt. Screenshots can be incredibly powerful context for the AI: "The layout looks good, but the button covers the text. Can you move it up?"

### Safe YOLO (Experimentation Branching)

Sometimes you want to experiment with a completely different approach without risking your working code. Create a temporary git branch (`git checkout -b experimental-feature`), then go wild with the AI generation. If it works, great -- merge it back. If not, just delete the branch (`git branch -D experimental-feature`) and you're back to safety. You may even generate multiple experimental branches and compare them side by side to see which one works best.

This gives you the best of both worlds: the ability to experiment freely while maintaining a stable codebase.

## Workflow is Your Friend

The key insight here is that successful AI-assisted development isn't about finding magical prompts. It's about **structured collaboration** between you and the AI. You provide direction, context, and quality control. The AI provides implementation speed and technical knowledge.

It's the same as working with a human developer. You don't just throw a vague idea over the fence and hope they get it right. You have a conversation, define requirements, and then work together to build something great.

When you follow this workflow, you'll find that the AI stays focused, makes fewer mistakes, and builds exactly what you had in mind. Plus, you'll actually understand what you're building instead of just hoping the AI got it right.

## BONUS: Git Basics for AI-Assisted Coding

Throughout this lesson, I've mentioned using Git to save your progress and experiment safely. If you're new to Git, here's a minimal primer to get you started (Tip: You can also ask your AI assistant for these commands):

### Essential Git Commands

**Setting up a new project:**
```bash
git init                    # Initialize a new Git repository
git add .                   # Stage all files for commit
git commit -m "Initial commit"  # Save your first snapshot
```

**The basic workflow after each AI task:**
```bash
git add .                   # Stage your changes
git commit -m "Add ingredient search component"  # Save with descriptive message
```

**Safe experimentation (in Safe YOLO):**
```bash
git checkout -b experiment-new-ui  # Create and switch to experimental branch
# ... let AI generate experimental code ...
git checkout main           # Switch back to main branch
git branch -D experiment-new-ui  # Delete experimental branch if not needed
```

**When things go wrong:**
```bash
git status                  # See what files have changed
git log --oneline          # See your commit history
git checkout HEAD~1 -- filename.js  # Restore specific file from previous commit
git reset --hard HEAD~1    # Go back to previous commit (careful - loses changes!)
```

### Why Git Matters for AI Coding

- **Checkpoint saves**: After each successful AI task, commit your progress. This gives you safe restore points.
- **Experimentation freedom**: Try wild AI ideas on branches without breaking your working code.
- **Change tracking**: See exactly what the AI changed in each iteration.
- **Collaboration**: If working with others, Git keeps everyone's changes organized.

Most AI coding tools integrate with Git automatically, but understanding these basics helps you take control when needed. Don't worry about mastering every Git feature - these commands cover 90% of what you'll need for AI-assisted development.