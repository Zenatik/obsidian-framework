---
categories: 
  - "[[Evergreen]]"
tags: 
  - evergreen
last: 2025-06-25
created: 2025-06-25
---
## Zenatik Notes System
I setup this note taking system to be a a minimal folder, category/tag context driven note taking system similiar to [[Kepano-obsidian-system]].

## Directories in "\_"
- **Bases** - Obsidian Bases of all my categories and some extras
- **Categories** - Top level categories every note needs to be assigned. Use this for navigation
- **Libraries** - System Libraries and reference info
- **Templates** - The default templates of all my note types. 

## Notable Frontmatter
### Properties
#### privacy
privacy setting for individual notes, defaulted in template but can be adjusted. Great for LLM access and other tooling
- **private** (default/missing): Most secure value, removes from any MCP and indexing. Could be used for encrypting.
	- Examples: "Medical history", "Tax documents", etc
	- LLM: never index, never expose
- **personal**: Local LLM indexing, my eyes only.
	- Examples: Journals, "Fitness Tracking", "Gift Ideas", "Personal Notes", etc
- **shared**: LLM indexing and shareable
	- Examples: Projects, Prompts, Homelab documentation, etc
- **public**: Open to the world
	- Examples: Reference notes, Documentation, etc

## Related
- https://stephango.com - Creator of the original system
- https://github.com/kepano/kepano-obsidian - Github repo for his system
- https://stephango.com/vault - Kepano's blog

## Obsidian Configs
- set the default new note setting to "Notes"
