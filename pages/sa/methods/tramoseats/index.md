---
layout: left-menu
title: Tramo-Seats
tagline: technical documentation for JDemetra+ using GitHub Pages
description: TramoSeats
order: 200
---

## {{page.description}}

JDemetra+ provides a new implementation of the program TRAMO-SEATS+, developed by Gianluca Caporello and Agustin Maravall -with programming support from Domingo Perez and Roberto Lopez- at the Bank of Spain, which is itself based on the program TRAMO-SEATS, previously developed by Victor Gomez and Agustin Maravall.

{: .alert .alert-info}
_Due to different algorithmic solutions and/or to different programming approaches, the results of the two software may be on occasions slightly different._

The entry point of TRAMO-SEATS in JD+ is integrated in the class `TramoSeatsProcessingFactory` (in the package `ec.satoolkit.algorithm.implementation`).  
Basically, the user has to define a `TramoSeatsSpecification` (often by reusing an existing one) and to use it with a time series (`TsData` object)

``` java
// Create/get the ts (for example...)
TsData input = Data.P;
// Using a pre-defined specification
TramoSeatsSpecification rsafull=TramoSeatsSpecification.RSAfull;
// Process
IProcResults rslts = TramoSeatsProcessingFactory.process(input, rsafull);
```

In most cases, the generic interface for retrieving information through dictionaries will be sufficient

``` java
// Gets the main series of the decomposition + the decomposition mode
TsData sa = rslts.getData("sa", TsData.class);
TsData trend = rslts.getData("t", TsData.class);
TsData irr = rslts.getData("i", TsData.class);
DecompositionMode mode = rslts.getData("mode", DecompositionMode.class);
```


