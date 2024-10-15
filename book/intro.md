(intro)=
# A tutorial for 'Advancing ecosystem carbon flux research'

This book helps to explore tools and datasets, that are useful for researchers working topics ranging from processes in the carbon cycle to machine learning tools and remote sensing. This book will be tested within the ["Advancing ecosystem carbon flux research"](https://www.lorentzcenter.nl/advancing-ecosystem-carbon-flux-research.html) at the Lorentz Center between 14 - 18 October 2024 and be used to inform the discussion on research priorities for the terrestrial carbon cycle and technical developments for research in the next decade. 

The aim is for the concepts covered during the workshop to open the discussion on openess and reproducibility with the community and to introduce researchers to some useful tools and concepts that can be transfered to their research. A longer overview of the material and sections covered in the workshop can be found [here](https://excited-co2.github.io/workshop_tutorial/main/overview.html)

## Working with modern (cloud) data formats
Currently, many datasets, such as FLUXNET are stored in CSV or netcdf/hdf5 formats, which need to be downloaded by the user from a database requiring an account. This process can be quite time consuming and make it difficult to replicate research if the version, variables used etc are not adequately documented. Additionally, geospatial datasets in general are becoming increasingly large and complex and as a result, downloading data has become increasingly impractical. Cloud-optimized geospatial formats present an alternative to downloading data, that is more efficient, flexible and scalable. Additionally, it allows the user to more easily download subsets of data, rather than the entire dataset.

An overwiew of the common formats and the advantages of cloud-optimised formats can be found [here](https://guide.cloudnativegeo.org/)

### Zarr
One common and increasingly popular cloud-optimised format is Zarr, which is community-maintained and designed for large datasets. With cloud-hosted data becoming easier and more common, Zarr was created out of the need for scientific data formats to be optimised for object storage rather than file-based storage. Therefore, Zarr has specific features that make it optimised for the cloud, not found in file formats like netCDF. Although Zarr has many advantages but it important to firstly consider the application, as its use may not always be ideal, such as in block-storage filesystems like HPCs. More information on the differences can be found [here](https://www.unidata.ucar.edu/blogs/news/entry/netcdf-vs-zarr-an-incomplete) and how to choose between the NetCDF and Zarr [here](https://help.marine.copernicus.eu/en/articles/8176692-how-to-choose-between-netcdf-and-zarr-format-using-the-toolbox).

#### Why use Zarr

In many cases, there are several advantages to using Zarr:

- Parallel computing: Zarr’s flexible indexing and compatibility with object storage lends itself to parallel processing. It provides a clean library for accessing the internals of binary files and also makes those internals themselves simple and transparent. Each n-dimensional chunk of data is given a name and placed in a separate file making it accessible without the need for a library. Zarr also integrates with popular parallel computing libraries, like dask. 

- Chunked and compressed storage: Data is stored into manageable chunks and supports compression algorithms. This approach allows for random access to subsets of the data and makes handling Zarr data less memory intensive and faster.  

- FAIR and accessible data: Though the bytes need decoding, a fair amount of the general structure needs no interpretation. Additionally, Zarr stores metadata alongside the data, which enhances organisation and facilitates reproducibility in scientific workflows.

 More information on the benefits and uses of Zarr can be found [in this blog](https://medium.com/open-source-science-initiative/why-i-zarr-ee64eb7ffbf8).
