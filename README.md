# xsa-db-companies
Demonstrating micro xsa db modules

This db module (referred to as parent elsewhere) consumes the objects defined in two seperate 
standalone modules mentioned below.

| imported module | to demonstrate |
|-----|-----|
|employees| table extensions|
| organisations| procedure calls|


Also checkout the [/companies/package.json](/companies/package.json) of this module.
It references the child modules with specific versions, or with any version string compatible with npm semVer standards. 
```json
{
	"dependencies":{
		"employees":"3.12.8",		
		"organisations":"4.3.7"		
	}
}
```
This would make sure that even on an incompatible change in the child db modules, the parent would still use the older versions until
the parent is upgraded too.

PS: For this repo to build correctly, the child modules should be published to a packge manager 
and accessible from the tool used for building this db module (for ex, webide).
