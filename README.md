# check-member-exists-in-team-actions

This GitHub Actions helps to check if a member exists in a GitHub Team

### How to run?

```yaml
name: Test custom GitHub Action

on:
  workflow_dispatch:

jobs:
  check-member:
    runs-on: ubuntu-latest
    name: Check if an user exists
    steps:
      - name: Check if member exists
        id: check-member
        uses: bryantson/check-member-exists-in-team-actions@1.0
        with:
          team_slug: SOME_TEAM_NAME
          org_slug: SOME_ORG_NAME
          gh_token: ${{ secrets.GH_TOKEN }}
          username: SOME_USER_NAME

      - name: Print whether member exists
        run: |
          echo "Does member exists: ${{ steps.check-member.outputs.exists-in-team }}"
```
