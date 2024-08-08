# README for the `githooks` Directory

This is the directory for git hooks that can be used in any project. They are located here, since `.git/hooks` is not under version control.

Here is a description of the hooks and how to use them.

## `prepare-commit-msg` hook

This hook checks that a commit is signed. If not, it prints an error message and exits with status 1. Using this hook saves you the trouble of having to retroactively sign your commits when a PR fails because the _DCO_ plugin rejects unsigned commits. Hence, we recommend installing it in your local repo clones. 

To use it do one of the following.

### You Have a Local Clone of the `community` Repo

Change to the root directory of your "target" repo clone, for example, `granite-code-cookbook`. Assuming that `community` is a sibling directory, run this command:

```shell
cp ../community/githooks/prepare-commit-msg .git/hooks
```

### If You Don't Have a Local Clone of the `community` Repo

In this case, create a new file in your editor, `.git/hooks/prepare-commit-msg` (starting in the root directory of your local clone of another repo).

Copy the contents of [the file in GitHub]() and paste it into the file.

### How It Works

Once installed, if you attempt to commit a change without using the `-s` flag for signing, the commit will fail with this error:

```
Error: Commits must be signed off. For example, add "-s" to your commit command:
  git commit -s -m "comment" ...

For more information, see:
https://github.com/granite-cookbooks/community/blob/main/CONTRIBUTING.md#legal
```




