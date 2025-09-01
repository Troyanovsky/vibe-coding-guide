# Lesson 10: Pro Tips for AI-Assisted Coding

[Share on Facebook](https://www.facebook.com/sharer/sharer.php?u=https%3A//github.com/Troyanovsky/vibe-coding-guide/blob/main/en/Lesson_10_Pro_Tips.md) | [Share on Twitter](https://twitter.com/intent/tweet?text=https%3A//github.com/Troyanovsky/vibe-coding-guide/blob/main/en/Lesson_10_Pro_Tips.md) | [Share on LinkedIn](https://www.linkedin.com/shareArticle?mini=true&url=https%3A//twitter.com/intent/tweet?text=https%253A//github.com/Troyanovsky/vibe-coding-guide/blob/main/en/Lesson_10_Pro_Tips.md)

By now, you've learned the fundamentals – from setting up your AI coding tools to prompting effectively, understanding code structure, and building both frontend and backend components. 

But here's the thing: knowing the basics is just the beginning. The difference between someone who occasionally gets lucky with AI coding and someone who consistently ships reliable prototypes and products comes down to developing solid professional habits and workflows.

Think of this lesson as your "advanced playbook" – the collection of pro tips, workflows, and mindset shifts that will help you level up from enthusiastic beginner to confident AI-assisted developer.

## Version Control with Git: Your Safety Net

For AI-assisted coding, I just cannot stress more the importance of **version control**, but sadly it's often overlooked by non-professional programmers. If you've ever worked on a design file and wished you could go back to an earlier version, or if you've ever accidentally deleted something important, then you already understand why version control matters. In [Lesson 3](en/Lesson_3_Workflow.md), we've touched upon some basic operations of Git and I'll explain it a little bit more here.

Git is like having multiple saved versions of your project, but much more powerful. Think of it as creating snapshots of your work at different points in time, with the ability to jump between these snapshots, compare them, or even merge different versions together.

Here's why Git becomes even more crucial when working with AI:

**AI makes mistakes.** Sometimes it breaks working code, sometimes it goes in the wrong direction entirely. With Git, you can fearlessly let the AI experiment because you can always roll back to a working state.

**AI iterates fast.** You might go through dozens of iterations in a single session. Git helps you track what actually worked versus what didn't.

**AI helps you collaborate.** Whether with other humans or even other AI conversations, Git makes it safe to combine different approaches.

### Some Essential Git Concepts

You don't need to become a Git expert, but understanding these basic concepts will make your AI-assisted coding much more effective:

- **Repository (repo):** Your project folder, but with superpowers. It tracks all changes to your files.
- **Commit:** A snapshot of your project at a specific point in time. Think "save checkpoint" in a video game.
- **Branch:** A separate timeline where you can experiment without affecting your main code.

While many modern AI tools like Cursor has some version control mechanism like checkpoint built-in, sometimes they're not reliable. So using Git gives you another layer of safety net. The good thing is that you don't really need to do this yourself, just add the following rules for AI and let the AI do it for you:

```
When introducing changes or creating new features, make sure to use git. Check git status first, then create feature branch if necessary.

Write concise and descriptive commit message like :`type: description`. For type, use imperative verb like edit/fix/refactor. Use one-line commit message for simple changes and detailed description for complex changes.
```

## Workflow Tips That Actually Work

Now let's talk about the workflows and habits that separate the pros from the beginners. These aren't just theoretical best practices – they're battle-tested approaches that will save you hours of frustration.

### Save & Commit Frequently (Especially When Working with AI)

Again, this might be the single most important habit to develop. When you're iterating with AI, things can go sideways quickly. Maybe the AI misunderstood your prompt and rewrote half your working code. Maybe it introduced a bug that seems impossible to track down.

With frequent commits, you're never more than a few minutes away from a known-good state. I personally commit after every significant change that works, even if it's just a small improvement.

**Pro tip:** Use descriptive commit messages that future you will appreciate. Instead of "fixed stuff," try "Added user authentication to login form" or "Fixed responsive layout issues on mobile."

### Use Branches for Safe Experimentation

Here's where Git branches become your best friend. Let's say your app is working well, but you want to try a completely different approach to the user interface. Instead of potentially breaking your working code, create a new branch:

```bash
git checkout -b experimental-ui-redesign
```

Now you have a completely safe sandbox to experiment in. Let the AI go wild, try radical changes, test crazy ideas. If it works out great, you can merge it back into your main code. If it's a disaster, you can simply delete the branch and go back to your working version:

```bash
git checkout main
git branch -D experimental-ui-redesign
```

No harm done, no time wasted trying to undo changes.

### Make Small Changes & Test Everything

This ties back to our prompting lessons, but it's worth reinforcing: small, incremental changes are your friend when working with AI. Instead of asking the AI to "rebuild the entire user interface," try "update just the header navigation to include a user profile dropdown."

Why? Because when something breaks (and it will), you'll know exactly what caused it. Debugging one small change is infinitely easier than debugging a massive overhaul.

### Learn to Read Code (Just a Little)

You don't need to become a programming expert, but developing basic code reading skills will supercharge your AI collaboration. You don't need to write the code yourself, but being able to spot obvious issues or understand roughly what the AI is doing will help you:

- Ask better follow-up questions
- Catch AI mistakes before they cause problems
- Provide more specific feedback when things aren't working

Start simple: can you identify which parts of the code handle user interactions? Can you spot where data is being fetched or saved? Even basic pattern recognition will make you much more effective.

If you really struggle with reading code, ask the AI to draw diagrams to help you understand code structure. For example: "Draw a mermaid diagram for how the components work together.", "Draw a sequence diagram of this API call with user, frontend, backend."

### Use Linters for Code Quality

Here's a pro tip that many beginners overlook: use tools called "linters" to automatically check your code quality. Linters like ESLint for JavaScript or Prettier for code formatting are like having a grammar checker for your code.

They catch common mistakes, enforce consistent style, and can even identify potential performance issues. The best part? AI tools can generate code that follows linting rules if you ask them to. Just add something like "run lint and fix lint errors" to your prompts or rules for AI.

### The "Don't Trust, Verify" Principle

This might be the most important mindset shift of all. AI-generated code should always be guilty until proven innocent. No matter how confident the AI sounds, no matter how clean the code looks, always test it thoroughly before considering it "done."

This doesn't mean being paranoid – it means being professional. Test the happy path (when everything works as expected), test edge cases (what happens with empty inputs?), and test error conditions (what happens when the API is down?).

### Quick Validation in Separate Folders

Here's a technique I use all the time when exploring completely new ideas: instead of potentially messing up your main project, create a separate folder and have the AI generate an isolated prototype there.

For example, if I want to test a new payment integration, I'll create a folder called `payment-test` and have the AI build a simple prototype there first. Once I know it works, I can carefully integrate it into my main project.

This approach is especially useful for testing third-party APIs, new frameworks, or complex algorithms.

### Advanced: Parallel Development with Multiple Checkouts

Here's a more advanced technique for when you're working on complex projects: maintain multiple local copies (clones) of your repository. This allows you to run different AI conversations or experiments simultaneously without them interfering with each other. This approach is used by the [Anthropic Engineering Team](https://www.anthropic.com/engineering/claude-code-best-practices)

For instance, you might have:
- `project-main/` - Your stable, working version
- `project-feature-A/` - Working on user authentication
- `project-feature-B/` - Experimenting with a new UI design

Each folder is a complete copy of your project, so you can safely experiment in each one independently.

## Basic Project Organization

Let's talk about organizing your code in a way that makes both you and your AI assistant more effective. Good organization isn't just about looking professional – it's about making your project easier to understand, debug, and maintain.

### Modular File Structure

Organize your files in a way that makes logical sense. Instead of throwing everything into a single folder, create a structure that reflects how your application works:

```
my-project/
├── src/
│   ├── components/     # Reusable UI components
│   ├── pages/         # Different screens/pages
│   ├── utils/         # Helper functions
│   └── api/          # API integration code
├── tests/            # Your test files
├── docs/             # Project documentation
└── assets/           # Images, icons, etc.
```

This modular approach has huge benefits when working with AI:

- **Focused context:** You can reference specific folders when prompting ("update just the components folder")
- **Easier debugging:** When something breaks, you know exactly where to look
- **Better collaboration:** For modules with little inter-dependency, it's possible to have multiple-agents to work in parallel efficiently. [reference](https://lucumr.pocoo.org/2025/6/12/agentic-coding/)

### Keep Reusable Components Organized

Remember those reusable components we created in Lesson 8? Keep them well-organized and documented. Create a simple catalog that both you and your AI can reference:

```
components/
├── ui/
│   ├── Button.jsx
│   ├── Input.jsx
│   └── Modal.jsx
├── forms/
│   ├── LoginForm.jsx
│   └── ContactForm.jsx
└── README.md  # Component documentation
```

## The "Slot Machine" Approach

Let's talk about a completely different philosophy that some teams use when they have unlimited access to AI agents. It's controversial, but worth understanding. [Ref 1](https://monadical.com/posts/vibe-code-how-to-stay-in-control.html) [Ref 2](https://www-cdn.anthropic.com/58284b19e702b49db9302d5b6f135ad8871e7658.pdf)

The traditional approach is: AI generates code → you debug and fix issues → you refine and improve → you commit when it works.

The "slot machine" approach is: AI generates code → you test it → if it fails, you roll back and let the AI try again → repeat until it works → commit the working version.

### When This Works

This approach can be effective when you have:
- **Unlimited AI usage:** No constraints on how many times you can regenerate code
- **Clear requirements:** You know exactly what "working" looks like
- **Automated tests:** You can quickly verify if the generated code works
- **Well-defined modules:** The AI is working on isolated pieces with clear interfaces

### When This Doesn't Work

This approach fails when:
- You don't have clear success criteria
- You're working on interconnected systems where failures cascade
- You're trying to learn and understand the code
- You have limited AI usage quotas

### Important Caveat

The "slot machine" approach only works if you have crystal-clear definitions of what success looks like, ideally backed by automated tests. If you can't automatically verify that the AI's output is correct, you'll end up with unreliable, broken code that looks like it works but fails in subtle ways.

## Putting It All Together

These pro tips aren't just individual techniques – they work best when combined into a cohesive workflow. Here's how a mature AI-assisted development session might look:

1. **Start with a clean Git state** - commit any existing work
2. **Create an experimental branch** for trying new features
3. **Use your organized project structure** to provide clear context to the AI
4. **Make small, incremental changes** with frequent testing
5. **Commit frequently** when things work
6. **Don't trust, verify** - test everything thoroughly
7. **Roll back fearlessly** when experiments don't work out

This might seem like a lot of process, but once these habits become second nature, they'll save you countless hours and frustration. You'll spend less time debugging broken code and more time building cool features.

## The Mindset Shift

Perhaps the most important "pro tip" of all is a mindset shift. As you develop these professional habits, you'll notice that AI-assisted coding becomes less about hoping the AI gets things right and more about creating an environment where both you and the AI can do your best work.

You become the architect and director, setting up systems and processes that help the AI be more effective. You're not just prompting randomly and hoping for the best – you're orchestrating a sophisticated development workflow where the AI is a powerful but guided collaborator.

This is the difference between vibe coding and professional AI-assisted development. Both have their place, but mastering the professional approach will give you the confidence to tackle bigger, more ambitious projects.

Remember: the goal isn't to eliminate AI mistakes or create perfect code on the first try. The goal is to create a workflow that makes mistakes recoverable, progress trackable, and success repeatable.

You've got this. Now go build something amazing.

---

**Next Steps:** With all these lessons under your belt, you're ready to tackle real projects. Start small, practice these professional habits, and gradually work your way up to more complex applications. The combination of AI power and professional workflows is incredibly potent – use it wisely.