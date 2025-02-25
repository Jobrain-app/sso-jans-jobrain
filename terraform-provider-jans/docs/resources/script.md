---
# generated by https://github.com/hashicorp/terraform-plugin-docs
page_title: "jans_script Resource - terraform-provider-jans"
subcategory: ""
description: |-
  Resource for managing custom scripts
---

# jans_script (Resource)

Resource for managing custom scripts

## Example Usage

```terraform
resource "jans_script" "test" {
	dn 												= "inum=4A4E-4F3D,ou=scripts,o=jans"
	inum 											= "4A4E-4F3D"
	name 											= "test_script"
	description 							= "Test description"
	script 										= ""
	script_type 							= "INTROSPECTION"
	programming_language 			= "PYTHON"
	level 										= 1
	revision 									= 1
	enabled 									= true
	modified 									= false
	internal 									= false
	location_type 						= "db"
	base_dn 									= "inum=4A4E-4F3D,ou=scripts,o=jans"

	module_properties {
			value1 = "location_type"
			value2 = "db"
	}

	module_properties {
			value1 = "location_option"
			value2 = "foo"
	}
	
}
```

<!-- schema generated by tfplugindocs -->
## Schema

### Required

- `level` (Number) Script level.
- `module_properties` (Block List, Min: 1) Module-level properties applicable to the script. (see [below for nested schema](#nestedblock--module_properties))
- `name` (String) Custom script name. Should contain only letters, digits and underscores.
- `programming_language` (String) Programming language of the custom script.
- `script` (String) Actual script.
- `script_type` (String) Type of script.

### Optional

- `aliases` (List of String) List of possible aliases for the custom script.
- `base_dn` (String)
- `configuration_properties` (Block List) Configuration properties applicable to the script. (see [below for nested schema](#nestedblock--configuration_properties))
- `description` (String) Details describing the script.
- `dn` (String)
- `enabled` (Boolean) boolean value indicating if script enabled.
- `internal` (Boolean) boolean value indicating if the script is internal.
- `inum` (String) XRI i-number. Identifier to uniquely identify the script.
- `location_path` (String)
- `location_type` (String)
- `modified` (Boolean) boolean value indicating if the script is modified.
- `revision` (Number) Update revision number of the script.

### Read-Only

- `id` (String) The ID of this resource.
- `script_error` (List of Object) Possible errors assosiated with the script. (see [below for nested schema](#nestedatt--script_error))

<a id="nestedblock--module_properties"></a>
### Nested Schema for `module_properties`

Optional:

- `description` (String)
- `value1` (String)
- `value2` (String)


<a id="nestedblock--configuration_properties"></a>
### Nested Schema for `configuration_properties`

Optional:

- `description` (String)
- `hide` (Boolean)
- `value1` (String)
- `value2` (String)


<a id="nestedatt--script_error"></a>
### Nested Schema for `script_error`

Read-Only:

- `raised_at` (String)
- `stack_trace` (String)


