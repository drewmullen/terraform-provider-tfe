---
layout: "tfe"
page_title: "Terraform Enterprise: tfe_no_code_module"
description: |-
  Manages no code settings for registry modules
---


<!-- Please do not edit this file, it is generated. -->
# tfe_no_code_module

Creates, updates and destroys no-code module for registry modules.

## Example Usage

Basic usage:

```typescript
// DO NOT EDIT. Code generated by 'cdktf convert' - Please report bugs at https://cdk.tf/bug
import { Construct } from "constructs";
import { Token, TerraformStack } from "cdktf";
/*
 * Provider bindings are generated by running `cdktf get`.
 * See https://cdk.tf/provider-generation for more details.
 */
import { NoCodeModule } from "./.gen/providers/tfe/no-code-module";
import { Organization } from "./.gen/providers/tfe/organization";
import { RegistryModule } from "./.gen/providers/tfe/registry-module";
class MyConvertedCode extends TerraformStack {
  constructor(scope: Construct, name: string) {
    super(scope, name);
    const foobar = new Organization(this, "foobar", {
      email: "admin@company.com",
      name: "my-org-name",
    });
    const tfeRegistryModuleFoobar = new RegistryModule(this, "foobar_1", {
      moduleProvider: "my_provider",
      name: "test_module",
      organization: foobar.id,
    });
    /*This allows the Terraform resource name to match the original name. You can remove the call if you don't need them to match.*/
    tfeRegistryModuleFoobar.overrideLogicalId("foobar");
    const tfeNoCodeModuleFoobar = new NoCodeModule(this, "foobar_2", {
      organization: foobar.id,
      registryModule: Token.asString(tfeRegistryModuleFoobar.id),
    });
    /*This allows the Terraform resource name to match the original name. You can remove the call if you don't need them to match.*/
    tfeNoCodeModuleFoobar.overrideLogicalId("foobar");
  }
}

```

Creating a no-code module with variable options:

```typescript
// DO NOT EDIT. Code generated by 'cdktf convert' - Please report bugs at https://cdk.tf/bug
import { Construct } from "constructs";
import { Token, TerraformStack } from "cdktf";
/*
 * Provider bindings are generated by running `cdktf get`.
 * See https://cdk.tf/provider-generation for more details.
 */
import { NoCodeModule } from "./.gen/providers/tfe/no-code-module";
import { Organization } from "./.gen/providers/tfe/organization";
import { RegistryModule } from "./.gen/providers/tfe/registry-module";
class MyConvertedCode extends TerraformStack {
  constructor(scope: Construct, name: string) {
    super(scope, name);
    const foobar = new Organization(this, "foobar", {
      email: "admin@company.com",
      name: "my-org-name",
    });
    const tfeRegistryModuleFoobar = new RegistryModule(this, "foobar_1", {
      moduleProvider: "my_provider",
      name: "test_module",
      organization: foobar.id,
    });
    /*This allows the Terraform resource name to match the original name. You can remove the call if you don't need them to match.*/
    tfeRegistryModuleFoobar.overrideLogicalId("foobar");
    const tfeNoCodeModuleFoobar = new NoCodeModule(this, "foobar_2", {
      organization: foobar.id,
      registryModule: Token.asString(tfeRegistryModuleFoobar.id),
      variableOptions: [
        {
          name: "ami",
          options: ["ami-0", "ami-1", "ami-2"],
          type: "string",
        },
        {
          name: "region",
          options: ["us-east-1", "us-east-2", "us-west-1"],
          type: "string",
        },
      ],
    });
    /*This allows the Terraform resource name to match the original name. You can remove the call if you don't need them to match.*/
    tfeNoCodeModuleFoobar.overrideLogicalId("foobar");
  }
}

```

## Argument Reference

The following arguments are supported:

- `name` - (Required) Name of the variable set.
- `organization` - (Optional) Name of the organization. If omitted, organization must be defined in the provider config.
- `registryModule` - (Required) The ID of the registry module to associate with the no code module.
- `enabled` - (Required) Whether or not no-code module is enabled for the associated registry module
- `versionPin` - (Optional) The version of the module to pin to.
- `variableOptions` - (Optional) A list of variable options to associate with the no code module.
  - `name` - (Required) The name of the variable option.
  - `type` - (Required) The type of the variable option.
  - `options` - (Required) A list of options for the variable option.

## Attributes Reference

- `id` - The ID of the no code module.

## Import

No-code modules can be imported; use `<NO CODE MODULE ID>` as the import ID. For example:

```shell
terraform import tfe_no_code_module.test nocode-qV9JnKRkmtMa4zcA
```

<!-- cache-key: cdktf-0.20.8 input-1204d286dd93ad6b8890ea46ff233ae490bae459320c56bddd6dbe876dc0cdb5 -->