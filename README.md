# DiniDATA - server installation

## Installation prerequisites

Windows application server 2016+ is needed.

1. Install MS SQL Express edition on application server **as a default instance** -[https://www.microsoft.com/en-us/sql-server/sql-server-downloads](https://www.microsoft.com/en-us/sql-server/sql-server-downloads)
   with "**Sql Server and Windows Authentication mode**" and set password for sa account.
   
   ![sqlSetup.png](.\sqlSetup.png)

2. Install IIS (Interner Information Service) on application server with these options:
   ![IIS.png](.\IIS.png)

3. Run Setup.exe

## Installation process

Run DiniDataSetUp.exe on the application server with admin privileges. Enter the name of the server  (or <enter> for the default value), path for the root of application, SQL admin user name  (sa) and password for sa.

![setup.png](.\setup.png)

Setup will do these tasks:

* copy files to the specified folder

* create database on the local MS SQL Express instance

* create database schema and initial date setup

* configure IIS application pool

* create application for BarCode Web Manager application within default site
  ```http://ATGV1PAPDINIS01.commscope.com/DiniData```

* create application for publishing of clients within default site
  `http://ATGV1PAPDINIS01.commscope.com/ClientPublish`

* try to run BarCode Web Manager application using default web browser from URL
  `http://ATGV1PAPDINIS01.commscope.com/DiniData`
  use **DiniDataAdmin** as a login ID

## Post-installation actions

* Create file share on folder **<DiniDataRootFolder>\Images** with name **Images**. Grant read permissions to all users and write permissions to user responsible for uploading photos.

* Install client application on the working station with connected scale device. Install from addres `http://ATGV1PAPDINIS01.commscope.com/ClientPublish`
