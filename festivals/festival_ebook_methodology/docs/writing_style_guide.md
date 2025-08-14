# Writing Style Guide for Festival Methodology Ebook

## Voice and Tone

### Overall Voice
- **Conversational**: Write like you're explaining to a colleague over coffee
- **Authoritative**: Confident in the methodology without being preachy
- **Empathetic**: Acknowledge reader's frustrations with current methods
- **Practical**: Focus on actionable advice over theory

### Tone Variations by Section
- **Introduction**: Warm, welcoming, slightly humorous
- **Principles**: Clear, confident, instructional
- **Case Studies**: Narrative, engaging, relatable
- **Templates**: Direct, functional, no-nonsense
- **Troubleshooting**: Patient, understanding, solution-focused

## Writing Guidelines

### Sentence Structure
- Prefer short, clear sentences
- Use active voice whenever possible
- Vary sentence length for rhythm
- One idea per sentence

### Technical Terms
- Define on first use
- Provide glossary entries
- Use consistently throughout
- Avoid jargon when plain language works

### Examples
- Use realistic scenarios
- Include both simple and complex cases
- Show both successes and failures
- Reference actual code/files when relevant

## Formatting Conventions

### Code Examples
```bash
# Use comments to explain non-obvious commands
mkdir -p festivals/festival_user_auth

# Show command output when helpful
$ ls festivals/
festival_user_auth/  festival_api_redesign/
```

### Directory Structures
```
festivals/
└── festival_name/
    ├── FESTIVAL_OVERVIEW.md    # Always include explanatory comments
    └── 001_first_sequence/
        └── task.md             # Keep examples focused
```

### Lists
- Use bullet points for unordered items
- Use numbers only for sequential steps
- Keep list items parallel in structure
- Limit to 7±2 items per list

## Language Preferences

### Do Use
- "You" to address the reader directly
- "We" when discussing shared experiences
- Concrete examples over abstract concepts
- Present tense for current states
- Future tense for outcomes

### Don't Use
- Passive voice (unless necessary for clarity)
- Unnecessarily complex words
- Absolute statements without evidence
- Condescending phrases like "simply" or "just"
- Excessive exclamation points

## Common Phrases and Terminology

### Preferred Terms
- "Festival planner" not "project manager"
- "Sequence" not "phase" or "stage"  
- "Task" not "story" or "ticket"
- "Goal" not "objective" or "outcome"
- "Methodology" not "framework" or "process"

### Key Phrases
- "Goals over process"
- "Flexible by design"
- "Ship when ready"
- "Adapt as you learn"
- "Clear dependencies, parallel work"

## Chapter-Specific Guidelines

### Case Studies
- Start with context and challenge
- Use real names (with permission) or realistic pseudonyms
- Include actual directory structures
- Show the messy reality, not just success
- End with concrete lessons learned

### How-To Sections
1. Start with the why
2. Show the simplest version first
3. Build complexity gradually
4. Provide escape hatches for problems
5. End with next steps

### Comparisons
- Be fair to other methodologies
- Acknowledge their strengths
- Focus on differences, not superiority
- Use tables for quick reference
- Provide migration paths

## Editorial Checklist
- [ ] Consistent terminology throughout
- [ ] All code examples tested and working
- [ ] Cross-references accurate
- [ ] Tone appropriate for section
- [ ] Examples relevant and realistic
- [ ] No unexplained jargon
- [ ] Active voice predominant
- [ ] Clear learning progression