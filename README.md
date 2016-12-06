# jpa-sortable
Sort entity with a very simple API: Craete Sort or Pageable objects easily while entity annotated by @Sortable.

# Principles
1. Never believe clients' inputs.
2. Guarantee outputs as possible as codes can do even incorrect inputs.

# Use
1. Annotate on entity's fields associated on columns of database.

  @Sortable(value = String[], properties = String[], directions = Direction[], isDefault = boolean)

  1.1 value: What clients input, field name default.

  1.2 properties: Sort properties, field name default.

  1.3 directions: Sort type, Direction.ASC default. Length of directions should be same as properties, directions will be truncated if longer and filled with Direction.ASC if shorter.

  1.4 isDefault: While clients' input incorrectly or absently, use these properties, false default. An entity type should only has one @Sortable Annotation whose isDefault tagged true, extra will ignored.

2. @Sortable can be also annotated on Entity type and assign default sorting properties, so value property will be ignored. This Annotation will not function while exists fileds annotated @Sortable will isDefault tagged true.
