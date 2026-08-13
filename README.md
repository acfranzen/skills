# skills

Public agent skills for [skills.sh](https://skills.sh).

```bash
npx skills add acfranzen/skills
```

Install one skill:

```bash
npx skills add acfranzen/skills --skill pinterest-depop-shopper
```

## Skills

| Skill | What it does |
| --- | --- |
| [pinterest-depop-shopper](skills/pinterest-depop-shopper) | Turn a Pinterest clothing board into a style profile, then hunt live Depop listings |

Glance lives in its own repo: [acfranzen/glance](https://github.com/acfranzen/glance).

## Layout

```
skills/
  <skill-name>/
    SKILL.md
    references/
```

Each `SKILL.md` has `name` and `description` frontmatter. No personal boards, sizes, or secrets in this repo. Copy `style-profile.template.md` to `style-profile.md` after install and fill it in.

## License

MIT
