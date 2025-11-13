# Forking and Setting Upstream for a Cloned Repository

## Forking a Repository

1. Navigate to the original repository on GitHub
2. Click the "Fork" button in the top-right corner
3. Select your account as the destination for the fork
4. GitHub creates a copy of the repository under your account

## Cloning Your Fork

```bash
git clone https://github.com/Ezecc/sumas-deep-learning
cd sumas-deep-learning
```

## Setting the Upstream Remote

After cloning your fork, configure the original repository as the upstream remote to keep your fork synchronized:

```bash
# Add the original repository as upstream
git remote add upstream https://github.com/Ezecc/sumas-deep-learning

# Verify the remotes
git remote -v
```

You should see:

- `origin` - your fork (where you push changes)
- `upstream` - the original repository (where you pull updates)

## Keeping Your Fork Up-to-Date

```bash
# Fetch changes from upstream
git fetch upstream

# Checkout your main branch
git checkout main

# Merge upstream changes
git merge upstream/main

# Push updates to your fork
git push origin main
```

## Workflow Summary

1. Fork the repo on GitHub
2. Clone your fork locally
3. Add upstream remote pointing to the original repo
4. Make changes on feature branches
5. Keep your fork synced by fetching from upstream
6. Push your changes to origin (your fork)
7. Create pull requests from your fork to upstream
