# Lesson 9: Testing, Debugging, and Quality Checks with AI

[Share on Facebook](https://www.facebook.com/sharer/sharer.php?u=https%3A//github.com/Troyanovsky/vibe-coding-guide/blob/main/en/9_Testing.md) | [Share on Twitter](https://twitter.com/intent/tweet?text=https%3A//github.com/Troyanovsky/vibe-coding-guide/blob/main/en/9_Testing.md) | [Share on LinkedIn](https://www.linkedin.com/shareArticle?mini=true&url=https%3A//twitter.com/intent/tweet?text=https%253A//github.com/Troyanovsky/vibe-coding-guide/blob/main/en/9_Testing.md)

## Why Testing and Quality Checks Matter

Here's the reality: AI code isn't perfect. It's incredibly powerful and can generate working prototypes faster than you ever imagined, but it's also prone to subtle bugs, inefficiencies, and sometimes just plain weird behavior. Think of AI as that brilliant but slightly chaotic colleague who churns out impressive work but occasionally forgets to check their spelling or leaves typos in important emails.

Testing and quality checks are your safety net. They help ensure your AI-generated app actually works as expected, looks good across different devices, and won't embarrass you when you demo it to stakeholders. Plus, learning to debug with AI is like having a coding mentor who's available 24/7 and never gets tired of your questions.

## Testing Your Prototype

### Manual Testing: The Human Touch

Before we get into fancy automated testing, let's talk about the basics. Manual testing is exactly what it sounds like – you, as a human, clicking around your prototype and making sure it works.

**The Manual Testing Checklist:**
- Does it look right? Check your layout, colors, fonts, and spacing
- Does it work as expected on different screen sizes? Try mobile, tablet, and desktop views (if applicable)
- Click every button, fill out every form, navigate through every flow
- Try to "break" things – what happens if you submit an empty form? Click a button twice? Enter weird data?

This might seem tedious, but it's surprisingly effective. You'll catch the majority of issues just by using your app like a real user would.

### Browser Developer Tools: Your Debugging Sidekick

Every modern browser comes with developer tools (right-click → "Inspect Element" in Chrome/Firefox). These are incredibly useful for spotting issues:

- **Console tab**: Shows JavaScript errors and warnings
- **Network tab**: Reveals if API calls are failing
- **Elements tab**: Lets you inspect and temporarily modify HTML/CSS
- **Responsive design mode**: Test different screen sizes without multiple devices

Don't worry about understanding everything – just look for red error messages and copy/paste them to your AI assistant for help.

### Automated Testing with AI

Here's where things get interesting. You can actually ask AI to create automated testing scripts for you. For example, if you're building a web app, you might prompt:

*"I have a login form with email and password fields. Can you create a Playwright test that checks if the form shows an error message when submitted with invalid credentials?"*

The AI can generate end-to-end tests that automatically click buttons, fill forms, and verify results. This is especially useful for repetitive workflows you need to test over and over.

## Debugging with Your AI Assistant

### Understanding Basic Error Messages

Before we dive into prompting strategies, let's get to know some common error messages you'll encounter:

- **"undefined"**: Usually means you're trying to use a variable that doesn't exist or hasn't been set
- **"Syntax error"**: There's a typo or structural problem in your code (missing semicolon, unmatched brackets)
- **"TypeError"**: You're trying to do something with data that doesn't support that operation (like calling a function on a number)
- **"404 Not Found"**: The code is looking for a file or API endpoint that doesn't exist

### Effective Debugging Prompts

When something breaks, your AI assistant becomes your debugging partner. Here's how to get the best help:

**The Error Message Prompt:**
*"I'm getting this error in the console: `TypeError: Cannot read property 'name' of undefined`. Here's the relevant code: `[mention your relevant code snippet or files]`. Can you help me find the issue?"*

**The Behavior Problem Prompt:**
*"When I click the 'Submit' button, it's supposed to submit the form and show a success message. But nothing happens when I click it. Here's the button code and the submit function. Please investigate the issue and fix it. `[mention your relevant code snippet or files]`"*

**The Explanation Request:**
*"Can you explain what this line of JavaScript does: `const user = users.find(u => u.id === userId)`? I'm trying to understand why my code isn't working."*

The key is being specific about what you expected to happen versus what actually happened, and providing the relevant code context.

## Defining Tests with AI

### Manual Test Planning

Even if you're not writing automated tests, AI can help you plan your manual testing. Try prompts like:

*"I have a form with an email input field and a submit button. I want to test that an error message appears if the email is invalid when I click submit. Describe the steps to manually test this. Include different flows and consider edge cases."*

*"Based on the requirements for this product card component [mention the requirements file], what are some key things I should test to ensure it's working correctly?"*

This helps you think through edge cases and scenarios you might not have considered.

### Test Case Generation

For more structured testing, you can ask AI to generate comprehensive test cases:

*"Here's my user registration flow: [describe the flow or mention relevant part in requirements file]. What are the most important test cases I should cover to make sure this works reliably?"*

The AI will typically suggest testing happy paths (everything works), error cases (invalid inputs), edge cases (empty fields), and boundary conditions (very long inputs).

### Automated Test Code

If you're comfortable with testing frameworks, AI can generate actual test code:

*"Create a Jest unit test for this JavaScript function that validates email addresses. The test should check both valid and invalid email formats."*

Remember to clearly define your expected inputs and outputs, and always ask the AI to explain what the test is checking.

## Basic Code Quality & Review

### Common AI Code Issues

AI-generated code, while functional, often has certain quirks:

- **Verbosity**: AI sometimes writes more code than necessary
- **Inefficiency**: The first solution isn't always the most performant
- **Security oversights**: AI might miss common security best practices
- **Inconsistent patterns**: Different parts of your codebase might use different approaches

### Quality Review Prompts

Here's how to get AI to help improve code quality:

**General Review:**
*"Can you review this code for clarity and suggest improvements to make it more readable? Does it adhere to DRY and KISS principles?"*
(These principles are in our rules for AI in [Lesson 2](en/Lesson_2_Tools.md))

**Performance Check:**
*"Are there any obvious performance issues with this JavaScript code? How can I make it more efficient?"*

**Simplification Request:**
*"This code works but feels overly complex. Can you simplify it while maintaining the same functionality?"*

**Maintainability Focus:**
*"Please refactor this code to make it more maintainable. Prioritize simple functions over complex class hierarchies."*

### Peer Review with AI

Here's an advanced technique: use multiple AI agents/assistants for quality control. Have one AI generate code, then ask a different AI model (or even the same one in a fresh conversation) to review it:

*"Please review this code for potential bugs, performance issues, and maintainability concerns. Suggest specific improvements."*

This multi-pass approach can catch issues that a single AI instance might miss.

## Advanced: Automated PR Review

### AI-Powered Code Review Tools

The landscape of AI code review tools is evolving rapidly. Some current options include:

- **GitHub Copilot**: Offers suggestions and can help review diffs
- **Cursor**: Built-in background AI that can analyze code changes for PR
- **Specialized tools**: Various AI-powered review tools that integrate with Git workflows, like [CodeRabbit](https://www.coderabbit.ai/) (Free for open-source projects.)

These tools can help with:
- Highlighting potential bugs before they reach production
- Suggesting code improvements and optimizations
- Checking for style consistency across your codebase
- Identifying potential security vulnerabilities

### Setting Up Automated Review

If you're using tools like Cursor or similar AI coding environments, you can set up automated review workflows:

*"Create a checklist for reviewing pull requests in this project. Include checks for functionality, performance, security, and code style."*

*"Review this code diff and highlight any potential issues or improvements: [mention your git commit]"*

Some AI will also allow you to connect with a GitHub account and automatically review any commit or PR made to your repositories.

## Making It All Work Together

Testing and debugging with AI isn't just about fixing problems – it's about building confidence in your prototypes. When you combine manual testing, AI-assisted debugging, and quality reviews, you create a safety net that catches issues before they become bigger problems.

Remember: the goal isn't to become a testing expert overnight, but to develop a reliable process that helps you ship better prototypes. Start simple with manual testing and basic error debugging, then gradually incorporate more sophisticated techniques as you get comfortable.

Your AI assistant is there to help every step of the way – from explaining cryptic error messages to generating test cases you hadn't thought of. The key is asking the right questions and providing enough context for the AI to give you useful answers.

**Next up**: We'll explore some more advanced tips for coding with AI. Stay tuned!