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
- [4. Exemples](#4-Exemples-de-consulta)
   * [4.1. EACAT_ENS - Petició](#41-EACAT_ENS-Petició)
   * [4.2. EACAT_ENS - Resposta](#42-EACAT_ENS-Resposta)    
   * [4.3. EACAT_USUARI - Petició](#43-EACAT_USUARI-Petició)
   * [4.4. EACAT_USUARI - Resposta](#44-EACAT_USUARI-Resposta)    
   * [4.5. EACAT_SERVEI - Petició](#45-EACAT_SERVEI-Petició)
   * [4.6. EACAT_SERVEI - Resposta](#46-EACAT_SERVEI-Resposta)    
   * [4.7. EACAT_TIPUS_ENS - Petició](#47-EACAT_TIPUS_ENS-Petició)
   * [4.8. EACAT_TIPUS_ENS - Resposta](#48-EACAT_TIPUS_ENS-Resposta)    
   * [4.9. EACAT_FUNCIONARI_HABILITAT - Petició](#49-EACAT_FUNCIONARI_HABILITAT-Petició)
   * [4.10. EACAT_FUNCIONARI_HABILITAT - Resposta](#410-EACAT_FUNCIONARI_HABILITAT-Resposta)    


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

A continuació es detalla la missatgeria corresponent al bloc de dades específiques de les modalitats de consum del producte.


## 3.1. Dades usuaris EACAT_USUARI

### 3.1.1. Petició dades específiques

Aquesta modalitat permet consultar les dades dels usuaris enregistrats a l’EACAT.

<p align="center">
<img align="center" src="img/peticioconsultausuari.jpg" />
</p>


| Element | Descripció |
| --- | --- |
| /peticioConsultaUsuari/nif | NIF de l’usuari a consultar.  |
| /peticioConsultaUsuari/codiEns | Codi INE de l’ens al que pertany l’usuari. Si no s’informa, es retornen tots els ens de l’usuari indicat.  |


### 3.1.2. Resposta dades específiques

De l’schema associat a la resposta especifica, el servei informa les dades que es detallen a continuació.

<p align="center">
<img align="center" src="img/respostaconsultausuari.jpg" />
</p>


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
|/respostaConsultaUsuari/resultat/codiResultat|	Codi de resultat de l'operació de consulta [Resultat operació](#3121-Resultat-de-la-operació) .|
|/respostaConsultaUsuari/resultat/descripcio|	Descripció del resultat.|


#### 3.1.2.1 Resultat de la operació

•	0: Operació realitzada correctament.

•	1: Error realitzant la consulta.


## 3.2. Dades usuaris EACAT_SERVEI

### 3.2.1. Petició dades específiques

Aquesta modalitat permet consultar les dades dels serveis enregistrats a l’EACAT.

<p align="center">
<img align="center" src="img/peticioconsultaserveis.jpg" />
</p>  


| Element | Descripció |
| --- | --- |
|/peticioConsultaServei/servei|	Codi del servei a consultar. | 
|/peticioConsultaServei/nif|	NIF de l’usuari a filtrar.  Si no s’informa, es retornen totes les dades del servei indicat.|
|/peticioConsultaServei/codiEns|	Codi INE de l’ens a filtrar. Si no s’informa, es retornen totes les dades del servei indicat.|



### 3.2.2. Resposta dades específiques

De l’schema associat a la resposta especifica, el servei informa les dades que es detallen a continuació.

<p align="center">
<img align="center" src="img/respostaconsultaserveis.jpg" />
</p>  


| Element | Descripció |
| --- | --- |
|/respostaConsultaServei/peticioConsultaServei|	Bloc de dades corresponent a la petició / criteris de cerca que origina la resposta. Per més detalls vegeu apartat anterior.|
|/respostaConsultaServei/resposta|	Bloc de dades corresponent a la resposta a la consulta.|
|/respostaConsultaServei/resposta/servei|	Bloc de dades corresponent a les dades dels serveis que compleixen els criteris de cerca.|
|//servei/nif|	NIF de l’usuari.|
|//servei/nom|	Nom de l’usuari.|
|//servei/perfil|	Perfil de l’usuari.|
|//servei/codiEns|	Codi de l’ens|
|//servei/nomEns|	Nom de l’ens.|
|//servei/idTipusEns|	Codi del tipus ens.|
|//servei/nomTipusEns|	Nom del tipus ens.|
|//servei/servei|	Servei.|
|//servei/rol|	Rol.|
|//servei/descripcio|	Descripció.|
|/respostaConsultaServei/resultat/codiResultat|	Codi de resultat de l’operació de consulta [Resultat operació](#3121-Resultat-de-la-operació).|
|/respostaConsultaServei/resultat/descripcio|	Descripció del resultat.|


## 3.3. Dades ens adherits EACAT_ENS

### 3.3.1. Petició dades específiques

Aquesta modalitat permet consultar les dades dels ens adherits a l’EACAT.

Com a mínim s’ha d’escollir un paràmetre d’entrada.

<p align="center">
<img align="center" src="img/peticioconsultaens.jpg" />
</p>


| Element | Descripció |
| --- | --- |
|/peticioConsultaEns/codiEns|	Codi INE de l’ens a consultar. |
|/peticioConsultaEns/idTipusEns|	Codi tipus de l’ens a consultar. |
|/peticioConsultaEns/nom|	Nom de l’ens a consultar. |
|/peticioConsultaEns/nomMunicipi|	Nom del municipi de l’ens a consultar. |
|/peticioConsultaEns/nomProvincia|	Nom de la provincia de l’ens a consultar. |



### 3.3.2. Resposta dades específiques

De l’schema associat a la resposta especifica, el servei informa les dades que es detallen a continuació.

La resposta màxim serà de 500 blocs (```/respostaConsultaEns/resposta/ens```). Si voleu per exemple obtindré tots els Ajuntaments, podeu realitzar 4 crides (una per cada provincia).

```/peticioConsultaEns/idTipusEns``` --> 2

```/peticioConsultaEns/nomProvincia``` --> Barcelona | Lleida | Tarragona | Girona


<p align="center">
<img align="center" src="img/respostaconsultaens.jpg" />
</p>


| Element | Descripció |
| --- | --- |
|/respostaConsultaEns/peticioConsultaEns|	Bloc de dades corresponent a la petició / criteris de cerca que origina la resposta. Per més detalls vegeu apartat anterior.|
|/respostaConsultaEns/resposta|	Bloc de dades corresponent a la resposta a la consulta.|
|/respostaConsultaEns/resposta/ens|	Bloc de dades corresponent a les dades dels ens que compleixen els criteris de cerca.|
|//ens/codiens|	Codi de L’ENS.|
|//ens/nom|	Nom.|
|//ens/idTipusEns|	Codi del tipus ens.|
|//ens/nomTipusEns|	Nom del tipus ens.|
|//ens/cif|	CIF.|
|//ens/adreca|	Adreça.|
|//ens/codiPostal|	Codi postal.|
|//ens/codiMunicipi|	Codi municipi.|
|//ens/nomMunicipi|	Nom municipi.|
|//ens/codiComarca|	Codi comarca.|
|//ens/nomComarca|	Nom comarca.|
|//ens/codiProvincia|	Codi província.|
|//ens/nomProvincia|	Nom província.|
|//ens/codiDelegacio|	Codi delegació:<ul><li>1: Barcelona</li><li>2: Girona</li><li>3: Lleida</li><li>4: Tarragona</li><li>5: Terres de l’Ebre</li><li>6: Catalunya Central</li><li>7: Alt Pirineu i Aran</li></ul>|
|//ens/nomDelegacio|	Nom delegació.|
|/respostaConsultaEns/resultat/codiResultat|	Codi de resultat de l’operació de consulta [Resultat operació](#3121-Resultat-de-la-operació).|
|/respostaConsultaEns/resultat/descripcio|	Descripció del resultat.|


## 3.4. Dades tipus ens adherits EACAT_TIPUS_ENS

### 3.4.1. Petició dades específiques

Aquesta modalitat, retorna un llistat amb tots els tipus d’ENS a l’EACAT. Per aquesta modalitat no hi ha paràmetres de cerques.

<p align="center">
<img align="center" src="img/peticioconsultatipusens.jpg" />
</p>

### 3.4.2. Resposta dades específiques

De l’schema associat a la resposta especifica, el servei informa les dades que es detallen a continuació.

<p align="center">
<img align="center" src="img/respostaconsultatipusens.jpg" />
</p>



| Element | Descripció |
| --- | --- |
|/respostaConsultaTipusEns/peticioConsultaTipusEns|	Bloc de dades corresponent a la petició / criteris de cerca que origina la resposta. Per més detalls vegeu apartat anterior.|
|/respostaConsultaTipusEns/resposta|	Bloc de dades corresponent a la resposta a la consulta.|
|/respostaConsultaTipusEns/resposta/tipusEns|	Bloc de dades corresponent a les dades dels tipus d’ens.|
|//ens/idTipusEns|	Codi del tipus ens.|
|//ens/nomTipusEns|	Nom del tipus ens.|
|/respostaConsultaTipusEns/resultat/codiResultat|	Codi de resultat de l’operació de consulta [Resultat operació](#3121-Resultat-de-la-operació).|
|/respostaConsultaTipusEns/resultat/descripcio|	Descripció del resultat.|


## 3.5. Dades Funcionari Habilitat EACAT_FUNCIONARI_HABILITAT

### 3.5.1. Petició dades específiques

Aquesta modalitat permet consultar els usuaris que s’han donat d’alta o baixa sobre el rols Funcionari Habilitat.

Es pot realitzar la petició sense paràmetres (per agafar tots els usuaris donats d’alta existents) i també indicant els següents paràmetres per una resposta més acurada:


<p align="center">
<img align="center" src="img/peticioconsultafuncionarishabilitats.jpg" />
</p>


| Element | Descripció |
| --- | --- |
|/peticioConsultaFuncionariHabilitat/codiEns|	Codi de l’ens|
|/peticioConsultaFuncionariHabilitat/nif|	Nif d’un usuari|
|/peticioConsultaFuncionariHabilitat/dataAltaInici|	Data inicial per agafar tots els usuaris desde aquesta data fins la data d’avui, es pot combinar amb dataAltaFi per indicar un rang de data mes curt. Exemple: 2020-09-29+01:00|
|/peticioConsultaFuncionariHabilitat/dataAltaFi|	Data fi per agafar tots els usuaris que s’hagin donat d’alta una data igual o inferior a la data informada, es pot combinar amb dataAltaFi per indicar un rang de data mes curt. Exemple: 2020-11-30+01:00|
|/peticioConsultaFuncionariHabilitat/assistirInteressats|	Boolean: Actiu/No actiu rol Assistència als interessats|
|/peticioConsultaFuncionariHabilitat/expCopiesAutentiques|	Boolean: Actiu/No actiu rol Expedició còpies autèntiques|
|/peticioConsultaFuncionariHabilitat/donatsBaixa|	Boolean: Sí s’envia un true també es mostraran els usuaris que s’han donat de baixa.|


### 3.5.2. Resposta dades específiques

De l’schema associat a la resposta especifica, el servei informa les dades que es detallen a continuació.

<p align="center">
<img align="center" src="img/respostaconsultafuncionarishabilitats.jpg" />
</p>


| Element | Descripció |
| --- | --- |
|/respostaConsultaFuncionariHabilitat/peticioConsultaFuncionariHabilitat|	Bloc de dades corresponent a la petició / criteris de cerca que origina la resposta. Per més detalls vegeu apartat anterior.|
|/respostaConsultaFuncionariHabilitat/funcionariHabilitat|	Bloc de dades corresponent a les dades dels Funcionaris Habilitats que compleixen els criteris de cerca.|
|//funcionariHabilitat/nom|	Nom de l’usuari.|
|//funcionariHabilitat/nif|	NIF de l’usuari|
|//funcionariHabilitat/tipus|	Tipus d’usuari:<ul><li>MLO: usuari del món local</li><li>WIN: administrador del sistema</li><li>EPC: usuari d’EPOCA (la contrasenya de l’usuari es valida contra EPOCA)</li><li>CAC: usuari del servei del Consell Audiovisual de Catalunya</li><li>SNC: usuari de la Sindicatura de Comptes.</ul>|
|//funcionariHabilitat/nomEns|	Nom de l’ens.|
|//funcionariHabilitat/codiEns|	Codi de l’ENS.|
|//funcionariHabilitat/dataAlta|	Quan es va donar d’alta el usuari a aquest rol.|
|//funcionariHabilitat/dataBaixa|	S’informa si s’ha donat de baixa aquest usuari al rol Funcionari Habilitat.|
|//funcionariHabilitat/assistirInteressats|	Rol Assistència als interessats|
|//funcionariHabilitat/expCopiesAutentiques|	Rol Expedició còpies autèntiques|
|//funcionariHabilitat/unitatAdministrativa|	Unitat administrativa.|
|/respostaConsultaFuncionariHabilitat/resultat/codiResultat|	Codi de resultat de l’operació de consulta [Resultat operació](#3121-Resultat-de-la-operació).|
|/respostaConsultaFuncionariHabilitat/resultat/descripcio|	Descripció del resultat.|


# 4. Exemples de consulta

## 4.1. EACAT_ENS Petició

Exemple de petició consultant per ```<codiEns>```.

```xml
<Peticion xmlns="http://gencat.net/scsp/esquemes/peticion">
  <Atributos>
     <IdPeticion>CU1-EACAT_ENS-${=(long)(System.currentTimeMillis())}</IdPeticion>
     <NumElementos>1</NumElementos>
     <TimeStamp/>
     <CodigoCertificado>EACAT_ENS</CodigoCertificado>
     <CodigoProducto>EACAT</CodigoProducto>
     <DatosAutorizacion>
        <IdentificadorSolicitante>9821920002</IdentificadorSolicitante>
        <NombreSolicitante>CAOC</NombreSolicitante>
        <Finalidad>PROVES</Finalidad>
     </DatosAutorizacion>
  </Atributos>
  <Solicitudes>
     <SolicitudTransmision>
        <DatosGenericos>
           <Solicitante>
              <IdentificadorSolicitante>9821920002</IdentificadorSolicitante>
              <NombreSolicitante>CAOC</NombreSolicitante>
              <Finalidad>PROVES</Finalidad>
              <Consentimiento>Si</Consentimiento>
           </Solicitante>
           <Transmision>
              <CodigoCertificado>EACAT_ENS</CodigoCertificado>
              <IdSolicitud>1</IdSolicitud>
              <IdTransmision>EXPEDIENT</IdTransmision>
              <FechaGeneracion/>
           </Transmision>
        </DatosGenericos>
        <DatosEspecificos>
           <peticioConsultaEns xmlns="http://www.aocat.net/eacat">
              <codiEns>9821920002</codiEns>
           </peticioConsultaEns>
        </DatosEspecificos>
     </SolicitudTransmision>
  </Solicitudes>
</Peticion>
```


## 4.2. EACAT_ENS Resposta

Exemple de resposta consultant per ```<codiEns>```.

```xml
<respostaConsultaEns xmlns="http://www.aocat.net/eacat" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
  <peticioConsultaEns>
     <codiEns>100235</codiEns>
  </peticioConsultaEns>
  <resposta>
     <ens>
        <codiEns>9821920002</codiEns>
        <nom>Consorci Administració Oberta de Catalunya</nom>
        <idTipusEns>12</idTipusEns>
        <nomTipusEns>Consorci</nomTipusEns>
        <cif>Q0801175A</cif>
        <adreca>C/ Tànger, 98, pl. baixa. 22@ Edif. Interface</adreca>
        <codiPostal>8018</codiPostal>
        <codiMunicipi>801930008</codiMunicipi>
        <nomMunicipi>Barcelona</nomMunicipi>
        <codiComarca>8101360009</codiComarca>
        <nomComarca>Barcelonès</nomComarca>
        <codiProvincia>8000840003</codiProvincia>
        <nomProvincia>Barcelona</nomProvincia>
        <codiDelegacio>2</codiDelegacio>
        <nomDelegacio>Girona</nomDelegacio>
     </ens>
  </resposta>
  <resultat>
     <codiResultat>0</codiResultat>
     <descripcio/>
  </resultat>
</respostaConsultaEns>
```


## 4.3. EACAT_USUARI Petició

Exemple de petició consultant per ```<nif>```.

```xml
 <Peticion xmlns="http://gencat.net/scsp/esquemes/peticion">
    <Atributos>
       <IdPeticion>CU2-EACAT_USUARI-${=(long)(System.currentTimeMillis())}</IdPeticion>
       <NumElementos>1</NumElementos>
       <TimeStamp/>
       <CodigoCertificado>EACAT_USUARI</CodigoCertificado>
       <CodigoProducto>EACAT</CodigoProducto>
       <DatosAutorizacion>
          <IdentificadorSolicitante>9821920002</IdentificadorSolicitante>
          <NombreSolicitante>CAOC</NombreSolicitante>
          <Finalidad>PROVES</Finalidad>
       </DatosAutorizacion>
    </Atributos>
    <Solicitudes>
       <SolicitudTransmision>
          <DatosGenericos>
             <Solicitante>
                <IdentificadorSolicitante>9821920002</IdentificadorSolicitante>
                <NombreSolicitante>CAOC</NombreSolicitante>
                <Finalidad>PROVES</Finalidad>
                <Consentimiento>Si</Consentimiento>
                <Funcionario>
                   <NombreCompletoFuncionario>${Properties#NombreCompletoFuncionario}</NombreCompletoFuncionario>
                   <NifFuncionario>${Properties#NIFFuncionario}</NifFuncionario>
                   <EMailFuncionario/>
                </Funcionario>
             </Solicitante>
             <Transmision>
                <CodigoCertificado>EACAT_USUARI</CodigoCertificado>
                <IdSolicitud>1</IdSolicitud>
                <IdTransmision>EXPEDIENT</IdTransmision>
                <FechaGeneracion/>
             </Transmision>
          </DatosGenericos>
          <DatosEspecificos>
             <peticioConsultaUsuari xmlns="http://www.aocat.net/eacat">
                <nif>82828282S</nif>
             </peticioConsultaUsuari>
          </DatosEspecificos>
       </SolicitudTransmision>
    </Solicitudes>
 </Peticion>
```


## 4.4. EACAT_USUARI Resposta

Exemple de resposta consultant per ```<nif>```.

```xml
<respostaConsultaUsuari xmlns="http://www.aocat.net/eacat" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
  <peticioConsultaUsuari>
     <nif>82828282S</nif>
  </peticioConsultaUsuari>
  <resposta>
     <usuari>
        <codiEns>803053010</codiEns>
        <nif>82828282S</nif>
        <tipus>MLO</tipus>
        <nom>Idea 1</nom>
        <dataAlta>2015-02-26+01:00</dataAlta>
        <email>ceandersson@opentrends.net</email>
        <tractament>Herr</tractament>
        <perfil>Alcalde president, Alcaldessa presidenta</perfil>
        <ens>
           <codiEns>803053010</codiEns>
           <nom>Organisme Autònom Museu-Col·lecció Municipal de Cabrils</nom>
           <idTipusEns>5</idTipusEns>
           <nomTipusEns>Ens de gestió</nomTipusEns>
           <cif>P0800143J</cif>
           <adreca>C/ Santa Creu, 5 Cal Ventura del Vi</adreca>
           <codiPostal>8348</codiPostal>
           <codiMunicipi>803050006</codiMunicipi>
           <nomMunicipi>Cabrils</nomMunicipi>
           <codiComarca>8102130008</codiComarca>
           <nomComarca>Maresme</nomComarca>
           <codiProvincia>8000840003</codiProvincia>
           <nomProvincia>Barcelona</nomProvincia>
           <codiDelegacio>1</codiDelegacio>
           <nomDelegacio>Barcelona</nomDelegacio>
        </ens>
     </usuari>
     <usuari>
        <codiEns>820553025</codiEns>
        <nif>82828282S</nif>
        <tipus>MLO</tipus>
        <nom>Idea 1</nom>
        <dataAlta>2015-07-08+02:00</dataAlta>
        <email>a@a.es</email>
        <ens>
           <codiEns>820553025</codiEns>
           <nom>Organisme Municipal d'Educació de Sant Cugat del Vallès</nom>
           <idTipusEns>5</idTipusEns>
           <nomTipusEns>Ens de gestió</nomTipusEns>
           <cif>V08901910</cif>
           <adreca>Cánovas del Castillo, 50</adreca>
           <codiPostal>8190</codiPostal>
           <codiMunicipi>820550006</codiMunicipi>
           <nomMunicipi>Sant Cugat del Vallès</nomMunicipi>
           <codiComarca>8104020002</codiComarca>
           <nomComarca>Vallès Occidental</nomComarca>
           <codiProvincia>8000840003</codiProvincia>
           <nomProvincia>Barcelona</nomProvincia>
           <codiDelegacio>1</codiDelegacio>
           <nomDelegacio>Barcelona</nomDelegacio>
        </ens>
     </usuari>
     <usuari>
        <codiEns>2523470005</codiEns>
        <nif>82828282S</nif>
        <tipus>MLO</tipus>
        <nom>Idea 1</nom>
        <dataAlta>2014-10-22+02:00</dataAlta>
        <email>proves@proves.es</email>
        <ens>
           <codiEns>2523470005</codiEns>
           <nom>Ajuntament de Tremp</nom>
           <idTipusEns>2</idTipusEns>
           <nomTipusEns>Ajuntament</nomTipusEns>
           <cif>P2529500G</cif>
           <adreca>Plaça de la Creu, 1</adreca>
           <codiPostal>25620</codiPostal>
           <codiMunicipi>2523470005</codiMunicipi>
           <nomMunicipi>Tremp</nomMunicipi>
           <codiComarca>8102520002</codiComarca>
           <nomComarca>Pallars Jussà</nomComarca>
           <codiProvincia>8002550006</codiProvincia>
           <nomProvincia>Lleida</nomProvincia>
           <codiDelegacio>7</codiDelegacio>
           <nomDelegacio>Alt Pirineu i Aran</nomDelegacio>
        </ens>
     </usuari>
     <usuari>
        <codiEns>7516070027</codiEns>
        <nif>82828282S</nif>
        <tipus>MLO</tipus>
        <nom>Idea 1</nom>
        <dataAlta>2014-05-21+02:00</dataAlta>
        <email>nshahin@opentrends.net</email>
        <ens>
           <codiEns>7516070027</codiEns>
           <nom>Sindicatura de Comptes</nom>
           <idTipusEns>16</idTipusEns>
           <nomTipusEns>Ens parlamentaris</nomTipusEns>
           <cif>S5800001I</cif>
           <codiPostal>8002</codiPostal>
           <codiMunicipi>801930008</codiMunicipi>
           <nomMunicipi>Barcelona</nomMunicipi>
           <codiComarca>8101360009</codiComarca>
           <nomComarca>Barcelonès</nomComarca>
           <codiProvincia>8000840003</codiProvincia>
           <nomProvincia>Barcelona</nomProvincia>
        </ens>
     </usuari>
     <usuari>
        <codiEns>7971100030</codiEns>
        <nif>82828282S</nif>
        <tipus>MLO</tipus>
        <nom>Idea 1</nom>
        <dataAlta>2013-10-10+02:00</dataAlta>
        <email>test@testaoc.cat</email>
        <tractament>Sr</tractament>
        <ens>
           <codiEns>7971100030</codiEns>
           <nom>Agència de Salut Pública de Catalunya</nom>
           <idTipusEns>71</idTipusEns>
           <nomTipusEns>EDP – Ent Dret Públic sub. ord. privat</nomTipusEns>
           <cif>S0800504C</cif>
           <adreca>C. Roc Boronat, 81-95</adreca>
           <codiPostal>8005</codiPostal>
           <codiMunicipi>801930008</codiMunicipi>
           <nomMunicipi>Barcelona</nomMunicipi>
           <codiComarca>8101360009</codiComarca>
           <nomComarca>Barcelonès</nomComarca>
           <codiProvincia>8000840003</codiProvincia>
           <nomProvincia>Barcelona</nomProvincia>
        </ens>
     </usuari>
     <usuari>
        <codiEns>7972100059</codiEns>
        <nif>82828282S</nif>
        <tipus>MLO</tipus>
        <nom>Idea 1</nom>
        <dataAlta>2015-10-08+02:00</dataAlta>
        <email>a@a.es</email>
        <tractament>Sra</tractament>
        <perfil>Alcalde president, Alcaldessa presidenta</perfil>
        <ens>
           <codiEns>7972100059</codiEns>
           <nom>Consorci Port de Mataró</nom>
           <idTipusEns>72</idTipusEns>
           <nomTipusEns>Consorci 2</nomTipusEns>
           <cif>Q5856419F</cif>
           <adreca>Passeig del Callao s/n</adreca>
           <codiPostal>8301</codiPostal>
           <codiMunicipi>812130008</codiMunicipi>
           <nomMunicipi>Mataró</nomMunicipi>
           <codiComarca>8102130008</codiComarca>
           <nomComarca>Maresme</nomComarca>
           <codiProvincia>8000840003</codiProvincia>
           <nomProvincia>Barcelona</nomProvincia>
        </ens>
     </usuari>
     <usuari>
        <codiEns>7976100038</codiEns>
        <nif>82828282S</nif>
        <tipus>MLO</tipus>
        <nom>Idea 1</nom>
        <dataAlta>2013-10-11+02:00</dataAlta>
        <email>test@testaoc.cat</email>
        <tractament>Sr</tractament>
        <ens>
           <codiEns>7976100038</codiEns>
           <nom>Servei Públic d’Ocupació de Catalunya</nom>
           <idTipusEns>76</idTipusEns>
           <nomTipusEns>Altres ens Públics</nomTipusEns>
           <cif>Q0801272F</cif>
           <adreca>Carrer Llull, 297-307</adreca>
           <codiPostal>8019</codiPostal>
           <codiMunicipi>801930008</codiMunicipi>
           <nomMunicipi>Barcelona</nomMunicipi>
           <codiComarca>8101360009</codiComarca>
           <nomComarca>Barcelonès</nomComarca>
           <codiProvincia>8000840003</codiProvincia>
           <nomProvincia>Barcelona</nomProvincia>
        </ens>
     </usuari>
     <usuari>
        <codiEns>7977100004</codiEns>
        <nif>82828282S</nif>
        <tipus>MLO</tipus>
        <nom>Idea 1</nom>
        <dataAlta>2013-09-09+02:00</dataAlta>
        <email>828282828s@aoc.cat</email>
        <dataModificacio>2013-09-09+02:00</dataModificacio>
        <ens>
           <codiEns>7977100004</codiEns>
           <nom>Agència de Protecció de la Salut</nom>
           <idTipusEns>77</idTipusEns>
           <nomTipusEns>Entitats autònomes administratives</nomTipusEns>
           <cif>Q0801405B</cif>
           <adreca>Roc Boronat, 81-95</adreca>
           <codiPostal>8005</codiPostal>
           <codiMunicipi>801930008</codiMunicipi>
           <nomMunicipi>Barcelona</nomMunicipi>
           <codiComarca>8101360009</codiComarca>
           <nomComarca>Barcelonès</nomComarca>
           <codiProvincia>8000840003</codiProvincia>
           <nomProvincia>Barcelona</nomProvincia>
        </ens>
     </usuari>
     <usuari>
        <codiEns>9610210360</codiEns>
        <nif>82828282S</nif>
        <tipus>MLO</tipus>
        <nom>Idea 1</nom>
        <dataAlta>2012-06-06+02:00</dataAlta>
        <email>test@test.cat</email>
        <tractament>Sr.</tractament>
        <dataModificacio>2012-06-06+02:00</dataModificacio>
        <ens>
           <codiEns>9610210360</codiEns>
           <nom>Escola d'Administració Pública de Catalunya</nom>
           <idTipusEns>14</idTipusEns>
           <nomTipusEns>Entitat col·laboradora</nomTipusEns>
           <cif>Q0840004F</cif>
           <adreca>Carrer de Girona, 20</adreca>
           <codiPostal>8010</codiPostal>
           <codiMunicipi>801930008</codiMunicipi>
           <nomMunicipi>Barcelona</nomMunicipi>
           <codiComarca>8101360009</codiComarca>
           <nomComarca>Barcelonès</nomComarca>
           <codiProvincia>8000840003</codiProvincia>
           <nomProvincia>Barcelona</nomProvincia>
        </ens>
     </usuari>
  </resposta>
  <resultat>
     <codiResultat>0</codiResultat>
     <descripcio/>
  </resultat>
</respostaConsultaUsuari>
```


## 4.5. EACAT_SERVEI Petició

Exemple de petició consultant per ```<codiEns>``` i ```<servei>```.

```xml
<Peticion xmlns="http://gencat.net/scsp/esquemes/peticion">
  <Atributos>
     <IdPeticion>CU1-EACAT_SERVEI-${=(long)(System.currentTimeMillis())}</IdPeticion>
     <NumElementos>1</NumElementos>
     <TimeStamp/>
     <CodigoCertificado>EACAT_SERVEI</CodigoCertificado>
     <CodigoProducto>EACAT</CodigoProducto>
     <DatosAutorizacion>
        <IdentificadorSolicitante>9821920002</IdentificadorSolicitante>
        <NombreSolicitante>CAOC</NombreSolicitante>
        <Finalidad>PROVES</Finalidad>
     </DatosAutorizacion>
  </Atributos>
  <Solicitudes>
     <SolicitudTransmision>
        <DatosGenericos>
           <Solicitante>
              <IdentificadorSolicitante>9821920002</IdentificadorSolicitante>
              <NombreSolicitante>CAOC</NombreSolicitante>
              <Finalidad>PROVES</Finalidad>
              <Consentimiento>Si</Consentimiento>
           </Solicitante>
           <Transmision>
              <CodigoCertificado>EACAT_SERVEI</CodigoCertificado>
              <IdSolicitud>1</IdSolicitud>
              <IdTransmision>EXPEDIENT</IdTransmision>
              <FechaGeneracion/>
           </Transmision>
        </DatosGenericos>
        <DatosEspecificos>
           <peticioConsultaServei xmlns="http://www.aocat.net/eacat">
              <servei>SV_CULT</servei>
              <codiEns>800180001</codiEns>
           </peticioConsultaServei>
        </DatosEspecificos>
     </SolicitudTransmision>
  </Solicitudes>
</Peticion>
```


## 4.6. EACAT_SERVEI Resposta

Exemple de resposta consultant per ```<codiEns>``` i ```<servei>```.

```xml
<respostaConsultaServei xmlns="http://www.aocat.net/eacat" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
  <peticioConsultaServei>
     <servei>SV_CULT</servei>
     <codiEns>800180001</codiEns>
  </peticioConsultaServei>
  <resposta>
     <servei>
        <nif>00001111F</nif>
        <nom>Usuari Proves TES</nom>
        <codiEns>800180001</codiEns>
        <nomEns>Ajuntament d'Abrera</nomEns>
        <idTipusEns>2</idTipusEns>
        <nomTipusEns>Ajuntament d'Abrera</nomTipusEns>
        <servei>SV_CULT</servei>
        <rol>#TESERVEI#</rol>
     </servei>
     <servei>
        <nif>00001111F</nif>
        <nom>Usuari Proves TES</nom>
        <codiEns>800180001</codiEns>
        <nomEns>Ajuntament d'Abrera</nomEns>
        <idTipusEns>2</idTipusEns>
        <nomTipusEns>Ajuntament d'Abrera</nomTipusEns>
        <servei>SV_CULT</servei>
        <rol>#VISUDOCS#</rol>
     </servei>
     <servei>
        <nif>82828282S</nif>
        <nom>Idea 1</nom>
        <codiEns>800180001</codiEns>
        <nomEns>Ajuntament d'Abrera</nomEns>
        <idTipusEns>2</idTipusEns>
        <nomTipusEns>Ajuntament d'Abrera</nomTipusEns>
        <servei>SV_CULT</servei>
        <rol>#TESERVEI#</rol>
     </servei>
     <servei>
        <nif>82828282S</nif>
        <nom>Idea 1</nom>
        <codiEns>800180001</codiEns>
        <nomEns>Ajuntament d'Abrera</nomEns>
        <idTipusEns>2</idTipusEns>
        <nomTipusEns>Ajuntament d'Abrera</nomTipusEns>
        <servei>SV_CULT</servei>
        <rol>#VISUDOCS#</rol>
     </servei>
     <servei>
        <nif>82828282S</nif>
        <nom>Idea 1</nom>
        <codiEns>800180001</codiEns>
        <nomEns>Ajuntament d'Abrera</nomEns>
        <idTipusEns>2</idTipusEns>
        <nomTipusEns>Ajuntament d'Abrera</nomTipusEns>
        <servei>SV_CULT</servei>
        <rol>CULT_EDIT</rol>
        <descripcio>Editor de trameses al Departament de Cultura (sol·licitant)</descripcio>
     </servei>
     <servei>
        <nif>82828282S</nif>
        <nom>Idea 1</nom>
        <codiEns>800180001</codiEns>
        <nomEns>Ajuntament d'Abrera</nomEns>
        <idTipusEns>2</idTipusEns>
        <nomTipusEns>Ajuntament d'Abrera</nomTipusEns>
        <servei>SV_CULT</servei>
        <rol>CULT_SIGN</rol>
        <descripcio>Signatura del representant legal (sol·licitant)</descripcio>
     </servei>
     <servei>
        <nif>82828282S</nif>
        <nom>Idea 1</nom>
        <codiEns>800180001</codiEns>
        <nomEns>Ajuntament d'Abrera</nomEns>
        <idTipusEns>2</idTipusEns>
        <nomTipusEns>Ajuntament d'Abrera</nomTipusEns>
        <servei>SV_CULT</servei>
        <rol>CULT_VIS</rol>
        <descripcio>Permet visualitzar les trameses al Departament de Cultura</descripcio>
     </servei>
  </resposta>
  <resultat>
     <codiResultat>0</codiResultat>
     <descripcio/>
  </resultat>
</respostaConsultaServei>

```


## 4.7. EACAT_TIPUS_ENS Petició

Exemple de petició de tipus d'ens.

```xml
 <Peticion xmlns="http://gencat.net/scsp/esquemes/peticion">
    <Atributos>
       <IdPeticion>CU1-EACAT_TIPUS_ENS-${=(long)(System.currentTimeMillis())}</IdPeticion>
       <NumElementos>1</NumElementos>
       <TimeStamp/>
       <CodigoCertificado>EACAT_TIPUS_ENS</CodigoCertificado>
       <CodigoProducto>EACAT</CodigoProducto>
       <DatosAutorizacion>
          <IdentificadorSolicitante>9821920002</IdentificadorSolicitante>
          <NombreSolicitante>CAOC</NombreSolicitante>
          <Finalidad>PROVES</Finalidad>
       </DatosAutorizacion>
    </Atributos>
    <Solicitudes>
       <SolicitudTransmision>
          <DatosGenericos>
             <Solicitante>
                <IdentificadorSolicitante>9821920002</IdentificadorSolicitante>
                <NombreSolicitante>CAOC</NombreSolicitante>
                <Finalidad>PROVES</Finalidad>
                <Consentimiento>Si</Consentimiento>
             </Solicitante>
             <Transmision>
                <CodigoCertificado>EACAT_TIPUS_ENS</CodigoCertificado>
                <IdSolicitud>1</IdSolicitud>
                <IdTransmision>EXPEDIENT</IdTransmision>
                <FechaGeneracion/>
             </Transmision>
          </DatosGenericos>
          <DatosEspecificos>
             <peticioConsultaTipusEns xmlns="http://www.aocat.net/eacat">
             </peticioConsultaTipusEns>
          </DatosEspecificos>
       </SolicitudTransmision>
    </Solicitudes>
 </Peticion>
```


## 4.8. EACAT_TIPUS_ENS Resposta

Resposta de petició de tipus d'ens.

```xml
<respostaConsultaTipusEns xmlns="http://www.aocat.net/eacat" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
  <peticioConsultaTipusEns/>
  <resposta>
     <tipusEns>
        <idTipusEns>2</idTipusEns>
        <nomTipusEns>Ajuntament</nomTipusEns>
     </tipusEns>
     <tipusEns>
        <idTipusEns>3</idTipusEns>
        <nomTipusEns>Consell comarcal</nomTipusEns>
     </tipusEns>
     <tipusEns>
        <idTipusEns>4</idTipusEns>
        <nomTipusEns>Entitat municipal descentralitzada</nomTipusEns>
     </tipusEns>
     <tipusEns>
        <idTipusEns>5</idTipusEns>
        <nomTipusEns>Ens de gestió</nomTipusEns>
     </tipusEns>
     <tipusEns>
        <idTipusEns>6</idTipusEns>
        <nomTipusEns>Diputació</nomTipusEns>
     </tipusEns>
     <tipusEns>
        <idTipusEns>7</idTipusEns>
        <nomTipusEns>Entitat metropolitana</nomTipusEns>
     </tipusEns>
     <tipusEns>
        <idTipusEns>9</idTipusEns>
        <nomTipusEns>Mancomunitat</nomTipusEns>
     </tipusEns>
     <tipusEns>
        <idTipusEns>10</idTipusEns>
        <nomTipusEns>Nuclis</nomTipusEns>
     </tipusEns>
     <tipusEns>
        <idTipusEns>11</idTipusEns>
        <nomTipusEns>Entitats de població</nomTipusEns>
     </tipusEns>
     <tipusEns>
        <idTipusEns>12</idTipusEns>
        <nomTipusEns>Consorci</nomTipusEns>
     </tipusEns>
     <tipusEns>
        <idTipusEns>13</idTipusEns>
        <nomTipusEns>Societat participada</nomTipusEns>
     </tipusEns>
     <tipusEns>
        <idTipusEns>14</idTipusEns>
        <nomTipusEns>Entitat col·laboradora</nomTipusEns>
     </tipusEns>
     <tipusEns>
        <idTipusEns>15</idTipusEns>
        <nomTipusEns>Ens instrumental</nomTipusEns>
     </tipusEns>
     <tipusEns>
        <idTipusEns>16</idTipusEns>
        <nomTipusEns>Ens parlamentaris</nomTipusEns>
     </tipusEns>
     <tipusEns>
        <idTipusEns>17</idTipusEns>
        <nomTipusEns>Comunitat de municipis</nomTipusEns>
     </tipusEns>
     <tipusEns>
        <idTipusEns>18</idTipusEns>
        <nomTipusEns>Fundacions</nomTipusEns>
     </tipusEns>
     <tipusEns>
        <idTipusEns>20</idTipusEns>
        <nomTipusEns>Organismes autónoms locals</nomTipusEns>
     </tipusEns>
     <tipusEns>
        <idTipusEns>21</idTipusEns>
        <nomTipusEns>Entitats públiques empresarials locals</nomTipusEns>
     </tipusEns>
     <tipusEns>
        <idTipusEns>22</idTipusEns>
        <nomTipusEns>Soc. merc. part. íntegrament ens local</nomTipusEns>
     </tipusEns>
     <tipusEns>
        <idTipusEns>60</idTipusEns>
        <nomTipusEns>Ens adherits per Resolució</nomTipusEns>
     </tipusEns>
     <tipusEns>
        <idTipusEns>70</idTipusEns>
        <nomTipusEns>EACIF -  Ent autònoma comer i financ</nomTipusEns>
     </tipusEns>
     <tipusEns>
        <idTipusEns>71</idTipusEns>
        <nomTipusEns>EDP – Ent Dret Públic sub. ord. privat</nomTipusEns>
     </tipusEns>
     <tipusEns>
        <idTipusEns>72</idTipusEns>
        <nomTipusEns>Consorci 2</nomTipusEns>
     </tipusEns>
     <tipusEns>
        <idTipusEns>73</idTipusEns>
        <nomTipusEns>Fundació</nomTipusEns>
     </tipusEns>
     <tipusEns>
        <idTipusEns>74</idTipusEns>
        <nomTipusEns>Societat Mercantil</nomTipusEns>
     </tipusEns>
     <tipusEns>
        <idTipusEns>75</idTipusEns>
        <nomTipusEns>Ens de gestió 2</nomTipusEns>
     </tipusEns>
     <tipusEns>
        <idTipusEns>76</idTipusEns>
        <nomTipusEns>Altres ens Públics</nomTipusEns>
     </tipusEns>
     <tipusEns>
        <idTipusEns>77</idTipusEns>
        <nomTipusEns>Entitats autònomes administratives</nomTipusEns>
     </tipusEns>
     <tipusEns>
        <idTipusEns>78</idTipusEns>
        <nomTipusEns>SCSE - Serv cat salut – ICS - INSS</nomTipusEns>
     </tipusEns>
     <tipusEns>
        <idTipusEns>79</idTipusEns>
        <nomTipusEns>Ens de la Generalitat</nomTipusEns>
     </tipusEns>
     <tipusEns>
        <idTipusEns>90</idTipusEns>
        <nomTipusEns>Universitat</nomTipusEns>
     </tipusEns>
     <tipusEns>
        <idTipusEns>91</idTipusEns>
        <nomTipusEns>Ens dependents utilitzats a l'eTauler</nomTipusEns>
     </tipusEns>
     <tipusEns>
        <idTipusEns>92</idTipusEns>
        <nomTipusEns>Ens instrumentals públics del món local</nomTipusEns>
     </tipusEns>
     <tipusEns>
        <idTipusEns>93</idTipusEns>
        <nomTipusEns>Ens instrumentals privats  del món local</nomTipusEns>
     </tipusEns>
     <tipusEns>
        <idTipusEns>95</idTipusEns>
        <nomTipusEns>Cambres de Comerç</nomTipusEns>
     </tipusEns>
     <tipusEns>
        <idTipusEns>96</idTipusEns>
        <nomTipusEns>Ens de Formació</nomTipusEns>
     </tipusEns>
     <tipusEns>
        <idTipusEns>97</idTipusEns>
        <nomTipusEns>Òrgan col·legiat</nomTipusEns>
     </tipusEns>
     <tipusEns>
        <idTipusEns>98</idTipusEns>
        <nomTipusEns>Ens virtuals</nomTipusEns>
     </tipusEns>
     <tipusEns>
        <idTipusEns>99</idTipusEns>
        <nomTipusEns>Generalitat</nomTipusEns>
     </tipusEns>
  </resposta>
  <resultat>
     <codiResultat>0</codiResultat>
     <descripcio/>
  </resultat>
</respostaConsultaTipusEns>
```


## 4.9. EACAT_FUNCIONARI_HABILITAT Petició

Exemple de petició consultant per ```<idens>```.

```xml
<Peticion xmlns="http://gencat.net/scsp/esquemes/peticion">
  <Atributos>
     <IdPeticion>CU1-EACAT_TIPUS_ENS-${=(long)(System.currentTimeMillis())}</IdPeticion>
     <NumElementos>1</NumElementos>
     <TimeStamp/>
     <CodigoCertificado>EACAT_FUNCIONARI_HABILITAT</CodigoCertificado>
     <CodigoProducto>EACAT</CodigoProducto>
     <DatosAutorizacion>
        <IdentificadorSolicitante>9821920002</IdentificadorSolicitante>
        <NombreSolicitante>CAOC</NombreSolicitante>
        <Finalidad>PROVES</Finalidad>
     </DatosAutorizacion>
  </Atributos>
  <Solicitudes>
     <SolicitudTransmision>
        <DatosGenericos>
           <Solicitante>
              <IdentificadorSolicitante>9821920002</IdentificadorSolicitante>
              <NombreSolicitante>CAOC</NombreSolicitante>
              <Finalidad>PROVES</Finalidad>
              <Consentimiento>Si</Consentimiento>
           </Solicitante>
           <Transmision>
              <CodigoCertificado>EACAT_FUNCIONARI_HABILITAT</CodigoCertificado>
              <IdSolicitud>1</IdSolicitud>
              <IdTransmision>EXPEDIENT</IdTransmision>
              <FechaGeneracion/>
           </Transmision>
        </DatosGenericos>
        <DatosEspecificos>
           <peticioConsultaFuncionariHabilitat xmlns="http://www.aocat.net/eacat">
           <idens>9821920002</idens>
           </peticioConsultaFuncionariHabilitat>
        </DatosEspecificos>
     </SolicitudTransmision>
  </Solicitudes>
</Peticion>
```


## 4.10. EACAT_FUNCIONARI_HABILITAT Resposta

Exemple de resposta consultant per ```<idens>```.

```xml
<respostaConsultaFuncionariHabilitat xmlns="http://www.aocat.net/eacat" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
  <peticioConsultaFuncionariHabilitat/>
  <resposta>
     <funcionariHabilitat>
        <nom>Adán Guerrero</nom>
        <nif>47903282D</nif>
        <tipus>MLO</tipus>
        <nomEns>Consorci Administració Oberta de Catalunya</nomEns>
        <codiEns>9821920002</codiEns>
        <dataAlta>2021-01-01+01:00</dataAlta>
        <assistirInteressats>true</assistirInteressats>
        <expCopiesAutentiques>false</expCopiesAutentiques>
     </funcionariHabilitat>
     <funcionariHabilitat>
        <nom>Jose Luis Pastor</nom>
        <nif>46801863Z</nif>
        <tipus>MLO</tipus>
        <nomEns>Consorci Administració Oberta de Catalunya</nomEns>
        <codiEns>9821920002</codiEns>
        <dataAlta>2020-10-01+02:00</dataAlta>
        <assistirInteressats>true</assistirInteressats>
        <expCopiesAutentiques>true</expCopiesAutentiques>
        <unitatAdministrativa>Secretaria</unitatAdministrativa>
     </funcionariHabilitat>
     <funcionariHabilitat>
        <nom>Pepita Matllo Aguilar</nom>
        <nif>52171818K</nif>
        <tipus>MLO</tipus>
        <nomEns>Consorci Administració Oberta de Catalunya</nomEns>
        <codiEns>9821920002</codiEns>
        <dataAlta>2020-10-04+02:00</dataAlta>
        <assistirInteressats>true</assistirInteressats>
        <expCopiesAutentiques>true</expCopiesAutentiques>
        <unitatAdministrativa>Intervenció</unitatAdministrativa>
     </funcionariHabilitat>
     <funcionariHabilitat>
        <nom>Usuari Proves SOC</nom>
        <nif>50505050V</nif>
        <tipus>MLO</tipus>
        <nomEns>Ajuntament d'Abrera</nomEns>
        <codiEns>800180001</codiEns>
        <dataAlta>2020-09-06+02:00</dataAlta>
        <assistirInteressats>true</assistirInteressats>
        <expCopiesAutentiques>true</expCopiesAutentiques>
        <unitatAdministrativa>Secretaria</unitatAdministrativa>
     </funcionariHabilitat>
     <funcionariHabilitat>
        <nom>Usuari Proves SOC</nom>
        <nif>50505050V</nif>
        <tipus>MLO</tipus>
        <nomEns>Consell Comarcal de l'Anoia</nomEns>
        <codiEns>8100690004</codiEns>
        <dataAlta>2020-10-04+02:00</dataAlta>
        <assistirInteressats>true</assistirInteressats>
        <expCopiesAutentiques>true</expCopiesAutentiques>
        <unitatAdministrativa>Secretaria</unitatAdministrativa>
     </funcionariHabilitat>
  </resposta>
  <resultat>
     <codiResultat>0</codiResultat>
     <descripcio/>
  </resultat>
</respostaConsultaFuncionariHabilitat>
```



