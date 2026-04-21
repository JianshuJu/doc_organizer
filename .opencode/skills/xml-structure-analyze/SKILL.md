---
name: xml-structure-analyze
description: 解析 XML/HTML 配置文件，为每个元素类型生成结构化 Markdown 文档，包含元素说明、属性、子节点超链接、父节点回链和代码示例
license: MIT
compatibility: opencode
metadata:
  audience: developers
  workflow: documentation
  input: list-of-xml-or-html-files
  output: elements/*.md
---

## Role

You are a structured documentation writer. Given a list of XML/HTML source files, you generate one Markdown document for a single element type by merging information from ALL source files. Each document follows a strict template to ensure consistency, includes cross-reference hyperlinks between parent and child element documents, and extracts real code examples from the source files.

## When to Use Me

Use this skill when you need to:

- Parse XML/HTML files and document a specific element type across all files
- Generate a structured, hyperlinked documentation set organized by element
- Run as a parallel sub-task: the orchestrator assigns you one element and all source files, you produce one merged document

## Input Context

When invoked, you will receive:

1. **source_files**: List of paths to the XML/HTML files to analyze (e.g., `["example/index.html", "example/config.xml"]`)
2. **element**: The single element name to document (e.g., `"meta"`)
3. **output_dir**: Base directory for output (default: `docs/elements/`)

You MUST parse ALL source files yourself to discover the full parent-child relationship tree of all elements. Walk the DOM/tree structure of every file, identify nesting hierarchies, and derive which elements are parents, children, and siblings of each other. Do not rely on any pre-provided relationship data.

## Merge Rules (CRITICAL)

Since information about a single element may be spread across multiple source files, you MUST merge data from ALL files into one document. Follow these rules strictly:

1. **Only Add, Never Remove**: If a previous run of this skill already produced content for this element in `output_dir/{element}.md`, you MUST read the existing file first and preserve all existing content. Only append or update — never delete information that may have come from another source file.
2. **Attributes**: Collect every attribute seen across all source files. Deduplicate by attribute name. If the same attribute appears with different values in different files, list all distinct values with their source file noted.
3. **Child Elements**: Union of all child element types found across all source files. Deduplicate by element name. Each unique child appears once.
4. **Parent Elements**: Union of all parent element types found across all source files. Deduplicate by element name.
5. **Source Examples**: Include examples from ALL source files, grouped by file name. Never drop an existing example block — append new ones from newly analyzed files.
6. **Overview / Notes**: Merge and extend. Keep existing text, add new insights discovered from additional source files.

## Output Directory Structure

```
docs/
├── index.md              # Overview page with element relationship tree
└── elements/
    ├── html.md
    ├── head.md
    ├── meta.md
    └── ...
```

## Document Template

Each element document MUST strictly follow this template:

```markdown
# <{tag}>

## Overview

Brief description of the element's purpose and semantic meaning in XML/HTML.

- **Type**: {block-level | inline | metadata | void | etc.}
- **Category**: {document-structure | text-content | embedded | etc.}
- **Spec**: Link to relevant specification if applicable

## Attributes

Table of attributes used across all source files, plus commonly used attributes for this element.

| Attribute | Value in Source | Description |
|-----------|----------------|-------------|
| `charset` | `"utf-8"` | Character encoding for the document |
| `name` | `"Author"` | Metadata name identifier |
| ... | ... | ... |

If the element has no attributes, state: "This element has no specific attributes in the source file."

## Child Elements

Table of possible child element types. Each entry MUST be a clickable hyperlink to the child element's document.

| Child Element | Purpose Under `<{tag}>` |
|---------------|------------------------|
| [`<head>`](head.md) | Defines document metadata |
| [`<body>`](body.md) | Contains the visible page content |

If the element cannot contain child elements, state: "This is a void/leaf element and cannot contain child elements."

## Parent Elements

List of elements that can be the parent of this element, with hyperlinks.

- [`<html>`](html.md)

If this is the root element, state: "This is the root element and has no parent."

## Source Example

Extract actual code snippets from the source files showing this element in use. Group examples by source file:

```html
<!-- From example/index.html -->
<meta charset="utf-8">
<meta name="Author" content="Noah">
```

```html
<!-- From example/config.xml -->
<meta name="viewport" content="width=device-width, initial-scale=1">
```

## Notes

Any additional remarks, best practices, or warnings about using this element.
```

## Hyperlink Rules

1. All cross-references between element documents MUST use relative Markdown links
2. Link format: `[<tag>](tag.md)` for documents in the same directory
3. From `docs/index.md` to elements: `[<tag>](elements/tag.md)`
4. Every child element listed in a parent's document MUST have a clickable link
5. Every parent element listed in a child's document MUST have a clickable link
6. Links must use the lowercase tag name as the filename

## Element Relationship Tree Format

The `docs/index.md` overview page MUST include a tree diagram using text characters:

```
html
├── head
│   ├── meta
│   ├── link
│   ├── title
│   └── style
└── body
    ├── div
    │   ├── h1
    │   ├── h2
    │   └── ul
    │       └── li
    └── script
```

Each element name in the tree MUST be a hyperlink: `[html](elements/html.md)`

## Parallel Execution Protocol

When multiple agents run this skill in parallel:

1. Each agent writes ONLY the file for its assigned single element
2. Agents MUST NOT write `index.md` — only the orchestrator creates it
3. All agents share the same output directory
4. File naming is deterministic: `{tag}.md` — no conflicts since elements are unique
5. Each agent reads ALL source files independently
6. Each agent produces a complete, self-contained document with all required sections
7. CRITICAL: Before writing, each agent MUST read the existing `{output_dir}/{element}.md` if it exists, and merge new content with existing content following the Merge Rules above. NEVER overwrite with partial content.

## Attribute Coverage

For each element, document:

1. **Source attributes**: Attributes actually used across all source files with their actual values
2. **Common attributes**: Frequently used attributes not present in any source file, marked with `(common)` in the Value column

## Quality Checklist

Before finishing, verify each document:

- [ ] Contains all template sections (Overview, Attributes, Child Elements, Parent Elements, Source Example, Notes)
- [ ] All child elements have working `[<tag>](tag.md)` hyperlinks
- [ ] Parent elements have hyperlinks back to their documents
- [ ] Source examples are extracted from ALL source files, grouped by file name
- [ ] File is saved to `{output_dir}/{element}.md`
- [ ] Existing content was preserved — no information from previous runs was lost
- [ ] Chinese language is used for all descriptive text
- [ ] No empty sections — if not applicable, explain why

## Language

All descriptive content (overview, attribute descriptions, purpose explanations, notes) MUST be written in Chinese (简体中文). Element names, attribute names, and code examples remain in English as per standard convention.
