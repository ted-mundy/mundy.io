---
title: MDC Syntax Reference Guide
description: A comprehensive reference for all MDC features available in this blog, with live examples you can copy.
date: 2024-02-10
tags: [reference, mdc, markdown]
author: Ted Mundy
draft: true
---

# MDC Syntax Reference Guide

This post serves as a reference for all the MDC (Markdown Components) features available on this blog. Use it as a cheatsheet when writing new posts!

::callout{type="info" icon="📚"}
**Note**: This post is marked as `draft: true` in the frontmatter, so it won't appear in production. Remove that line to publish it.
::

## Standard Markdown

### Text Formatting

**Bold text** with `**text**`

*Italic text* with `*text*`

***Bold and italic*** with `***text***`

~~Strikethrough~~ with `~~text~~`

`Inline code` with backticks

### Links and Images

[Link to homepage](/)

[External link](https://nuxt.com)

![Example image](/placeholder.jpg)

### Lists

**Unordered:**
- Item 1
- Item 2
  - Nested item
  - Another nested item
- Item 3

**Ordered:**
1. First item
2. Second item
3. Third item

**Task list:**
- [x] Completed task
- [ ] Incomplete task
- [ ] Another task

### Blockquotes

> This is a blockquote.
> It can span multiple lines.
> 
> And have multiple paragraphs.

### Tables

| Feature | Supported | Notes |
|---------|-----------|-------|
| MDC | ✅ | Full support |
| Code highlighting | ✅ | Shiki powered |
| Vue components | ✅ | Any component! |
| TypeScript | ✅ | Type-safe |

### Horizontal Rules

---

## Code Blocks

### JavaScript

```javascript
const greeting = (name) => {
  console.log(`Hello, ${name}!`)
}

greeting('World')
```

### TypeScript

```typescript
interface User {
  id: number
  name: string
  email: string
}

const user: User = {
  id: 1,
  name: 'Ted',
  email: 'ted@mundy.io'
}
```

### Vue

```vue
<script setup lang="ts">
const count = ref(0)
const increment = () => count.value++
</script>

<template>
  <button @click="increment">
    Count: {{ count }}
  </button>
</template>
```

### Bash

```bash
# Install dependencies
npm install

# Run dev server
npm run dev

# Build for production
npm run build
```

## MDC Components

### Callout Component

**Info callout:**

::callout{type="info"}
This is an **informational** callout with Markdown support!
::

**Warning callout:**

::callout{type="warning"}
⚠️ Be careful with this operation - it cannot be undone!
::

**Success callout:**

::callout{type="success"}
Everything worked perfectly! Great job!
::

**Error callout:**

::callout{type="error"}
An error occurred during processing. Please try again.
::

**Custom icon:**

::callout{type="info" icon="🚀"}
You can customize the icon for any callout type!
::

### Nested Components

You can nest components inside each other:

::callout{type="info"}
**Outer Callout**

This callout contains another one:

::callout{type="success"}
Nested callout! This works perfectly with MDC.
::

And we're back to the outer callout.
::

### Component Props

**Inline props:**
```markdown
::component{prop="value" another="test"}
::
```

**YAML props:**
```markdown
::component
---
prop: value
another: test
complex:
  nested: data
---
::
```

**JSON props:**
```markdown
::component{:data='[1, 2, 3]' :options='{"theme": "dark"}'}
::
```

## Advanced Markdown

### Attributes on Elements

Add styling to inline elements:

Hello [World]{style="color: #10b981; font-weight: bold;"}!

This is `code`{style="color: cyan; background-color: #1e293b;"} with custom styling.

**Bold text**{.text-accent} with a class.

### Nested Lists with Content

1. **First major point**
   
   Some explanatory text about the first point.
   
   ```javascript
   const example = 'code in lists'
   ```
   
2. **Second major point**
   
   ::callout{type="info"}
   You can even put components in lists!
   ::
   
3. **Third major point**

### Complex Blockquotes

> **Note**: This is an enhanced blockquote
> 
> It can contain **formatted text**, `code`, and [links](/).
> 
> > And even nested blockquotes!
> 
> Pretty cool, right?

## Layout Examples

### Two Column Layout (Using Lists)

**Pros:**
- Easy to use
- Fast performance
- Great developer experience

**Cons:**
- Learning curve for MDC
- Requires some setup

### Step-by-Step Instructions

::callout{type="info" icon="1️⃣"}
**Step 1: Install dependencies**

Run `npm install` to get started.
::

::callout{type="info" icon="2️⃣"}
**Step 2: Configure**

Create your `content.config.ts` file.
::

::callout{type="success" icon="3️⃣"}
**Step 3: Start building**

You're all set! Create your first post.
::

## Syntax Cheatsheet

### Component Syntax

```markdown
# Basic component
::component-name
Content
::

# With inline props
::component{prop="value"}
Content
::

# With YAML props
::component
---
title: Hello
count: 42
---
Content
::

# With named slots
::component
Default slot content

#slot-name
Named slot content
::

# Self-closing (no content)
::component{prop="value"}
::
```

### Attribute Syntax

```markdown
# On links
[Link]{.class #id style="color: red;"}

# On code
`code`{.highlight}

# On emphasis
**bold**{.text-accent}
```

## Tips for Writing

1. **Use descriptive headings** - They become anchor links automatically
2. **Add code comments** - Help readers understand complex code
3. **Use callouts for important info** - They draw attention effectively
4. **Keep paragraphs short** - Easier to read on screens
5. **Test your components** - Make sure they render correctly

::callout{type="success"}
**You're ready!** 

Start writing amazing content with MDC. Check out `/content/README.md` for more information.
::

---

## Creating Your Own Components

Want to extend MDC with custom components? Just create a Vue file in `components/content/`:

```vue
<!-- components/content/MyComponent.vue -->
<script setup lang="ts">
const props = defineProps<{
  title: string
}>()
</script>

<template>
  <div class="my-component">
    <h3>{{ title }}</h3>
    <slot />
  </div>
</template>
```

Then use it:

```markdown
::my-component{title="Hello!"}
Component content here
::
```

## Resources

- [Nuxt Content Docs](https://content.nuxt.com)
- [MDC Syntax](https://content.nuxt.com/usage/markdown)
- [Vue Components](https://vuejs.org/guide/components)

Happy writing! 🚀
