# Clash rules bt

This project generates **RULE-SET** for public trackers that applies to [**Clash Premium**](https://github.com/Dreamacro/clash/releases/tag/premium) and all GUI client that uses Clash Premium Core.

## Usage

### URLs

- **anime trackers** generated from [@DeSireFire/animeTrackerList](https://github.com/DeSireFire/animeTrackerList)
  - **Github**: [https://raw.githubusercontent.com/Pioooooo/clash-rules-bt/main/anime_trackers.txt](https://raw.githubusercontent.com/Pioooooo/clash-rules-bt/main/anime_trackers.txt)
  - **jsDelivr**: [https://cdn.jsdelivr.net/gh/Pioooooo/clash-rules-bt@main/anime_trackers.txt](https://cdn.jsdelivr.net/gh/Pioooooo/clash-rules-bt@main/anime_trackers.txt)

### Clash Config

#### Rule Providers

```yaml
rule-providers:
  anime-trackers:
    type: http
    behavior: domain
    url: "https://raw.githubusercontent.com/Pioooooo/clash-rules-bt/main/anime_trackers.txt"
    path: ./ruleset/anime-trackers.yaml
    interval: 86400
```

#### Rules

```yaml
rules:
  - RULE-SET,anime-trackers,DIRECT
```

#### CFW Parser

```yaml
parsers:
  - reg: .*$
    yaml:
      prepend-rules:
        - RULE-SET,anime-trackers,DIRECT
      mix-rule-providers:
        anime-trackers:
          type: http
          behavior: domain
          url: "https://cdn.jsdelivr.net/gh/Pioooooo/clash-rules-bt@main/anime_trackers.txt"
          path: ./ruleset/anime-trackers.yaml
          interval: 86400
```

## Acknowlegements

- [@DeSireFire/animeTrackerList](https://github.com/DeSireFire/animeTrackerList)
- [@Dreamacro/clash](https://github.com/Dreamacro/clash)
- [@Loyalsoldier/clash-rules](https://github.com/Loyalsoldier/clash-rules)

## License

The GPL-3.0 License.  