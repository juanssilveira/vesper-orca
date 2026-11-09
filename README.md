# Vesper for Orca

Peppermint and orange flavored dark theme for [Orca](https://github.com/stablyai/orca), ported from
[Vesper](https://github.com/raunofreiberg/vesper) for VS Code by Rauno Freiberg.

- **App theme:** `Vesper` (dark), with editor, sidebars, tabs, diffs and git decorations.
- **Terminal theme:** `Vesper`.

Choose it under Settings → Appearance; its terminal colors are offered alongside it.

## Palette

| Role | Color |
| --- | --- |
| Background | `#101010` |
| Raised surfaces | `#161616` `#1C1C1C` `#232323` |
| Text | `#FFFFFF` |
| Secondary text, keywords | `#A0A0A0` |
| Orange: functions, types, numbers, accent | `#FFC799` |
| Peppermint: strings, added | `#99FFE4` |
| Red: errors, removed | `#FF8080` |

## Differences from the VS Code theme

Orca's theme rules differ from VS Code's, so a few colors were adjusted:

- Comments are `#666666` instead of the translucent `#8b8b8b94`: Orca needs opaque code colors
  with at least 3:1 contrast, and the original falls below that.
- Rules with descendant selectors (`source.json meta.structure... support.type.property-name.json`)
  are flattened to the most specific single scope, since Orca does not read selectors with spaces.
- Vesper has no terminal palette; this one follows the theme's peppermint, orange and soft
  pastels.

### Chat tokens for newer Orca

Orca 1.4.250 does not accept the chat tokens yet. Once your Orca validates them, add these to
`themes/vesper.json`:

```json
"--chat-bold-foreground": "#FFFFFF",
"--chat-muted-foreground": "#A0A0A0",
"--chat-inline-code": "#1C1C1C",
"--chat-inline-code-foreground": "#99FFE4",
"--chat-code-block": "#161616",
"--chat-selection": "#FFFFFF25",
"--chat-selection-foreground": "#FFFFFF"
```

## Development

```sh
orca plugin validate .
orca plugin dev load .
```

Orca reloads the theme on every save while the folder is loaded as a development plugin.

## License

MIT. The original Vesper notice is kept in [LICENSE](LICENSE).
