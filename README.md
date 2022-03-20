# github-action-pipeline
Sample to manage the releaess with Github Action

# Pipelines with several stages

Suppose we have two main branches, `dev` and `master`

| Stage   |      Description      |  Branches | Notes |
|----------|:-------------|:-------------:|:-------------|
| Test  | two conditions: (1) new commit is pushed to feature branches (not dev or master branches) (2) pull request to dev or master branches| feature branches, not dev or master branches | Test can be unit tests, integration test, lint, etc |
| Dev |    trigger the build and deployment to dev environment when new commit is pushed to Dev  |  dev  | you can set more main branches if needed, such as staging, svt, qa, etc |
| Prod |    trigger the build when new push to master, generate a new semantic versioning tag and push it to the commit |  master  | main or master branch |
| Production deploy on new tag |    trigger the production deployment when new tag is pushed to master branch , wait for approval. If approved, will deploy to production|  master  |  |
| rollback | re-run the jobs on pervious tag/release |  master  |  |
