# CPE Datasets

This repository contains datasets related to CPE in machine readable formats so that we can ingest this data into various tools.

## `repositories.yml`

The list of CPE owned repositories.
The best way to access this file via tooling is by using the following URL: `https://raw.githubusercontent.com/CircleCI-Public/cpe-datasets/main/repositories.yml`.
You can also filter on the commandline with `yq`.
For example, to list just actual image repos:

```bash
curl -sSL "https://raw.githubusercontent.com/CircleCI-Public/cpe-datasets/main/repositories.yml" | yq '.[] | select( .type == "image" )'
```

With a programming language such as Go or Python, this is even easier to use.

Format:

```yaml
- url: "GitHub URL of repository"
  team: "<teamname>"
  subteam: "<subteam>"
  type: "<type>"
  account: "<account>"
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
  - valid values: 'image', 'orb', 'tooling', 'docs', 'sample-project'
- `account`:
  - "Which CircleCI account does this live in?"
  - valid values: 'CircleCI', 'CircleCI-Public'
