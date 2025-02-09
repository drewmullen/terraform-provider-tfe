---
layout: "tfe"
page_title: "Terraform Enterprise: tfe_organization_run_task"
sidebar_current: "docs-resource-tfe-organization-run-task"
description: |-
  Manages Run tasks.
---

# tfe_organization_run_task

[Run tasks](https://www.terraform.io/cloud-docs/workspaces/settings/run-tasks) allow Terraform Cloud to interact with external systems at specific points in the Terraform Cloud run lifecycle. Run tasks are reusable configurations that you can attach to any workspace in an organization.

The tfe_organization_run_task resource creates, updates and destroys [Organization Run tasks](https://www.terraform.io/cloud-docs/workspaces/settings/run-tasks#creating-a-run-task).

## Example Usage

Basic usage:

```hcl
resource "tfe_organization_run_task" "example" {
  organization = "org-name"
  url          = "https://external.service.com"
  name         = "task-name"
  enabled      = true
}
```

## Argument Reference

The following arguments are supported:

* `category` - (Optional) The type of task.
* `enabled` - (Optional) Whether the task will be run.
* `hmac_key` - (Optional) HMAC key to verify run task.
* `name` - (Required) Name of the task.
* `organization` - (Required) Name of the organization.
* `url` - (Required) URL to send a run task payload.

## Attributes Reference

* `id` - The ID of the task.

## Import

Run tasks can be imported; use `<ORGANIZATION NAME>/<TASK NAME>` as the
import ID. For example:

```shell
terraform import tfe_organization_run_task.test my-org-name/task-name
```
