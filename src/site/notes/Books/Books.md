---
{"dg-publish":true,"permalink":"/books/books/","dgPassFrontmatter":true,"dg-note-properties":{}}
---


```base
filters:
  and:
    - file.inFolder("Books")
    - '!file.ext.containsAny("base", "md")'
views:
  - type: table
    name: Table

```

