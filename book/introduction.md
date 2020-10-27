# Introduction

ServiceX furnishes data in a columnar form (root files or parquet files, currently).

## How to get the Data

There are a number of ways to build a _query_ for ServiceX. Examples and some user documentation is contained in the rest of this document for each of the ways:

- `TCut` queries for a simple list of columns of data and simple cuts.
- `func_adl` for more complex or computer generated cuts, or if you'd like to flatten your query.
- `qastle` for low-level queries.

## Data formats

ServiceX can and extract columns of data from the following sources:

- Flat ROOT files (any `root` file that can be ready by `uproot`). Often referred to as the `uproot` backend.
- ATLAS `xAOD` binary files, using the `AnalysisBase` C++ framework to extract the data. Often referred to as the `xAOD` backend.

Natively, ServiceX will return `parquet` and `root` files:

- The ATLAS `xAOD` backend returns `root` files.
- The `uproot` backend returns `parquet` files.

The `servicex` frontend can convert both of those file formats to an in memory format after automatically downloading the files to your machine:

- `pandas` - The query must return a flat dataset that will fit into a `pandas DataFrame` neatly: no nested data.
- `awkward0 LazyArray` - Supports all formats of data the query can generate.

## Capabilities for Column Shape

There are a number of options you can use describe your columns of data. At its core, ServiceX can:

- Deliver all data column, e.g. all electron $p_T$'s.
- Filter a column, e.g. all electrons $p_T>30 GeV$
- Create a new column, $p_T/1000.0$
- Calculate quantities that relate one column to another, e.g. jet $p_T$ for only jets that are within $\Delta R < 0.2$ of a MC particle with $pdgId=35$.
