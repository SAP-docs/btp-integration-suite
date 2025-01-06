<!-- loio760b267f434b49949ba60a06d2e35354 -->

# Batch Payload and Operation

Use this option to modify multiple records in a single payload either using INSERT, UPDATE or DELETE modes. This enables you to process collection queries in a single request.

> ### Note:  
> For visual instructions on how to execute batch payload operations, refer the tutorial [Execute Batch Payload Operations Using Java Database Connectivity \(JDBC\) Receiver Adapter.](https://developers.sap.com/tutorials/btp-integration-suite-execute-batch-payload.html)



## Batch Payload

Batch mode is supported in following ways:

-   XML payload is supported in INSERT, UPDATE and DELETE modes only.

    > ### Sample Code:  
    > ```
    > <root>
    > 	<insert_statement1>
    > 		<dbTableName action="INSERT">
    > 			<table>dbo.employee</table>
    > 			<access>
    > 				<emp_id>127</emp_id>
    > 				<birth_date hasQuot="Yes">1999-02-03</birth_date>
    > 				<email hasQuot="Yes">abcd@gmail.com</email>
    > 				<emp_name hasQuot="Yes">v XXXXX</emp_name>
    > 				<join_date hasQuot="Yes">2021-01-25</join_date>
    > 				<phone hasQuot="Yes">0123456789</phone>
    > 			</access>
    > 		</dbTableName>
    > 	</insert_statement1>
    > 	<insert_statement2>
    > 		<dbTableName action="INSERT">
    > 			<table>dbo.employee</table>
    > 			<access>
    > 				<emp_id>128</emp_id>
    > 				<birth_date hasQuot="Yes">2008-01-25</birth_date>
    > 				<email hasQuot="Yes">efgh@gmail.com</email>
    > 				<emp_name hasQuot="Yes"> g28</emp_name>
    > 				<join_date hasQuot="Yes">2021-10-25</join_date>
    > 				<phone hasQuot="Yes">0123456789</phone>
    > 			</access>
    > 		</dbTableName>
    > 	</insert_statement2>
    > </root>
    > 
    > ```

    -   With JDBC adapter Version 1.5 and above, you can now use multiple *access* tags with INSERT mode.

        > ### Sample Code:  
        > ```
        > <root>
        >     <Insert_Statement1>
        >         <dbTableName action="INSERT">
        >             <table>TEST</table>
        >             <access>
        >                 <emp_id>1</emp_id>
        >                 <emp_name>test</emp_name>
        >                 <email>test@gmail.com</email>
        >             </access>
        >             <access>
        >                 <emp_id>2</emp_id>
        >                 <emp_name>test</emp_name>
        >                 <email>test@gmail.com</email>
        >             </access>
        >         </dbTableName>
        >     </Insert_Statement1>
        >     <Update_Statement2>
        >         <dbTableName action="UPDATE">
        >             <table>TEST</table>
        >             <access>
        >                 <join_date>testuser</join_date>
        >             </access>
        >             <key>
        >                 <emp_id>1</emp_id>
        >             </key>
        >         </dbTableName>
        >     </Update_Statement2>
        >     <Delete_Statement3>
        >         <dbTableName action="DELETE">
        >             <table>TEST</table>
        >             <key>
        >                 <emp_id>1</emp_id>
        >             </key>
        >         </dbTableName>
        >     </Delete_Statement3>
        > </root>
        >  
        > ```
        > 
        > > ### Output Code:  
        > > ```
        > > <?xml version="1.0" encoding="UTF-8" standalone="no"?>
        > > <root>
        > >     <Insert_Statement1>
        > >         <table>TEST</table>
        > >         <insert_count>2</insert_count>
        > >     </Insert_Statement1>
        > >     <Update_Statement2>
        > >         <table>TEST</table>
        > >         <update_count>3</update_count>
        > >     </Update_Statement2>
        > >     <Delete_Statement3>
        > >         <table>TEST</table>
        > >         <delete_count>1</delete_count>
        > >     </Delete_Statement3>
        > > </root>
        > > ```


-   **Update Insert**: This operation lets you update an existing entry. If it does not exist, a new entry is created.

    > ### Note:  
    > -   Multiple *access* tags are not supported.
    > -   Native Batch for UPSERT statement is not available in [SAP HANA Platform](https://help.sap.com/docs/HANA_SERVICE_CF/7c78579ce9b14a669c1f3295b0d8ca16/ea8b6773be584203bcd99da76844c5ed.html#example) and all other databases.

    > ### Sample Code:  
    > For successful scenarios:
    > 
    > ```
    > 
    > <?xml version="1.0" encoding="UTF-8"?>
    > <root>
    >    <UPDATE_INSERT_statement>
    >       <dbTableName action="UPDATE_INSERT">
    >          <table>test</table>
    >          <access>
    >             <emp_name>test227</emp_name>
    >             <email>test@gmail.com</email>
    >          </access>
    >          <key>
    >             <emp_id>227</emp_id>
    >          </key>
    >       </dbTableName>
    >    </UPDATE_INSERT_statement>
    >    <UPDATE_INSERT_statement>
    >       <dbTableName action="UPDATE_INSERT">
    >          <table>test</table>
    >          <access>
    >             <emp_name>test228</emp_name>
    >             <email>test@gmail.com</email>
    >          </access>
    >          <key>
    >             <emp_id>228</emp_id>
    >          </key>
    >       </dbTableName>
    >    </UPDATE_INSERT_statement>
    >     
    >    <UPDATE_INSERT_statement>
    >       <dbTableName action="UPDATE_INSERT">
    >          <table>test</table>
    >          <access>
    >             <emp_name>test229</emp_name>
    >             <email>test@gmail.com</email>
    >          </access>
    >          <key>
    >             <emp_id>229</emp_id>
    >          </key>
    >       </dbTableName>
    >    </UPDATE_INSERT_statement>
    > </root>
    > ```
    > 
    > > ### Output Code:  
    > > ```
    > > <?xml version="1.0" encoding="UTF-8" standalone="no"?>
    > > <root>
    > > <insert_statement><table>TEST</table>
    > > <update_insert_count>1</update_insert_count></insert_statement>
    > > <insert_statement><table>TEST</table><update_insert_count>1</update_insert_count></insert_statement>
    > > <insert_statement><table>TEST</table><update_insert_count>1</update_insert_count></insert_statement>
    > > </root>
    > > 
    > > 
    > > 
    > > ```

    > ### Sample Code:  
    > For failure scenarios:
    > 
    > ```
    > 
    > <?xml version="1.0" encoding="UTF-8"?>
    > <root>
    >     
    >    <UPDATE_INSERT_statement>
    >       <dbTableName action="UPDATE_INSERT">
    >          <table>saffrontest</table>
    >          <access>
    >             <emp_name>test227</emp_name>
    >             <email>test@gmail.com</email>
    >          </access>
    >          <key>
    >             <emp_id>227</emp_id>
    >          </key>
    >       </dbTableName>
    >    </UPDATE_INSERT_statement>
    >     
    >    <UPDATE_INSERT_statement>
    >       <dbTableName action="UPDATE_INSERT">
    >          <table>saffrontest</table>
    >          <access>
    >             <emp_name>test228</emp_name>
    >             <email>test@gmail.com</email>
    >          </access>
    >          <key>
    >             <emp_id>228</emp_id>
    >          </key>
    >       </dbTableName>
    >    </UPDATE_INSERT_statement>
    >     
    >    <UPDATE_INSERT_statement>
    >       <dbTableName action="UPDATE_INSERT">
    >          <table>saffrontest</table>
    >          <access>
    >             <emp_id>221</emp_id>
    >             <emp_name>test</emp_name>
    >             <email>test@gmail.com</email>
    >          </access>
    >          <key>
    >             <emp_id>229</emp_id>
    >          </key>
    >       </dbTableName>
    >    </UPDATE_INSERT_statement>
    > </root>
    > ```
    > 
    > > ### Output Code:  
    > > ```
    > > Error Details
    > > 
    > > com.sap.it.rt.adapter.http.api.exception.HttpResponseException: An internal server error occured: ORA-00001: unique constraint (XIVERI.SYS_C0032530) violated
    > > 
    > > Statement : UPDATE_INSERT_statement ; Failed Operation : INSERT ; statement sequence : 3 .
    > > 
    > > The MPL ID for the failed message is : AGO_s9LDIZCVYPn25Ir6mqBK7EJw
    > > 
    > > 
    > > ```
    > 
    > > ### Note:  
    > > The above error occurs because the table **test** already contains a record with **221 \(emp\_id\)** as primary key. Hence, the key **229** cannot be updated as **221**, primary key should be unique.

-   Native SQL queries are supported with prepared statements only. If you are using batch mode with native SQL queries, ensure:

    -   *Message Body* contains query.
    -   *Message Header* contains payload against the parameter name *CamelSqlParameters*. The data type of the parameter must be List of List.

    A way to achieve this is via Groovy Script.

    > ### Sample Code:  
    > ```
    > import com.sap.gateway.ip.core.customdev.util.Message;
    > import java.util.HashMap;
    > import java.util.Arrays;
    > 
    > //Insert script
    > def Message processData(Message message) {
    > 
    >     //Headers
    >     List paramList = new ArrayList();
    >     paramList.add(Arrays.asList(108, 'test', 2021-01-01,1,1,'test@gmail.com'));
    >     paramList.add(Arrays.asList(107, 'test', 2021-01-01,1,1,'test@gmail.com'));
    >     paramList.add(Arrays.asList(111, 'test', 2021-01-01,1,1,'test@gmail.com'));
    >     paramList.add(Arrays.asList(105, 'test', 2021-01-01,1,1,'test@gmail.com'));
    >     message.setHeader("CamelSqlParameters",paramList);
    >     
    >     //Body 
    >     message.setBody("INSERT INTO XIVERI.dbo.saffrontest(emp_id,emp_name,join_date,a1,a2,email) VALUES(?,?,?,?,?,?)");
    >     return message;
    > }
    > ```


> ### Note:  
> If your database has column names with special characters \(like \#, \* etc\), then, you must set `ColumnNameAsTag="false"` in the incoming XML payload for JDBC receiver adapter to process these column names without throwing an exception.
> 
> > ### Sample Code:  
> > In this example, `ColumnNameAsTag` is set as `false` and `name` and `value` of the column must be defined separately under `column` tag.
> > 
> > ```
> > <root>
> >     <InsertStatement ColumnNameAsTag="false">
> >         <dbTableName action = "SELECT">
> >             <table> sampletest </table>
> >             <access>
> >                 <column>
> >                     <name>ID#</name>
> >                     <value>112</value>
> >                 </column>
> >                 <column hasQuot="Yes">
> >                     <name>NAME#</name>
> >                     <value>XXX</value></column>
> >             </access>
> >         </dbTableName>
> >     </InsertStatement>
> >     <InsertStatement>
> >         <dbTableName action = "SELECT">
> >             <table> sampletest </table>
> >             <access>
> >                 <column>
> >                     <name>ID#</name>
> >                     <value>113</value>
> >                 </column>
> >                 <column hasQuot="Yes">
> >                     <name>NAME#</name>
> >                     <value>ABC</value>
> >                  </column>
> >             </access>
> >         </dbTableName>
> >     </InsertStatement>
> > </root>
> >              
> > ```



## Batch Operation

You can select the behavior of Batch operation:

-   *Atomic*- Considers each batch operation as a single unit. It updates the whole batch operation successfully or reverts the entire operation to its initial state if anything in the batch operation fails.
-   *Non-Atomic*- This is based on the behavior of the database. It updates all the successfully executed records and throws an exception if anything fails. It does not revert the failed records to its initial state.

