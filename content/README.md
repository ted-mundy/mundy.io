# Content Guide

This directory contains all blog posts and content for the site.

## Directory Structure

```
content/
├── blog/           # Blog posts (.md files)
└── README.md       # This file
```

## Creating a New Blog Post

1. Create a new `.md` file in the `blog/` directory:

```bash
touch content/blog/my-new-post.md
```

2. Add frontmatter at the top of the file:

```markdown
---
title: My Awesome Post
description: A brief description of what this post is about.
date: 2024-02-20
tags: [nuxt, vue, tutorial]
author: Ted Mundy
draft: false
---

# My Awesome Post

Your content here...
```

## Frontmatter Fields

| Field | Type | Required | Description |
|-------|------|----------|-------------|
| `title` | string | ✅ | Post title |
| `description` | string | ✅ | Post description (used in previews and SEO) |
| `date` | string | ✅ | Publication date (YYYY-MM-DD format) |
| `tags` | array | ❌ | Array of tags for categorization |
| `author` | string | ❌ | Author name (defaults to "Ted Mundy") |
| `draft` | boolean | ❌ | Set to true to hide from production (defaults to false) |
| `image` | string | ❌ | Hero image URL |

## Using MDC Syntax

MDC (Markdown Components) allows you to use Vue components directly in your Markdown files.

### Basic Syntax

```markdown
::component-name
Content goes here
::
```

### With Props

**Inline props:**
```markdown
::component-name{prop="value" another="test"}
Content
::
```

**YAML props:**
```markdown
::component-name
---
prop: value
another: test
---
Content
::
```

### With Named Slots

```markdown
::component-name
Default content

#slot-name
Content for named slot
::
```

## Available Components

All components in `components/content/` are automatically available in your Markdown files.

### Callout

Display info boxes with different types:

```markdown
::callout{type="info"}
This is an informational callout.
::

::callout{type="warning"}
This is a warning!
::

::callout{type="success"}
Great success!
::

::callout{type="error"}
Something went wrong.
::
```

You can also pass a custom icon:

```markdown
::callout{type="info" icon="🚀"}
Custom icon callout!
::
```

### CodeSandbox

Embed CodeSandbox iframes:

```markdown
::code-sandbox{id="your-sandbox-id" title="Example Demo" height="600px"}
::
```

### ImageComparison

Create before/after image sliders:

```markdown
::image-comparison{beforeSrc="/before.jpg" afterSrc="/after.jpg"}
::
```

### VideoPlayer

Embed videos with controls:

```markdown
::video-player{src="/videos/demo.mp4" poster="/posters/demo.jpg" caption="Demo video"}
::
```

### TweetEmbed

Embed tweets:

```markdown
::tweet-embed{id="1234567890"}
::
```

## Code Highlighting

Code blocks are automatically highlighted using Shiki with the GitHub Dark theme:

````markdown
```typescript
const greeting = (name: string): string => {
  return `Hello, ${name}!`
}
```
````

Supported languages:
- TypeScript
- JavaScript
- JSON
- Bash
- Vue
- CSS
- HTML
- And many more!

## Markdown Features

### Standard Markdown

All standard Markdown features are supported:

- **Bold text** with `**text**`
- *Italic text* with `*text*`
- [Links](https://example.com) with `[text](url)`
- Images with `![alt](url)`
- Lists (ordered and unordered)
- Blockquotes with `>`
- Tables

### Attributes

Add attributes to inline elements:

```markdown
Hello [World]{style="color: green;" .custom-class #custom-id}!

This is `inline code`{style="color: cyan;"} with styling.

**Bold text**{.highlight} with a class.
```

## Creating Custom Components

Want to add your own components? Just create a new Vue component in `components/content/`:

```bash
touch components/content/MyComponent.vue
```

Example component:

```vue
<script setup lang="ts">
const props = defineProps<{
  title: string
  icon?: string
}>()
</script>

<template>
  <div class="my-component">
    <h3>{{ icon }} {{ title }}</h3>
    <slot />
  </div>
</template>
```

Then use it in your Markdown:

```markdown
::my-component{title="Hello World" icon="👋"}
This is the slot content!
::
```

## Tips & Tricks

### Draft Posts

Set `draft: true` in frontmatter to hide posts from production:

```yaml
---
title: Work in Progress
draft: true
---
```

### Tags & Filtering

Use consistent tag names for better filtering on the blog index page:

```yaml
tags: [nuxt, vue, tutorial, architecture]
```

### SEO Optimization

- Write compelling `title` (50-60 characters)
- Write clear `description` (150-160 characters)
- Add relevant `tags`
- Use proper heading hierarchy (H1 → H2 → H3)
- Add `alt` text to images

### URL Structure

The URL for your post will be based on the filename:

```
content/blog/my-awesome-post.md
→ https://mundy.io/blog/my-awesome-post
```

Use kebab-case for filenames to create clean URLs.

## Questions?

Check out the [Nuxt Content docs](https://content.nuxt.com) for more information.
