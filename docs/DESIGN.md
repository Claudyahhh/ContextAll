# Design system

## Intent

The interface should feel like a warm personal desk with strong navigational ink: intimate enough for journaling, structured enough for serious retrieval.

## Palette

| Role | Color | Approximate share | Usage |
|---|---|---:|---|
| Primary warmth | `#FFC9C9` | 50% | cards, active context, large soft surfaces |
| Supporting light | `#FFF1C7` | 30% | canvas, secondary panels, quiet highlights |
| Structural emphasis | `#4A6FA5` | 20% | titles, buttons, borders, links, focus states |

Opacity variants are allowed. Deep blue should not become a large background field; it is the structure, not the atmosphere.

## Information hierarchy

The UI should make trust layers visible:

- original Context uses the calmest, largest reading surface;
- index metadata is compact and blue-accented;
- AI derivation uses a distinct pale-yellow region and explicit provenance label;
- privacy state is always visible near the document title;
- destination routes appear as links, not as replacements for the source.

## Components

Recommended first components:

1. Inbox queue
2. Context reader/editor
3. Entity drawer
4. Topic navigation rail
5. Source-versus-derivation split view
6. Route-to-destination action
7. Privacy badge
8. Review dashboard

## Interaction principles

- Show what will change before applying a destructive merge or move.
- Make every AI-generated block visibly attributable.
- Let users reach a source passage in at most three navigational steps.
- Prefer progressive disclosure over a dashboard crowded with metrics.
- Keep raw text exportable as plain Markdown.

## Tokens

Executable starter tokens are in `skills/contextall-manager/assets/design/design-tokens.css`.
