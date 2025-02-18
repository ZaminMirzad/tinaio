---
title: Templates
id: templates
last_edited: '2022-06-15T15:51:56.737Z'
next: /docs/reference/types
prev: /docs/reference/fields
---

<!-- # next: /docs/reference/schema -->

In most cases, just using [`fields`](/docs/reference/fields/) is enough, however templates can be used when there are multiple variants of the same collection or object. For example in a "page" collection there might be a need for a marketing page template and a content page template, both under the collection "page". 

## Definition

| Property     | Description              |
|--------------|--------------------------|
| `name` | The name of the template |
| `label` | A human friendly label that will be displayed to the user|
| `fields` | An array of [fields](/docs/reference/fields/) |


## Example using templates instead of fields

```ts
const schema = defineSchema({
  collections: [
    {
      name: "page",
      label: "A page of the website",
      path: "content/pages",
      format: "mdx",
      templates: [
        {
          name: "content",
          label: "Content Page",
          fields: [
            // ... content page fields
          ],
        },
        {
          name: "marketing",
          label: "Marketing Page",
          fields: [
            //... marketing page fields
          ],
        },
      ],
    },
  ],
});

// ...

export default schema
```




## More examples
- [Using templates in rich-text](https://tina-gql-playground.vercel.app/rich-text)
- [Using templates in an object field](https://tina-gql-playground.vercel.app/object-list-templates)
