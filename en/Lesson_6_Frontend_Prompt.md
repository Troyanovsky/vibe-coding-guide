# Lesson 6: Prompting for Frontend

[Share on Facebook](https://www.facebook.com/sharer/sharer.php?u=https%3A//github.com/Troyanovsky/vibe-coding-guide/blob/main/en/Lesson_6_Frontend_Prompt.md) | [Share on Twitter](https://twitter.com/intent/tweet?text=https%3A//github.com/Troyanovsky/vibe-coding-guide/blob/main/en/Lesson_6_Frontend_Prompt.md) | [Share on LinkedIn](https://www.linkedin.com/shareArticle?mini=true&url=https%3A//twitter.com/intent/tweet?text=https%253A//github.com/Troyanovsky/vibe-coding-guide/blob/main/en/Lesson_6_Frontend_Prompt.md)

## Frontend is All About the User Experience

When you're working on frontend development with AI, remember this: **frontend focuses on UI and user experience**. This isn't just about making things look pretty (though that matters too) – it's about creating interfaces that people actually want to use. 

Because of this focus, your prompts need to be incredibly specific about the user interface and experience details. Think of it this way: if you were hiring a designer, you wouldn't just say "make it look good." You'd talk about your users, their goals, the specific interactions you want, and how everything should feel. The same applies when prompting AI for frontend code.

## A Good vs Bad Prompt for Frontend

Let's look at what separates a terrible frontend prompt from a great one.

### Bad Prompt Example
"I want a screen that has my step count."

This prompt is basically useless. The AI has to guess everything: What platform? What should it look like? How should the data be displayed? Where does the step count come from? Will this page be connected to other pages? It's like asking a contractor to "build me a room" without any blueprints, specifications, or even telling them what the room is for.

### Good Prompt Example
"For iOS, using SwiftUI, I want a pedometer home screen that prominently displays the user's current step count. This count should be large, centered, and updated in real-time. Around the step count, there should be a circular progress bar (like Apple's Activity rings) that visually fills as the user approaches their daily step goal. Below the main display, show the remaining steps to the goal, distance walked, and calories burned in smaller, legible text. A bottom navigation bar should provide access to 'History' and 'Settings'. For font, use SF Pro Display, and for icons use SF Symbols."

Now *that's* a prompt that gives the AI everything it needs to build something useful.

## The Five Pillars of Great Frontend Prompts

When crafting frontend prompts, think about these five key areas. You don't need to cover all of them in every prompt, but the more detail you provide, the better your results will be.

### 1. Foundation (The Tech Stack)
This is your technical foundation – like choosing the right materials before building a house.

- **Platform**: Are you building for iOS, Android, web, or desktop?
- **Framework**: SwiftUI for iOS, React/Vue for web, Flutter for cross-platform?
- **Key Libraries**: Will you use shadcn/ui for React components, Bulma for CSS, or your own design system?

Why this matters: Different platforms have different conventions and capabilities. An iOS app should feel like an iOS app, not a web page crammed into a mobile shell.

### 2. Layout & Structure (The Bones)
This defines how everything is organized and arranged on screen.

- **Visual Hierarchy**: What's most important? What should users see first?
- **Placement**: Should things be in rows, columns, centered, or following a specific grid?
- **Specific Components**: Do you need a progress bar, tabs, cards, modals, or custom components?

Why this matters: Good structure guides users naturally through your interface. Poor structure leaves them confused and frustrated.

### 3. Data & State (The Brains)
This covers what information you're showing and where it comes from.

- **Data to Display**: Step count with units, user profiles, product listings?
- **Data Sources**: REST API, GraphQL, device sensors like HealthKit, local storage?
- **Edge Cases**: What happens when data is loading, when there's an error, or when there's no data to show?

Why this matters: Real apps deal with real data, and real data is messy. Planning for edge cases prevents your app from breaking when things go wrong.

### 4. Interaction & Feel (The Soul)
This is where your interface comes alive and feels responsive.

- **Interactivity**: What happens when users tap, swipe, scroll, or hover? Will the user navigate to other pages?
- **Behavior & Animation**: Should data update in real-time? Do you want pull-to-refresh? Smooth transitions between screens?
- **Accessibility**: Will your app work with VoiceOver, screen readers, or for users with different abilities?

Why this matters: Static interfaces feel dead. Good interactions make your app feel polished and professional.

### 5. Aesthetics (The Paint Job)
This is your visual design – the first thing users notice.

- **Branding**: What's your color palette? Do you follow Material Design, Human Interface Guidelines, or have custom branding?
- **Typography**: Specific fonts like SF Pro Display, font sizes, font weights?
- **Iconography**: Are you using SF Symbols, Feather icons, custom icons, or specific icon styles?

Why this matters: Users judge your app in milliseconds. Good aesthetics build trust and make your app feel legitimate.

## Pro Tips for Frontend Prompting

### Use Your Planning Documents
Remember those planning documents we talked about in Lesson 3? Your `requirements.md`, `system_design.md`, and `todo_list.md` are gold mines for frontend prompting. Reference them to avoid building duplicate components, ensure you're building single-responsibility components, and keep your code organized and modular.

### Prompt Iteratively
Don't expect to get everything perfect in one shot. Use live preview (if you're in VSCode or Cursor with the plugin) to see your changes immediately. Start with basic functionality, then refine the design, then add interactions. It's like sculpting – you start with rough shapes and gradually add detail.

### Try Different Vibes
The best thing about using AI to code is that it becomes no burden to build multiple versions and pick the best one you like. Ask the AI to build different versions and see which one gives the best **vibe**.

### Reference Well-Known Apps
Instead of trying to describe every detail, you can also reference well-known apps. "Like the Instagram story interface" or "Similar to the Spotify now playing screen" gives the AI instant context.

### Use Visual Aids
Screenshots of other apps, your hand-drawn wireframes, or Figma mockups are incredibly helpful. A picture really is worth a thousand words, especially for visual interfaces.

### Leverage Component Libraries
Don't reinvent the wheel. Use established component libraries like shadcn/ui for React, or build up your own component library over time. We'll dive deeper into this in a later lesson, but for now, know that mentioning these libraries in your prompts will give you better, more consistent results.

## Putting It All Together

Great frontend prompting is about being specific enough that the AI can build exactly what you envision, while still leaving room for the AI to handle the technical implementation details you might not know about.

Think of yourself as the director of a movie – you need to communicate your vision clearly, but you don't need to operate the camera or edit the film yourself. The more clearly you can communicate what the final user experience should feel like, the better your AI coding partner can help you build it.

In our next lesson, we'll dive into backend prompting and see how the considerations change when you're dealing with data, APIs, and server-side logic. But for now, start practicing these frontend prompting techniques on your current projects. You'll be amazed at how much better your results become when you give the AI the context it needs to build great user experiences.