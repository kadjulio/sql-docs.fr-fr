---
description: Création, modification et suppression de schémas
title: Création, modification et suppression de schémas
ms.date: 08/06/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- schemas [SMO]
ms.assetid: 3e3619de-c6a2-4280-b2be-4ec9924608fb
author: markingmyname
ms.author: maghan
monikerRange: =azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||>=sql-server-linux-2017||=azuresqldb-mi-current
ms.openlocfilehash: 114bb00bbbd4303cbda03cdee669d35764fb944d
ms.sourcegitcommit: 1a544cf4dd2720b124c3697d1e62ae7741db757c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/14/2020
ms.locfileid: "97431639"
---
# <a name="creating-altering-and-removing-schemas"></a>Création, modification et suppression de schémas
[!INCLUDE [SQL Server ASDB, ASDBMI, ASDW ](../../../includes/applies-to-version/sql-asdb-asdbmi-asa.md)]

  L'objet <xref:Microsoft.SqlServer.Management.Smo.Schema> représente le contexte de propriété pour un objet de base de données. La propriété <xref:Microsoft.SqlServer.Management.Smo.Database.Schemas%2A> de l'objet <xref:Microsoft.SqlServer.Management.Smo.Database> représente une collection d'objets <xref:Microsoft.SqlServer.Management.Smo.Schema>.  
  
## <a name="example"></a>Exemple  
 Pour utiliser un exemple de code qui est fourni, vous devrez choisir l'environnement de programmation, le modèle de programmation et le langage de programmation dans lequel créer votre application. Pour plus d’informations, consultez [créer un projet Visual C&#35; Smo dans Visual Studio .net](../../../relational-databases/server-management-objects-smo/how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).  
  
## <a name="creating-altering-and-removing-a-schema-in-visual-basic"></a>Création, modification et suppression d'un schéma en Visual Basic  
 Cet exemple de code montre comment créer un schéma et l'attribuer à un objet de base de données. Le programme accorde ensuite l'autorisation à un utilisateur, puis crée une table dans le schéma.  
  
```VBNET
'Connect to the local, default instance of SQL Server.
Dim srv As Server
srv = New Server
'Reference the AdventureWorks2012database.
Dim db As Database
db = srv.Databases("AdventureWorks2012")
'Define a Schema object variable by supplying the parent database and name arguments in the constructor.
Dim sch As Schema
sch = New Schema(db, "MySchema1")
sch.Owner = "dbo"
'Create the schema on the instance of SQL Server.
sch.Create()
'Define an ObjectPermissionSet that contains the Update and Select object permissions.
Dim obperset As ObjectPermissionSet
obperset = New ObjectPermissionSet()
obperset.Add(ObjectPermission.Select)
obperset.Add(ObjectPermission.Update)
'Grant the set of permissions on the schema to the guest account.
sch.Grant(obperset, "guest")
'Define a Table object variable by supplying the parent database, name and schema arguments in the constructor.
Dim tb As Table
tb = New Table(db, "MyTable", "MySchema1")
Dim mycol As Column
mycol = New Column(tb, "Date", DataType.DateTime)
tb.Columns.Add(mycol)
tb.Create()
'Modify the owner of the schema and run the Alter method to make the change on the instance of SQL Server.
sch.Owner = "guest"
sch.Alter()
'Run the Drop method for the table and the schema to remove them.
tb.Drop()
sch.Drop()
``` 
  
## <a name="creating-altering-and-removing-a-schema-in-visual-c"></a>Création, modification et suppression d'un schéma en Visual C#  
 Cet exemple de code montre comment créer un schéma et l'attribuer à un objet de base de données. Le programme accorde ensuite l'autorisation à un utilisateur, puis crée une table dans le schéma.  
  
```csharp  
{  
         //Connect to the local, default instance of SQL Server.   
         Server srv = new Server();   
        //Reference the AdventureWorks2012 database.   
        Database db = srv.Databases["AdventureWorks2012"];   
        //Define a Schema object variable by supplying the parent database and name arguments in the constructor.   
        Schema sch = new Schema(db, "MySchema1");   
        sch.Owner = "dbo";   
  
        //Create the schema on the instance of SQL Server.   
        sch.Create();   
  
        //Define an ObjectPermissionSet that contains the Update and Select object permissions.   
        ObjectPermissionSet obperset = new ObjectPermissionSet();   
        obperset.Add(ObjectPermission.Select);   
        obperset.Add(ObjectPermission.Update);   
  
        //Grant the set of permissions on the schema to the guest account.   
        sch.Grant(obperset, "guest");   
  
        //Define a Table object variable by supplying the parent database, name and schema arguments in the constructor.   
        Table tb = new Table(db, "MyTable", "MySchema1");   
       Column mycol = new Column(tb, "Date", DataType.DateTime);   
        tb.Columns.Add(mycol);   
        tb.Create();   
  
        //Modify the owner of the schema and run the Alter method to make the change on the instance of SQL Server.   
        sch.Owner = "guest";   
        sch.Alter();   
  
        //Run the Drop method for the table and the schema to remove them.   
        tb.Drop();   
        sch.Drop();   
}  
```  
  
## <a name="creating-altering-and-removing-a-schema-in-powershell"></a>Création, modification et suppression d'un schéma dans PowerShell  
 Cet exemple de code montre comment créer un schéma et l'attribuer à un objet de base de données. Le programme accorde ensuite l'autorisation à un utilisateur, puis crée une table dans le schéma.  
  
```powershell   
# Set the path context to the local, default instance of SQL Server and get a reference to AdventureWorks2012  
CD \sql\localhost\default\databases  
$db = get-item Adventureworks2012  
  
# Define a schema object variable by supplying the parent database and name arguments in the constructor.   
$sch  = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Schema `  
-argumentlist $db, "MySchema1"  
  
# Set schema owner  
$sch.Owner = "dbo"   
  
# Create the schema on the instance of SQL Server.   
$sch.Create()  
  
# Define an ObjectPermissionSet that contains the Update and Select object permissions.   
$obperset  = New-Object -TypeName Microsoft.SqlServer.Management.SMO.ObjectPermissionSet  
$obperset.Add([Microsoft.SqlServer.Management.SMO.ObjectPermission]::Select)  
$obperset.Add([Microsoft.SqlServer.Management.SMO.ObjectPermission]::Update)  
  
# Grant the set of permissions on the schema to the guest account.   
$sch.Grant($obperset, "guest")  
  
#Create a SMO Table with one column and add it to the database  
$tb = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Table -argumentlist $db, "MyTable", "MySchema1"  
$Type = [Microsoft.SqlServer.Management.SMO.DataType]::DateTime  
$mycol =  New-Object -TypeName Microsoft.SqlServer.Management.SMO.Column -argumentlist $tb,"Date", $Type  
$tb.Columns.Add($mycol)  
$tb.Create()   
  
# Modify the owner of the schema and run the Alter method to make the change on the instance of SQL Server.   
$sch.Owner = "guest"  
$sch.Alter()  
  
# Run the Drop method for the table and the schema to remove them.   
$tb.Drop()  
$sch.Drop()  
```  
  
  
