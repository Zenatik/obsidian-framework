---
categories: 
  - "[[Evergreen]]"
tags: 
  - evergreen
last: 2025-06-25
created: 2025-06-25
---
## Zenatik Notes Framework

I setup this note taking framework to be a a minimal folder, category/tag context driven note taking system similiar to [[Kepano-obsidian-system]].

## Directories in "\_"
- **Bases** - Obsidian Bases of all my categories and some extras
- **Categories** - Top level categories every note needs to be assigned. Use this for navigation
- **Libraries** - System Libraries and reference info
- **Templates** - The default templates of all my note types. 

## Privacy Configuration

I plan to expose my notes to AI/LLM, so I set the system up to have 2 layers in its approach. Folder & Frontmatter. The frontmatter is straight forward and the templates default all the values for "privacy" property. Values are listed below.

The folder approach requires a plugin and configuration to move notes on the filesystem. You can use either the root "/\_inbox" & "/Notes" for a public by default or use the identical folders in "/Personal" for a privacy forward default.

I use QuickAdd Community Plugin to setup macro's to move templated notes to the correct folder.

All of this was setup so that you can use MCPs & GIT. The folder approach lets you use a basic filesystem MCP to ignore the Personal directory entirely in addition to using .gitignore the entire directory for GIT. Or a custom MCP so that you use frontmatter to handle privacy at the content level.

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

## Plugins I use

All plugins are optional but do add some convenience and note handling and are ordered in priority:

  1. **QuickAdd** - Mostly for the Privacy configuration and handle "Note" vs "References" folder moves
  2.  **Git** - Because I use GIT to version and sync my notes across devices
  3.  **Media DB** - Load in metadata for reference notes for movies, books, shows, games, etc
  4.  **Omnisearch** - just a really good searching plugin
  5. **Calendar** - Journals are dated as are evergreen, its nice to see on a calendar
  6. **Linter** - because I get annoyed by markdown warnings.
  7. **Minimal Theme Settings** - I use the Minimal Them

## Related
- https://stephango.com - Creator of the original system
- https://github.com/kepano/kepano-obsidian - Github repo for his system
- https://stephango.com/vault - Kepano's blog

## Obsidian default configs

- set the default new note setting to "Notes" or "Personal/Notes"
- set the unique note creator to "\_inbox" or "Personal/\_inbox"
- set the attachments folder path to "Attachments"
- set daily note setting to "Personal/Journal/"
