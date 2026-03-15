---
visibility: public
type: readme
title: Data Napkin Math
---
This readme describes the structure of data as markdown files here.

There are two subdirs for now: inputs and scenarios.

These subdirs also have subdirs, but they are just for human convenience -- the actual
category data is stored in markdown frontmatter (as `variable_type` for scenarios and `category` for scenarios). Right now these are redundant, but in the future as the library grows in size this might change. So, it is important to list the variable type and category in the markdown directly.

For `inputs`, the main citation fields now include:

- `source_url`: the main source page or document; this may be `null` only for `assumption` or `heuristic` inputs that do not claim an external source
- `sourceName`: short human-readable source label
- `sourceNote`: quick summary of the claim
- `sourceLocator`: where to look inside the source, such as a section name, table, figure, or page hint
- `sourceLocatorUrl`: optional deep link to the exact citation location
- `sourceExcerpt`: a short verification-ready excerpt or tight paraphrase of the cited claim
- `derivationNote`: optional note for values that sum, divide, or otherwise derive from source figures
- `sourceQuality`: evidence type, such as `official`, `primary`, `reported`, `industry`, `heuristic`, or `assumption`
- `confidence`: a 0-1 confidence score for the chosen value

The citation checker treats externally sourced inputs separately from project assumptions and heuristics. Assumption-style inputs still need structured notes, locators, excerpts, and quality/confidence labels, but they are no longer counted as externally verification-ready.
