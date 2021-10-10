# Jenkins with Ansible

Start of a template for installing and configuring a jenkins and jdk.

## Parameters

 * `jenkins_version` - Version of Jenkins
 * `jenkins_download_url` - URL of war for install
 * `jenkins_download_sha256` - Checksum of war file

And ansible-jdk parameters:
 * `jdk_version` - Version of JDK
 * `jdk_download_url` - URL of tar.gz for release
 * `jdk_download_sha256` - Checksum of tar.gz for release

## Testing

Credit: Tested with vagrant image from [@geerlingguy's Ansible for Devops](https://github.com/geerlingguy/ansible-for-devops)

### Initial Install
```
vagrant up
```

### Reapply provisioning
```
vagrant provision
```

## TODO

 * Remove ca-certificates update when no longer necessary
 * Improve systemd script
 * Set initial password
 * Install desired plugins