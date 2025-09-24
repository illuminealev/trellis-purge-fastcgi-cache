# Trellis Purge FastCGI Cache

This Ansible role provides FastCGI cache purging functionality for Trellis WordPress sites.

## Installation

Add this role to your Trellis project after the nginx role in `server.yml`:

```yaml
- { role: trellis-purge-fastcgi-cache, tags: [ trellis-purge-fastcgi-cache, nginx ], when: fastcgi_cache_enabled | default(false) }
```

## Configuration

Enable FastCGI cache purging in your site configuration by adding the following to `group_vars/production/wordpress_sites.yml` (or the appropriate environment):

```yaml
wordpress_sites:
  example.com:
    # ... existing config ...
    fastcgi_cache_enabled: true  # Already in Trellis
    fastcgi_cache_purge_enabled: true  # Your new option
```

## Author

[Yervand](https://github.com/y-soghomonyan) & [Tomek](https://github.com/tomektomczuk)