# SLURM Notes

This is a job scheduler for HPC.

### Inline Method

You can do this in a few ways, but the easiest are `sbatch` and `srun`. The three things to specify are
- `-c <num CPUs>`; plain integer
- `--mem-per-cpu <mem>`; e.g. 10G for 10 Gb per cpu, 50M for 50 Mb per cpu.
- `-t <time>`; e.g. 5:0:0 for 5 hours, 3-0:0:0 for 3 days

So an example command would be:
```sh
sbatch -c 2 --mem-per-cput 2G -t 5:0:0 -J name --wrap "python name.py"
```

### Script Method

You can declare a `job.sh` as something like:
```bash
#!/bin/bash
#SBATCH --job-name=my_analysis      # name shown in the queue
#SBATCH --output=logs/%x_%j.out     # stdout (%x = job name, %j = job ID)
#SBATCH --error=logs/%x_%j.err      # stderr
#SBATCH --partition=general         # partition/queue (cluster-specific)
#SBATCH --nodes=1
#SBATCH --ntasks=1
#SBATCH --cpus-per-task=4
#SBATCH --mem=16G
#SBATCH --time=02:00:00             # HH:MM:SS wall-clock limit
#SBATCH --mail-type=END,FAIL
#SBATCH --mail-user=you@example.com

module load python/3.11             # load software your cluster provides
source ~/venvs/myenv/bin/activate

python my_script.py --threads $SLURM_CPUS_PER_TASK
```

Then submit and manage it:

```bash
mkdir -p logs sbatch job.sh # submit; prints "Submitted batch job 123456" 
squeue -u $USER # check your jobs in the queue 
scancel 123456 # cancel a job sacct -j 123456 # accounting info after it finishes
```

## References
- https://www.youtube.com/watch?v=Juo_mb3otJ0