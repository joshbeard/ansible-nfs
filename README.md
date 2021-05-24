# jbeard.nfs Ansible Role

Ansible role for managing _nfs_ exports.

Refer to [`defaults/main.yml`](defaults/main.yml) for variables.

## Variables

### `nfs_exports`

List of exports in key/value pairs, where the key is the name of the file to
create under `/etc/exports.d/`

```yaml
nfs_exports:
  # This will create /etc/exports.d/movies.exports
  - movies: /store/movies 10.0.10.0/24(sync,rw,no_subtree_check,no_root_squash)
  # This will create /etc/exports.d/tvshows.exports
  - tvshows: /store/tvshows 10.0.10.0/24(sync,rw,no_subtree_check,no_root_squash)
```

### `nfs_exports_file`

List of lines to manage in `/etc/exports`
