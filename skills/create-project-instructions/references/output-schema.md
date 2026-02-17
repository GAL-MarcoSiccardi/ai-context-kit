# Output Schema: create-project-instructions

## YAML Frontmatter
```yaml
---
name: {project-name-slug}
description: Project-specific instructions for {Project Name} (v{version}, spec v1.2, updated {date})
applyTo: "**/*"
---
```

## Required Sections (in order)
1. Project Context - {Project Name}
2. Session Prerequisites
3. Overview
4. Default Session State
5. State Management & Control
6. Role Definitions
7. Tech Stack
8. Current Objectives
9. Development Principles
10. Repository Context
11. Working Together
12. Key Components
13. Testing Strategy
14. Documentation Standards
15. Testing Commands
16. Related Files
17. Future Roadmap

## Section Quality Requirements
- All required sections must have substantive, project-specific content.
- Session state table must include Project, Role, Phase, Output Style, Tone, Interaction Mode.
- Output must remain provider-neutral.
