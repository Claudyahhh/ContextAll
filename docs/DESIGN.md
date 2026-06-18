# User-owned design profile

[Documentation index](README.md) · [Architecture](ARCHITECTURE.md)

## Principle

ContextAll defines information structure, not the user's aesthetic. A personal Context system may feel calm, playful, archival, technical, tactile, minimal, or something else entirely. The user owns that decision.

Repository branding must not silently become a user's permanent design system.

## What the user should define

Before generating a UI or visual artifact, collect or confirm:

### 1. Color roles

- primary color and approximate share;
- supporting color(s) and approximate share;
- emphasis color and restricted uses;
- background and text colors;
- light/dark mode preference;
- contrast or accessibility requirements.

### 2. Visual character

Ask for three to five words, such as “warm, quiet, editorial” or “precise, technical, dense.” These words guide spacing, shape, imagery, and motion—not only color.

### 3. Typography and density

- serif, sans-serif, handwritten, or mixed;
- compact versus spacious information density;
- preferred heading contrast;
- language-specific font needs.

### 4. Component behavior

- card or document-first layout;
- border, shadow, and radius preferences;
- navigation style;
- how Source Context and Derived Context should look different;
- how privacy states should appear.

## Agent behavior

If a design profile exists, read it before visual work. If it does not exist, ask the user for a palette or mood before establishing durable tokens. A temporary neutral preview is acceptable only when clearly labeled as temporary.

Never infer that an example palette is the user's preference. Never overwrite a confirmed profile because a new artifact used different colors once.

## Configuration

Start with [`design-profile.example.md`](../skills/contextall-manager/assets/config/design-profile.example.md). Store the completed profile in the private vault path configured by `vault-map.yaml`.

Generate executable CSS variables only after the user confirms the profile. The bundled token file is a role-based template, not a prescribed palette.
