<!-- copy35e2b1331e8d410f80c45123ecb50ffd -->

# Example: Transformation to a JSON Message without Root Element Tag

Examples and Special Cases of JSON Message without Root Element Tag

The following examples apply to XML-to-JSON conversion:



## Example

The following example shows the transformation from *XML to JSON* \(option *Suppress JSON Root Element* is selected\).

Input XML Message

```
<root>
			<A>a</A>
			<B>b</B>
			<C>c</C>
			<D>d</D>
	</root>
```

Output JSON Message

```

{              

   "A": "a",

   "B": "b",

   "C": "c",

   "D": "d"               

}


```

**Special Cases**

Input XML Message: Root Element with Simple Value

```
<root>v</root>
			
```

Output JSON Message

```
"v"
			
```

Input XML Message: Root Element with no Value

```
<root></root>
			
```

Output JSON Message

```
""
			
```

Input XML Message: Root Element with Simple Value \(options *Suppress JSON Root Element, Steaming All* are selected\)

```
<root><A>a<A><B><C>c</C></B></root>
			
```

Output JSON Message

```

{"A":["a"],"B":[{"C":["c"]}]}

with dropRootElement=false

{"root":{["A":["a"],"B":[{"C":["c"]}]]}}
			
```

