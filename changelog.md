# Change Log #

### Release 0.2 ###

Feature enhancements:
  * Supported to create index
  * Supported to query for more complex rules
  * New utility class to create data model initial field

Critial Changes:
  * The usage of DQWhere class is changed to adapt a faster way of usage. It is incompatible with 0.1.

Detailed Changes:

> DQWhere
  * Deprecated &,| operator overloading and removed from code. It is replaced by && and 
  * Changed the definition of constructor. The left operand pass to constructor is restricted to data model field only. It is not compatible with old code
  * Improved the operator overloading mechanism. It become a more powerful class
  * Supported to query by compare the value on different field. The following query become possible:
> > - select **from table where field1 = field2
  * New supported operators: &&,||,+,-,**,/,%,equal,notEqual,between,in,notIn,like,glob,is,isNot.



> DQ\_DECLARE\_MODEL
  * Supported private field

> DQIndex
  * A new class for sqlite indexing

> DQField
  * Supported bool and QStringList as the template type T
  * Added operator T() casting. It can be casted to T automatically.

> DQBaseField::get() / DQModelMetaInfo::value() - Added a new argument "convert"
  * It is true if the QVariant return should be converted to a type which is suitable for saving. It is designed for type like QStringList which is not supported by SQLite backend by default.

> DQConnection
  * Change this connection to be the default connection
  * operator == / !- compare is two connection share the same database

> DQSharedQuery
  * Added new function select()  - Construct a new query object with only the fields assigned in result
  * Added new function orderBy() - Construct a new query object with required sorting order
  * Added new function setConnection() - Set the database connection

> DQStream
  * A new class, it provides a stream interface for reading and writing data model field

> DQListWriter
  * A new class, it is a utility class to create the content for DQList object with predefined field

> DQSharedList
  * Added new function save() - Save all the contained item to database