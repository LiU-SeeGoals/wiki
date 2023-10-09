## Feature Branch Integration

### Feature Branch Creation
Create feature branch by linking it to an issue. This can be done when editing the issue.
Creating issue in this manner will give it a identifier number.

### Writing Commits
If feature branch has specific a identifier number - start commit with "ID: <your message>"

### Squash Commits
Make sure to squash smaller commits before integration.

### Rebase
Use rebase, not merge! Workflow:
1. Rebase feature branch with destination branch on the feature branch.
2. Merge rebased feature branch into destination branch.
**NOTE** If many commits - squash them according previous heading.