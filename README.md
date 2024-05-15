# Prometheus y Grafana

Dentro de una maquina virtual de Azure, incorporar dentro de Grafana y Prometheus  que Nginx nos redirija a la pagina personal (https://hectorcrzbq.github.io/webpage/).

**Video de ayuda**: https://youtu.be/PCJwJpbln6Q?si=otLgHfmGyHEm4CVv

1.	Abrimos una terminal e introducimos el siguiente comando **cd C:\Users\hecto\azure** para acceder a la ubicación de la clave
2.	Ejecutamos el comando **ssh -i myVm_key.pem azureuser@172.210.148.251** donde definimos donde esta la **clave privada de acceso a la maquina virtual** con el nombre **myVm_key.pem** y la dirección IP publica que es **172.210.148.251** 
3.	Descargamos Docker en la VM
4.	Creamos una carpeta donde alojaremos todos los documentos bajo el nombre de **grafana_and_prometheus**, con el comando **sudo mkdir garafana_and _prometheus**.

![image](https://github.com/HectorCRZBQ/grafana_and_prometheus/assets/148070442/8622d119-5628-455b-8728-3eb246912281)

5.	Accedemos a la carpeta para crear los códigos necesarios usando el comando **cd grafana_and_prometheus**
6.	Creamos el archivo de **docker-compose.yml** usando el comando **sudo nano docker-compose.yml**

![image](https://github.com/HectorCRZBQ/grafana_and_prometheus/assets/148070442/51aeac60-2dd1-4129-be7f-f4cd45a18c50)
 
7.	Creamos el archivo de **prometheus.yml** usando el comando **sudo nano prometheus.yml**

![image](https://github.com/HectorCRZBQ/grafana_and_prometheus/assets/148070442/abb39ee1-bb26-4d1a-813f-e9d2acf04426)

![image](https://github.com/HectorCRZBQ/grafana_and_prometheus/assets/148070442/2a3b4bcc-6ecb-4a58-b033-fb731556ff3a)

8. Dentro de la carpeta creamos una nueva carpeta para poder alojar la pagina web, con el comando de **sudo mkdir docker_webpage**

![image](https://github.com/HectorCRZBQ/grafana_and_prometheus/assets/148070442/c09f285f-ee3e-4714-9cb1-d67f59ff0332)

9.	Ejecutamos los comandos para instalar **git** en la VM, **sudo apt update** y **sudo apt install git**

![image](https://github.com/HectorCRZBQ/grafana_and_prometheus/assets/148070442/d0f358d8-6a98-489f-aa56-25c1c20b18ba)
 
10.	Clonamos en la carpeta el repositorio que tiene la pagina web de Docker con el comando de **sudo git clone https://github.com/HectorCRZBQ/webpage.git**

![image](https://github.com/HectorCRZBQ/grafana_and_prometheus/assets/148070442/ebd39609-f044-481e-9997-aadcafd6f933)

![image](https://github.com/HectorCRZBQ/grafana_and_prometheus/assets/148070442/00e01a0d-008d-4e56-b4af-a4dbf9910a61)
 
11.	Modificamos el archivo de **nginx.conf** usando el comando **sudo nano nginx.conf** de la carpeta de **/etc/nginx**.

![image](https://github.com/HectorCRZBQ/grafana_and_prometheus/assets/148070442/c7bf78f9-bef9-44b8-857b-829f288ffdb7)

12.	Solo quedaría levantar los servicios usando el comando **docker-compose up -d**

![image](https://github.com/HectorCRZBQ/grafana_and_prometheus/assets/148070442/d387e2b0-a99a-47f2-93cf-73ecfffc980d)

![image](https://github.com/HectorCRZBQ/grafana_and_prometheus/assets/148070442/df8815ed-c396-4d37-8697-078a55ed8fac)
 
13.	Podemos acceder:
 - **Prometheus**: http://localhost:9090

![image](https://github.com/HectorCRZBQ/grafana_and_prometheus/assets/148070442/533c2f57-7897-4310-8c81-cd0014933db8)

![image](https://github.com/HectorCRZBQ/grafana_and_prometheus/assets/148070442/30a503a4-b0ac-40e8-aae0-04c115de204b)

 - **Node Exporter**: http://localhost:9100
 
 ![image](https://github.com/HectorCRZBQ/grafana_and_prometheus/assets/148070442/968a1a21-1553-4b25-b0e1-d38624511a78)

![image](https://github.com/HectorCRZBQ/grafana_and_prometheus/assets/148070442/73b03caa-2e6e-4da6-832b-12152627d382)

 - **Mi página de GitHub usando Nginx**: http://localhost
 
![image](https://github.com/HectorCRZBQ/grafana_and_prometheus/assets/148070442/bf4c5c01-b862-48a7-a9cf-8d682b8cc1a3)

 - **cAdvisor**: http://localhost:8080

14.	Accedemos a **Grafana** en **http://localhost:3000/login**, usando los credenciales de **usuario: admin** y **contraseña: admin**

![image](https://github.com/HectorCRZBQ/grafana_and_prometheus/assets/148070442/e9aeddcb-1292-4e1a-9da5-b3f4fa531ab5)

![image](https://github.com/HectorCRZBQ/grafana_and_prometheus/assets/148070442/dcd1f502-8544-41d9-939d-1b29c6908f5c)

![image](https://github.com/HectorCRZBQ/grafana_and_prometheus/assets/148070442/a72f7374-29a7-4c2b-b47e-003ff61877dd)
 
![image](https://github.com/HectorCRZBQ/grafana_and_prometheus/assets/148070442/970a500d-2094-469d-893e-1e8a17653d40)

**Siempre debemos apagar la VM cuando no estemos usando o la acabemos de usar.**

Hector de la Cruz Baquero - [Linkdedin](https://www.linkedin.com/in/h%C3%A9ctor-de-la-cruz-baquero-ba193429b/) - [Webpage](https://hectorcrzbq.github.io/)

