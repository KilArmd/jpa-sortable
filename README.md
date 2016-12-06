# jpa-sortable
Sort entity with a very simple API: Craete Sort or Pageable objects easily while entity annotated by @Sortable.

# principles
1. Never believe clients' inputs.
2. Guarantee outputs as possible as codes can do even incorrect inputs.

#
1. Annotate entity's fields, fields should be associated on columns of database.
@Sortable(value = String[], properties = String[], directions = Direction[], isDefault = boolean)
1) value: What clients input, use filed name if ignored.
2) properties: Sort use this properties, use filed name if ignored.
3) directions: Sort type is ascending or descending, Direction.ASC default. length of directions should be same as properties, igonred if longer and filled Direction.ASC if shorter.
4) isDefault: While clients' input incorrectly, use this sortable. codes will read all fileds annotated @Sortable whose isDefault tags true.
2. @Sortable can be also annotated on Entity type, but this Annotation should function with no annotated fileds, and value method of @Sortable will be ignored.
