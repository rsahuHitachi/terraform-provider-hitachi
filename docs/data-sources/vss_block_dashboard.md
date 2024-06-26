---
# generated by https://github.com/fbreckle/terraform-plugin-docs
page_title: "hitachi_vss_block_dashboard Data Source - terraform-provider-hitachi"
subcategory: "VSS Block Dashboard"
description: |-
  Obtains the information about Dashboard Information.
---

# hitachi_vss_block_dashboard (Data Source)

Obtains the information about Dashboard Information.

## Example Usage

```terraform
#
# Hitachi VSS Block Dashboard Data Retrieval
#
# This section defines a data source block to fetch dashboard information from a
# Hitachi Virtual Storage System (VSS) using HashiCorp Configuration Language (HCL).
#
# The data source block "hitachi_vss_block_dashboard" retrieves a dashboard of
# information associated with the provided parameters. This allows you to access
# an overview of various metrics and details about the storage system.
#
# Customize the value of the parameter (vss_block_address) to match your environment,
# enabling you to retrieve dashboard information from the desired VSS.
#

data "hitachi_vss_block_dashboard" "dashboard" {
  vss_block_address = "10.10.12.13"
}

output "dashboardoutput" {
  value = data.hitachi_vss_block_dashboard.dashboard
}
```

<!-- schema generated by tfplugindocs -->
## Schema

### Required

- `vss_block_address` (String) The host name or the IP address (IPv4) of the REST API server on Virtual Storage Software block.

### Optional

- `dashboard_info` (Block List) This is dashboard output (see [below for nested schema](#nestedblock--dashboard_info))

### Read-Only

- `id` (String) The ID of this resource.

<a id="nestedblock--dashboard_info"></a>
### Nested Schema for `dashboard_info`

Optional:

- `health_status` (Block List) Displays the health status (see [below for nested schema](#nestedblock--dashboard_info--health_status))

Read-Only:

- `compute_node_count` (Number) Total number of compute nodes
- `compute_port_count` (Number) Total number of compute ports
- `data_reduction` (Number) Ratio of the data capacity before and after data reduction (unit: %).
- `drive_count` (Number) Total number of drives
- `fault_domain_count` (Number) Total number of fault domains.
- `free_capacity_gb` (Number) Free pool capacity in GB
- `free_capacity_mb` (Number) Free pool capacity in MB
- `storage_node_count` (Number) Total number of storage nodes
- `storage_pool_count` (Number) Total number of storage nodes
- `total_capacity_gb` (Number) Total pool capacity in GB
- `total_capacity_mb` (Number) Total pool capacity in MB
- `total_efficiency` (Number) Indicates the effect of volume creation and snapshot functions on capacity consumption.
- `used_capacity_gb` (Number) Used pool capacity in GB
- `used_capacity_mb` (Number) Used pool capacity in MB
- `volume_count` (Number) Total number of volumes.

<a id="nestedblock--dashboard_info--health_status"></a>
### Nested Schema for `dashboard_info.health_status`

Optional:

- `status` (String) Health status.
- `type` (String) Object type.


