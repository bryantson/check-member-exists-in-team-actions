# check-member-exists-in-team-actions

This GitHub Actions helps to check if a member exists in a team

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
      - name: University search
        id: check-member
        uses: check-member-exists-in-team-actions@v1.0
        with:
          team_slug: TEAM_NAME
          org_slug: ORGANIZATION_NAME
          gh_token: GitHub_TOKEN

      - name: Print if member exists
        run: |
          echo "Does member exists: ${{ steps.check-member.outputs.exists-in-team }}"

```
