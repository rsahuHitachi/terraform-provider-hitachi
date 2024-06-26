---
# generated by https://github.com/fbreckle/terraform-plugin-docs
page_title: "hitachi_vss_block_storage_pools Data Source - terraform-provider-hitachi"
subcategory: "VSS Block Storage Pools"
description: |-
  Obtains a list of storage pool information.
---

# hitachi_vss_block_storage_pools (Data Source)

Obtains a list of storage pool information.

## Example Usage

```terraform
#
# Hitachi VSS Block Storage Pools Data Retrieval
#
# This section defines a data source block to fetch information about specific storage pools
# from a Hitachi Virtual Storage System (VSS) using HashiCorp Configuration Language (HCL).
#
# The data source block "hitachi_vss_block_storage_pools" retrieves details about storage pools
# associated with the provided parameters. This allows you to access configuration and property
# information for the specified storage pools.
#
# Customize the values of the parameters (vssb_address, storage_pool_names) to match your
# environment, enabling you to retrieve information about the desired storage pools.
#

data "hitachi_vss_block_storage_pools" "pool" {
  vssb_address = "10.10.11.12"
  storage_pool_names = ["SP01"]
}

output "pool" {
  value = data.hitachi_vss_block_storage_pools.pool
}
```

<!-- schema generated by tfplugindocs -->
## Schema

### Required

- `vssb_address` (String) VSS block address of the storage device

### Optional

- `storage_pool_names` (List of String) List of pool names to be fetched from storage device

### Read-Only

- `id` (String) The ID of this resource.
- `storage_pools` (Block List) This is storage pools output (see [below for nested schema](#nestedblock--storage_pools))

<a id="nestedblock--storage_pools"></a>
### Nested Schema for `storage_pools`

Read-Only:

- `blocked_physical_capacity` (Number) Blocked physical capacity of pool
- `capacity_manage` (Block List) Capacity manage information (see [below for nested schema](#nestedblock--storage_pools--capacity_manage))
- `data_redundancy` (Number) Redundant type of pool
- `free_capacity` (Number) Free capacity of pool
- `meta_data_physical_capacity` (Number) Meta data physical capacity of pool
- `number_of_volumes` (Number) Number of volumes on pool
- `other_volume_capacity` (Number) Other volume capacity of pool
- `pool_id` (String) Id of pool
- `pool_name` (String) Name of pool
- `protection_domain_id` (String) Protection domain ID of pool
- `provisioned_volume_capacity` (Number) Provisioned volume capacity of pool
- `rebuild_capacity_policy` (String) Rebuild capacity policy of pool
- `rebuild_capacity_resource_setting` (Block List) Rebuild capacity resource setting information (see [below for nested schema](#nestedblock--storage_pools--rebuild_capacity_resource_setting))
- `rebuild_capacity_status` (String) Rebuild capacity status of pool
- `rebuildable_resources` (Block List) Rebuildable resources information (see [below for nested schema](#nestedblock--storage_pools--rebuildable_resources))
- `redundant_policy` (String) Number of volumes on pool
- `redundant_type` (String) of pool
- `reserved_physical_capacity` (Number) Reserved physical capacity of pool
- `saving_effects` (Block List) Saving effects information (see [below for nested schema](#nestedblock--storage_pools--saving_effects))
- `status` (String) Status of pool
- `status_summary` (String) Status summary of pool
- `storage_controller_capacities_general_status` (String) Storage controller capacities general status of pool
- `temporary_volume_capacity` (Number) Temporary volume capacity of pool
- `total_capacity` (Number) Total capacity of pool
- `total_physical_capacity` (Number) Total physical capacity of pool
- `total_raw_capacity` (Number) Total raw capacity of pool
- `total_volume_capacity` (Number) Total volume capacity of pool
- `usable_physical_capacity` (Number) Usable physical capacity of pool
- `used_capacity` (Number) Used capacity of pool

<a id="nestedblock--storage_pools--capacity_manage"></a>
### Nested Schema for `storage_pools.capacity_manage`

Read-Only:

- `maximum_reserve_rate` (Number) Maximum reserve rate of pool
- `threshold_depletion` (Number) Threshold depletion of pool
- `threshold_storage_controller_depletion` (Number) Threshold storage controller depletion of pool
- `threshold_warning` (Number) Threshold warning of pool
- `used_capacity_rate` (Number) Used capacity rate of pool


<a id="nestedblock--storage_pools--rebuild_capacity_resource_setting"></a>
### Nested Schema for `storage_pools.rebuild_capacity_resource_setting`

Read-Only:

- `number_of_tolerable_drive_failures` (Number) Number of tolerable drive failures of pool


<a id="nestedblock--storage_pools--rebuildable_resources"></a>
### Nested Schema for `storage_pools.rebuildable_resources`

Read-Only:

- `number_of_drives` (Number) Number of drives of pool


<a id="nestedblock--storage_pools--saving_effects"></a>
### Nested Schema for `storage_pools.saving_effects`

Read-Only:

- `calculation_end_time` (String) Calculation end time of saving effects
- `calculation_start_time` (String) Calculation start time of saving effects
- `data_reduction_without_system_data` (Number) Data reduction without system data of saving effects
- `data_reduction_without_system_data_status` (String) Data reduction without system data status of saving effects
- `efficiency_data_reduction` (Number) Efficiency data reduction of saving effects
- `post_capacity_data_reduction` (Number) Post capacity data reduction of saving effects
- `post_capacity_data_reduction_without_system_data` (Number) Post capacity data reduction without system data of saving effects
- `pre_capacity_data_reduction` (Number) Pre capacity data reduction of saving effects
- `pre_capacity_data_reduction_without_system_data` (Number) Pre capacity data reduction without system data of saving effects
- `total_efficiency` (Number) Total efficiency of saving effects
- `total_efficiency_status` (String) Total efficiency status of saving effects


