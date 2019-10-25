# psr_search
Pulsar searching pipeline for Effelsberg radio telescope based on pulsar software called PRESTO.

You must have PRESTO installed.
from here https://www.cv.nrao.edu/~sransom/presto/




Example of running the pipeline in a slurm supercomputer cluster 

sbatch --partition=p.64g --nodes=1 -t 10:0:0 --export=ALL,DATAFILES='/u/joey/HTRU-N/data_to_process/G026.6+14.6/PFFTS_6370_03_0001.fits',OUTDIR='/hercules/results/joey/HTRUN/results/55549/G026.6+14.6/171019T133905'  --job-name=HTRUN_batchjob --error=/hercules/results/joey/HTRUN/logs/qsublog/HTRUN_batchjob.e%j --output=/hercules/results/joey/HTRUN/logs/qsublog/HTRUN_batchjob.o%j /u/joey/src/pipelineHTRUN/bin/search.sh

search.sh runs batch python script search.py, which sets up and gets filename, working directory, results direcoty, output directory. Copies filenames to working directory, imports HTRUN_presto_search (which is the main pipeline to search for pulsars in the filename given), then copies the results to output directory. Finally cleans up the work direcoty and results direcoty. 


