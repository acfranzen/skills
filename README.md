# skills

Public agent skills for [skills.sh](https://skills.sh).

```bash
npx skills add acfranzen/skills
```

Install Fitz only:

```bash
npx skills add acfranzen/skills --skill fitz
```

## Skills

| Skill | What it does |
| --- | --- |
| [Fitz](skills/fitz) | Pinterest board in, live Depop haul out |

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
