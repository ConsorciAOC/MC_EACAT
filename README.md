# EACAT - Modalitats de consum

Document d’integració del servei 


<b>Control del document</b>

<b>Informació general</b>

|Títol:         |Document d’integració del servei|
|----           | ----------              |
|Creat per:     |Departament de Projectes CAOC|
|A revisar per: |Departament de Projectes CAOC|
|A aprovar per: |Departament de Projectes CAOC|


<b>Històric de revisions</b>

|Versió|Data       |Autor          |Comentaris           |
|----  |----       |----           |----                 |
|V1.0	 |23/07/2015	|Projectes CAOC	|Creació del document |  
|V1.1	 |27/03/2018	|Projectes CAOC	|Actualització del document|
|V1.2	|20/04/2021	|Projectes CAOC	|Creació de la modalitat de conum funcionaris habilitats|


# Taula de continguts

- [1. Introducció](#1-introducció)
- [2. Transmissions de dades disponibles](#2-Transmissions-de-dades-disponibles)
- [3. Missatgeria del servei](#3-Missatgeria-del-servei)
   * [3.1. Dades d'usuaris (EACAT_USUARI)](#31-Dades-usuaris-EACAT_USUARI)
      - [3.1.1. Petició dades específiques](#311-Petició-dades-específiques)
      - [3.1.2. Resposta dades específiques](#312-Resposta-dades-específiques)   
          - [3.1.2.1. Resultat de l'operació](#3121-Resultat-de-la-operació)         
   * [3.2. Dades d'usuaris (EACAT_SERVEI)](#32-Dades-usuaris-EACAT_SERVEI)
      - [3.2.1. Petició dades específiques](#321-Petició-dades-específiques)
      - [3.2.2. Resposta dades específiques](#322-Resposta-dades-específiques)   
   * [3.3. Dades d'ens adherits  (EACAT_ENS)](#33-Dades-ens-adherits-EACAT_ENS)
      - [3.3.1. Petició dades específiques](#331-Petició-dades-específiques)
      - [3.3.2. Resposta dades específiques](#332-Resposta-dades-específiques)   
   * [3.4. Dades tipus d'ens adherits (EACAT_TIPUS_ENS)](#34-Dades-tipus-ens-adherits-EACAT_TIPUS_ENS)
      - [3.4.1. Petició dades específiques](#341-Petició-dades-específiques)
      - [3.4.2. Resposta dades específiques](#342-Resposta-dades-específiques)   
   * [3.5. Dades Funcionari Habilitat (EACAT_FUNCIONARI_HABILITAT)](#35-Dades-Funcionari-Habilitat-EACAT_FUNCIONARI_HABILITAT)
      - [3.5.1. Petició dades específiques](#351-Petició-dades-específiques)
      - [3.5.2. Resposta dades específiques](#352-Resposta-dades-específiques)


# 1. Introducció

Aquest document detalla la missatgeria associada al servei de consulta de dades d’EACAT.

Per poder realitzar la integració cal conèixer prèviament la següent documentació:

•	Document d’Especificació de missatgeria pel consum de productes de la plataforma PCI del Consorci AOC.


# 2. Transmissions de dades disponibles

Les dades i operacions disponibles a través del servei són les que es presenten a continuació:

|EMISSOR|
|----|
|Consorci Administració Oberta de Catalunya|

|PRODUCTE | MODALITAT                                                                                | DESCRIPCIO|
|----     | ----------                                                                               | ----------|
|EACAT     | [EACAT_USUARI](#31-Dades-usuaris-EACAT_USUARI)                                           | Consulta de dades d’usuaris enregistrats a l'EACAT.|
|EACAT     | [EACAT_SERVEI](#32-Dades-usuaris-EACAT_SERVEI)                                           | Consulta de dades de serveis enregistrats a l'EACAT.|
|EACAT     | [EACAT_ENS](#33-Dades-ens-adherits-EACAT_ENS)                                            | Consulta de dades d’ens adherits a l'EACAT.|
|EACAT     | [EACAT_TIPUS_ENS](#34-Dades-tipus-ens-adherits-EACAT_TIPUS_ENS)                          | Consulta de tipus d'ens a l'EACAT.|
|EACAT     | [EACAT_FUNCIONARI_HABILITAT](#35-Dades-Funcionari-Habilitat-EACAT_FUNCIONARI_HABILITAT)  | Consulta de funcionaris habilitats a l'EACAT.|


# 3. Missatgeria del servei


## 3.1. Dades usuaris EACAT_USUARI

### 3.1.1. Petició dades específiques

| Element | Descripció |
| --- | --- |
| /peticioConsultaUsuari/nif | NIF de l’usuari a consultar.  |
| /peticioConsultaUsuari/codiEns | Codi INE de l’ens al que pertany l’usuari. Si no s’informa, es retornen tots els ens de l’usuari indicat.  |


### 3.1.2. Resposta dades específiques

| Element | Descripció |
| --- | --- |
|/respostaConsultaUsuari/peticioConsultaUsuari|	Bloc de dades corresponent a la petició / criteris de cerca que origina la resposta. Per més detalls vegeu apartat anterior.|
|/respostaConsultaUsuari/resposta|	Bloc de dades corresponent a la resposta a la consulta.|
|/respostaConsultaUsuari/resposta/usuari|	Bloc de dades corresponent a les dades dels usuaris que compleixen els criteris de cerca.|
|//usuari/codiens|	Codi de l’ens.|
|//usuari/nif| NIF.|
|//usuari/tipus| Tipus d'usuari:<ul><li>MLO: usuari del món local</li><li>WIN: administrador del sistema</li><li>EPC: usuari d’EPOCA (la contrasenya de l’usuari es valida contra EPOCA)</li><li>CAC: usuari del servei del Consell Audiovisual de Catalunya</li><li>SNC: usuari de la Sindicatura de Comptes.</li></ul>|
|//usuari/nom|	Nom.|
|//usuari/dataAlta|	Data d’alta de l’usuari a l’EACAT.|
|//usuari/email|	Correu electrònic.|
|//usuari/tractament|	Tractament.|
|//usuari/perfil|	Perfil.|
|//usuari/dataModificacio|	Data de modificació.|
|//usuari/telèfon|	Telèfon.|
|//usuari/ens|	Bloc de dades corresponents a les dades de l’ens.|
|//usuari/ens/codiens|	Codi de l’ENS.|
|//usuari/ens/nom|	Nom de l’ens.|
|//usuari/ens/idTipusEns|	Codi del tipus ens.|
|//usuari/ens/nomTipusEns|	Nom del tipus ens.|
|//usuari/ens/cif|	CIF de l’ens.|
|//usuari/ens/adreca|	Adreça de l’ens.|
|//usuari/ens/codiPostal|	Codi postal de l’ens.|
|//usuari/ens/codiMunicipi|	Codi municipi de l’ens.|
|//usuari/ens/nomMunicipi|	Nom municipi de l’ens.|
|//usuari/ens/codiComarca|	Codi comarca de l’ens.|
|//usuari/ens/nomComarca|	Nom comarca de l’ens.|
|//usuari/ens/codiProvincia|	Codi província de l’ens.|
|//usuari/ens/nomProvincia|	Nom província de l’ens.|
|//usuari/ens/codiDelegacio|	Codi delegació de l’ens:<ul><li>1: Barcelona</li><li>2: Girona</li><li>3: Lleida</li><li>4: Tarragona</li><li>5: Terres de l’Ebre</li></ul>|
|//usuari/ens/nomDelegacio|	Nom delegació de l’ens.|
|/respostaConsultaUsuari/resultat/codiResultat|	Codi de resultat de l’operació de consulta (vegeu apartat 3.1.2.1).|
|/respostaConsultaUsuari/resultat/descripcio|	Descripció del resultat.|


#### 3.1.2.1 Resultat de la operació



## 3.2. Dades usuaris EACAT_SERVEI

### 3.2.1. Petició dades específiques



### 3.2.2. Resposta dades específiques



## 3.3. Dades ens adherits EACAT_ENS

### 3.3.1. Petició dades específiques

### 3.3.2. Resposta dades específiques



## 3.4. Dades tipus ens adherits EACAT_TIPUS_ENS

### 3.4.1. Petició dades específiques

### 3.4.2. Resposta dades específiques



## 3.5. Dades Funcionari Habilitat EACAT_FUNCIONARI_HABILITAT

### 3.5.1. Petició dades específiques

### 3.5.2. Resposta dades específiques
