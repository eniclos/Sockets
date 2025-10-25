#### 3.3.3.3  Resolució de noms DNS 

Fins ara l’accés als equips s’està fent mitjançant l’adreçament IP, que correspon l’identificació a nivell de xarxa però en una aplicació és molt habitual referir-se als equips no per IP sino per un nom de host, identificació freqüent en capa d’aplicació.

No obstant això, conforme una aplicació va baixant a capes inferiors per a fer la transmissió de dades, no entén la identificació de nom de host i requereix una traducció a una IP. Per exemple, quan s’accedeix mitjançant navegador a [https://aules.edu.gva.es](http://https://aules.edu.gva.es), eixa URL és un nom que identifica un host per establir una comunicació a nivell de transport deu identificar-se amb un adreçament IP. 

D’això se n’encarrega un servei d’internet anomenat servidor de noms de domini, habitualment conegut com a **DNS** *(Domain Name System)*. Els servidors DNS són serveis gratuïts d’internet, que poden ser interrogats per un nom de domini o subdomini per tal d’aconseguir les adreces IP associades al nom. La xarxa de servidors DNS constitueix una immensa base de dades distribuïda de forma jeràrquica. La responsabilitat de mantenir les dades actualitzada correspon al propietari dels dominis de manera que el manteniment és mínim.

Les aplicacions que admeten noms de dispositius, hauran de consultar el servei DNS per trobar la IP a la qual hauran de direccionar la informació.

La classe InetAddress  disposa de mètodes estàtics que realitzen la resolució DNS, és a dir, donat un nom de host DNS, permet obtindre l’adreça IP associada. També cal dir que disposa de mètodes que realitzen la resolució inversa.

Els mètodes son:

| Mètodes de InetAddress | Descripció |
| ----- | ----- |
| static InetAddress     getByName(String host) | Obté una adreça IP a partir de:<br> - Un nom de host usant els serveis de resolució de noms. P.e. “*www.wikipedia.org*”.<br> - Una representació textual d’una adreça IP. P.e. “*192.168.1.1*”     	 |
| static InetAddress\[\]     getAllByName(String host) | Semblant a l’anterior però més complet, permet retornar un vector amb totes les adreces IP que es poden obtindre usant els serveis de resolució de noms. |
| String     getHostName() | Realitza la resolució inversa de nom, es a dir, obtindre el nom de host a patir de l’adreça IP. |
| String     getCanonicalHostName() | Retorna el nom canònic o FQDN usant el protocol DNS per a averiguar-ho. |
| static InetAddress     getLocalHost() | Retorna l’adreça IP del propi host.. |