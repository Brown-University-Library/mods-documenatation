# Intro
**Element:** ```<language>```

**Definition:** A designation of the language in which the content of a resource is expressed.

**Attributes:**
```usage```
```objectPart```
```displayLabel```
```altRepGroup```
```lang```
```xml:lang```
```script```
```transliteration:```

**Subelements:** ```<languageTerm>``` ```<scriptTerm>```

# Indexing

## Fields Created

* ```mods_language_ssim``` - *multivalued*, *indexed*
Looks at the ```languageTerm``` subelement of the ```language``` element.
The value of the field is the ```text()``` value of the ```languageTerm``` subelement.

* ```mods_language_*_ssim``` - *multivalued*, *indexed*
If the languageTerm has a ```@type``` attribute then the ```*``` above
is replaced with the ```@type```
The value is constructed just as in ```mods_language_ssim```
    * ```mods_language_text_ssim``` and ```mods_language_code_ssim``` are common fields created with this patterm. 

# Display
