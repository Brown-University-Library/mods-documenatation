# Intro
**Element:** ```<originInfo>```

**Definition:**  Information about the origin of the resource,
including place of origin or publication, publisher/originator, 
and dates associated with the resource.

**Attributes:**
```eventType```
```displayLabel```
```altRepGroup```
```lang```
```xml:lang```
```script```
```transliteration```

**Subelements:**
```<place>```
```<publisher>```
```<dateIssued>```
```<dateCreated>```
```<dateCaptured>```
```<dateValid>```
```<dateModified>```
```<copyrightDate>```
```<dateOther>```
```<edition>```
```<issuance>```
```<frequency>```

# Indexing
## Indexing Publisher/Publication Place (Direct XPATH mappings)

INDEX_FIELD | XPATH
----------  |------
```publisher```           | ```mods:originInfo/mods:publisher```
```mods_publisher_ssim``` | ```mods:originInfo/mods:publisher```
```publication_place```           | ```mods:originInfo/mods:place/mods:placeTerm[@type="text"]```
```mods_publication_place_ssim``` | ```mods:originInfo/mods:place/mods:placeTerm[@type="text"]```
```publication_code```           | ```mods:originInfo/mods:place/mods:placeTerm[@type="code"]```
```mods_publication_code_ssim``` | ```mods:originInfo/mods:place/mods:placeTerm[@type="code"]```

**Note:** Duplication above.  Preference is for namespaced fields.


## Indexing Dates
The following discussion is applicable to each of the following date subelements
```<dateCreated>```
```<dateIssued>```
```<dateCaptured>```
```<dateValid>```
```<dateModified>```
```<copyrightDate>```
```<dateOther>```


For each of these non-empty date elements we look at the following attributes.
```@qualifier```, ```@point```, ```@keyDate```

The first of each sub-element adds the following fields, if ```@qualifier!='questionable'```
and ```(@point!='end' or @keyDate=='yes')```:

* ```[date_name]``` - *indexed*, *single-valued*  
The ```text()``` value for the above element converted into ```ISO 8601``` if possible.  
Ex: ```YYYY-MM-DDT00:00:00Z```.
* ```[date_name]_year_ssim``` - *indexed*, *multivalued*  
Just the ```YYYY``` part of the above date
* ```[date_name]_ssim``` - *indexed* *multivalued*  
If the date is not in ```ISO 8601``` format.  
Just store the ```text()``` value of the element.
* ```mods_dateOther_quarter_facet``` - *indexed* *multivalued*  
This field is added if ```[date_name]==dateOther``` and ```@type=='quarterSort'```  
The value is ```text()```
* ```mods_dateOther_year_facet``` - *indexed* *multivalued*  
This field is added if ```[date_name]==dateOther``` and ```@type=='yearSort'```  
The value is ```text()```
* ```mods_[date_name]_end_ssim``` - *indexed* *multivalued*  
This field is added if ```@point=='end'```  
The value is ```text()```
* ```mods_[date_name]_[qualifier]_ssim``` - *indexed* *multivalued*  
This field is added if @qualifer is in the following list ```approximate```,
```inferred```, ```questionable```  
The value is ```text()```



# Display
