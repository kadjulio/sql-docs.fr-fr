---
description: Méthode getSuperTypes (SQLServerDatabaseMetaData)
title: Méthode getSuperTypes (SQLServerDatabaseMetaData) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
apiname:
- SQLServerDatabaseMetaData.getSuperTypes
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: 5b8e78e6-2bb0-4dc7-9c77-a5609654cb05
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 38784846d997b0ad37f67a21cb44e0cdcf8e40c1
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/30/2021
ms.locfileid: "99174886"
---
# <a name="getsupertypes-method-sqlserverdatabasemetadata"></a>Méthode getSuperTypes (SQLServerDatabaseMetaData)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Récupère une description des hiérarchies de type définies par l'utilisateur dans un schéma particulier de cette base de données.  
  
> [!NOTE]  
>  Actuellement, cette méthode n’est pas prise en charge avec [!INCLUDE[jdbcNoVersion](../../../includes/jdbcnoversion_md.md)]. Lorsqu'elle est utilisée, cette méthode retourne toujours un jeu de résultats vide.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
public java.sql.ResultSet getSuperTypes(java.lang.String catalog,  
                                        java.lang.String schemaPattern,  
                                        java.lang.String typeNamePattern)  
```  
  
#### <a name="parameters"></a>Paramètres  
 *catalog*  
  
 **Chaîne** contenant le nom du catalogue.  
  
 *schemaPattern*  
  
 **Chaîne** contenant le modèle de nom du schéma.  
  
 *tableNamePattern*  
  
 **String** contenant le modèle de nom de la table.  
  
## <a name="return-value"></a>Valeur de retour  
 Objet [SQLServerResultSet](../../../connect/jdbc/reference/sqlserverresultset-class.md).  
  
## <a name="exceptions"></a>Exceptions  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Notes  
 Cette méthode getSuperTypes est spécifiée par la méthode getSuperTypes de l’interface java.sql.DatabaseMetaData.  
  
## <a name="see-also"></a>Voir aussi  
 [SQLServerDatabaseMetaData, méthodes](../../../connect/jdbc/reference/sqlserverdatabasemetadata-methods.md)   
 [SQLServerDatabaseMetaData, membres](../../../connect/jdbc/reference/sqlserverdatabasemetadata-members.md)   
 [SQLServerDatabaseMetaData, classe](../../../connect/jdbc/reference/sqlserverdatabasemetadata-class.md)  
  
  
