# GenerateDataUsingTemplate
Tool to generate large data using a template and CSV

Add a template of what data needs to be generated and pass the data in CSV format to generate the complete output

## **Example 1 (Create an XML):**

**Template:**
```
<product>
	<id>{0}</id>
	<name>{1}</name>
	<cost>{2}</cost>
	<tag>{3}</tag>
</product>
```

**Data (CSV):**

Item1, Alpha, 100, single

Item2, Mega Bundle, 500, bundle

Item3, Beta, 250, single

Item4, Polo, 300, single

**Output**
```
<product>
	<id>Item1</id>
	<name>Alpha</name>
	<cost>100</cost>
	<tag>single</tag>
</product>
<product>
	<id>Item2</id>
	<name>Mega Bundle</name>
	<cost>500</cost>
	<tag>bundle</tag>
</product>
<product>
	<id>Item3</id>
	<name>Beta</name>
	<cost>250</cost>
	<tag>single</tag>
</product>
<product>
	<id>Item4</id>
	<name>Polo</name>
	<cost>300</cost>
	<tag>single</tag>
</product>
```

## **Example 2 (Create a json config):**

**Template:**
```
{
    "Id": "{0}",
    "Name": "{1}",
    "ProductId": "{2}",
    "Co": [
        {
            "c": "{3}",
            "v": {4}
        }
    ]
}
```

**Data (CSV):**

OFF-001, Offer1, com.company.offer1, usd, 1.99

OFF-002, Offer2, com.company.offer2, usd, 9.99

OFF-003, Offer3, , diamon, 400

OFF-004, Offer4, com.company.offer4, usd, 49.99

**Output**
```
{
    "Id": "OFF-001",
    "Name": "Offer1",
    "ProductId": "com.company.offer1",
    "Co": [
        {
            "c": "usd",
            "v": 1.99
        }
    ]
},
{
    "Id": "OFF-002",
    "Name": "Offer2",
    "ProductId": "com.company.offer2",
    "Co": [
        {
            "c": "usd",
            "v": 9.99
        }
    ]
},
{
    "Id": "OFF-003",
    "Name": "Offer3",
    "ProductId": "",
    "Co": [
        {
            "c": "diamond",
            "v": 400
        }
    ]
},
{
    "Id": "OFF-004",
    "Name": "Offer4",
    "ProductId": "com.company.offer4",
    "Co": [
        {
            "c": "usd",
            "v": 49.99
        }
    ]
}
```
