# Reusable GHWF-CD for Websites

Reusable workflow to pull new changes, build a new production build, and restart NGINX.

## Environment Variables

- `HOSTNAME`: **(Required)** IP Address of EC2
- `USER_NAME`: **(Required)** User of EC2
- `SSH_KEY`: **(Required)** SSH Key to Sign in with

## Example Usage

```yaml
name: Deploy Website

on:
  workflow_dispatch:

jobs:
  deploy:
    name: Deploy to EC2
    runs-on: ubuntu-latest
    environment: prod
    steps:
      - name: Call workflow to deploy to EC2
        uses: Cloud-City-Computing/ghwf-cd@v1
        env:
          HOSTNAME: ${{ secrets.HOSTNAME }}
          USER_NAME: ${{ secrets.USER_NAME }}
          SSH_KEY: ${{ secrets.SSH_KEY }}
```
