---
id: "2d721c8a-94fa-4e93-8e94-065707297ff1"
title: "Key Stores"
slug: "6-6-process-engine-administration-reference-key-stores"
category: "Administration guide"
category_path:
  - "Product guides"
  - "Previous versions"
  - "i-Edition 6.6"
  - "Process Engine"
  - "Administration guide"
status: "published"
content_type: "block"
version: 1
public_version: 1
created_at: "2025-08-04T10:14:46.761Z"
modified_at: "2025-08-20T18:57:09.556Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-administration-reference-key-stores"
synced_at: "2026-01-28T21:01:35.275Z"
checksum: "5eb0c3424345c039"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

Application may use key stores in various ways. For example, Infinica credentials rely on keys to sign their tokens, and Process Engine can use a key pair to allow users to store their credentials in Task Manager tasks created by a process.

If any of these features are used, one or more key stores must first be configured. These key stores can be created and maintained with Java’s standard `keytool` command line utility or other compatible applications.

## Configuring Key Stores
Key stores are configured in a `&lt;keyStores&gt;` element in the separate `keystores `namespace.

`&lt;keyStores xmlns="http://www.infinica.com/keystores"
    default="..."&gt; ①

  &lt;keyStore
      id="..." ②
      url="..." ③
      password="..." /&gt; ④
  ...
&lt;/keyStores&gt;`Most setups will only use a single key store, but multiple key stores can be configured if required. In this case, `default `[1] must be set to the ID of the key store that should be used if a key reference does not specify a key store ID.

Each `&lt;keyStore&gt;` element configures a single key store file. The `id` [2] may be omitted if only one key store is configured (and thus automatically serves as the default key store). Otherwise, each key store must have its own ID, one of which must be referenced by `defaultKeyStore`.

The `url` [3] attribute specifies the absolute URL of the key store file (relative URLs cannot currently be used).

`password `[4] sets the password required to access the key store.

> Tip

If the same key store configuration is shared by multiple applications, it can be stored in a separate file and referenced via XInclude.

### Auto-creating Key Stores
For quick test and demo setups, Doxee may be configured to automatically create key stores and key pairs.

> Caution

Auto creation should *never* be used for production systems. Automatically created key pairs may not fulfill the security standards required by your organisation.

Additionally, great care must be taken when using auto creation with more than one Doxee application. Key stores and key pairs are auto-created during application startup if they do not exist. Unless it is guaranteed that multiple applications start up in a strictly sequential manner, two applications may try to auto-create the same key store at the same time, leading to unexpected results or startup errors.

A key store is auto-created if its configuration contains an `&lt;autoCreate&gt;` element. During application startup, if the key store does not yet exist, it is automatically created. Additionally, if the the `&lt;autoCreate&gt;` element defines key pairs, ever key pair that is not yet found in the key store is created as well.

`&lt;keyStore ...&gt;
  &lt;autoCreate enabled="true"&gt; ①
    &lt;keyPair
        alias="..." ②
        password="..." ③
        algorithm="..." ④
        provider="..." ⑤
        size="..." ⑥
        issuer="..." ⑦
        subject="..." ⑧
        expirationDate="..." /&gt; ⑨
    ...
  &lt;/autoCreate&gt;
&lt;/keyStore&gt;`Auto-creation may be disabled by setting `enabled `[1] to `false `(if not specified, it defaults to `true`).

Each `&lt;keyPair&gt;` element must configure the key pair to be created with the following attributes:

`alias`

The alias of the key pair in the key store.

`password`

The password for the key pair, if it differs from that of the key store.

`algorithm`

Key pair algorithm (defaults to `RSA`).

`provider`

The Java provider used to generate keys (defaults to `BC`, Bounce Castle’s default provider).

`size`

Key size in bytes (defaults to 4096).

`issuer`

Issuer DN (defaults to `cn=infinica`).

`subject`

Subject DN (defaults to `dc=infinica`).

`expirationDate`

Key pair expiration date, e.g. `2021-01-03T22:00:00`. If not specified, this defaults to a timestap one hundred years in the future.

## Referencing Keys
Once a key store has been configured, elements that require keys may reference it using key `references`. Each reference selects either a public or a private key:

`&lt;keys:publicKey
    keyStore="..." ①
    alias="..." ②
    password="..." /&gt; ③````
&lt;keys:privateKey
    keyStore="..." ①
    alias="..." ②
    password="..." /&gt; ③
```> Note

The `keys`prefix must be mapped to the namespace `http://www.infinica.com/keystores`

`keyStore `[1] must be the ID of a configured key store. If not specified, the default key store is used. `alias `[2] is required and specifies the alias of the referenced key in the key store. If that key’s password differs from the key store’s main password, it must be specified in the `password `attribute [3].

> Tip

Most setups use a single key store without individual key passwords. In this case, each key reference only has to specify the alias of its key.

Java key stores can contain different types of entries. Depending on the target entry referenced by the alias, public key and private key references are resolved in different ways:

- For *key pair* entries, `&lt;privateKey&gt;` selects the private key and `&lt;publicKey&gt;` selects the public key, i.e. the first certificate from its certificate chain.

- For *certificates*, `&lt;publicKey&gt;` selects the certificate and `&lt;privateKey&gt;` selects nothing.

- For *symmetric keys*, `&lt;publicKey&gt;` selects the certificate and `&lt;privateKey&gt;` selects nothing.

> Tip

As can be seen, `&lt;privateKey&gt;` references only work when the referenced key store entry is a key pair.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}