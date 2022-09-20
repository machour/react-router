---
title: redirect
new: true
---

# `redirect`

Comme vous pouvez retourner ou lancer des réponses depuis les loaders ou actions, vous pouvez utiliser `redirect` pour rediriger vers une autre route.

```jsx
import { redirect } from "react-router-dom";

const loader = async () => {
  const user = await getUser();
  if (!user) {
    return redirect("/login");
  }
};
```

Il s'agit en réalité d'un raccourci pour ceci :

```jsx
new Response("", {
  status: 302,
  headers: {
    Location: someUrl,
  },
});
```

Il est recommandé d'utiliser `redirect` dans vos loaders et actions plutôt qu'utiliser `useNavigate` dans vos composants, lorsque la redirection est en réaction aux données.

Lire également :

- [Retourner des réponses depuis les loaders][responses]

## Déclaration de type

```ts
type RedirectFunction = (
  url: string,
  init?: number | ResponseInit
) => Response;
```

## `url`

L'URL vers laquelle rediriger.

```js
redirect("/login");
```

## `init`

Les options de l'objet [Response][response] utilisé comme réponse.

[responses]: ../route/loader#returning-responses
[response]: https://developer.mozilla.org/en-US/docs/Web/API/Response/Response
