# BIML-DataProvisioning-Framework

Automated development framework to automatically create data provisioning platforms using BIML Express and T4 Templates for development time Code Creation.

It has it's own repository database that is designed to be an extension of SSISDB. Rather than double up features that SSIS already has (e.g. enviornment configuration) and create confusion for administrators and developers it extends SSISDB providing further logging capabilities, metadata management and development framework solution configuration.

Currently this project only holds assets to create a basic staging layer. I'm currently working on the DW layer and adding further metadata management, ETL and ELT features. It comes setup with a workable example using Adventure Works which can be downloaded and installed seperately.

You will require at minimum:
* Visual Studio 2015
* SQL Server 2014 (inc SSIS)
* SQL Server Data Tools for Visual Studio
* BIML Express 2017 for Visual Studio

All these development tools can be accessed for free under the right circumstances (see individual licenses). See [Dev Essentials](https://www.visualstudio.com/dev-essentials/) for Visual Studio Community and SQL Server Developer Editions that includes SQL Server and SSIS. [BIML Express](https://www.varigence.com/BimlExpress) is the free Visual Studio plugin from Varigence.

It works with SQL Server 2016 also just change the deployment target in the database and SSIS projects. Note that SSIS is not yet supported in Visual Studio 2017 and therefore it's advised to work with the BIML solution in Visual Studio 2015. The other projects however can be worked in Visual Studio 2017.


## What's in this project

This repo has 2 visual studio solutions each having 2 projects.

1. **SemanticInsight.Weave**
   
   http://github.com/semanticinsight/BIML-DataProvisioning-Framework/tree/master/BIML.Framework.RDBMS/SSIS 
    
  * SemanticInsight.SSISDB (SQL Server database project)
  
    SSDB extensions for fully integrated logging, row stats, data lineage, rag status reporting, BIML script conifguration and most importantly a meta data repository with procedures that maps metadata and returns BIML script.

  * SemanticInsight.Weave (C# library)
    
    C# assembly to integrate BIML scripts with the metadata repository SemanticInsight.SSISDB
  
2. **BIML**

   https://github.com/semanticinsight/BIML-DataProvisioning-Framework/tree/master/BIML.Framework.RDBMS/SSIS

  * BIML ETL (SSIS project)
  
    This SSIS project creates the operational packages that will be deployed with re-usable emebedded framework extensions for logging, row stats, data lineage all tied to the meta data repository and mappings.
  
  * BIML Utility (SSIS Project)
    
    This SSIS project creates working development utility packages that bulk scrape metadata into the metadata repository, create tables and delete tables

## How Does it Work

![alt text](https://github.com/semanticinsight/BIML-DataProvisioning-Framework/blob/master/Framework%20Stage.png)

## Getting Started

https://semanticinsight.wordpress.com/2017/06/28/adp-framework-getting-started/

## More Docs

Configuring System Components and Schema Object mappings.
https://semanticinsight.wordpress.com/2017/07/04/adp-framework-schema-object-mapping/
