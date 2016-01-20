# Intro

**Element:** ```<relatedItem>```

**Definition:**
Information that identifies other resources related to the one being described.

**Attributes:**
```type```
```xlink:href```
```displayLabel```
```ID```
```otherType```
```otherTypeAuth```
```otherTypeAuthURI```
```otherTypeURI```

**Subelements:**
All MODS elements can appear as subelements.

# Indexing
## Fields Created
* ```collection_title``` - *indexed* *multivalued*  
If a ```<relatedItem>``` has a ```<titleInfo><title>``` sublement **AND** the attribute
```@type=='host'``` **AND** the attribute ```@displayLabel``` starts with ```"Collection"```  
the value is ```text()``` value of the ```<title>```
* ```other_title``` - *indexed* *multivalued*  
If a ```<relatedItem>``` has a ```<titleInfo><title>``` sublement that does not 
fulfill that of the ```collection_title``` field above:  
the value is ```text()``` value of the ```<title>```

* ```mods_related_id_ssim```- *indexed* *multivalued*  
If a ```<relatedItem>``` has a ```<identifier>``` sublement
the value is ```text()``` value of the ```<identifier>```
* ```mods_related_id_*_ssim```- *indexed* *multivalued*  
If a ```<relatedItem>``` has a ```<identifier>``` sublement with a ```@type``` attribute:  
the ```*``` above is the slugified version of the ```@type``` attribute  
the value is ```text()``` value of the ```<identifier>```
* ```mods_related_name_ssim```- *indexed* *multivalued*  
If a ```<relatedItem>``` has a ```<name><namePart>``` sublement
the value is ```text()``` value of the ```<namePart>```

## Direct XPATH mappings

INDEX_FIELD | XPATH
----------  |------
```mods_collection_id``` | ```mods:relatedItem[@type="host" and starts-with(@displayLabel,"Collection")]/mods:identifier[@type = "COLID"]```

# Display
