---
layout: "tfe"
page_title: "Terraform Enterprise: tfe_data_retention_policy"
description: |-
  Manages data retention policies for organizations and workspaces
---


<!-- Please do not edit this file, it is generated. -->
# tfe_data_retention_policy

Creates a data retention policy attached to either an organization or workspace. This resource is for Terraform Enterprise only.

## Example Usage

Creating a data retention policy for a workspace:

```typescript
// DO NOT EDIT. Code generated by 'cdktf convert' - Please report bugs at https://cdk.tf/bug
import { Construct } from "constructs";
import { TerraformStack } from "cdktf";
/*
 * Provider bindings are generated by running `cdktf get`.
 * See https://cdk.tf/provider-generation for more details.
 */
import { DataRetentionPolicy } from "./.gen/providers/tfe/data-retention-policy";
import { Organization } from "./.gen/providers/tfe/organization";
import { Workspace } from "./.gen/providers/tfe/workspace";
interface MyConfig {
  dontDelete: any;
}
class MyConvertedCode extends TerraformStack {
  constructor(scope: Construct, name: string, config: MyConfig) {
    super(scope, name);
    const testOrganization = new Organization(this, "test-organization", {
      email: "admin@company.com",
      name: "my-org-name",
    });
    const testWorkspace = new Workspace(this, "test-workspace", {
      name: "my-workspace-name",
      organization: testOrganization.name,
    });
    new DataRetentionPolicy(this, "foobar", {
      deleteOlderThan: [
        {
          days: 42,
        },
      ],
      workspaceId: testWorkspace.id,
      dontDelete: config.dontDelete,
    });
  }
}

```

Creating a data retention policy for an organization:

```typescript
// DO NOT EDIT. Code generated by 'cdktf convert' - Please report bugs at https://cdk.tf/bug
import { Construct } from "constructs";
import { TerraformStack } from "cdktf";
/*
 * Provider bindings are generated by running `cdktf get`.
 * See https://cdk.tf/provider-generation for more details.
 */
import { DataRetentionPolicy } from "./.gen/providers/tfe/data-retention-policy";
import { Organization } from "./.gen/providers/tfe/organization";
interface MyConfig {
  dontDelete: any;
}
class MyConvertedCode extends TerraformStack {
  constructor(scope: Construct, name: string, config: MyConfig) {
    super(scope, name);
    const testOrganization = new Organization(this, "test-organization", {
      email: "admin@company.com",
      name: "my-org-name",
    });
    new DataRetentionPolicy(this, "foobar", {
      deleteOlderThan: [
        {
          days: 1138,
        },
      ],
      organization: testOrganization.name,
      dontDelete: config.dontDelete,
    });
  }
}

```

Creating a data retention policy for an organization and exclude a single workspace from it:

```typescript
// DO NOT EDIT. Code generated by 'cdktf convert' - Please report bugs at https://cdk.tf/bug
import { Construct } from "constructs";
import { TerraformStack } from "cdktf";
/*
 * Provider bindings are generated by running `cdktf get`.
 * See https://cdk.tf/provider-generation for more details.
 */
import { DataRetentionPolicy } from "./.gen/providers/tfe/data-retention-policy";
import { Organization } from "./.gen/providers/tfe/organization";
import { Workspace } from "./.gen/providers/tfe/workspace";
interface MyConfig {
  dontDelete: any;
}
class MyConvertedCode extends TerraformStack {
  constructor(scope: Construct, name: string, config: MyConfig) {
    super(scope, name);
    const testOrganization = new Organization(this, "test-organization", {
      email: "admin@company.com",
      name: "my-org-name",
    });
    const testWorkspace = new Workspace(this, "test-workspace", {
      name: "my-workspace-name",
      organization: testOrganization.name,
    });
    new DataRetentionPolicy(this, "foobar", {
      deleteOlderThan: [
        {
          days: 1138,
        },
      ],
      organization: testOrganization.name,
      dontDelete: config.dontDelete,
    });
  }
}

```

## Argument Reference

The following arguments are supported:

* `organization` - (Optional) The name of the organization you want the policy to apply to. Must not be set if `workspaceId` is set.
* `workspaceId` - (Optional) The ID of the workspace you want the policy to apply to. Must not be set if `organization` is set.
* `deleteOlderThan` - (Optional) If this block is set, the created policy will apply to any data older than the configured number of days. Must not be set if `dontDelete` is set.
* `dontDelete` - (Optional) If this block is set, the created policy will prevent other policies from deleting data from this workspace or organization. Must not be set if `deleteOlderThan` is set.


## Import

A resource can be imported; use `<ORGANIZATION>/<WORKSPACE NAME>` or `<ORGANIZATION>` as the import ID. For example:

```shell
terraform import tfe_data_retention_policy.foobar my-org-name/my-workspace-name
```

<!-- cache-key: cdktf-0.20.8 input-f96ec458c2bca8796e296f06011ad4fc674072a5029841651f6906f053e79d76 -->