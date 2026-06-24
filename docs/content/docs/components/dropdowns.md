---
title: Dropdowns
description: PaperCSS Dropdowns
---

### JavaScript-controlled dropdown

Use dropdown classes when an application controls the open state with JavaScript. Add `.paper-dropdown-open` to the trigger or wrapper while the menu is open. Use `.paper-dropdown-label` for the trigger text and `.paper-dropdown-icon` for a caret or app icon. Menu buttons can use `.paper-dropdown-item-selected` or `aria-selected="true"` for the active item. Selected and hovered item fills are inset with the same hand-drawn radius treatment as other PaperCSS controls.

<div class="docs-dropdown-demo">
  <div class="paper-dropdown paper-dropdown-open">
    <button class="paper-dropdown-trigger paper-dropdown-open" type="button" aria-expanded="true">
      <span class="paper-dropdown-label">Public</span>
      <svg class="paper-dropdown-icon" aria-hidden="true" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round">
        <path d="m6 9 6 6 6-6"></path>
      </svg>
    </button>
    <div class="paper-dropdown-menu" role="listbox">
      <button class="paper-dropdown-item paper-dropdown-item-selected" type="button" role="option" aria-selected="true">Public</button>
      <button class="paper-dropdown-item" type="button" role="option">Friends</button>
      <button class="paper-dropdown-item" type="button" role="option">Private</button>
    </div>
  </div>
</div>

#### Code:

```html
<div class="paper-dropdown paper-dropdown-open">
  <button class="paper-dropdown-trigger paper-dropdown-open" type="button" aria-expanded="true">
    <span class="paper-dropdown-label">Public</span>
    <svg class="paper-dropdown-icon" aria-hidden="true" viewBox="0 0 24 24"
      fill="none" stroke="currentColor" stroke-width="2.5"
      stroke-linecap="round" stroke-linejoin="round">
      <path d="m6 9 6 6 6-6"></path>
    </svg>
  </button>
  <div class="paper-dropdown-menu" role="listbox">
    <button class="paper-dropdown-item paper-dropdown-item-selected" type="button" role="option" aria-selected="true">Public</button>
    <button class="paper-dropdown-item" type="button" role="option">Friends</button>
    <button class="paper-dropdown-item" type="button" role="option">Private</button>
  </div>
</div>
```

### App menu popovers

Use `.paper-menu-popover` for compact app/navigation popovers that should share
one PaperCSS width token. The default width is `--paper-menu-popover-width`
(`min(18rem, calc(100vw - 2rem))`). Use `.paper-menu-list` and
`.paper-menu-section` for stacked menu groups, `.paper-menu-section-title` for
compact labels, `.paper-menu-item` for full-width menu actions, and
`.paper-menu-nested` for expanded child panels. Use `.paper-menu-item-selected`,
`aria-current="page"`, or `aria-selected="true"` for selected menu items. The
nested panel uses the PaperCSS vertical sketch stroke instead of a straight
left border.

<div class="paper-menu-popover">
  <div class="paper-menu-list">
    <div class="paper-menu-section">
      <button class="paper-menu-item" type="button">My status</button>
      <button class="paper-menu-item" type="button">Profile</button>
      <button class="paper-menu-item" type="button">App</button>
    </div>
    <div class="paper-menu-section paper-menu-nested">
      <span class="paper-menu-section-title">Settings</span>
      <button class="paper-menu-item" type="button">Notifications</button>
      <button class="paper-menu-item" type="button">Bots</button>
    </div>
  </div>
</div>

#### Code:

```html
<div class="paper-menu-popover">
  <div class="paper-menu-list">
    <div class="paper-menu-section">
      <button class="paper-menu-item" type="button">My status</button>
      <button class="paper-menu-item" type="button">Profile</button>
      <button class="paper-menu-item" type="button">App</button>
    </div>
    <div class="paper-menu-section paper-menu-nested">
      <span class="paper-menu-section-title">Settings</span>
      <button class="paper-menu-item" type="button">Notifications</button>
      <button class="paper-menu-item" type="button">Bots</button>
    </div>
  </div>
</div>
```
