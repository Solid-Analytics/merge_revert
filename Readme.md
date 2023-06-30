# Instructions to revert main to origial state

## Problem

Accidently pushed and merged a feature branch to the main rather than to the development branch.

### Solution

#### if you have not deleted the feature branch you have merged.

1. Checkout main branch, and run the following command:

```sh
git checkout main
```

2. Get the lastest main , and run the following command:

```sh
git pull
```

3. To get a list of commits you have on main branch. You need to scroll through commit list, to copy the commit id that you want to revert to, and run the following command:

```sh
git reflog
```

```sh
23d12e4 (HEAD -> main, origin/main, origin/development, development) HEAD@{0}: reset: moving to 23d12e4
87425bf HEAD@{1}: pull: Fast-forward
23d12e4 (HEAD -> main, origin/main, origin/development, development) HEAD@{2}: reset: moving to 23d12e4
87425bf HEAD@{3}: pull: Fast-forward
23d12e4 (HEAD -> main, origin/main, origin/development, development) HEAD@{4}: reset: moving to 23d12e4
87425bf HEAD@{5}: reset: moving to 87425bffcebc909dd489110f4e620e0145f8f532
145163a (origin/feature-3, feature-3) HEAD@{6}: reset: moving to 145163aa0f54038221aabdb15fe8e35615a3f984

```

4. Revert all changes & revert back to actual content at specific commit id eg: 23d12e4. Run the following command:

```sh
git reset --hard 23d12e4
```

5. Push the specific state to the GitHub Repo. Run the following command:

```sh
git push origin main --force
```
