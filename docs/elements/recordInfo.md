# Intro

**Element:** ```<recordInfo>```

**Definition:**
Information about the metadata record.

**Attributes:**
```displayLabel; altRepGroup; lang; xml:lang; script; transliteration```

**Subelements:**
```<recordContentSource>```
```<recordCreationDate>```
```<recordChangeDate>```
```<recordIdentifier>```
```<recordOrigin>```
```<recordInfoNote>```
```<languageOfCataloging>```
```<descriptionStandard>```

# Indexing

```mods_record_info_record_identifier_ssim``` - indexed, multivalued  
If ```<recordInfo>``` has a subelement ```<recordIdentifier>``` then include that value in this field

```mods_record_info_record_identifier_*_ssim```- indexed, multivalued  
Same as above, however ```*``` is the slugified version of the ```@source``` 
attribute of the ```<recordIdentifier>```

# Display

