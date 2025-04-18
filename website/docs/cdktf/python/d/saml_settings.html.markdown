---
layout: "tfe"
page_title: "Terraform Enterprise: tfe_saml_settings"
description: |-
  Get information on SAML Settings.
---


<!-- Please do not edit this file, it is generated. -->
# Data Source: tfe_saml_settings

Use this data source to get information about SAML Settings. It applies only to Terraform Enterprise and requires admin token configuration. See example usage for incorporating an admin token in your provider config.


## Example Usage

Basic usage:

```python
# DO NOT EDIT. Code generated by 'cdktf convert' - Please report bugs at https://cdk.tf/bug
from constructs import Construct
from cdktf import TerraformStack
#
# Provider bindings are generated by running `cdktf get`.
# See https://cdk.tf/provider-generation for more details.
#
from imports.tfe.data_tfe_saml_settings import DataTfeSamlSettings
from imports.tfe.provider import TfeProvider
class MyConvertedCode(TerraformStack):
    def __init__(self, scope, name):
        super().__init__(scope, name)
        TfeProvider(self, "tfe",
            hostname=hostname.string_value,
            token=token.string_value
        )
        admin = TfeProvider(self, "tfe_1",
            alias="admin",
            hostname=hostname.string_value,
            token=admin_token.string_value
        )
        DataTfeSamlSettings(self, "foo",
            provider=admin
        )
```

## Argument Reference

No arguments are required for this data source.

## Attributes Reference

The following attributes are exported:

* `id` - It is always `saml`.
* `enabled` - Whether SAML single sign-on is enabled.
* `debug` - Whether debug mode is enabled, which means that the SAMLResponse XML will be displayed on the login page.
* `team_management_enabled` - Whether Terraform Enterprise is set to manage team membership.
* `authn_requests_signed` - Whether `<samlp:AuthnRequest>` messages are signed.
* `want_assertions_signed` - Whether `<saml:Assertion>` elements are signed.
* `idp_cert` - PEM encoded X.509 Certificate as provided by the IdP configuration.
* `old_idp_cert` - Previous version of the PEM encoded X.509 Certificate as provided by the IdP configuration.
* `slo_endpoint_url` - Single Log Out URL.
* `sso_endpoint_url` - Single Sign On URL.
* `attr_username` - Name of the SAML attribute that determines the user's username.
* `attr_groups` - Name of the SAML attribute that determines team membership.
* `attr_site_admin` - Site admin access role.
* `site_admin_role` - Site admin access role.
* `sso_api_token_session_timeout` - Single Sign On session timeout in seconds.
* `acs_consumer_url` - ACS Consumer (Recipient) URL.
* `metadata_url` - Metadata (Audience) URL.
* `certificate` - Request and assertion signing certificate.
* `certificate` - Request and assertion signing certificate.
* `private_key` - The private key used for request and assertion signing.
* `signature_signing_method` - Signature Signing Method.
* `signature_digest_method` - Signature Digest Method.

<!-- cache-key: cdktf-0.20.8 input-2995e79c51b29afd8d8b89c5d98dae47701709e1502f993d5be8b2b681de4895 -->