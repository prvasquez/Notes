3/20/17
scp prvasque@farm.cse.ucdavis.edu:/(paste what I get from pwd)/*.html .
pwd = print working directory

didnt end up working

4/16/17
make sure to type
`export PROJECT=~/work`
then
`source ~/.bashrc`
Finished Step 1
Finished Step 2
Started step 3
Put in 
```
Trinity --left left.fq \
 --right right.fq --seqType fq --max_memory 14G \
 --CPU 2
 ```
Got a message saying trinity wasn't installed
Installed trinity???? by doing
```
cd ${HOME}

wget https://github.com/trinityrnaseq/trinityrnaseq/archive/Trinity-v2.3.2.tar.gz \
 -O trinity.tar.gz
tar xzf trinity.tar.gz
cd trinityrnaseq*/
make |& tee trinity-build.log
```
Then did
```
echo export PATH=$PATH:$(pwd) >> ~/miniconda3/envs/eel-pond/bin/activate
```
Still didn't work
Ended at the "Assembling with Trinity" step in step 3

5/3/2017
DONT FORGET
**srun -p high -t 24:00:00 --mem=40000 --pty bash**

```
source ~/.bashrc
cd ${PROJECT}
module load trinity
```
Got an error
`trinity/2.2.0(5):ERROR:151: Module 'trinity/2.2.0' depends on one of the module(s) 'rsem/1.3.0 rsem/1.2.23 rsem/1.2.11'
trinity/2.2.0(5):ERROR:102: Tcl command execution failed: prereq rsem`
Then did
```
module load rsem/1.3.0
module load trinity
Trinity --left left.fq \
>  --right right.fq --seqType fq --max_memory 14G \
>  --CPU 2
```
Got an error
```
Error, Trinity requires access to Java version 1.7 or higher.  Currently installed version is: java version "1.6.0_41"
OpenJDK Runtime Environment (IcedTea6 1.13.13) (6b41-1.13.13-0ubuntu0.14.04.1)
OpenJDK 64-Bit Server VM (build 23.41-b41, mixed mode)
```
Java wasnt loaded
`module load java/1.8`

Tried trinity command again and got the error code
`No command 'Trinity' found, did you mean:
 Command 'trinity' from package 'trinity' (universe)
Trinity: command not found`

Couldn't figure it out.
