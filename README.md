# Logwatch Role for Ansible

This role installs Logwatch which is an application that helps with simple log
management by daily analyzing and reporting a short digest from activities taking place on your server.

## Requirements

This role requires [Ansible](http://www.ansibleworks.com/) version 2.0 or higher and the Debian/Ubuntu platform.

## Role Variables

The variables that can be passed to this role and a brief description about
them are as follows:

```yaml
# Default output method for Logwatch reports
logwatch_output: "mail"

# Default output format for Logwatch reports
logwatch_format: "text"

# Default output encoding for Logwatch reports
logwatch_encode: "none"

# Default report email recipient
logwatch_admin_email: "root"

# Default report email sender
logwatch_sender_email: "Logwatch"

# The default time range for the report
logwatch_range: "yesterday"

# The default detail level for the report
logwatch_detail: "Med"

# The default system MTA
logwatch_mailer: "/usr/sbin/sendmail -t"

# The default directory where logs are found
logwatch_log_dir: '/var/log'

# The default directory where Logwatch keeps temp data
logwatch_tmp_dir: '/var/cache/logwatch'
```

## Examples

1. Install Logwatch with the defaults

    ```yaml
    ---
    # This playbook installs Logwatch

    - name: Install logwatch to all nodes
      hosts: all
      roles:
        - logwatch
    ```

2. Install Logwatch with custom settings

    ```yaml
    ---
    # This playbook installs Logwatch

    - name: Install logwatch to all nodes
      hosts: all
      roles:
        - { role: logwatch,
            logwatch_detail: "Low",
            logwatch_format: "Html"
          }
    ```

## Dependencies

None.
