---
title: Profile card
description: PaperCSS2 profile summary card
---

Profile cards give profile or feed-home summaries a distinct PaperCSS2 treatment
without using the generic card body layout.

Use `.paper-profile-card` on the outer card, `.paper-profile-card-header` for
the top band, `.paper-profile-card-kicker` and `.paper-profile-card-title` for
labels and names, `.paper-profile-card-meta` for wrapping metadata chips, and
`.paper-profile-card-bio` or `.paper-profile-card-body` for the content area.

<section class="paper border paper-profile-card">
  <div class="paper-profile-card-header">
    <p class="paper-profile-card-kicker">Feed home</p>
    <h1 class="paper-profile-card-title">Ada Lovelace</h1>
  </div>
  <p class="paper-profile-card-meta">
    <span>@ada</span>
    <span>ada@example.com</span>
    <span>Joined Jun 2026</span>
  </p>
  <p class="paper-profile-card-bio">Short profile copy wraps cleanly and keeps the profile header separate from timeline cards.</p>
</section>

#### Code:

```html
<section class="paper border paper-profile-card">
  <div class="paper-profile-card-header">
    <p class="paper-profile-card-kicker">Feed home</p>
    <h1 class="paper-profile-card-title">Ada Lovelace</h1>
  </div>
  <p class="paper-profile-card-meta">
    <span>@ada</span>
    <span>ada@example.com</span>
    <span>Joined Jun 2026</span>
  </p>
  <p class="paper-profile-card-bio">Short profile copy wraps cleanly and keeps the profile header separate from timeline cards.</p>
</section>
```
