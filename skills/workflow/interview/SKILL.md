---
name: interview
description: Deep interview before building features or projects. Asks 20-50 questions across business, product, technical, security, and marketing blocks. Use before any major feature, new project, or architectural decision.
disable-model-invocation: true
allowed-tools: AskUserQuestion, Read, Glob, Grep, Write, Edit
argument-hint: [plan-file]
model: opus
effort: high
---

# GODMODE Interview

Conduct a detailed interview using AskUserQuestion about the plan/spec:

@$ARGUMENTS

## Interview blocks (ask questions from EACH block):

### 1. BUSINESS
- Who is the target user? (ICP)
- What problem are we solving? (Job to be Done)
- How does the user solve this NOW without us?
- Why is our solution better?
- Can you explain the value in ONE sentence?
- How much would the customer pay?
- How will the customer DISCOVER our product?
- Can we use Supabase or need custom backend?

### 2. PRODUCT
- What does the UI look like? Key screens?
- What is the core user flow?
- Accessibility requirements?
- Mobile, web, or both?

### 3. TECHNICAL
- What tech stack? Why?
- What integrations needed?
- Expected scale (users, data volume)?
- Performance requirements?

### 4. SECURITY
- Are there payments?
- Personal data handling?
- Compliance requirements (GDPR, etc)?
- Authentication method?

### 5. LAUNCH
- Where to host?
- Target platforms (iOS, Android, Web)?
- CI/CD requirements?
- Timeline expectations?

### 6. MARKETING
- Go-to-market strategy?
- Beachhead market?
- Competitive landscape?
- North Star Metric?

## Rules:
- Ask NON-OBVIOUS questions only
- Be maximally detailed
- Continue interviewing until EVERYTHING is clarified
- Then write the final spec back to $ARGUMENTS
- Questions should challenge assumptions, not confirm them