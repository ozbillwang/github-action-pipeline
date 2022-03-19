# github-action-pipeline
Sample to manage the releaess with Github Action

# Pipelines with several stage

Suppose we have two main branches, `dev` and `master`

| Stage   |      Description      |  Branches | Notes |
|----------|:-------------:|:-------------:|:-------------:|
| Test  | two conditions: (1) new commits is pushed to feature branches (not dev or master branches) (2) pull request to dev or master branches| feature branches, not dev or master branches | Test can be unit tests, integration test, lint, etc |
| Dev |    trigger the build and deployment to dev environment when new commit is pushed to Dev  |  dev  |  |
| Prod |    trigger the build when new push to master, if successful, tag the commit |  master  |  |
| versioning deployment |    trigger the production deployment when new tag is pushed to master branch |  master  |  |
