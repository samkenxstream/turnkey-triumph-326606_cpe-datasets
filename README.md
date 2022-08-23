# CPE Datasets

This repository contains datasets related to CPE in machine readable formats so that we can ingest this data into various tools.

## `repositories.yml`

The list of CPE owned repositories.

Format:

```yaml
- url: "GitHub URL of repository"
  team: "<teamname>"
  subteam: "<subteam>"
  type: "<type>"
```

What keys mean::

- `team`
  - "The owning team for the entire repository."
  - valid values: 'CPE'
- `subteam`
  - "The sub-team owning the repo, if there is one."
  - valid values: 'Images', 'Orbs'
- `type`:
  - "What type of repository is it? This can be helpful for running automation on only certain repos. For example, a repository may be owned by the Images subteam but the repo itself doesn't represent an image."
  - valid values: 'image', 'orb', 'tooling', 'docs'
