github-get-files
=========

Get files from github repo

Role Variables
--------------

### required
repo_name:        full_name of repo (example: octocat/Hello-World)
dest:             directory full path to download to

### optional
token:            github token (example: ghp_qweASDzxc...)
branch:           branch name. default branch will be used if not defined
force:            will download the file every time and replace the file if the contents change (get_url 'force' parameter)
create_dest:      create destination if not exists
create_dest_mode: set mode to directories when creating
recurse:          recursively set the specified file attributes on directory contents when creating destination
mode:             the permissions the resulting filesystem object should have (get_url 'mode' parameter)
skip_files:       list of files to skip download

### role internal variables
github_get_files_retries:       http requests retries (default: 3)
github_get_files_delay:         http requests delay (defaul: 5)
github_get_files_path_list:     initial list of repo files path (default: [])
github_get_files_http_headers:  initial dict of http headers (default: {Accept: "application/vnd.github.v3+json"})

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

```
---
- hosts: localhost
  roles:
    - github-get-files
  vars:
    repo_name: crashwind/docker-ps
    dest: /tmp/ansible/docker-ps
...
```
