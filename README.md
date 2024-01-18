# Quest
a simple tutorial on Quest

## Useful links:

- [Quest Documentation](https://services.northwestern.edu/TDClient/30/Portal/KB/ArticleDet?ID=505)
- [Quest Consult Request](https://app.smartsheet.com/b/form/50e510db18b847099616df2787486555)



## Login:

### Through ssh
```
ssh -X <NetID>@quest.northwestern.edu
```
then type the password. Although it doesn't show on the screen, it is working when you're typing. 

### Through FastX
- If you are off campus, connect to VPN first: https://services.northwestern.edu/TDClient/30/Portal/KB/ArticleDet?ID=1818
- download FastX: https://starnet.com/download/fastx-client
- Create the connection: 
	- **Host**: quest.northwestern.edu
	- **User:** _Enter_ **your own NetID** in lower-case letters.
	- **Port**: 22
	- **Name**: Quest (_Can be whatever you want though it is for your own reference_)

For more details: https://services.northwestern.edu/TDClient/30/Portal/KB/ArticleDet?ID=1511

## Change to project folder:

```
cd /projects/p32069
```
Don't forget the `/` before ”projects“. 

## List items in folder

```
ls
```

## Print work directory

```
pwd
```

## Get cpu (job) assigned:

```
srun --x11 -N 1 -n 4 --account=p32069 --mem=12G --partition=short --time=01:00:00 --pty bash -l
```
A breakdown of the syntax:
- `--x11` and `--pty bash -l`: syntax for interactive job.
- `-N 1`: 1 node
- `-n 4`: 4 cpus
- `--account=p32069`: account the job ran under. Here under the p32069 allocation.
- `--men=12G`: 12 GB memories. You can ask for larger memories if the dataset is big. 
- `--time=01:00:00`: this job will last 1 hour. The session automatically ends after the time is out. 
- `--partition=short`: partition depends on time. 

|   partition|time|
|:-|:-|
|short|00:00:00-04:00:00|
|normal|04:00:00-48:00:00|
|long|48:00:00-168:00:00|


For more information on `srun`: https://slurm.schedmd.com/srun.html

For more information on interactive jobs on Quest: https://services.northwestern.edu/TDClient/30/Portal/KB/ArticleDet?ID=1964#section-section-interactive-jobs-gui

## Load stata:

```
module load stata/17
```

## Run stata:

### In terminal:
```
stata-mp
```
If run `stata` here, you will run Stata/BE instead. This command runs stata in the terminal. This one is faster, but some commands like `br` cannot be used. 

### With GUI: 
```
xstata-mp
```
This command runs Stata/MP with a GUI. 

## Exit stata:

### In terminal:
```
exit
```

### With GUI: 
close the window.

## Check which version of stata is loaded:

```
module avail stata
```

```
stata/14-b1041    stata/14 (D)    stata/15    stata/17 (L)

  

  Where:

   L:  Module is loaded

   D:  Default Module
```

## Transfer files to Quest:
- Download Globus Connect Personal
- d5990400-6d04-11e5-ba46-22000b92c6ec or Northwestern Quest to find the endpoint in Quest. 
- path: /projects/p32069
- Search Northwestern Quest Onedrive Pilot to get access to Quest. You can sync the files in /projects/p32069 daily to Onedrive. 

For more details: https://services.northwestern.edu/TDClient/30/Portal/KB/ArticleDet?ID=2014

