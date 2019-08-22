## Welcome to "Hello World" with GitHub Actions

This course will walk you through writing your first action and using it with a workflow file. 

## Github

* [Automating your workflow with GitHub Actions](https://help.github.com/en/categories/automating-your-workflow-with-github-actions)
* [Learning Lab](https://github.com/marketplace/github-learning-lab)
  * [Learning Lab - Actions](https://lab.github.com/github/hello-github-actions!)

### Branch Permissions

[Configuring protected branches](https://help.github.com/en/articles/configuring-protected-branches)
[About required reviews for pull requests](https://help.github.com/en/articles/about-required-reviews-for-pull-requests)

## Docker

[Docker Hub Debian](https://hub.docker.com/_/debian)

* [Install Docker Desktop](https://hub.docker.com/?overlay=onboarding)
  * [Docker Desktop requires Win 10 Pro](https://stackoverflow.com/q/49677610/1366033)
    * [Upgrade Win 10 Home -> Pro](https://support.microsoft.com/en-us/help/12384/windows-10-upgrading-home-to-pro)

## Bash Script

[What does `chmod +x filename` do and how do I use it?](https://askubuntu.com/q/443789/349745)
[`chmod u+x` versus `chmod +x`](https://askubuntu.com/q/29589/349745)

[https://ss64.com/bash/chmod.html]:

> **`chmod`**
> Change access permissions, **ch**ange **mo**de


### Syntax

```bash
chmod [Options]... Mode [,Mode]... file...
```

### Mode

```
<user><operator><permission>
```

#### User

| letter | User	                               |
|:------:|--------------------------------------|
|   u    | The user who owns it                 |
|   g    | Other users in the file's Group      |
|   o    | Other users not in the file's group  |
|   a    | All users                            |

where `a` is the default if no value is specified and `a` essentially equals `u` + `g` + `o`

#### Operator

| symbol | Operator	                      |
|:------:|--------------------------------|
|   +    | add selected permissions       |
|   -    | remove selected permissions    |
|   =    | only permissions for the file  |


#### Permission

| letter | Permission                              |
|:------:|-----------------------------------------|
|   r    | Read                                    |
|   w    | Write                                   |
|   x    | Execute (or access for directories)     |
|   X    | Execute only if the file is a directory |

#### Examples

```bash
chmod a-x file # Deny execute permission to everyone
chmod  +r file # Allow read permission to everyone
```

**Make script executable**:

```bash
chmod +x action-a/entrypoint.sh
```

[Get the chmod value for a file](https://unix.stackexchange.com/q/46915/128893)

```bash
stat -c %A action-a/entrypoint.sh
```

### Change Script Permissions on Windows

[Change file permissions when working with git repo’s on windows](https://medium.com/@akash1233/change-file-permissions-when-working-with-git-repos-on-windows-ea22e34d5cee)

[Updating file permissions with git-bash on Windows 7](https://stackoverflow.com/a/57584620/1366033)


1. Open up a bash terminal like git-bash on Windows
2. Navigate to the `.sh` file where you want to grant execute permissions
3. Check the existing permissions with the following command:

    ```bash
    git ls-files --stage 
    ```

    Which should return something like *100644*

4. Update the permissions with the following command

    ```bash
    git update-index --chmod=+x 'name-of-shell-script'
    ```

5. Check the file permission again 

    ```bash
    git ls-files --stage 
    ```

    Which should return something like *100755*

6. Commit changes and push!


## Script Header

[What is the difference between #!/bin/sh and #!/bin/bash?](https://askubuntu.com/a/141997/349745)

* `#!/bin/sh` - system shell (default)
* `#!/bin/bash` - bash shell

## Running a script

1. The interpreter process needs to read the file
2. It checks if it is marked as executable

