# testfiles
random collection of test files for easy access

Sources:

ca-500.zip: from https://www.briandunning.com/sample-data/ca-500.zip


To build a talend job into a docker image manually:

1- build Talend job as zip file from Talend Open Studios console (right click on job > Build Job)  
2- Build images: ## build and fill arguments:  
docker build . -f Dockerfile_job.txt -t <repo>:<tag> --build-arg talend_job=<jobname> --build-arg talend_version=<jobversion>   
3- Check Docker images built: docker images  
4- Run job to test:  docker run --rm -ti -v <hostvolume>:<dockervolume> -e ARGS="--context_param directory=/data/"  <repo>:<tag>  
5- log into the docker account: docker login -u <username>  
6- push image to repo: docker image push <repo>:<tag>  
