# Intro
**Element:** ```<note>```

**Definition:** General textual information relating to a resource.

**Attributes:**
```type```
```displayLabel```
```altRepGroup```
```xlink```
```ID```
```lang```
```xml:lang```
```script```
```transliteration```
```typeURI```

**Subelements:** None

# Indexing

## Fields Created
In the following indexed fields, there is frequently the idea of a ```note_label```  
The ```note_label``` is constructed by looking at the attribute ```@displayLabel```  
If it ends with either ```:```, ```?```, or ```!```:  
the label is used as is.  
Otherwise a ```:``` is added to create the ```note_label```

* ```note``` - *multivalued*, *indexed*  
The value is constructed as follows:  
```[note_label ]note_value```
where ```note_value``` is the```text()``` value of the element
* ```mods_note_*_ssim``` - *multivalued*, *indexed*  
The ```*``` above is the slugified version of the attribute ```@displayLabel``` if available
The value is the```text()``` value of the element
* ```mods_note_*_ssim``` - *multivalued*, *indexed*  
The ```*``` above is the slugified version of the attribute ```@type``` if available
The value is the```text()``` value of the element

# Display
