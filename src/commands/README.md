# Commands

Easily add and author [Reusable Commands](https://circleci.com/docs/2.0/reusing-config/#authoring-reusable-commands) to the `src/commands` directory.

Each _YAML_ file within this directory will be treated as an orb command, with a name which matches its filename.

```yaml
description: >
  Downloads NPM package to build image and push it to GCR
parameters:
  merge-trigger-branch:
    type: string
    default: "a-branch-that-shall-never-exist"
    description: "Branch trigger merge"
  merge-destination-branch:
    type: string
    default: "a-branch-that-shall-never-exist"
    description: "Branch merge destination"
  fingerprints:
    type: string
    description: "CircleCI fingerprints"
  project-name:
    type: string
    description: "Task project name"
  git-branch:
    type: string
    description: "Pipeline Git branch"
  build-id:
    type: string
    description: "CircleCI Build/Pipeline ID"
```
