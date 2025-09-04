	Printing:
mobileprint@unibas.ch

Connect to Drives
  - Biozentrum: smb://unibasel.ads.unibas.ch/bz/
  - Scicore Biozentrum: smb://toucan-all.scicore.unibas.ch/donafl00-calcium$/ 
  - Biopz Jumbo: smb://biopz-jumbo.storage.p.unibas.ch/RG-FD02$/_Members/mauser00/Desktop
  - Puma: \\puma.scicore.p.unibas.ch\biopz-a-scicore-rg-fd02-data01$


Animal Handling:
- LTK for animal work
	- here you find information on what you need to do: [https://www.ltk.uzh.ch/en/Teaching-and-Training/Training/Registration-System.html](https://www.ltk.uzh.ch/en/Teaching-and-Training/Training/Registration-System.html)
	- here is the link to the course: [https://vsfltkreg.uzh.ch/course/m-1/en](https://vsfltkreg.uzh.ch/course/m-1/en) where you can click on "register": german courses [https://vsfltkreg.uzh.ch/course/m-1/de](https://vsfltkreg.uzh.ch/course/m-1/de)


Communication:
- [how_to_make_a_great_presentation](https://www.ted.com/playlists/574/how_to_make_a_great_presentation)
- [Best suggestion writing grants](https://corticalia.wordpress.com/2015/09/01/how-to-write-a-winning-grant-proposal/)
- [Book: Art of Explanation](https://www.goodreads.com/book/show/64631477-the-art-of-explanation)
- [Simplify Complex Ideas](https://www.forbes.com/sites/carminegallo/2023/10/06/4-proven-rules-to-simplify-complex-ideas/)


# Scicore
Presentation Slides from HPC Seminar:
D:\SwitchDrive\Uni\Work\Dokuments\HPC Best Practices
## Links
- [sciCORE | Home](https://scicore.unibas.ch/)
- [sciCORE user guide - Scientific Computing Core Facility Uni Basel - Biozentrum Wiki](https://wiki.biozentrum.unibas.ch/display/scicore/sciCORE+user+guide)
- [Jupyter Notebook - Open OnDemand](https://ood.scicore.unibas.ch/pun/sys/dashboard/batch_connect/sys/jupyterlab/scicore/session_contexts/new)
- [Useful Slurm commands — Research Computing University of Colorado Boulder documentation](https://curc.readthedocs.io/en/latest/running-jobs/slurm-commands.html#controlling-queued-and-running-jobs-using-scontrol)
- [Deep storage - Scientific Computing Core Facility Uni Basel - Biozentrum Wiki](https://wiki.biozentrum.unibas.ch/display/scicore/Deep%2Bstorage)
- [Storage quotas at sciCORE - Scientific Computing Core Facility Uni Basel - Biozentrum Wiki](https://wiki.biozentrum.unibas.ch/pages/viewpage.action?spaceKey=scicore&title=Storage+quotas+at+sciCORE#StoragequotasatsciCORE-Checking(remotely)anetworkshare(NFS,SMB))
- [Log in - Service Desk](https://support.scicore.unibas.ch/servicedesk/customer/portal/1/user/login?destination=portal%2F1)
- [Loading and using an LLM on sciCORE - Scientific Computing Core Facility Uni Basel - Biozentrum Wiki](https://wiki.biozentrum.unibas.ch/pages/viewpage.action?spaceKey=scicore&title=Loading+and+using+an+LLM+on+sciCORE)
- [multi gpu, cpu NN Parallel in PyTorch - Video Tutorials — PyTorch Tutorials 2.2.1+cu121 documentation](https://pytorch.org/tutorials/beginner/ddp_series_intro.html)
- [pytorch ResNet Example](https://git.scicore.unibas.ch/fucileg/pytorch_resnet_example)
## Parallelization (Use Numba)
### Python
#### Single Job
##### Cython (700ms)
##### Numpy (350ms)
##### Numba (1. 700ms, 2. 30ms)
Compiles function on the fly. The function takes 1 time to compile.
```python
from numba import jit
@jit
def function():
	do stuff
```
##### Multiprocessing 
Does not have a shared memory, so it creates copies of the data 
1. create a pool of resources (has overhead)
2. map function to data collection
3. pool.close()
4. pool.join()
#### Multi-Job

##### Numba 
```python
import os
os.environ["NUMBA_DEBUG_ARRAY_OPT_STATS"]=""1"
```

```python
from numba import njit

@njit(parallel=True)
def function():
	do stuff 

function()
```

##### Multiprocessing
## Slurm
### Parallelization

#### C++/Fortran
OpenMP uses CPUs per tasks
MPI uses Tasks and those can spread over different threads
![[Pasted image 20240409094936.png]]
### Debugging (in interactive terminal)
There are different methods for debugging:
1. [Open On Demand (OOD)](https://ood.scicore.unibas.ch)
2. **Terminal in Computing node**: 
	1. ```srun --nodes=1 --cpus-per-task=8 --mem=16G --pty bash```
	2. ```salloc --nodes=1 --cpus-per-task=8 --mem=16G --pty bash
	   ssh <allocated node>```
### Use Multiple small jobs (Array Jobs)
The smaller the Task the better for Slurm. Everything will finish faster.
![[Pasted image 20240409092047.png]]
Use dependencies for Tasks, so tasks will only run after 1 task is finished. This can be used also for array jobs.
![[Pasted image 20240409092331.png]]
## File System
1. Compress Datasets with hdf5
### LabKey (Analysis Environment)
- Analysis