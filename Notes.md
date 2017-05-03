3/20/17
scp prvasque@farm.cse.ucdavis.edu:/(paste what I get from pwd)/*.html .
pwd = print working directory

didnt end up working

4/16/17
make sure to type
`export PROJECT=~/work`
then
`source activate eel-pond`
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
