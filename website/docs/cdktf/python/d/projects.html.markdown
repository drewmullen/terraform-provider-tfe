---
layout: "tfe"
page_title: "Terraform Enterprise: tfe_projects"
description: |-
  Get information on projects in an organization.
---


<!-- Please do not edit this file, it is generated. -->
# Data Source: tfe_projects

Use this data source to get information about all projects in an organization.

## Example Usage

```python
# DO NOT EDIT. Code generated by 'cdktf convert' - Please report bugs at https://cdk.tf/bug
from constructs import Construct
from cdktf import TerraformStack
#
# Provider bindings are generated by running `cdktf get`.
# See https://cdk.tf/provider-generation for more details.
#
from imports.tfe.data_tfe_projects import DataTfeProjects
class MyConvertedCode(TerraformStack):
    def __init__(self, scope, name):
        super().__init__(scope, name)
        DataTfeProjects(self, "all",
            organization="my-org-name"
        )
```

## Argument Reference

The following arguments are supported:

* `organization` - (Optional) Name of the organization. If omitted, organization must be defined in the provider config.

## Attributes Reference

* `projects` - List of projects in the organization. Each element contains the following attributes:
  * `id` - ID of the project.
  * `name` - Name of the project.
  * `description` - Description of the organization.
  * `organization` - Name of the organization.
  * `auto_destroy_activity_duration` - A duration string for all workspaces in the project, representing time after each workspace's activity when an auto-destroy run will be triggered.

<!-- cache-key: cdktf-0.20.8 input-80f7374bb86183375fd75ccdf9e337a9635c8ca4a605c4f1544be31f69bcced8 -->