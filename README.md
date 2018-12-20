# xsa-db-companies
Demonstrating micro xsa db modules

This db module (referred to as parent elsewhere) consumes the objects defined in two seperate 
standalone modules mentioned below.

| imported module | to demonstrate |
|-----|-----|
|employees| table extensions|
| organisations| procedure calls|


Also checkout the [/companies/package.json](/companies/package.json) of this module. It references the child modules. 

For this repo to build correctly, the child modules should be published to a packge manager 
and accessible from the tool used for building this db module (for ex, webide).