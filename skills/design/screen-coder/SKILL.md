---
name: screen-coder
description: Converts UI screenshots and design mockups into production-ready HTML/CSS code. Multi-agent architecture analyzes layout, plans structure, generates clean code. Use when you have a design image and need code. Don't use for code-to-code tasks.
disable-model-invocation: true
model: opus
effort: high
allowed-tools: Read, Write, Bash, Glob
argument-hint: [path-to-screenshot]
---

# ScreenCoder — Screenshot to Code

Convert a UI design screenshot into production-ready code.

## Process:
1. Analyze the screenshot layout and visual structure
2. Identify all UI components (buttons, cards, inputs, navigation)
3. Plan HTML structure and CSS approach
4. Generate clean, editable HTML + CSS/Tailwind code
5. Ensure responsive design

## Input: $ARGUMENTS (path to screenshot image)

## Output:
- Clean HTML file
- Tailwind CSS classes (preferred) or separate CSS
- Component structure matching the design

## Rules:
- Match the design as closely as possible
- Use semantic HTML elements
- Mobile-first responsive approach
- Use existing component patterns from the project if available

## Reference: https://github.com/leigest519/ScreenCoder