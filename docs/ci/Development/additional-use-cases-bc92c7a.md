<!-- loiobc92c7a4c5a641cbb282895b2c6d6225 -->

# Additional Use Cases

****


<table>
<tr>
<th valign="top">

Use Case

</th>
<th valign="top">

Example Requests / More Information

</th>
</tr>
<tr>
<td valign="top">

Address value mappings

</td>
<td valign="top">

Use the `ValueMappingApi` interface to address value mappings.

The following Groovy Script retrieves a value transformed by a value mapping:

```
def service = ITApiFactory.getApi(ValueMappingApi.class, null);
if( service != null)
            {
def mappedValue = service.getMappedValue("SuccessFactors", "locale", "de_DE", "SAPHCM", "language");
					//(SrcAgencey,SrcSchema,SrcValue,TargetAgency,TargetSchema)
      
messageLog.setStringProperty("Information","The transformed locale value is : " + mappedValue);
}
      }
      catch(Exception e)
      {
        messageLog.setStringProperty("Exception",e.toString())
        return null;
      }

    
       return message;
}
```



</td>
</tr>
<tr>
<td valign="top">

Address number ranges

</td>
<td valign="top">

Us the `NumberRangeConfigurationService` interface to address number ranges.

The following Groovy Script retrieves a value from a *Number Ranges* artifact:

```
def service = ITApiFactory.getApi(NumberRangeConfigurationService.class, null);   
   
if( service != null)
{ 
  //Get next value from number range configured in web tooling.
   def nextValue = service.getNextValuefromNumberRange("new", null);
}
```



</td>
</tr>
</table>

