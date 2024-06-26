---
# generated by https://github.com/fbreckle/terraform-plugin-docs
page_title: "hitachi_vsp_iscsi_chap_user Resource - terraform-provider-hitachi"
subcategory: "VSS Block iSCSI Target CHAP User"
description: |-
  The following request sets the CHAP user name for the iSCSI target. Two types of CHAP user names can be set: the CHAP user name of the iSCSI target side and the CHAP user name of the host (iSCSI initiator) that connects to the iSCSI target.
---

# hitachi_vsp_iscsi_chap_user (Resource)

The following request sets the CHAP user name for the iSCSI target. Two types of CHAP user names can be set: the CHAP user name of the iSCSI target side and the CHAP user name of the host (iSCSI initiator) that connects to the iSCSI target.

## Example Usage

```terraform
//
// Hitachi VSP iSCSI CHAP User Resource
//
// This section defines a Terraform resource block to create a Hitachi VSP iSCSI CHAP user.
// The resource "hitachi_vsp_iscsi_chap_user" represents an iSCSI CHAP user on a Hitachi
// Virtual Storage Platform (VSP) and allows you to manage its configuration using Terraform.
//
// In the storage system, a CHAP user is uniquely identified by the combination of the
// serial, port_id, iscsi_target_number, chap_user_type, and chap_user_name. In Terraform,
// the resource is uniquely identified by the resource name "my_iscsi_initiator_chap_user3".
// The values of the mandatory input fields (serial, port_id, iscsi_target_number,
// chap_user_type, and chap_user_name) cannot be changed once the resource has been created.
//
// Customize the values of the parameters (serial, port_id, iscsi_target_number,
// chap_user_type, chap_user_name, chap_user_password) to match your desired CHAP user configuration.
//

resource "hitachi_vsp_iscsi_chap_user" "my_iscsi_initiator_chap_user3" {
  serial              = 12345                
  port_id             = "CL4-C"              
  iscsi_target_number = 01                   
  chap_user_type      = "initiator"          
  chap_user_name      = "chapuser"           
  chap_user_password  = "TopSecretForMyChap" 
}
```

<!-- schema generated by tfplugindocs -->
## Schema

### Required

- `chap_user_name` (String) CHAP user name.
- `chap_user_type` (String) Type of CHAP user name
			o target : CHAP user name of the iSCSI target side
			o initiator : CHAP user name of the host bus adapter (iSCSI initiator) side
- `iscsi_target_number` (Number) Target ID of the iSCSI target.
- `port_id` (String) Port number
- `serial` (Number) Serial number of storage

### Optional

- `chap_user_password` (String) Specify a secret consisting of 12 to 32 characters for the specified CHAP user.
			If you specify a null character, the password is reset.

### Read-Only

- `chap_user` (Block List) This is chap user output (see [below for nested schema](#nestedblock--chap_user))
- `id` (String) The ID of this resource.

<a id="nestedblock--chap_user"></a>
### Nested Schema for `chap_user`

Read-Only:

- `chap_user_id` (String) Object ID for the CHAP user
- `chap_user_name` (String) CHAP user name.
- `chap_user_type` (String) Type of CHAP user name
		o target : CHAP user name of the iSCSI target side
		o initiator : CHAP user name of the host bus adapter (iSCSI initiator) side
- `iscsi_target_number` (Number) Target ID of the iSCSI target.
- `port_id` (String) Port number
- `storage_serial_number` (Number) Serial number of storage


