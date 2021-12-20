github-get-files
=========

Get files from github repo

Role Variables
--------------

### required
```
github_get_files_repo_name:  full_name of repo (example: octocat/Hello-World)
github_get_files_dest:       directory full path to download to
```

### optional
```
github_get_files_token:             github token (example: ghp_qweASDzxc...)
github_get_files_branch:            branch name. default branch will be used if not defined
github_get_files_force:             will download the file every time and replace the file if the contents change (get_url 'force' parameter)
github_get_files_create_dest:       create destination if not exists
github_get_files_create_dest_mode:  set mode to directories when creating
github_get_files_recurse:           recursively set the specified file attributes on directory contents when creating destination
github_get_files_mode:              the permissions the resulting filesystem object should have (get_url 'mode' parameter)
github_get_files_skip_files:        list of files to skip download
```

### role internal variables
```
github_get_files_retries:       http requests retries (default: 3)
github_get_files_delay:         http requests delay (defaul: 5)
github_get_files_path_list:     initial list of repo files path (default: [])
github_get_files_http_headers:  initial dict of http headers (default: {Accept: "application/vnd.github.v3+json"})
```

Example Playbook
----------------

```yaml
---
- hosts: localhost
  roles:
    - github-get-files
  vars:
    github_get_files_repo_name: crashwind/docker-ps
    github_get_files_dest: /tmp/ansible/docker-ps
...
```
