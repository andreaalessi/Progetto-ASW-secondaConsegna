# Progetto-ASW-secondaConsegna

Progetto-ASW-secondaConsegna
Repository progetto Architetture Software.

All'interno della repository sono presenti due file:

progettoGameShop.zip che contiene il codice dell'intero progetto REST. 

consegnaDefinitiva.rar che contiene i dockerFile necessari per la creazione dei contenitori docker.

Preparazione:

1.Posizionarsi nella cartella postgres ed effettuare la build dell'immagine (Es: "docker build -t postgres-img .")

2.Posizionarsi nella cartella tomee ed effettuare la build dell'immagine (Es: "docker build  -t tomcat-img ."), nell'eventualità che il firewall dia problemi durante la build dell'immagine sostituire la porzione di codice (do-done): 

do \
  gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; \
 done
 
 con 
 
 do \
  gpg --keyserver hkp://p80.pool.sks-keyservers.net:80 --recv-keys "$key"; \
 done
 
 all'interno del docker file.
 
 3.Effettuare il run di postgres "docker run -p 5432:5432 -e POSTGRES_PASSWORD=postgres --name=postgress postgres-img"
 
 4.Effettuare il run di tomcat "docker run -p 8080:8080 --link postgress:postgress --name=tomcatt tomcat-img"
 

Avvio:
Da Browser Web inserire l'url: ipMacchinaVirtualeDocker:8080/gameshop

