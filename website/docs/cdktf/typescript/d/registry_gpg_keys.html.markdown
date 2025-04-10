---
layout: "tfe"
page_title: "Terraform Enterprise: tfe_registry_gpg_keys"
description: |-
  Get information on private registry GPG keys of an organization.
---


<!-- Please do not edit this file, it is generated. -->
# Data Source: tfe_registry_gpg_key

Use this data source to get information about all private registry GPG keys of an organization.

## Example Usage

```typescript
// DO NOT EDIT. Code generated by 'cdktf convert' - Please report bugs at https://cdk.tf/bug
import { Construct } from "constructs";
import { TerraformStack } from "cdktf";
/*
 * Provider bindings are generated by running `cdktf get`.
 * See https://cdk.tf/provider-generation for more details.
 */
import { DataTfeRegistryGpgKeys } from "./.gen/providers/tfe/data-tfe-registry-gpg-keys";
class MyConvertedCode extends TerraformStack {
  constructor(scope: Construct, name: string) {
    super(scope, name);
    new DataTfeRegistryGpgKeys(this, "all", {
      organization: "my-org-name",
    });
  }
}

```

## Argument Reference

The following arguments are supported:

* `organization` - (Optional) Name of the organization. If omitted, organization must be defined in the provider config.

## Attributes Reference

* `keys` - List of GPG keys in the organization. Each element contains the following attributes:
  * `id` - ID of the GPG key.
  * `organization` - Name of the organization.
  * `asciiArmor` - ASCII-armored representation of the GPG key.
  * `createdAt` - The time when the GPG key was created.
  * `updatedAt` - The time when the GPG key was last updated.

<!-- cache-key: cdktf-0.20.8 input-985032e5d21704bbf9d65466c89a423c9765fcddc79c819677b5b011797a49e7 -->