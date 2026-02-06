---
id: "ba8a1d32-d61d-479f-b525-9e7fe3612e1e"
title: "SSH keys"
slug: "security-configuration-guide-6-6-ssh-keys-1"
category: "Authentication mechanisms and user stores"
category_path:
  - "Product guides"
  - "Security configuration"
  - "Authentication mechanisms and user stores"
status: "published"
content_type: "block"
version: 1
public_version: 1
created_at: "2026-01-07T13:45:19.639Z"
modified_at: "2026-01-07T13:49:26.008Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/security-configuration-guide-6-6-ssh-keys-1"
synced_at: "2026-01-28T20:40:15.923Z"
checksum: "474baf99a0833bec"
---

SSH key authentication is available for the SFTP protocol. It pairs a user name with an OpenSSH key file, which can be optionally secured with a password.

This authentication type uses the `SshKeys` authentication scheme.

Since SSH keys can currently only be used for accessing SFTP servers, no authentication configuration is available.

## Credentials
SSH key authentication uses SSH key credentials:

`&lt;sshKeyCredentials xmlns="http://www.infinica.com/credentials"
    username="..."
    url="..."
    password="..." /&gt;``username` and `url` are required; the URL may be specified as a relative path from the containing configuration file. It should point to an OpenSSH key file containing the private key for the specified user name.

If the key file is password protected, the password must be specified as well.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}