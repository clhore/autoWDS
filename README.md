<div align="center">
  <h1>autoWDS</h1>
  <h4>Esta herramienta esta creada con el fin de automatizar la intalacion de y configuracion de todos los requerimientos necesarios para crear un WDS, utilizando PowerShell.</h4>
</div>
<ul>
    <li>Es te script es capaz de configurar la IP del Windows Server 2016 y los DNS, que previamente hallamos definido en el script.</li>
    <li>En los comentarios del script se puede encontrar también una pequeña explicación de como cambiar los servidores NTP del SO.</li>
</ul> 

Requisitos
======
Este escript está realizado para Windows Server 2016 por lo que si se ejecuta en otro sistema puede que ocasiones problemas al intentar crear el WDS.


CONFIGURACION
======
<h4>INTERFAZ DE RED</h4>
<p>Debemos definir en el scriptlos siguientes parametros</p>
<ul>
    <li>ifIndex</li>
    <li>ipParam</li>
    <li>dnsParams</li>
</ul> 
<div align="center">
  <img src="img/conf/red.png">
</div>

<h4>NOMBRE DEL EQUIPO Y DOMINIO</h4>
<p>Debemos definir en el scriptlos siguientes parametros</p>
<ul>
    <li>namePc</li>
    <li>domainName</li>
</ul> 
<div align="center">
  <img src="img/conf/userDomain.png">
</div>

<h4>DHCP</h4>
<p>Debemos definir en el scriptlos siguientes parametros</p>
<div align="center">
  <img src="img/conf/dhcp.png">
</div>


Ejecucion del script PowerShell
======
<div align="center">
  <h4>Una vez ya hemos configurado todos los parametros necesarios, procedemos ha ejecutar PowerShell en Windows Server 2016 y importamos el modulo.</h4>
</div>

    Import-Module .\autoWDS
    
<div align="center">
  <img src="img/autoWDS_1.png">
</div>

<div align="center">
  <h4>Ejecutamos la funcion helpPanel. Y seguimos los pasos que nos indica.</h4>
</div>

    helpPanel
    
<div align="center">
  <img src="img/autoWDS_2.png">
</div>

<div align="center">
  <h4>Configuramos la red, utilizando la funcion redConfig.</h4>
</div>

    redConfig
    
<div align="center">
  <img src="img/autoWDS_3.png">
</div>

<div align="center">
  <h4>Ahora comenzamos con el cambio de nombre del equipo y con la parte 1 de la creacion del DC. Una vez acabe se reiniciara y deberas volver ha abrir PowerShell y importar el modulo.</h4>
</div>

    namePc_and_domainServicesInstallation_1
    
<div align="center">
  <img src="img/autoWDS_4.png">
</div>
<div align="center">
  <img src="img/autoWDS_5.png">
</div>

<div align="center">
  <h4>Una vez se ha reiniciado importamos el modulo otravez.</h4>
</div>

    Import-Module .\autoWDS
    
<div align="center">
  <img src="img/autoWDS_1.png">
</div>

<div align="center">
  <h4>Ejecutamos la parte dos de la creacion del DC. Una vez lo ejecutes te pedira la contraseña de Administrador. Cuando acabe se reiniciara.</h4>
</div>

    namePc_and_domainServicesInstallation_2
    
<div align="center">
  <img src="img/autoWDS_6.png"><br>
  <img src="img/autoWDS_7.png"><br>
  <img src="img/autoWDS_8.png"><br>
</div>

<div align="center">
  <h4>Es posible que se quede en una pantalla de carga durante un largao periodo de tiempo, no apages el equipo y deja que acabe.</h4>
</div>
  
<div align="center">
  <img src="img/autoWDS_9.png"><br>
</div>

<div align="center">
  <h4>Una vez inicie si no a aavido ningun error el equipo deveria de quedar configurado como un DC.</h4>
</div>
    
<div align="center">
  <img src="img/autoWDS_10.png"><br>
</div>

<div align="center">
  <h4>Iniciamos como administrador del dominio, y volvemos a importar el modulo</h4>
</div>

    Import-Module .\autoWDS
    
<div align="center">
  <img src="img/autoWDS_1.png">
</div>

<div align="center">
  <h4>Ejecutaremos el Intalador de DHCP y WDS.</h4>
</div>

    DHCP_WDS_Installation
    
<div align="center">
  <img src="img/autoWDS_11.png">
</div>

<div align="center">
  <h4>En este punto el servicio DHCP ya estaria configurado, por lo que solo quedaria configurar el servidor WDS.</h4>
</div>
    
<div align="center">
  <img src="img/autoWDS_12.png"><br>
</div>

<div align="center">
  <h4>En este punto podemos configurar el servidor WDS de forma manual o haciendo uso del script.</h4>
  <h4>Si queremos configurarlo mediante el script deveremos volver a importar el modulo.</h4>
</div>


    Import-Module .\autoWDS
    
<div align="center">
  <img src="img/autoWDS_1.png">
</div>

<div align="center">
  <h4>Una vez importado el modulo ejecutaremos el siguiente comado.</h4>
</div>
    
    configWDS
    
<div align="center">
  <img src="img/autoWDS_13.png"><br>
</div>

<div align="center">
  <img src="img/autoWDS_14.png"><br>
</div>
