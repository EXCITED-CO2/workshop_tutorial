(intro)=
# A tutorial for 'Advancing ecosystem carbon flux research'

This book helps to explore tools and datasets, that are useful for researchers working topics ranging from processes in the carbon cycle to machine learning tools and remote sensing. This book will be tested within the ["Advancing ecosystem carbon flux research"](https://www.lorentzcenter.nl/advancing-ecosystem-carbon-flux-research.html) at the Lorentz Center between 14 - 18 October 2024 and be used to inform the discussion on research priorities for the terrestrial carbon cycle and technical developments for research in the next decade. 

The aim is for the concepts covered during the workshop to open the discussion on openess and reproducibility with the community and to introduce researchers to some useful tools and concepts that can be transfered to their research. 

# Working with modern (cloud) data formats
Geospatial data is experiencing exponential growth in both size and complexity. As a result, traditional data access methods, such as file downloads, have become increasingly impractical for achieving scientific objectives. With the limitations of these older methods becoming more apparent, cloud-optimized geospatial formats present a much-needed solution.

Cloud optimization enables efficient, on-the-fly access to geospatial data. An overwiew of the common formats and the advantages of cloud-optimised formats can be found [here](https://guide.cloudnativegeo.org/)

## Zarr
Currently, many datasets, such as FLUXNET are stored in CSV or netcdf/hdf5 formats, which need to be downloaded by the user from a database requiring an account. This process can be quite time consuming and make it difficult to replicate research if the version, variables used etc are not adequately documented. 

### Why use Zarr instead of formats such as CSV/TIFF

Zarr format provides a clean library for accessing the internals of binary files, it also makes those internals themselves simple and transparent. Each n-dimensional chunk of data is given a name and placed in a separate file making it accessible without the need for a library and vastly improving parallelism.

An added benefit of the simplicity of Zarr is how tractable keeping your data FAIR and accessible in the long-term becomes. Though the bytes need decoding, a fair amount of the general structure needs no interpretation. 

More information on the benefits and uses of Zarr can be found [in this blog](https://medium.com/open-source-science-initiative/why-i-zarr-ee64eb7ffbf8).

Additionally, due to the nature of CSV files, the metadata is included in a separate file and not with the data


