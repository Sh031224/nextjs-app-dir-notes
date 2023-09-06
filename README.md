# nextjs-app-dir-notes

This is a repository that collects cautions that are good to read before using the app directory of next.js.


# Categories

- [Routes](#routes)
- [Runtime](#runtime)


## Routes

<details>
    <summary>Loading.tsx and layout.tsx do not work correctly in Parallel routes.</summary>

[See More](https://github.com/vercel/next.js/issues/49243)
</details>

<details>
    <summary>Once notFound is processed, the not found screen continues to appear even when the query is changed.</summary>

[CodeSandbox](https://codesandbox.io/p/sandbox/twilight-tdd-4gtyt4)
</details>




## Runtime

<details>
    <summary>Page refresh occurs when moving between edge runtime and node runtime pages.</summary>

```tsx
// foo/page.tsx
export const runtime = 'edge';
export default function Foo() {
  return <Link href="/bar">Go to bar</Link>
}
```

```tsx
// bar/page.tsx
export default function Foo() {
  return <Link href="/foo">Go to foo</Link>
}
```

When you click the link, the page moves with a refresh.
</details>
