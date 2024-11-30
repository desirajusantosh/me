---
title: "Git push using token"
weight: 2
resources:
params:
date: 2024-11-11T18:00:53-05:00
showDate: false
draft: false
tags: ["blog","howto"]
---

# Resolving GitHub Authentication Issues: Using Personal Access Tokens

Have you encountered this message when attempting to `git push`?


remote: Support for password authentication was removed on August 13, 2021.
remote: Please see https://docs.github.com/get-started/getting-started-with-git/about-remote-repositories#cloning-with-https-urls for information on currently recommended modes of authentication.
fatal: Authentication failed for 'https://github.com/desirajusantosh/<>'
text

Don't worry! GitHub has transitioned to more secure authentication methods. Here's how to resolve this issue using a Personal Access Token (PAT):

## Creating a Personal Access Token

1. Go to your GitHub account settings
2. Navigate to "Developer settings" > "Personal access tokens"
3. Click "Generate new token"
4. Set a descriptive name for your token
5. Choose an expiration date (or select "No expiration" if needed)
6. Select necessary scopes:
   - For most operations, the 'repo' scope is sufficient
   - This grants full control of private repositories
7. Click "Generate token" and copy it immediately

## Using Your Personal Access Token

Once you have your PAT, you can use it in place of your password for Git operations:

- When prompted for a password, use the PAT instead
- For HTTPS cloning, use this format:

git clone https://your-personal-access-token@github.com/username/repo.git

## Store credentials (optional):
Create a file at ~/.git-credentials with this line:
https://{username}:{personal_access_token}@github.com
Run: git config --global credential.helper store
