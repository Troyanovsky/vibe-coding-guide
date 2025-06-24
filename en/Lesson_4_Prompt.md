# Lesson 4: Effective Prompting

[Share on Facebook](https://www.facebook.com/sharer/sharer.php?u=https%3A//github.com/Troyanovsky/vibe-coding-guide/blob/main/en/Lesson_4_Prompt.md) | [Share on Twitter](https://twitter.com/intent/tweet?text=https%3A//github.com/Troyanovsky/vibe-coding-guide/blob/main/en/Lesson_4_Prompt.md) | [Share on LinkedIn](https://www.linkedin.com/shareArticle?mini=true&url=https%3A//twitter.com/intent/tweet?text=https%253A//github.com/Troyanovsky/vibe-coding-guide/blob/main/en/Lesson_4_Prompt.md)

## The Art of AI Conversation

Here's something that might surprise you: **prompting an AI is basically management in disguise.** Think about it – when you're managing a team member, you don't just say "make the website better." You provide context, set clear expectations, define constraints, and guide them toward the outcome you want.

(I actually think this lesson is great for not only having conversations with AI but also for collaborating at work. I've seen too many cases of requests without clear context at work.)

The same principles apply when you're working with AI coding tools. The difference? Your AI "employee" is incredibly capable but also incredibly literal. It will do exactly what you ask for. And if your instructions are vague or missing key context, you'll get results that technically fulfill your request but completely miss the mark. 

Master this, and you'll find yourself building things faster and with fewer frustrations.

## What Makes a Prompt Effective

Let's break down what separates a great prompt from a mediocre one. There are some key elements that transform vague requests into precise instructions:

### Clarity & Specificity: Say What You Actually Mean

Bad prompt: "Make a form for users."

Good prompt: "Create a contact form with fields for name, email, message, and a submit button. Include client-side validation to ensure all fields are required, highlight errors in real-time, and disable the submit button until the form is valid. Use semantic HTML and accessible ARIA labels. Use Vue3 and Tailwind CSS."

The difference? The second prompt eliminates guesswork. Your AI knows exactly what fields to include, what validation to add, and what the end result should look like.

### Context & Priorities: Set the Stage

This is where that workflow from Lesson 3 really shines. Remember those `requirements.md`, `system_design.md`, and `todo_list.md` files we talked about? They're your secret weapons for providing rich context without overwhelming the AI.

Instead of typing everytime, you can reference these documents: "Based on the requirements in requirements.md, create the user authentication flow described in system_design.md."

Context also means being clear about priorities. If you're building a prototype, say so. If performance is critical, mention it. If you need it to work on mobile first, lead with that.

As AI models get more capable, I actually think "prompt engineering" should be renamed as "context engineering", because how you exactly write the prompts matter less, but what context you include in the prompt matters more.

### Constraints: Draw the Boundaries

AI tools are incredibly creative – sometimes too creative. I notice this happens more with more advanced reasoning models, as they will try to make further optimizations/refactoring that's beyond the scope you want.

Without constraints, you might ask for a simple button and get back a complex component with animations, state management, and dependencies you didn't want.

Be explicit about your constraints for the current scoped edit:
- "Change only the button component in the sign up form. Don't change anything else."
- "Use the existing vue components in `src/components/` and don't add new ones."
- "Fix only functionality related to the sign up form. Don't optimize for redundant code, modularity, or performance yet."

### Desired Output: Be Specific About What You Want

Do you just want an explanation of potential strategy? A plan for implementation? A code snippet/edit? Be explicit.

- "Provide the complete HTML file with inline CSS"
- "Show me just the JavaScript function, with comments explaining each step"
- "Give me a step-by-step implementation plan, don't write the code yet"

## Iterative Prompting & Conversation Context

Remember, **it's a conversation, not a one-shot command.** Don't feel like you need to get everything perfect in your first prompt. Instead, think of it as a collaborative back-and-forth.

### Start Slow, Course Correct Early

Remember our workflow? Don't jump straight to "write all the code." Start by confirming the approach:

"I want to build a todo app. Based on my requirements.md, what would be the best way to structure the components?"

Let the AI propose an approach. If it's heading in the wrong direction, course correct immediately: "Actually, I want to keep it simpler. Can we use just vanilla JavaScript instead of React?"

This saves you from getting 200 lines of code in a framework you didn't want.

### The Power of Follow-Up Questions

Once you have a foundation, build on it iteratively:
- "Now add validation for the email field"
- "Make the submit button blue and add a hover effect"
- "Add error handling for when the API call fails"

Each request builds on the previous context, creating increasingly sophisticated functionality. Make sure to use git commits to keep track of the changes.

### Know When to Start Fresh

Sometimes conversations go off the rails. The AI gets stuck on a wrong assumption, or you've been working on multiple different features and the context becomes muddy. This is called **context pollution** – when early misconceptions contaminate everything that follows.

When this happens, don't be afraid to start a new conversation. Revert the changes if needed and start a new conversation. It's often faster than trying to untangle a confused conversation thread and debug.

### Learning from Cloudflare's Engineering Team

Here's a pattern that Cloudflare's engineering team found incredibly effective: **"You did X, but we should do Y. Please fix."**

No elaborate explanations. No complex instructions. Just clear context about the current state, why it needs to change, and what direction to go. It's remarkably like giving feedback to a colleague – direct, contextual, and actionable.

[Read More](https://www.maxemitchell.com/writings/i-read-all-of-cloudflares-claude-generated-commits/)

## 4.3. Advanced Prompting Tactics

Once you've mastered the basics, these advanced techniques will take your prompting to the next level:

### Few-Shot Prompting: Show, Don't Just Tell

Instead of describing what you want, show examples of similar code:

"Here's how I've styled other cards in this project: @card_exmaple.vue. Create a new testimonial card following the same design patterns and CSS structure."

Most AI coding tools let you reference existing files directly. Use this feature liberally – it's like giving your AI a style guide to follow.

### Ask for Alternatives

Don't settle for the first solution. AI tools can generate multiple approaches:

"Show me two different ways to implement this dropdown menu – one using pure CSS and another with Tailwind CSS."

For smaller experiments, use temporary files. For bigger architectural decisions, you might even ask the AI to create different git branches to test.

### Plan Before Action

Earlier, we've mentioned that planning before action is important and we talked about having a system design doc and a to-do list for your project.

This applies to scoped changes too. Ask the AI for a plan before you ask it to write code. 

"Before writing any code, list the files that need to be created or modified, and the order of implementation."

This gives you a roadmap and helps catch potential issues before you're deep in implementation.

### Treat Prompts as Documentation

Here's a pro tip: include your key prompts in commit messages or project documentation. Not the entire conversation, but the crucial prompts that led to important architectural decisions or complex implementations.

Future you (or your teammates) will thank you when trying to understand why code was written a certain way. It's like leaving breadcrumbs for debugging and maintenance.

(This is also what's done by the Cloudflare engineering team when they used Claude to generate their [OAuth 2.1 library](https://github.com/cloudflare/workers-oauth-provider))

### A Picture's Worth a Thousand Words

If your AI tool supports it, don't underestimate the power of images. Screenshot a design mockup, a broken UI, or even hand-drawn wireframes. Visual context can be incredibly powerful for:
- Design implementation: "Build this interface" [attach mockup]
- Bug reports: "The layout breaks like this on mobile" [attach screenshot]
- Architecture diagrams: "Implement this database schema" [attach diagram]

## Making It All Work Together

The magic happens when you combine all these techniques. Start with clear requirements documents, use specific and constrained prompts, iterate through conversation, course correct early, and don't be afraid to start fresh when needed.

In our next lesson, we'll get a little bit more technical to help you better understand what you're building. It's a great primer if you're new to programming and app architecture.