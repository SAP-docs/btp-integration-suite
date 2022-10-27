<!-- loio760b267f434b49949ba60a06d2e35354 -->

# Batch Payload and Operation

Use this option to modify multiple records in a single payload either using INSERT, UPDATE or DELETE modes. This enables you to process collection queries in a single request.



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




## Batch Operation

You can select the behavior of Batch operation:

-   *Atomic*- Considers each batch operation as a single unit. It updates the whole batch operation successfully or reverts the entire operation to its initial state if anything in the batch operation fails.
-   *Non-Atomic*- This is based on the behavior of the database. It updates all the successfully executed records and throws an exception if anything fails. It does not revert the failed records to its initial state.

