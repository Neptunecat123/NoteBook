# Git 参考

## Setup and Config

### git

[git](https://git-scm.com/docs/git)

    git [--version] [--help] [-C <path>] [-c <name>=<value>]
        [--exec-path[=<path>]] [--html-path] [--man-path] [--info-path]
        [-p|--paginate|-P|--no-pager] [--no-replace-objects] [--bare]
        [--git-dir=<path>] [--work-tree=<path>] [--namespace=<name>]
        [--super-prefix=<path>]
        <command> [<args>]

### config

[git-config](https://git-scm.com/docs/git-config)

获取和设置存储库或全局配置

    git config [<file-option>] [--type=<type>] [--show-origin] [--show-scope] [-z|--null] name [value [value_regex]]
    git config [<file-option>] [--type=<type>] --add name value
    git config [<file-option>] [--type=<type>] --replace-all name value [value_regex]
    git config [<file-option>] [--type=<type>] [--show-origin] [--show-scope] [-z|--null] --get name [value_regex]
    git config [<file-option>] [--type=<type>] [--show-origin] [--show-scope] [-z|--null] --get-all name [value_regex]
    git config [<file-option>] [--type=<type>] [--show-origin] [--show-scope] [-z|--null] [--name-only] --get-regexp name_regex [value_regex]
    git config [<file-option>] [--type=<type>] [-z|--null] --get-urlmatch name URL
    git config [<file-option>] --unset name [value_regex]
    git config [<file-option>] --unset-all name [value_regex]
    git config [<file-option>] --rename-section old_name new_name
    git config [<file-option>] --remove-section name
    git config [<file-option>] [--show-origin] [--show-scope] [-z|--null] [--name-only] -l | --list
    git config [<file-option>] --get-color name [default]
    git config [<file-option>] --get-colorbool name [stdout-is-tty]
    git config [<file-option>] -e | --edit

### help

### bugreport

## Getting and Creating Projects

### init

### clone

## Basic Snapshotting

### add

### status

### diff

### commit

### notes

### restore

### reset

### rm

### mv

## Branching and Merging

### branch

### checkout 

### switch

### merge

### mergetool

### log

### stash

### tag

### worktree

## Sharing and Updating Projects

### fetch

### pull

### push

### submodule

## Inspection and Comparison

### show

### log

### diff

### difftool

### range-diff

### shortlog

### describe

## Patching

### apply

### cherry-pick

### diff

### rebase

### revert

## Debugging

### bisect

### blame

### grep

## To be continued...