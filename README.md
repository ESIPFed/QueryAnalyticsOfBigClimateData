# Query Analytics of Big Climate Data
A High Performance Spatial Web Portal for Query Analytics of Big Climate Data

Observations, model simulations, and reanalysis produce vast amounts of climate data. The unprecedented data volume and intrinsic complexity of geospatial statistics and analysis requires efficient analysis to investigate global problems such as climate change, natural disasters, diseases, and other environmental issues. However, this requirement poses grand challenges due to the unprecedented data volume and intrinsic complexity of geospatial statistics and analysis. Addressing these challenges requires efficient data management strategies, complex parallel algorithms and scalable computing resources. These challenges result in a noticeable gap between the vast amount of data and user communities.  Existing solutions are not sufficient to bridge the gap because they 1) lack flexibility. Most climate analysis tools (web-based or standalone) only allow users to conduct analysis using pre-built operations, and provide non-customizable functions and operations; and 2) have limitations in handling multi-dimensional, large-scale climate data since they lack the seamless integration of parallel computing and geospatial analytical functions.

To bridge the gap and strength the ties between climate data (providers) and user communities, in this project we prototype a high performance spatial web portal for parallel query analytics of big climate data. The back-end of the web portal is built upon two core technologies developed by the investigators including 1) a spatiotemporal indexing for efficient climate data management and access with Hadoop MapReduce (Li et al., 2016) and, and 2) a spatiotemporal query analytical framework for parallel aggregation and analysis of climate data with Hadoop Hive (Li et al., 2017). In this project, we further developed query analytical middleware with 1) a hybrid query engine integrating Cloudera Impala (for record-based data) and Hive (for array-based data), and 2) a multi-level caching mechanism to aggregate and cache the original data at different spatiotemporal scales. In addition, we extended the default Hive/Impala SQL with two new keywords AOI = REGION, VISUALIZE AS to better support both server side parallel processing and client side data visualization.  


# Prototye

The web portal prototype can be accessed and tested at: 
http://gis.cassc.edu/climateci

Currently, the protoype is powered by a Hadoop cluster consisting of 13 computer servers with 108 CPU cores, 416 GB RAM memory, and 40 Terabytes storage. 

# Data

Three NASA MERRA data products (~ 2 terabytes) are loaded into the prototye system including MST1NXMLD,MATMNXINT, and MATMCPTDT. 

MST1NXMLD is a global 2-dimentional MERRA-Land product with temporal resolution of hourly (from 1979-01-01 to 2016-02-29) and spatial resolution of 2/3-degree longitude by 1/2-degree latitude. The data is stored as HDF-EOS format (based on HDF4) containing 50 land surface diagnostics. It is organized as daily files with about 140 MB per file. Total data size is around 1.8 terabytes.

MATMNXINT is a monthly 2-Dimensional vertical integral of IAU diagnostics with 2/3-degree longitude by 1/2-degree latitude resolution. The dataset is organized as monthly HDF files from 1979-01-01 to 2016-02-29, containing 111 climate variables. Total data size is around 28 GB. 

MATMCPTDT is a 3-Dimensional temperature tendencies of 8 variables that is time averaged on 42 pressure levels with at a reduced resolution with 1.25-degree longitude by 1.25-degree latitude resolution. The dataset is organized as monthly HDF files from 1979-01-01 to 2016-02-29. Total data size is around 20 GB

# Acknowledges
Prototye development was funded through the ESIP Testbed initiative.


For questions/comments, contact Zhenlong Li at zhenlong@sc.edu .

