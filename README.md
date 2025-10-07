# RunReveal Detection Sync

A Github Action that will run `runreveal detections lint` on your RunReveal detections.

## Usage

```yaml
- name: lint-runreveal-detections
  uses: runreveal/detection-lint-action@v1
  with:
    # The relative path expression to your sigma detections
    # Defaults to all files in a directory named `sigma`.
    sigma-pattern: '**/sigma/*'

    # The relative path expression to your SQL detections.
    # Defaults to all .sql files in the repository.
    sql-pattern: '**/*.sql'

    # A RunReveal API token generated with detection edit permissions
    # For best results generate your token with the `cibot` role. 
    token: ${{ secrets.RUNREVEAL_TOKEN }}

    # The RunReveal workspace ID to sync the detections with.
    # This workspace should match the workspace the token was generated under.
    workspace: ${{ vars.RUNREVEAL_WORKSPACE }}
```
