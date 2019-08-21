## Welcome to "Hello World" with GitHub Actions

This course will walk you through writing your first action and using it with a workflow file. 

## Github

### Branch Permissions

[Configuring protected branches](https://help.github.com/en/articles/configuring-protected-branches)
[About required reviews for pull requests](https://help.github.com/en/articles/about-required-reviews-for-pull-requests)

## Docker

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

## Script Header

[What is the difference between #!/bin/sh and #!/bin/bash?](https://askubuntu.com/a/141997/349745)

* `#!/bin/sh` - system shell (default)
* `#!/bin/bash` - bash shell

## Running a script

1. The interpreter process needs to read the file
2. It checks if it is marked as executable

