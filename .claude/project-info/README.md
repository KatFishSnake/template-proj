# Project Information Directory

This directory contains all feature documentation and architectural patterns for the project.

## Structure

```
.claude/project-info/
├── README.md                    # This file
├── project-description.md       # High-level project overview
├── architectural-patterns.md    # Top-level architectural patterns
├── [feature]-[name]/            # Feature template (copy this)
│   ├── feature-info.md          # Requirements from human
│   └── technical-plan.md        # Implementation from agent
└── [feature]-actual-name/       # Actual feature directories
    ├── feature-info.md
    └── technical-plan.md
```

## Workflow

### 1. Human Creates Feature

When starting a new feature:

```bash
# Copy the template
cp -r ".claude/project-info/[feature]-[name]" ".claude/project-info/[feature]-my-feature"

# Edit feature-info.md with requirements
```

### 2. Human Writes Requirements

Edit `feature-info.md` with:
- Feature overview and goals
- Requirements (functional & non-functional)
- User stories
- Acceptance criteria

### 3. Agent Creates Technical Plan

Agent reads `feature-info.md` and creates `technical-plan.md` with:
- Implementation approach
- Files to modify/create
- Step-by-step plan
- Technical decisions
- Testing strategy

### 4. Implementation

Agent implements based on `technical-plan.md`, updating the plan as needed.

## Rules

- **All features must have a directory** in `.claude/project-info/`
- **Human owns** `feature-info.md` (requirements)
- **Agent owns** `technical-plan.md` (implementation)
- **No standalone planning** - plans must relate to a feature
- **Keep updated** - mark status in technical-plan.md

## Naming Convention

Feature directories: `[feature]-[descriptive-name]`

Examples:
- `auth-login`
- `dashboard-analytics`
- `payment-stripe-integration`
- `profile-edit`

## Top-Level Files

### project-description.md
High-level project overview, goals, and next steps.

### architectural-patterns.md
Project-wide patterns for:
- Data flow
- State management
- API design
- Authentication
- Error handling
- Testing
- Deployment

## Benefits

- **Centralized documentation** - All feature context in one place
- **Clear ownership** - Human defines "what", agent defines "how"
- **Searchable history** - Git tracks all feature evolution
- **Onboarding** - New developers/agents can read feature docs
- **Context preservation** - No lost context between sessions
