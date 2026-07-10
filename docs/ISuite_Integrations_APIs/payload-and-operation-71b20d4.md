<!-- loio71b20d4828da4df1a5c31b300cd88924 -->

# Payload and Operation

Payload is the data that you are sending through the JDBC receiver adapter. You can perform various operations like INSERT, UPDATE, DELETE etc on this XML Payload.



<a name="loio71b20d4828da4df1a5c31b300cd88924__section_zrq_wbz_4vb"/>

## Operations



### INSERT

> ### Sample Code:  
> ```
> <root>
> <Insert_Statement1>
> <dbTableName action="INSERT">
> <table>test</table>
> <access>
> <emp_id>121</emp_id>
> <emp_name>test121</emp_name>
> </access>
> <access>
> <emp_id>122</emp_id>
> <emp_name>test122</emp_name>
> </access>
> <access>
> <emp_id>123</emp_id>
> <emp_name>test123</emp_name>
> </access>
> </dbTableName>
> </Insert_Statement1>      
> </root>
> ```

> ### Output Code:  
> ```
> <?xml version="1.0" encoding="UTF-8" standalone="no"?>
> <root>
>     <Insert_Statement1_response>
>         <insert_count>1</insert_count>
>     </Insert_Statement1_response>
> </root>
> ```



### UPDATE

> ### Sample Code:  
> ```
> <root>
>     <Update_Statement1>
>         <dbTableName action="UPDATE">
>             <table>test</table>
>             <access>
>                 <emp_name>test121</emp_name>
>             </access>
>             <key>
>                 <emp_id>121</emp_id>
>             </key>
>         </dbTableName>
>     </Update_Statement1>
> </root>
> 
> ```

> ### Output Code:  
> ```
> <?xml version="1.0" encoding="UTF-8" standalone="no"?>
> <root>
>     <StatementName_response>
>         <update_count>1</update_count>
>     </StatementName_response>
> </root>
> 
> ```



### DELETE

> ### Sample Code:  
> ```
> 
> ```

> ### Output Code:  
> ```
> <?xml version="1.0" encoding="UTF-8" standalone="no"?>
> <root>
>     <Delete_Statement1_response>
>         <delete_count>1</delete_count>
>     </Delete_Statement1_response>
> </root><root>
>     <Delete_Statement1>
>         <dbTableName action="DELETE">
>             <table>TEST</table>
>             <key>
>                 <emp_id>123</emp_id>
>             </key>
>         </dbTableName>
>     </Delete_Statement1>
> </root>
> ```



### SELECT

> ### Sample Code:  
> ```
> <<root>
>     <Select_Statement1>
>         <dbTableName action="SELECT">
>             <table>TEST</table>
>             <access>
>             </access>
>                 <key>
>                    <emp_id>122</emp_id>
>                 </key>
>         </dbTableName>
>     </Select_Statement1>
> </root>
> ```

> ### Sample Code:  
> ```
> <root>
>  <Select_Statement1>
>         <dbTableName action="SELECT">
>             <table>TESTCOL</table>
>             <access>
>                 <col1/>
>                 <col2/>
>                 <col3/>
>             </access>
>             <key1>
>                 <col2>val2old</col2>
>                 <col4>val4</col4>
>             </key1>
>             <key2>
>                 <col2>val2old2</col2>
>             </key2>
>         </dbTableName>
>  </Select_Statement1>
> </root>
> ```



### EXECUTE

> ### Sample Code:  
> ```
> <root>
>   <StatementName>
>     <storedProcedureName action="EXECUTE">
>       <table>samplestoredproc</table>
>       <emp_id type="INTEGER" isInput="true">3</emp_id>
>       <emp_name type="VARCHAR" isInput="true">test</emp_name>
>       <email type="VARCHAR" isOutput="true"></email>
>     </storedProcedureName >
>   </StatementName>
> </root>
> ```



### UPDATE INSERT

This operation lets you to update an existing entry. If it does not exist, a new entry is created.

> ### Sample Code:  
> ```
> <root>
>     <StatementName>
>         <dbTableName action="UPDATE_INSERT">
>             <table>test</table>
>             <access>
>                 <name>test125</name>
>                 <id>125</id>
>             </access>
>             <key>
>                 <id>125</id>
>             </key>
>         </dbTableName>
>     </StatementName>
> </root>
> ```

> ### Output Code:  
> ```
> <?xml version="1.0" encoding="UTF-8" standalone="no"?>
> <root>
>     <StatementName_response>
>         <update_insert_count>1</update_insert_count>
>     </StatementName_response>
> </root>
> ```

> ### Note:  
> If your database has column names with special characters \(like \#, \* etc\), then, you must set `ColumnNameAsTag="false"` in the incoming XML payload for JDBC receiver adapter to process these column names without throwing an exception.
> 
> > ### Sample Code:  
> > In this example, `ColumnNameAsTag` is set as `false` and `name` and `value` of the column must be defined separately under `column` tag.
> > 
> > ```
> > <root>
> >     <insert_statement ColumnNameAsTag="false">
> >         <dbTableName action="INSERT">
> >             <table>sampletest</table>
> >             <access>
> >                 <column>
> >                     <name>ID#</name>
> >                     <value>112</value>
> >                 </column>
> >                 <column hasQuot="No">
> >                     <name>NAME#</name>
> >                     <value>XXX</value></column>
> >             </access>
> >             <access>
> >                 <column>
> >                     <name>ID#</name>
> >                     <value>113</value>
> >                 </column>
> >                 <column hasQuot="Yes">
> >                     <name>NAME#</name>
> >                     <value>ABC</value>
> >                 </column>
> >             </access>
> >         </dbTableName>
> >     </insert_statement>
> > </root>
> > ```
> 
> > ### Output Code:  
> > ```
> > 2 Rows inserted
> > 
> > <?xml version="1.0" encoding="UTF-8" standalone="no"?>
> > 
> > <root><insert_statement_response>
> > 
> > <insert_count>2</insert_count>
> > 
> > </insert_statement_response>
> > 
> > </root>
> > ```

