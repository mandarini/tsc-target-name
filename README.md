# Change name of target

## What this is

This is a repo that shows that changing the name of a target to something else works.

The trick is to use the new name of the target when trying to call it.

## What I did

1. Generated a new `js` library that builds with `tsc`.
2. Changed the name of the `build` target to `katerina` in [`libs/mylib/project.json`](libs/mylib/project.json).

## How to use

1. `pnpm i` to install dependencies
2. `nx katerina mylib` to build the library

## How to see an error

`nx build mylib` gives you the expected error

```
npx nx build mylib --verbose

 >  NX   Cannot find configuration for task mylib:build


Error: Cannot find configuration for task mylib:build
    at ProcessTasks.createTask (/Users/katerina/Projects/nrwl/test_nx_workspaces/tscbuild/node_modules/.pnpm/nx@16.4.0/node_modules/nx/src/tasks-runner/create-task-graph.js:156:19)
    at ProcessTasks.processTasks (/Users/katerina/Projects/nrwl/test_nx_workspaces/tscbuild/node_modules/.pnpm/nx@16.4.0/node_modules/nx/src/tasks-runner/create-task-graph.js:23:39)
    at createTaskGraph (/Users/katerina/Projects/nrwl/test_nx_workspaces/tscbuild/node_modules/.pnpm/nx@16.4.0/node_modules/nx/src/tasks-runner/create-task-graph.js:192:21)
    at createTaskGraphAndValidateCycles (/Users/katerina/Projects/nrwl/test_nx_workspaces/tscbuild/node_modules/.pnpm/nx@16.4.0/node_modules/nx/src/tasks-runner/run-command.js:69:63)
    at /Users/katerina/Projects/nrwl/test_nx_workspaces/tscbuild/node_modules/.pnpm/nx@16.4.0/node_modules/nx/src/tasks-runner/run-command.js:94:31
    at Generator.next (<anonymous>)
    at /Users/katerina/Projects/nrwl/test_nx_workspaces/tscbuild/node_modules/.pnpm/tslib@2.5.3/node_modules/tslib/tslib.js:167:75
    at new Promise (<anonymous>)
    at Object.__awaiter (/Users/katerina/Projects/nrwl/test_nx_workspaces/tscbuild/node_modules/.pnpm/tslib@2.5.3/node_modules/tslib/tslib.js:163:16)
    at /Users/katerina/Projects/nrwl/test_nx_workspaces/tscbuild/node_modules/.pnpm/nx@16.4.0/node_modules/nx/src/tasks-runner/run-command.js:91:114
```

Since you changed the name of `build` to `katerina`, then it's expected that `nx build mylib` will fail. However, `nx katerina mylib` will work.
