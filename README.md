# @quartz-community/obsidian-flavored-markdown

Transforms Obsidian-specific markdown syntax including wikilinks, callouts, highlights, Mermaid diagrams, tags, and media embeds.

Mermaid fences default to the Mermaid.js renderer. You can opt into [Pele](https://pele.run) with `diagramRenderer: pele`. Mermaid.js remains the default during a deprecation period; Pele is the intended long-term renderer.

## Installation

```bash
npx quartz plugin add github:quartz-community/obsidian-flavored-markdown
```

## Usage

```yaml title="quartz.config.yaml"
plugins:
  - source: github:quartz-community/obsidian-flavored-markdown
    enabled: true
    options:
      enableInHtmlEmbed: false
      enableCheckbox: true
      # diagramRenderer: pele  # opt-in; default is mermaid
```

For advanced use cases, you can override in TypeScript:

```ts title="quartz.ts (override)"
import * as ExternalPlugin from "./.quartz/plugins";

ExternalPlugin.ObsidianFlavoredMarkdown({
  enableInHtmlEmbed: false,
  enableCheckbox: true,
  diagramRenderer: "pele",
});
```

## Configuration

| Option                 | Type                    | Default     | Description                                                                                             |
| ---------------------- | ----------------------- | ----------- | ------------------------------------------------------------------------------------------------------- |
| `comments`             | `boolean`               | `true`      | Whether to parse Obsidian-style comments.                                                               |
| `highlight`            | `boolean`               | `true`      | Whether to parse Obsidian-style highlights.                                                             |
| `wikilinks`            | `boolean`               | `true`      | Whether to parse wikilinks.                                                                             |
| `callouts`             | `boolean`               | `true`      | Whether to parse callouts.                                                                              |
| `mermaid`              | `boolean`               | `true`      | Whether to parse Mermaid diagram fences.                                                                |
| `diagramRenderer`      | `"mermaid"` \| `"pele"` | `"mermaid"` | Which engine draws Mermaid fences. Pele is opt-in; Mermaid.js is default (deprecated path toward Pele). |
| `parseTags`            | `boolean`               | `true`      | Whether to parse tags.                                                                                  |
| `parseBlockReferences` | `boolean`               | `true`      | Whether to parse block references.                                                                      |
| `enableInHtmlEmbed`    | `boolean`               | `false`     | Whether to enable parsing in HTML embeds.                                                               |
| `enableYouTubeEmbed`   | `boolean`               | `true`      | Whether to enable YouTube embeds.                                                                       |
| `enableVideoEmbed`     | `boolean`               | `true`      | Whether to enable video embeds.                                                                         |
| `enableCheckbox`       | `boolean`               | `false`     | Whether to enable checkboxes.                                                                           |

## Documentation

See the [Quartz documentation](https://quartz.jzhao.xyz/plugins/ObsidianFlavoredMarkdown) for more information.

## License

MIT
