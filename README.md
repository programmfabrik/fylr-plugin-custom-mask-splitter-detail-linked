# Custom Mask Splitter: Show References

This fylr plugin adds a custom mask splitter that shows reverse references. It lists all objects that link to the object currently shown in the detail view.

The plugin searches for objects whose linked fields point to the current object. The results are grouped by object type. They can also be grouped by the field that holds the link. Each group is paginated with 10 objects per page.

## Configuration

The plugin is configured in the mask editor. Open the mask editor in the administration, select a mask and add a new element. Choose the mask splitter "Display of references". Move the splitter to the position where the references should appear.

The splitter offers the following options.

### Mode

The display format of the referencing objects.

| Value | Description |
|-------|-------------|
| Standard | Full card with thumbnail and detail information |
| Short | Compact single line, like the condensed view of nested objects |
| Text | Text only, showing the standard text of the object |

### Object types

Selects the object types that are searched for references. Only object types with a linked field pointing to the current object type are offered. All of them are selected by default.

### Include inherited data

If enabled, references from inherited field values are included. If disabled, only references from fields filled directly on the object are shown.

### Group by fields

If enabled, the references are grouped by object type and by the field that holds the link. This is useful when an object type has several linked fields pointing to the same target type.

An example: the object type "Document" has the fields "Author" and "Reviewer", both linking to "Person". With this option enabled, the detail view of a person shows two separate groups. One group lists the documents where the person is the author. The other group lists the documents where the person is the reviewer.

### Sorting

Defines a sort order per object type. Without this configuration the references are sorted alphabetically by their standard text.

Add a row to the table and select an object type. Each object type can be configured only once. Then select the field to sort by and the sort order, ascending or descending. Object types without a row keep the default sorting.

These sort fields are available.

| Field | Description |
|-------|-------------|
| Default (Standard Text) | Alphabetical by the standard text of the object |
| System Object ID | The internal system object ID |
| Created | The creation date |
| Last Modified | The date of the last change |
| Standard A, B, C | The standard texts of the object type |
| Mask fields | Any sortable field of the object type |

## Behavior and limits

The splitter renders only in the detail view. It does not render in the editor or in other views. It cannot be used inside nested tables.

Only fields that are visible in the expert search are searched. Nested tables are searched as well. Each group of results is limited to 1000 objects.
