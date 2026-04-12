---
layout: post
title: "Example tech brief (folder-per-post)"
date: 2026-04-05
article: true
---

This is a sample article. The post file is `articles/example-tech-brief/index.md`, and images for this piece can sit in the same folder (for example `diagram.png`) and be referenced with a **relative** path:

```markdown
![Diagram]({{ page.dir | append: 'diagram.png' | relative_url }})
```

Below, the site uses an existing asset so the page renders even before you add your own PNG or JPEG files:

<img src="{{ "/assets/img/my_title.png" | relative_url }}" alt="Example image using a shared site asset" class="post-pic"/>

### Adding a new article

1. Copy the folder `articles/example-tech-brief/` to a new name (use a short slug, e.g. `articles/my-new-topic/`).
2. Edit `index.md`: set `title`, `date`, and keep `article: true` so it appears on the [Articles](/articles/) list.
3. Add `your-image.png` next to `index.md` and embed it with `./your-image.png`.
