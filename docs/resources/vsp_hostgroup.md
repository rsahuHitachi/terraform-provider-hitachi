---
# generated by https://github.com/fbreckle/terraform-plugin-docs
page_title: "hitachi_vsp_hostgroup Resource - terraform-provider-hitachi"
subcategory: "VSP Storage Host Group"
description: |-
  The following request creates a host group for the port. The host mode and the host mode option can also be specified at the same time when the host group is created.
---

# hitachi_vsp_hostgroup (Resource)

The following request creates a host group for the port. The host mode and the host mode option can also be specified at the same time when the host group is created.

## Example Usage

```terraform
resource "hitachi_vsp_hostgroup" "myhg" {
  serial           = 40014 // REQUIRED
  hostgroup_number = 23
  hostgroup_name   = "TESTING-HOSTGROUP" // REQUIRED
  port_id          = "CL1-A"             // REQUIRED
  // For detail information about host_mode_options and host_mode, please look at the following link:
  // https://knowledge.hitachivantara.com/Documents/Management_Software/SVOS/9.8.6/Volume_Management_-_VSP_E_Series/Host_Attachment/14_Host_modes_and_host_mode_options
  host_mode_options = [12, 32]
  host_mode         = "AIX"
 
  # SET of LUN
  lun {
    ldev_id = 25
    lun     = 12
  }

}
```

<!-- schema generated by tfplugindocs -->
## Schema

### Required

- `hostgroup_name` (String) The Host Group name to be specified to create the group
- `port_id` (String) The Port ID to be specified
- `serial` (Number) The host group serial number need to be specified

### Optional

- `host_mode` (String) The Host Mode to create the group
- `host_mode_options` (List of Number) The number of host mode options to be given to create the group.
- `hostgroup_number` (Number) The Host Group number to be specified
- `lun` (Block Set) Properties of Luns to create the group (see [below for nested schema](#nestedblock--lun))
- `wwn` (Block Set) World wide name of the Host group (see [below for nested schema](#nestedblock--wwn))

### Read-Only

- `hostgroup` (Block List) Response data of the created host group (see [below for nested schema](#nestedblock--hostgroup))
- `id` (String) The ID of this resource.

<a id="nestedblock--lun"></a>
### Nested Schema for `lun`

Optional:

- `ldev_id` (Number) Ldev ID of the Lun
- `lun` (Number) Lun ID of the Lun


<a id="nestedblock--wwn"></a>
### Nested Schema for `wwn`

Optional:

- `host_wwn` (String) Name of the wwn resource
- `wwn_nickname` (String) Nickname of the wwn resource


<a id="nestedblock--hostgroup"></a>
### Nested Schema for `hostgroup`

Read-Only:

- `hg_luns` (List of Number) Host group lun IDs
- `host_mode` (String) Mode of the hostgroup
- `host_mode_options` (List of Number) The number of items in the host mode options list
- `hostgroup_name` (String) Name of the HostGroup
- `hostgroup_number` (Number) Created HostGroup number
- `ldevs` (List of Number) The number of ldevs Ids in the host group
- `lun_paths` (Block List) HostGroup lun paths with lun ids and ldev ids (see [below for nested schema](#nestedblock--hostgroup--lun_paths))
- `port_id` (String) Assigned port ID of the HostGroup
- `storage_serial_number` (Number) The serial number of the storage
- `wwns` (List of String) WWNs list for the created host group.
- `wwns_detail` (Block List) Details of wwns for the created host group including id and name (see [below for nested schema](#nestedblock--hostgroup--wwns_detail))

<a id="nestedblock--hostgroup--lun_paths"></a>
### Nested Schema for `hostgroup.lun_paths`

Read-Only:

- `hg_lun_id` (Number) Lun Paths Host group ID
- `ldev_id` (Number) Lun Paths Ldev ID


<a id="nestedblock--hostgroup--wwns_detail"></a>
### Nested Schema for `hostgroup.wwns_detail`

Read-Only:

- `name` (String) Name of the WWN resource
- `wwn` (String) ID of the WWN resource

