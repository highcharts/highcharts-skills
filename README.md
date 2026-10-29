# Highcharts skills

Documentation skills for coding agents building applications with Highcharts.
Each bundle includes task-specific instructions, selected Highcharts
documentation, and a topic index.

## Install

From your application directory, run the
[skills CLI](https://github.com/vercel-labs/skills/blob/main/docs/commands.md):

```bash
npx skills add highcharts/highcharts-skills
```

Choose the skills and coding agents when prompted. Installation targets the
current project by default; add `-g` to install for your user account instead.
To select skills directly, add `--skill highcharts-react` or several skill names.

## Skills

| Skill | Use for |
|-------|---------|
| `highcharts-js` | Core chart setup, configuration, axes, series, and styling |
| `highcharts-stock` | Stock charts, navigation, data grouping, and indicators |
| `highcharts-maps` | Map data, projections, map views, and map series |
| `highcharts-gantt` | Tasks, dependencies, milestones, and schedules |
| `highcharts-react` | Applications using `@highcharts/react` |
| `highcharts-accessibility` | Accessibility, keyboard navigation, and sonification |
| `highcharts-data` | Loading, parsing, mapping, and updating data |
| `highcharts-exporting` | Chart and data export, printing, and export servers |
| `highcharts-morningstar` | Morningstar data connectors and investment analysis |

## Versions and updates

The `main` branch follows Highcharts `master` documentation and may describe
unreleased features. The root `source.json` records the Highcharts source
revision and the included skills.

For a fixed snapshot, pass a GitHub URL pointing to a skill at a commit from
this repository to `npx skills add`. Check its `source.json` and choose a
snapshot matching the Highcharts or React version used by your application.

Update a skill installed from a moving branch:

```bash
npx skills update highcharts-react
```

To change a pinned snapshot, install again using the new commit URL. Replace
the whole skill directory so instructions, references, and indexes stay together
and obsolete pages are removed.

## Contributing

Sources are maintained in
[`highcharts/highcharts`](https://github.com/highcharts/highcharts):

- `skills/` contains authored skill instructions and supporting resources.
- `docs/` contains the reference documentation.
- `tools/skill-configs/` selects the documentation for each skill.

To try source changes, build complete bundles from the Highcharts repository
root:

```bash
npm run generate:skills -- --yes
```

Then install from the build output in your application directory:

```bash
npx skills add /absolute/path/to/highcharts/build/skills/highcharts-react
```

Build output includes the reference pages and index needed for installation.
Submit changes to the source repository; publication replaces this repository's
`skills/` directory and root `source.json`, preserving the README, license, and
workflows.

See the
[build guide](https://github.com/highcharts/highcharts/blob/master/tools/GENERATE-DOC-SKILLS.md)
and
[publication setup](https://github.com/highcharts/highcharts/blob/master/.github/workflows/skills-publish.md)
for validation and publishing instructions.
