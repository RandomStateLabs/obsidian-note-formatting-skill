# Obsidian Note Formatting Skill

A Claude skill for creating well-formatted Obsidian notes with proper frontmatter, backlinking, templates, and organization.

## 🎯 What This Skill Does

This skill helps Claude:
- Create properly formatted Obsidian notes with YAML frontmatter
- Apply consistent templates based on note type (technical, idea, meeting, etc.)
- Search your vault for related notes and add proper wikilinks `[[Note Title]]`
- Suggest appropriate folder placement based on content
- Use Obsidian MCP tools to save notes directly to your vault

## 📦 Installation

### For claude.ai (Pro/Max/Team/Enterprise)

1. Download the [latest release](https://github.com/RandomStateLabs/obsidian-note-formatting-skill/releases)
2. Go to claude.ai → Settings → Capabilities → Skills
3. Click "Upload" and select the downloaded ZIP file
4. Enable the skill

### For Claude Desktop (Workaround)

Since Claude Desktop doesn't officially support Skills yet, use the CLAUDE.md approach:

```bash
# Copy SKILL.md to your Obsidian vault
cp SKILL.md /path/to/your/obsidian/vault/CLAUDE.md
```

Claude Desktop will read this file for project-specific instructions.

### For Claude Code CLI

```bash
# Copy to Claude Code skills directory
mkdir -p ~/.claude/skills/obsidian-note-formatting-skill
cp -r . ~/.claude/skills/obsidian-note-formatting-skill/
```

## 🚀 Usage

Simply ask Claude naturally:

```
"Create an Obsidian note about setting up a new Next.js project"
"Document this business idea for my vault"
"Help me create meeting notes from today's standup"
```

Claude will:
1. Determine the note type
2. Generate proper YAML frontmatter
3. Apply the appropriate template
4. Search your vault for related notes
5. Add wikilinks to related content
6. Ask if you want to save to your vault (if MCP is configured)

## 🔧 MCP Integration (Optional)

For automatic vault saving, configure the Obsidian MCP server:

**Requirements:**
- MCP_DOCKER with Obsidian integration
- Permissions for `obsidian_append_content` and `obsidian_simple_search`

The skill will automatically use MCP to:
- Search for related notes in your vault
- Save formatted notes directly to the correct folder

## 📝 Features

- ✅ Consistent YAML frontmatter (date, status, type, tags)
- ✅ Template selection (Technical, Ideas, Meeting, Daily, Learning)
- ✅ Folder placement suggestions based on content
- ✅ Related note discovery via vault search
- ✅ Proper wikilink formatting `[[Note Title]]`
- ✅ Tag suggestions based on content domain
- ✅ File naming conventions (Title Case, <60 chars)
- ✅ Validation checklist included

## 📚 Templates Included

- Architecture Documentation
- How-To Guides
- Technical Notes
- Business Ideas
- Project Brainstorms
- Meeting Notes
- Daily Notes
- Literature Notes
- Learning Notes

## 🎨 Example Output

```markdown
---
date: 2025-11-16
status: capture
type: note
tags:
  - nextjs
  - web-development
  - setup
---

# Setting Up Next.js Project

## Overview
[Your content here]

## Related Notes
- [[React Best Practices]]
- [[TypeScript Configuration]]
- [[Deployment Strategies]]
```

## 🛠️ Development

### File Structure

```
obsidian-note-formatting-skill/
├── SKILL.md                    # Main skill definition (272 lines)
├── references/
│   ├── templates.md            # Complete template library
│   └── folder-structure.md     # Vault organization guide
├── scripts/
│   └── validate_frontmatter.py # Python validator
└── README.md                   # This file
```

### Validation Script

Test note formatting:

```bash
# Install dependencies
pip3 install pyyaml

# Validate a note
python scripts/validate_frontmatter.py "path/to/note.md"
```

## 📄 License

MIT License - See LICENSE file for details

## 🤝 Contributing

Issues and pull requests welcome at [GitHub repository](https://github.com/RandomStateLabs/obsidian-note-formatting-skill)

## 🔗 Related Projects

- [obsidian-note-taker-plugin](https://github.com/RandomStateLabs/obsidian-note-taker-plugin) - Full Claude Code plugin with agents and commands

---

**Created by RandomStateLabs** | For use with Claude (claude.ai, Claude Desktop, Claude Code)
