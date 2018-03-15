# Samples-Aviation
This is the README file for SAMPLES-AVIATION. 
The end of the file has setup instructions.
************************************************************************************
Use or operation of this code is subject to acceptance of the license available in the code 
repository for this code.
************************************************************************************
SAMPLES-AVIATION provides sample data for use in exploring InterSystems IRIS Text Analytics capabilities. 
In order to use this sample, you must have an InterSystems IRIS license that includes these capabilities.

After setup, the data is available for use in various ways:
* For use in [InterSystems IRIS Natural Language Processing](http://docs.intersystems.com/irislatest/csp/docbook/DocBook.UI.Page.cls?KEY=GIKNOW).
  The repo also contains specific samples related to NLP.
* For use with [InterSystems IRIS SQL Search](http://docs.intersystems.com/irislatest/csp/docbook/DocBook.UI.Page.cls?KEY=GSQLSRCH).
* For use with [Text Analytics options in InterSystems IRIS Business Intelligence](http://docs.intersystems.com/irislatest/csp/docbook/DocBook.UI.Page.cls?KEY=D2MODADV_ch_iknow).
  
  The repo also contains specific samples related to these options.

## Repo items related to the data
* The `Aviation.Aircraft`, `Aviation.Crew`, and `Aviation.Event` classes are persistent
  classes/tables that collectively represent a selected subset of aviation 
  incidents reported to the U.S. National Transportation Safety Board. 
  
* Upon setup (see end), data is loaded from the `gbl/Aviation.xml` file into these
  classes.

* The `Aviation.Utils` class is a helper classes used by the repo setup routine (see end).

## Repo items for use with InterSystems IRIS Natural Language Processing (NLP) 
* The `Aviation.ReportDomain` class defines a sample NLP domain based on the data
  from this repo. You can run NLP queries against this domain. See [Using InterSystems IRIS Natural Language Processing](http://docs.intersystems.com/irislatest/csp/docbook/DocBook.UI.Page.cls?KEY=GIKNOW).

* The `Aviation.Classification.Utils` class illustrates how to build and test Text 
  Categorization models programmatically. See [Text Categorization](http://docs.intersystems.com/irislatest/csp/docbook/DocBook.UI.Page.cls?KEY=GIKNOW_textcat).

* The `Aviation.Metrics.Builder` and `Aviation.Metrics.Definition` classes demonstrate
  how to customize NLP by adding custom metrics. See [Custom Metrics](http://docs.intersystems.com/irislatest/csp/docbook/DocBook.UI.Page.cls??KEY=GIKNOW_metrics).

* The `Aviation.UI` package contains two sample classes that you can use to perform
  NLP queries and visualize the results.

## Repo items for use with Text Analytics options in InterSystems IRIS Business Intelligence (BI)
* The `Cubes` package contains BI cube definitions that use Text Analytics features
  and that use the data in this repo. See [Using Text Analytics in Cubes](http://docs.intersystems.com/irislatest/csp/docbook/DocBook.UI.Page?KEY=D2MODADV_ch_iknow) for details.
* `KPI.TopConcepts` contains a BI KPI that uses a Text Analytics query.
* `KPI.Actions` defines a KPI action (which is used on a dashboard also in this sample).
* `Aviation.DashboardsEtc` defines Business Intelligence pivot tables and dashboards
  that display the data in this repo and that provide you the ability of performing
  simple analyses of that data.

## Setup instructions
1. Clone or [download](http://docs.intersystems.com/irislatest/csp/docbook/DocBook.UI.Page.cls?KEY=asamples) the repository.
2. If you have not yet created a namespace in InterSystems IRIS, follow the [detailed instructions](http://docs.intersystems.com/irislatest/csp/docbook/DocBook.UI.Page.cls?KEY=ASAMPLES_createns) to do so. These instructions also provide the steps to create a web application for use in this namespace and enable that web app for use with analytics. Complete those steps as well.
3. Open the InterSystems IRIS Terminal.
4. Enter the following command (replacing with the namespace where you want to load the sample):
```
   ZN "mynamespace"
   ```
5. Enter the following commands (replacing with the full path of the file `buildsample/Build.AviationSample.cls`):
```
   do $system.OBJ.Load("full-path-to-Build.AviationSample.cls","ck")
   do ##class(Build.AviationSample).Build()
```
6. When prompted, enter the full path of the directory to which you downloaded this sample. The method then loads and compiles the code and performs other needed setup steps.

