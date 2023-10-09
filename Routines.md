## Feature Branch Integration

### Writing Commits
If feature branch has specific a identifier number - start commit with "ID: <your message>"

### Squash Commits
Make sure to squash smaller commits before integration.
[Tutorial](https://www.youtube.com/watch?v=V5KrD7CmO4o)

### Rebase
Use rebase, not merge! Workflow:
1. Rebase feature branch with destination branch on the feature branch.
2. Merge rebased feature branch into destination branch.
**NOTE** If many commits - squash them according previous heading.