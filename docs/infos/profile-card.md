# Profile Card Component

Reusable profile summary styles live in `src/components/_profile-card.scss` and
are imported by `src/styles.scss`.

## Classes

- `.paper-profile-card`: outer component shell, usually paired with `paper border`.
- `.paper-profile-card-header`: top title area.
- `.paper-profile-card-kicker`: compact section label.
- `.paper-profile-card-title`: display name or profile title.
- `.paper-profile-card-meta`: wrapping row for metadata chips.
- `.paper-profile-card-body`: padded fallback/body slot.
- `.paper-profile-card-bio`: longer profile copy slot.

## Usage

Use this component for user/profile/feed-home summaries that should be visually
distinct from generic `.card` content but still read as PaperCSS2. Keep
product-specific layout decisions in the consuming app; keep reusable spacing,
metadata chips, and typography here.

After changing the SCSS, rebuild generated CSS with `npm run css:build`.
