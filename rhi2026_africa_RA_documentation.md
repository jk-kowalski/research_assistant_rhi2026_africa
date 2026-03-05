# RHI 2026: Guidebook to Data Processing for Research on Human Capital in Africa

Kuba Kowalski, Research Assistant (kuba.kowalski@wur.nl)

Supervised by the Economic and Environmental History Group: Sandra de
Pleijt & Ewout Frankema

Start & end of assistantship: 02/03/2026-01/06/2026 (extension possible)

Last modified on 3/3/2026 3:15 PM

## Table of Contents

[1. Overview [2](#overview)](#overview)

[2. Data Collection [3](#data-collection)](#data-collection)

[3. Processing [4](#processing)](#processing)

[1_mortality.sql & 2_fertility.sql [4](#_Toc207883749)](#_Toc207883749)

[3_regression_prov.ipynb [6](#_Toc207883750)](#_Toc207883750)

[4_regression_micro.ipynb [6](#_Toc207883751)](#_Toc207883751)

[4. Results [7](#results)](#results)

[Microdata [7](#microdata)](#microdata)

[Summary Statistics [7](#summary-statistics)](#summary-statistics)

[Spatial Datasets [8](#spatial-datasets)](#spatial-datasets)

[Maps [8](#maps)](#maps)

[Annex A: List of all variables [9](#annex-a)](#annex-a)

[Annex B: Codebook for Key Variables
[11](#_Toc207883758)](#_Toc207883758)

## 1. Overview

This document is a guidebook which describes all steps of processing a
CSV extract and Shapefiles from IPUMS using the software PostgreSQL for
the purpose of studying the growth of human capital in Africa. For
overview of countries, see [Table 1](#_Ref223444060).

  -------------------------------------------------------------------------------
  ID   Research Area    Research        Database           Comments
                        Timeframe       integration (Y/N)  
  ---- ---------------- --------------- ------------------ ----------------------
  1    Benin            2013, 2002,                        
                        1992, 1979                         

  2    Botswana         2011, 2001,                        
                        1991, 1981                         

  3    Burkina Faso     2006, 1996,                        
                        1985                               

  4    **Côte           1998, 1988                         
       d'Ivoire**                                          

  5    **Ethiopia**     2007, 1994,                        Beware of migratory
                        1984                               tribes. Birth_prov
                                                           untrustworthy. Consult
                                                           Ewout.

  6    **Ghana**        2010, 2000,                        
                        1984                               

  7    Guinea           2014, 1996,                        
                        1983                               

  8    **Kenya**        2019, 2009,                        
                        1999, 1989,                        
                        1979, 1969                         

  9    Malawi           2018, 2008,                        
                        1998, 1987                         

  10   Mali             2009, 1998,                        
                        1987                               

  11   Mozambique       2017, 2007,                        
                        1997                               

  12   Rwanda           2012, 2002,                        
                        1991                               

  13   **Senegal**      2013, 2002,                        
                        1988                               

  14   Sierra Leone     2015, 2004                         

  15   **Tanzania\***   2012, 2002,                        First attempt at
                        1988                               database construction

  16   Togo             2010, 1970,                        
                        1960                               

  17   Uganda           2014, 2002,                        
                        1991                               

  18   Zambia           2010, 2000,                        
                        1990                               
  -------------------------------------------------------------------------------

  : []{#_Ref223444060 .anchor}Table 1. Overview of research areas,
  timeframes, and integration in PostgreSQL database. Research areas in
  bold were labelled by Ewout as of extra importance. Asterix (\*)
  indicates ongoing database integration

Below are the scripts that process the CSV extract with the following
run order:

- \[Placeholder\]

The scripts create multiple outputs with the following being most
important:

- \[Placeholder\]

- PostgreSQL database:

  - rhi2025_database_final.sql[^1]

Additionally, the following map ensembles were created using the
exported GEOJSON files in the PDF, PNG and SVG formats:

- \[Placeholder\]

## 2. Data Collection

All data was collected from IPUMS between April and August 2025. The
following datasets were downloaded and are available in \".\\path\":

- \[placeholder\]

## 3. Processing 

### 3.1 Tanzania (15)

The following choices were made in the processing of the Tanzania
dataset

## 4. Results

### Microdata

- \[Placeholder

### Summary Statistics

These are the datasets created by aggregating on province-level
(geolvl1) and district-levels (geolvl2). The specifications per file
are:

- Dataset.csv

  - Variables: XX (n1, n2, n3...

  - Rows: XX

### Spatial Datasets

These are the summary statistics datasets after a table join with the
province and district shapefiles. All specifications are the same as for
the summary statistics file in the CSV format, except for the addition
of a geometry column (GEOM). View these datasets by dragging and
dropping them in QGIS or by using the tool "JSON to Feature" in ArcGIS
Pro[^2].

- mortality_summary_prov_geom.geojson

### Maps

The maps were generated using ArcGIS Pro and the aforementioned GEOJSON
files. For replicability, please see the packaged ArcGIS Pro project
which includes all loaded datasets, layout formats, symbology presents,
and everything else possibly required to replicate the maps.

## Annex A

[^1]: If a password is requested when importing the database, put in
    "rhi2025". Same password used for the Indonesia database.

[^2]: Important, when importing the GEOJSON files to ArcGIS Pro, it is
    possible that the province or combined department will not be
    initially visible. To make it visible, apply the tool "Repair
    Geometry". IPUMS occasionally merges geolvl2 boundaries. See
    codebook for detailed documentation.
