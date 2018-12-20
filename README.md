# xsa-db-companies
Demonstrating micro xsa db modules

This db module (referred to as parent elsewhere) consumes the objects defined in two seperate 
standalone modules mentioned below.

| imported module | to demonstrate |
|-----|-----|
|[employees](https://github.com/ifb-servicesNA/xsa-db-employees)| table extensions|
| [organisations](https://github.com/ifb-servicesNA/xsa-db-organisations)| procedure calls|


Also checkout the [/companies/package.json](/companies/package.json) of this module.
It references the child modules with specific versions, or with any version string compatible with npm semVer standards. 

For eg: in the below dependencies section, companies db module requires any version of employees module between 3.12.8 and 3.14.9.
Whereas, the organisations module can be anything less than 4.3.7
```json
{
	"dependencies":{
		"employees":"3.12.8-3.14.9",		
		"organisations":"<4.3.7"		
	}
}
```
This would make sure that even on an incompatible change in the child db modules, the parent would still use the older versions until
the parent is upgraded too.

PS: For this repo to build correctly, the child modules should be published to a packge manager 
and accessible from the tool used for building this db module (for ex, webide).

PPS: Testcases can be defined individually for each child repo's objects and treated as a blackbox from the parent's perspective.
