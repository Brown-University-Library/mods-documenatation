# Intro

**Element:** ```<subject>```

**Definition:**
A term or phrase representing the primary topic(s) on which a work is focused.

**Attributes:**
```authority```
```authorityURI```
```valueURI```
```usage```
```displayLabel```
```altRepGroup```
```xlink```
```ID```
```lang```
```xml:lang```
```script```
```transliteration```

**Subelements:**
```<topic>```
```<geographic>```
```<temporal>```
```<titleInfo>```
```<titleInfoname>```
```<genre>```
```<hierarchicalGeographic>```
```<cartographics>```
```<geographicCode>```
```<occupation>```

# Indexing
In the following indexed fields, there is frequently the idea of a ```subject_label```  
The ```subject_label``` is constructed by looking at the attribute ```@displayLabel```  
If it ends with either ```:```, ```?```, or ```!```:  
the label is used as is.  
Otherwise a ```:``` is added to create the ```subject_label```
## Fields Created

* ```keyword``` - *multivalued*, *indexed*  
Same as mods_subject_ssim

* ```mods_subject_ssim``` - *multivalued*, *indexed*  
Looks at the ```topic``` and ```temporal``` subelements of the ```subject``` elements.
The value is constructed as follows:  
```[subject_label ]subject_value```
where ```subject_value``` is value of the respective ```topic``` or ```temporal``` subelement

* ```mods_subject_*_ssim``` - *multivalued*, *indexed*  
If the subject has an ```@authority``` attribute then the ```*``` above 
is replaced with the ```@authority```  
The value is constructed just as in ```mods_subject_ssim```

* ```mods_subject_*_ssim``` - *multivalued*, *indexed*  
If the subject has an ```@displayLabel``` attribute then the ```*``` above is replaced with a slugified version of the ```@displayLabel```  
The value is constructed as follows:  
```subject_value```
where ```subject_value``` is value of the respective ```topic``` or ```temporal``` subelement

## Direct XPATH mappings

INDEX_FIELD | XPATH
----------  |------
```subject```     | ```mods:subject/mods:name/mods:namePart[not(@type)]```
```subject```     | ```mods:subject/mods:name/mods:role/mods:roleTerm[@type="text"]```
```subject```     | ```mods:subject/mods:titleInfo/mods:title```
```subject```     | ```mods:subject/mods:cartographics```
```subject```     | ```mods:subject/mods:geographic```
```other_title``` | ```mods:subject/mods:titleInfo/mods:title```
```mods_subject_title_ssim``` | ```mods:subject/mods:titleInfo/mods:title```
```mods_cartographics_ssim``` | ```mods:subject/mods:cartographics```
```mods_geographic_ssim```    | ```mods:subject/mods:geographic```
```mods_hierarchical_geographic_continent_ssim``` | ```mods:subject/mods:hierarchicalGeographic/mods:continent```
```mods_hierarchical_geographic_country_ssim```   | ```mods:subject/mods:hierarchicalGeographic/mods:country```
```mods_hierarchical_geographic_region_ssim```    | ```mods:subject/mods:hierarchicalGeographic/mods:region```
```mods_hierarchical_geographic_province_ssim```  | ```mods:subject/mods:hierarchicalGeographic/mods:province```
```mods_hierarchical_geographic_state_ssim```     | ```mods:subject/mods:hierarchicalGeographic/mods:state```
```mods_hierarchical_geographic_territory_ssim``` | ```mods:subject/mods:hierarchicalGeographic/mods:territory```
```mods_hierarchical_geographic_county_ssim```    | ```mods:subject/mods:hierarchicalGeographic/mods:county```
```mods_hierarchical_geographic_city_ssim``` 	  | ```mods:subject/mods:hierarchicalGeographic/mods:city```
```mods_hierarchical_geographic_city_section_ssim``` | ```mods:subject/mods:hierarchicalGeographic/mods:citySection```
```mods_hierarchical_geographic_island_ssim```    | ```mods:subject/mods:hierarchicalGeographic/mods:island```
```mods_hierarchical_geographic_area_ssim```      | ```mods:subject/mods:hierarchicalGeographic/mods:area```

## Notes for future

* Could retire ```keyword``` in the indexer.
* ```other_title``` and ```mods_subject_title_ssim``` index the same thing

# Display
