---
id: "ecf8e9fa-7d0d-4dc5-ae30-9b4bf24d8a64"
title: "Generic OAuth authentication (JWT)"
slug: "security-configuration-guide-6-6-generic-oauth-authentication-jwt-1"
category: "Authentication mechanisms and user stores"
category_path:
  - "Product guides"
  - "Security configuration"
  - "Authentication mechanisms and user stores"
status: "published"
content_type: "block"
version: 1
public_version: 1
created_at: "2026-01-07T13:45:19.559Z"
modified_at: "2026-01-07T13:49:26.008Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/security-configuration-guide-6-6-generic-oauth-authentication-jwt-1"
synced_at: "2026-01-28T20:40:15.241Z"
checksum: "1f11af485d64a671"
---

With the generic OAuth backend, Doxee applications can validate JWT based OAuth access tokens and use them for authentication, and even generate their own custom OAuth JWT tokens to access other services.

This authentication type uses the `Bearer` authentication scheme.

## Authentication Configuration
`&lt;oauth&gt;
  &lt;signature&gt; &lt;!--1--&gt;
    &lt;keys:publicKey alias="..." /&gt;
  &lt;/signature&gt;

  &lt;decryption&gt; &lt;!--2--&gt;
    &lt;keys:privateKey alias="myKey" /&gt;
  &lt;/decryption&gt;

  &lt;jwkSet&gt;...&lt;/jwkSet&gt; &lt;!--3--&gt;
  &lt;jwtType&gt;...&lt;/jwtType&gt; &lt;!--4--&gt;
  &lt;iss&gt;...&lt;/iss&gt; &lt;!--5--&gt;
  &lt;aud&gt;...&lt;/aud&gt; &lt;!--6--&gt;
  &lt;validateTimeout&gt;true&lt;/validateTimeout&gt; &lt;!--7--&gt;

  &lt;requiredClaims&gt; &lt;!--8--&gt;
    &lt;claim&gt;...&lt;/claim&gt;
  &lt;/requiredClaims&gt;

  &lt;validateClaims&gt; &lt;!--9--&gt;
    &lt;validation claim="..." validation="any|all"&gt;
      &lt;value&gt;...&lt;/value&gt;
    &lt;/validation&gt;
  &lt;/validateClaims&gt;

  &lt;groupsClaim&gt;...&lt;/groupsClaim&gt; &lt;!--10--&gt;
  &lt;groupsSeparator&gt;...&lt;/groupsSeparator&gt; &lt;!--11--&gt;

  &lt;customAttributes&gt; &lt;!--12--&gt;
    &lt;attribute name="..." claim="..." /&gt;
  &lt;/customAttributes&gt;
&lt;/oauth&gt;`Parameter

Description

**signature [1]**

An optional public key for signature validation. If no key store is specified, the default key store is used. If no alias is specified, the token’s `kid` (key ID) claim is used to find the matching key. If a signature key is specified, incoming tickets are required to have a matching signature.

**decryption [2]**

An optional private key to decrypt tokens. If specified, tokens may be encrypted using the matching public key. If not specified, encrypted tokens are not supported. If a decryption key is specified, incoming tickets are required to be encrypted with the matching public key.

**jwkSet [3]**

An optional URL of a JWK set used for validating tokens. If this is specified, signature public keys will be read from the JWK set found at this URL, and the signature key reference will be ignored.

**jwtType [4]**

The expected JWT type. If set, incoming tokens are required to have the same type in the JWT header.

**iss [5]**

The expected issuer. If set, an incoming token's issuer must match.

**aud [6]**

The expected audience. If set, an incoming token must have an audience claim, and one of its values must match this one.

**validateTimeout [7]**

Whether expired tokens should be rejected. Defaults to true.

**requiredClaims [8]**

A list of claims which must be present in the token.

**validateClaims [9]**

A list of claims which must have specific values in the token. The `validation` attribute can have the value `any` (at least one specified value must be in the token) or `all` (all specified values must be in the token).

**groupsClaim [10]**

If configured, each value of the specified claim in the token will be used as the name of a group to which the authenticated user belongs.

**groupsSeparator [11]**

By default, the groups claim is expected to be a string array with each individual string representing the name of the group. By setting this element, the groups claim is instead interpreted as a single string value and split using the specified separator. Each resulting string is then used as a group name.

**customAttributes [12]**

This element can be used to map custom claims to additional user attributes which can then be accessed by the Doxee applications.

## Credentials
`&lt;oauthCredentials&gt;
  &lt;signature&gt; &lt;!--1--&gt;
    &lt;keys:privateKey alias="..." /&gt;
  &lt;/signature&gt;

  &lt;encryption&gt; &lt;!--2--&gt;
    &lt;keys:publicKey alias="..." /&gt;
  &lt;/encryption&gt;

  &lt;jwtType&gt;...&lt;/jwtType&gt; &lt;!--3--&gt;
  &lt;kid&gt;...&lt;/kid&gt; &lt;!--4--&gt;
  &lt;sub&gt;...&lt;/sub&gt; &lt;!--5--&gt;
  &lt;iss&gt;...&lt;/iss&gt; &lt;!--6--&gt;

  &lt;aud&gt; &lt;!--7--&gt;
    &lt;audience&gt;...&lt;/audience&gt;
    ...
  &lt;/aud&gt;

  &lt;timeout&gt;...&lt;/timeout&gt; &lt;!--8--&gt;
  &lt;groupsClaim&gt;...&lt;/groupsClaim&gt; &lt;!--9--&gt;
  &lt;groupsSeparator&gt;...&lt;/groupsSeparator&gt; &lt;!--10--&gt;

  &lt;groups&gt;
    &lt;group&gt;...&lt;/group&gt; &lt;!--11--&gt;
    ...
  &lt;/groups&gt;

  &lt;customClaims&gt; &lt;!--12--&gt;
    &lt;claim name="..."&gt;
      &lt;value&gt;...&lt;/value&gt;
      ...
    &lt;/claim&gt;
    ...
  &lt;/customClaims&gt;

  &lt;ticket&gt;...&lt;/ticket&gt; &lt;!--13--&gt;

  &lt;oauthConfig&gt;...&lt;/oauthConfig&gt; &lt;!--14--&gt;
&lt;/oauthCredentials&gt;`Field

Description

**signature [1]**

Specifies a private key that will be used to sign the tickets. If not specified, the ticket is not signed.

**encryption [2]**

Specifies a public key that will be used to encrypt the tickets. If not specified, the ticket is not encrypted.

**jwtType [3]**

Sets the type of the created JWT tickets.

**kid [4]**

The JWT key ID. If not specified, the `kid` claim of the generated JWTs will be set to the alias of the signature key (if one is set).

**sub [5]**

The subject of the created JWTs (mandatory).

**iss [6]**

The issuer of the created JWTs.

**aud [7]**

The audience of the created JWTs.

**timeout [8]**

An optional timeout for the created JWTs, relative to the time at which they were created (e.g. `60s` or `15m`).

**groupsClaim [9]**

The name of the JWT claim which will be used to provide user group names (see below).

**groupsSeparator [10]**

By default, group names will be provided as an array in the groups claim specified above. If a separator is set, the group names will instead be concatenated to a single string value using the separator.

**groups [11]**

The names of user groups that should be included in the created JWTs.

**customClaims [12]**

Additional custom claims to set in the created JWTs.

**ticket [13]**

A complete, encoded access token. If specified, this token is used instead of generating new ones using the information provided in the other fields.

**oauthConfig [14]**

The optional credentials configuration:

`&lt;oauthConfig&gt;
  &lt;signature&gt;
    &lt;keys:privateKey alias="..." /&gt;
  &lt;/signature&gt;

  &lt;encryption&gt;
    &lt;keys:publicKey alias="..." /&gt;
  &lt;/encryption&gt;

  &lt;jwtType&gt;...&lt;/jwtType&gt;
  &lt;iss&gt;...&lt;/iss&gt;

  &lt;aud&gt;
    &lt;audience&gt;...&lt;/audience&gt;
  &lt;/aud&gt;

  &lt;timeout&gt;...&lt;/timeout&gt;
  &lt;groupsClaim&gt;...&lt;/groupsClaim&gt;
  &lt;groupsSeparator&gt;...&lt;/groupsSeparator&gt;

  &lt;customClaims&gt;
    &lt;claim name="..."&gt;
      &lt;value&gt;...&lt;/value&gt;
    &lt;/claim&gt;
  &lt;/customClaims&gt;
&lt;/oauthConfig&gt;`All elements in the credentials configuration provide default values. Any values that are not specified in the credentials will be taken from the credentials configuration.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}