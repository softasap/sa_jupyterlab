When we are developing ansible roles we should follow the conventions below.

## Roles
### Role name
Role name should be in the format of `sa_<service_name>`

## Tasks

We should use fully qualified names for modules, as per ansible documentation.
When calling a module, always specify name in a format  GOAL | What step does.

Example:
```
- name: GIT | Install modern git ppa repo
```

usually goal is the word after tasks_, in tasks file name, like GIT for tasks_git.yml

### Arguments

When calling a module, do not pass arguments in the same line inline,
prefer yaml style with sub-nodes.


