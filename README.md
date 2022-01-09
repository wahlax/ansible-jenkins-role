# Jenkins with Ansible

Role installing and configuring a jenkins and jdk.

## Required Parameters (provide via vault)

 * `jenkins_admin_username` - admin username
 * `jenkins_admin_password` - admin password
 * `jenkins_global_secrets` - list of items as show below

```
jenkins_global_secrets:
  - name: test1-secret
    description: this is test 1
    text: test1-secret-value
```

## Optional Parameters

 * `jenkins_version` - Version of Jenkins
 * `jenkins_download_url` - URL of war for install
 * `jenkins_download_sha256` - Checksum of war file
 * `jenkins_install_path` - Install path of jenkins
 * `jenkins_local_url` - URL for localhost
 * `jenkins_extra_params` - Extra params for jenkins cli
 * `jenkins_selfsigned_cert` - yes/no for self-signed ssl cert (yes = disabled cert validation during install)

Optional ansible-jdk-role parameters:
 * `jdk_version` - Version of JDK
 * `jdk_download_url` - URL of tar.gz for release
 * `jdk_download_sha256` - Checksum of tar.gz for release

## Testing

Credit: Tested with vagrant image from [@geerlingguy's Ansible for Devops](https://github.com/geerlingguy/ansible-for-devops)

Run the following from the test directory:

### Initial Install
```
ansible-galaxy install -r requirements.yml
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
