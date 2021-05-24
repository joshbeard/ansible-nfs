# jbeard.dev / Homelab / Ansible / nfs

Ansible role for managing _nfs_ on my Homelab systems.

This is a _very_ rudimentary role with limited features.

__NOTE:__ This module isn't intended for general public use.

Refer to [`defaults/main.yml`](defaults/main.yml) for variables.


## Variables

### `nfs_exports`

List of exports in key/value pairs, where the key is the name of the file to
create under `/etc/exports.d/`

```yaml
nfs_exports:
  # This will create /etc/exports.d/movies.exports
  - movies: /store/movies 10.0.13.0/24(sync,rw,no_subtree_check,no_root_squash)
  # This will create /etc/exports.d/tvshows.exports
  - tvshows: /store/tvshows 10.0.13.0/24(sync,rw,no_subtree_check,no_root_squash)
```

### `nfs_exports_file`

List of lines to manage in `/etc/exports`
