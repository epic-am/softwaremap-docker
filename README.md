# softwaremap-docker

for i in softwaremap-*; do echo "== building $i"; cd $i; docker build -t $i .; cd ..; done


Commands to launch front service :

1. Goto the front folder : 
cd softwaremap-front

2. Build the container :
docker build -t softwaremap/front .

3. Lauch it :
docker run -td --name="softwaremap-front" -p 8080:8080 -v /project/PERSO/softwareMap/GITHUB/:/project/ softwaremap/front

4. Enjoy !
http://localhost:8080


Commands to launch the core service : 

1. Goto the core folder :
cd softwaremap-core

2. Build the container :
docker build -t softwaremap/core .

3. Lauch it :
docker run -td --name="softwaremap-core" -p 4000:4000 -v /project/PERSO/softwareMap/GITHUB/:/project/ softwaremap/core