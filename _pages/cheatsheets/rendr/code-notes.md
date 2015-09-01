---
permalink: "/cheatsheets/rendr/code-notes/"
layout: page
title:  "Rendr: Code Notes"
---

## Models and Collections

`syncer` is mixed into these to help give them isomorphic functionality.

```js
_.extend(BaseModel.prototype, syncer);
```

