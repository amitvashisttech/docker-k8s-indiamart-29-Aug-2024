```   
   19  git clone https://github.com/amitvashisttech/docker-k8s-indiamart-29-Aug-2024.git
   20  ls
   21  cd docker-k8s-indiamart-29-Aug-2024/
   22  ls
   23  mkdir 01-Docker/00-Setup -p 
   24  cd 01-Docker/00-Setup/
   25  ls
   26  docker ps 
   27  ls
   28  cp -rf ../../../k8s-paypal-20-Aug-2024/00-Setup/install-docker.sh . 
   29  ls
   30  vim install-docker.sh 
   31  ls
   32  sh install-docker.sh 
   33  ls
   34  cd ..
   35  ls
   36  git add . ; git commit -m "Docker - Setup" ; git push 
   37  git config --global credential.helper 'cache --timeout=360000'
   38  docker version 
   39  systemctl status docker 
   40  ls
   41  docker images 
   42* 
   43  docker images 
   44  docker run -it busybox 
   45  docker images 
   46* docker r
   47  docker ps 
   48  docker ps -a
   49  docker pull ubuntu 
   50  docker pull ubuntu:20.04
   51  docker images 
   52  docker run -it ubuntu:20.04 
   53  docker ps 
   54  docker run -it ubuntu
   55  docker ps 
   56  docker ps -a 
   57  docker start efa385371fed
   58  docker ps 
   59  docker attach efa385371fed
   60  docker ps 
   61  docker exec -it efa385371fed ls /
   62  docker exec -it efa385371fed ls /root
   63  docker exec -it efa385371fed cat /root/hello_docker.txt
   64  docker exec -it efa385371fed bash 
   65  ls
   66  cd ..
   67  ls
   68  cd 01-Docker/
   69  ls
   70  mkdir 01-DockerCommands
   71  s
   72  cd 01-DockerCommands/
   73  ls
   74  history 
   75  ls
   76  vim History.txt 
   77  ls
   78  cd ..
   79  ls
   80  cd ..
   81  ls
   82  git add . ; git commit -m "Docker - Setup" ; git push 
   83  ls
   84  git pull 
   85  cat 01-Docker/01-DockerCommands/History.txt 
   86  ls
   87  cd 01-Docker/01-DockerCommands/
   88  s
   89  ls
   90  mv History.txt README.md 
   91  vim README.md 
   92  git add . ; git commit -m "Docker - Setup" ; git push 
   93  ls
   94  history >> README.md 
```
