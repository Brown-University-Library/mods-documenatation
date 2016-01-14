# Intro
**Element:** ```<identifier>```

**Definition:** Contains a unique standard number or code that distinctively identifies a resource.

**Attributes:**
```type```
```displayLabel```
```invalid```
```altRepGroup```
```lang```
```xml:lang```
```script```
```transliteration```
```typeURI```

**Subelements:** None

# Indexing

## Fields Created
All of the following identifiers do not have an attribute ```@type``` in the following set of values ```COLID``` ```URI ``` ```doi``` ```METSID```

* ```identifier``` - *multivalued*, *indexed*  
The value is the```text()``` value of the element
* ```mods_id_*_ssim``` - *multivalued*, *indexed*  
The ```*``` above is the slugified version of the attribute ```@displayLabel``` if available
The value is the```text()``` value of the element
* ```mods_id_*_ssim``` - *multivalued*, *indexed*  
The ```*``` above is the slugified version of the attribute ```@type``` if available
The value is the```text()``` value of the element

## Direct XPATH mappings

INDEX_FIELD | XPATH
----------  |------
```mods_id_doi_ssi``` | ```mods:identifier[@type="doi"]```
```mods_id_mets_ssi``` | ```mods:identifier[@type="METSID"]```
```mets_id``` | ```mods:identifier[@type="METSID"]```

# Display
