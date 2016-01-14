# Intro
**Element:** ```<genre>```

**Definition:** A term or terms that designate a category characterizing a particular style, form, or content, such as artistic, musical, literary composition, etc.

**Attributes:** 
```type```
```authority```
```authorityURI```
```valueURI```
```usage```
```displayLabel```
```altRepGroup```
```lang```
```xml:lang```
```script```
```transliteration```

**Subelements:** None

# Indexing

## Fields Created

* ```genre``` - *multivalued*, *indexed*  
The ```text()``` value of each ```genre``` element
* ```mods_genre_*_ssim``` - *multivalued*, *indexed*  
If the ```genre``` element has an attribute ```@autority```
then the ```*``` in the above field is the slugified version of 
```@authortiy```.  
The value of the field is the ```text()``` value of the element.

## Notes for future

* ```genre``` should probably be ```mods_genre_ssim``` 

# Display
