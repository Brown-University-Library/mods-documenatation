#Intro

**Element:** ```<titleInfo>```

**Definition:** A word, phrase, character, or group of characters, normally appearing in a
resource, that names it or the work contained in it.

**Attributes:**
``` type```, ``` authority```, ``` authorityURI, valueURI```, ``` usage```, ``` displayLabel```, ``` supplied```, ``` nameTitleGroup```, ``` altRepGroup```, ``` altFormat```, ``` contentType```, ``` xlink```, ``` ID```, ``` lang```, ``` xml:lang```, ``` script```, ``` transliteration```, ``` otherType```

**Subelements:**
```<title>```, ```<subTitle>```, ```<partNumber>```, ```<partName>```, ```<nonSort>```

# Indexing

## Current
```titleInfo``` is a repeatable element and the indexing will vary  depending upon the attribute ```type```

## Fields Created

* ```mods_title_alt``` - a *multivalued*, *indexed* field
all ```title``` sub-elements of the set of ```titleInfo``` which have the attribute ```@type="alternative"```

* ```other_title``` - a *multivalued*, *indexed* field
all ```title``` sub-elements of the set of ```titleInfo``` which have the attribute ```@type!="alternative"``` which are not the first element

* ```primary_title``` - a *single valued*, *sortable* *indexed* field
```title``` sub-element of the the first ```titleInfo```
in the set of ```titleInfo``` which have the 
attribute ```@type!="alternative"``` 

* ```subtitle``` - a *single valued*, *sortable* *indexed* field
```subtitle``` sub-element of the the first ```titleInfo```
in the set of ```titleInfo``` which have the 
attribute ```@type!="alternative"``` 

* ```partnumber``` - a *single valued*, *sortable* *indexed* field
```partnumber``` sub-element of the the first ```titleInfo```
in the set of ```titleInfo``` which have the 
attribute ```@type!="alternative"``` 

* ```partname``` - a *single valued*, *sortable* *indexed* field
```partname``` sub-element of the the first ```titleInfo```
in the set of ```titleInfo``` which have the 
attribute ```@type!="alternative"``` 

* ```nonsort``` - a *single valued*, field
```nonsort``` sub-element of the the first ```titleInfo```
in the set of ```titleInfo``` which have the 
attribute ```@type!="alternative"``` 

## Notes for future
* Only the "primary" title has it's non ```title``` subelements indexed.  This should change
* More types are vailable than ```type="alternative"```.  Such as ```abbreviated```, ```translated```, and ```uniform```
* A composit title or ```mods_title_full``` could be created wich is an intelligent concatination of the sub-elements in a given ```titleInfo``` element. It may be useful to sort on this.
* The attribute "@displayLabel" should be respected and incorporated if present
* If ```@type="translated"``` then the ```@language``` attribute would be important

# Display

## Current

Usually only the elements associated with the ```primary_title``` are displayed they are a concatination of 
```
[nonsort] primary_title[: subtitle] [partname] [partnumber]
```
