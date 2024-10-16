# Overview

## Working with modern (cloud) data formats
An overwiew of the common cloud-optimised formats and the their advantages can be found [here](https://guide.cloudnativegeo.org/). In this book we will be focusing on Zarr format and how to use it. 

### Introduction to zarr
The Zarr data format is a community-maintained format for large n-dimensional data, which may be difficult to download to users’ machines. Zarr breaks up the data into smaller chunks and organizes it in a way where users can take just take the bits they need or distribute the load of processing to lots of those bits (stored as chunks) across many machines.

The Zarr data format has been adopted by various groups, who have created [open datasets](https://zarr.dev/datasets/), including [CMIP6](https://console.cloud.google.com/marketplace/details/noaa-public/cmip6) & [ERA5](https://cloud.google.com/storage/docs/public-datasets/era5) data. 

In this book we will introduce some of these public datasets and how to use Zarr with xarray. More background information on Zarr and how to use it can be found [here](https://guide.cloudnativegeo.org/zarr/intro.html)

## Tutorials in this book
### 1. [Cloud Optimized ERA5](ARCO-ERA5.ipynb)

In their [public dataset program](https://cloud.google.com/storage/docs/public-datasets), Google's Cloud Storage provides a variety of public datasets that can be accessed by the community. Google pays for the hosting of these datasets.

One of these datasets is an "Analysis-Ready, Cloud Optimized" [(ARCO) ERA5 dataset](https://github.com/google-research/arco-era5) from 1940 to now. In this section, we go over opening and selecting ARCO ERA5 data, how chunking data works and its drawbacks as well as plotting the data with cartopy. 

### 2. [Zarr store for FLUXNET2015](FLUXNET2015.ipynb)

The [FLUXNET2015 dataset](https://fluxnet.org/data/fluxnet2015-dataset) is an amazing collection of site data from multiple regional flux networks.
The data collection and analysis represents the efforts of hundreds of scientists and technicians around the world, and [has broad applications ranging from ecophysiology studies, remote sensing studies, and development of ecosystem and Earth system models](https://doi.org/10.1038/s41597-020-0534-3).

FLUXNET data is stored in CSV format, which needs to be downloaded by the user from a database requiring an account. This process can be time consuming and make it more difficult to reproduce research. 

In this section, [a Zarr store](https://github.com/EXCITED-CO2/zarr-fluxnet2015) of a sample of FLUXNET2015 data is used as an example for opening and using Zarr data to plot variables. 

### 3. [Dask: lazy and distributed compute](lazy_computation.ipynb)

 In the [EXCITED project](https://research-software-directory.org/projects/excited) we developed a tool to perform regridding in xarray, using lazy computation, which is a common operation in geosciences, either to reduce computation time or to aggregate data onto a common grid. Lazy computation is when you only load data and perform the computations once it is required, which reduces processing time and memory consumption.

In this section, we use [xarray-regrid](https://github.com/xarray-contrib/xarray-regrid) to regrid sea surface temperatures as an example of lazy computation. 
