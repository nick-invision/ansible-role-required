# Required

A basic role that asserts variables are set and paths exist. Intended to run first in a playbook in order to fail-fast rather than wait until the task which requires the var or path is executed.

## Requirements

None

## Role Variables

No default vars are set, but if any of the below are found then the specified assertion is made.

```yaml
# if set, checks that var is defined and not zero length
required_vars
# if set, checks locally for presence of path
required_local_paths
# if set, checks on each remote for presence of path
required_remote_paths
```

## Dependencies

None

## Example Playbook

```yaml
- name: Validate Prerequisites
  include_role:
    name: nick_invision.required
  vars:
    required_vars:
      - an_important_var
      - another_important_var
```

```yaml
- name: Validate Prerequisites
  include_role:
    name: nick_invision.required
  vars:
    required_local_paths:
      - ~/something/locally/important.txt
      - something/locally/relatively/important.txt
      - /something/locally/absolutely/important.txt
```

```yaml
- name: Validate Prerequisites
  include_role:
    name: nick_invision.required
  vars:
    required_remote_paths:
      - ~/something/remote/important.txt
      - something/remote/relatively/important.txt
      - /something/remote/absolutely/important.txt
```

```yaml
- name: Validate Prerequisites
  include_role:
    name: nick_invision.required
  vars:
    required_vars:
      - an_important_var
      - another_important_var
    required_local_paths:
      - ~/something/locally/important.txt
      - something/locally/relatively/important.txt
      - /something/locally/absolutely/important.txt
    required_remote_paths:
      - ~/something/remote/important.txt
      - something/remote/relatively/important.txt
      - /something/remote/absolutely/important.txt
```

## License

MIT
