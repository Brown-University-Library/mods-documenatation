**Element:** ```<physicalDescription>```

**Definition:**
Describes the physical attributes of the information resource.

**Attributes:**
```displayLabel```
```altRepGroup```
```lang```
```xml:lang```
```script```
```transliteration```
```unit```

**Subelements:**
```<form>```
```<reformattingQuality>```
```<internetMediaType>```
```<extent>```
```<digitalOrigin>```
```<note>```

# Indexing
## Fields Created
* ```mods_physicalDescription_form_ssim``` - *multivalued*, *indexed*  
This element is added if the ```<physicalDescription>``` has a subelement ```<form>``` 
**without** a specified ```@type``` attribute.  
The value of this field is that of the ```<form>``` element's ```text()``` value
* ```mods_physicalDescription_form_*_ssim``` - *multivalued*, *indexed*  
This element is added if the ```<physicalDescription>``` has a subelement ```<form>``` **with** a 
specified ```@type``` attribute.  The ```*``` above is ```@type``` attribute  
The value of this field is that of the ```<form>``` element's ```text()``` value
## Direct XPATH mappings

INDEX_FIELD | XPATH
----------  |------
```mods_physicalDescription_extent_ssim``` | ```mods:physicalDescription/mods:extent```
```mods_physicalDescription_digitalOrigin_ssim``` | ```mods:physicalDescription/mods:digitalOrigin```

# Display
