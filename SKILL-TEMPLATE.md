---
name: skill-name-here
description: >
  One-paragraph description of what this skill does and when to trigger it.
  Include natural language triggers like "when the user asks to...", "when the user says...",
  "when the user wants to...". Be specific about the marketing function it serves.
---

# Skill Display Name

Brief explanation of what this skill does and why it matters for marketers.

## Granularity Check

> Can this be completed in a single 10-minute Claude session? If the answer is no, this skill is too broad — split it.

## User Intent Mapping

This skill should trigger when the user says things like:

- "Direct command" (e.g., "Generate a content brief for...")
- "Problem statement" (e.g., "I don't know what to write about...")
- "Goal-oriented" (e.g., "I want to rank for...")
- "Tool-specific" (e.g., "Help me with my SEO...")

## Input Contract

### Required Input

| Column / Field | Type | Description | Example |
|---|---|---|---|
| field_name | string | What this field contains | `"example value"` |

### Optional Input

| Column / Field | Type | Default | Description |
|---|---|---|---|
| optional_field | string | `"default"` | What this field does |

### Sample Input Row

```csv
field_name,optional_field
"example value","default"
```

### Input Validation Rules

1. Required columns must be present
2. [Field] must not be empty
3. [Field] must match format: [pattern]

**If validation fails:** Tell the user exactly which columns/rows are invalid and provide a corrected sample.

## Process

1. **Validate input** — Check all required fields. Stop with clear error if missing.
2. **Step 2** — What Claude does
3. **Step 3** — What Claude does
4. **Human checkpoint** — Present intermediate output for user review before proceeding.
5. **Step 5** — What Claude does after user approves

## Output Contract

### Output Format

| Output | Format | Contents |
|---|---|---|
| Primary deliverable | Markdown/HTML/XLSX | What's in it |
| Secondary deliverable | CSV | What's in it |

### Output Schema (if XLSX/CSV)

| Column | Type | Description |
|---|---|---|
| output_field | string | What this contains |

### Sample Output Row

```csv
output_field
"example output"
```

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| Empty/insufficient input | User provides too little data | Ask clarifying questions, provide sample input |
| Ambiguous intent | Skill can't determine what user wants | Present 2-3 options and ask user to choose |
| External data unavailable | Web search returns nothing relevant | Fall back to user-provided context, explain limitation |

## How to Get Your Data

### From [Tool Name] (e.g., Google Analytics, HubSpot)

1. Navigate to [specific menu path]
2. Click [specific button]
3. Select date range / filters
4. Export as CSV
5. Upload the CSV when prompted

## Example

**User prompt:** "I need help with [task description]"

**Claude output:** [Brief description of what the skill would produce]
