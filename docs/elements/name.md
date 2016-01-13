# Intro

**Element:** ```<name>```

**Definition:** The name of a person, organization, or event (conference, meeting, etc.)
associated in some way with the resource.

**Attributes:**
```type```,
```authority```,
```authorityURI```,
```valueURI```,
```usage```,
```displayLabel```,
```nameTitleGroup```,
```altRepGroup```,
```xlink```,
```ID```,
```lang```,
```xml:lang```,
```script```,
```transliteration```,
```etal```

**Subelements:**
```<namePart>```,
```<displayForm>```,
```<affiliation>```,
```<role>```,
```<description>```,
```<etal>```,
```<nameIdentifier>```

# Indexing

## Fields Created

* ```name``` - *multivalued*, *indexed*  
Looks at all ```namepart``` sub-element.  
If the attribute ```@type!="date"``` then 
use the text of the subelement

* ```contributor``` - a *multivalued*, *indexed* field  
Looks at the ```role``` and ```roleterm``` sub-elements of the ```name```.  
If the ```roleterm!=creator```:  
The value is the ```namepart```.

* ```contributor_display``` - a *multivalued*, *indexed* field  
Combines the ```namepart``` ```roleterm``` and ```date=namepart with @type="date"```
in the following way  
```namepart[, date][ (roleterm)]```  
where ```[]``` denotes an optional component

* ```creator``` - a *multivalued*, *indexed* field  
Looks at the ```role``` and ```roleterm``` sub-elements of the ```name```.  
If the ```roleterm==creator```:  
The value is the ```namepart```.

* ```mods_role_ssim``` - a *multivalued*, *indexed* field  
Looks at the ```roleterm``` and adds the first ```roleterm```
for a given ```name``` to the list of roles availible for this document

* ```mods_role_*_ssim``` - a *multivalued*, *indexed* field  
The ```*``` in this field is the *first* roleterm associated with the name.
The value is the namepart.

* ```mods_name_place_ssim``` - a *multivalued*, *indexed* field  
If the ```name``` has a ```roleterm``` and the ```roleterm``` ends with " place".
The value is the ```namepart```.

* ```mods_name_nonplace_ssim``` - a *multivalued*, *indexed* field  
If the ```name``` does not have a ```roleterm``` **OR** 
If the ```name``` has a ```roleterm``` and 
the ```roleterm``` **DOES NOT** end with " place".
The value is the ```namepart```.

## Notes for future

* The ```@type``` attribute on the name is not used.  This could provide good information.
* Only the first namepart is ever used.
* For mods_role_ssim, only the first roleterm is used


# Display
