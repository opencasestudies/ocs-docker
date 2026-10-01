FROM jhudsl/ottr_viz:dev

RUN grep -Rl "cli.github.com" /etc/apt/sources.list.d/ | xargs rm -f || true

RUN apt-get update && apt-get install -y \
    libfftw3-dev \
    libgdal-dev \
    libgeos-dev \
    libproj-dev \
    patch \
    && rm -rf /var/lib/apt/lists/*

RUN Rscript -e "BiocManager::install(c( \
                                     'BiocParallel', \
                                     'ComplexHeatmap', \
                                     'DelayedArray', \
                                     'DelayedMatrixStats', \
                                     'EBImage', \
                                     'GEOquery', \
                                     'GSVA', \
                                     'rhdf5' \
                                     ))"
                                     
RUN Rscript -e "options(warn = 2); \
                install.packages(c('arrow', \
                                    'hdf5r', \
                                 'R.utils', \
                                 'sf') , \
                    repos = 'https://cloud.r-project.org')"

RUN Rscript -e "options(warn = 2); remotes::install_version( \
                    'Matrix', \
                    version = '1.6-5' \
                    )"

RUN Rscript -e "options(warn = 2); remotes::install_github('fridleylab/spatialGE')"

