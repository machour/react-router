---
title: json
new: true
---

# `json`

Un raccourci pour :

```jsx
new Response(JSON.stringify(someValue), {
  headers: {
    "Content-Type": "application/json; utf-8",
  },
});
```

Généralement utilisé dans les loaders :

```jsx
import { json } from "react-router-dom";

const loader = async () => {
  const data = getSomeData();
  return json(data);
};
```

Lire également :

- [Retourner des réponses depuis les loaders][responses]

[responses]: ../route/loader#returning-responses
