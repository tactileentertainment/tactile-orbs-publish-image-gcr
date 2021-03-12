# Jobs

Easily author and add [Parameterized Jobs](https://circleci.com/docs/2.0/reusing-config/#authoring-parameterized-jobs) to the `src/jobs` directory.

Each _YAML_ file within this directory will be treated as an orb job, with a name which matches its filename.

Jobs may invoke orb commands and other steps to fully automate tasks with minimal user configuration.


```yaml
  This job only calls the command
executor: tag-build-deploy-executor
parameters:
    merge-trigger-branch:
        type: string
        default: a-branch-that-shall-never-exist
    merge-destination-branch:
        type: string
        default: a-branch-that-shall-never-exist
    fingerprints:
        type: string
    projectName:
        type: string
    git-branch:
        type: string
steps:
    - tag-build-deploy:
          merge-trigger-branch: << parameters.merge-trigger-branch >>
          merge-destination-branch: << parameters.merge-destination-branch >>
          fingerprints: << parameters.fingerprints >>
          projectName: << parameters.projectName >>
          git-branch: << parameters.git-branch >>
```

## See:
 - [Orb Author Intro](https://circleci.com/docs/2.0/orb-author-intro/#section=configuration)
 - [How To Author Commands](https://circleci.com/docs/2.0/reusing-config/#authoring-parameterized-jobs)
 - [Node Orb "test" Job](https://github.com/CircleCI-Public/node-orb/blob/master/src/jobs/test.yml)