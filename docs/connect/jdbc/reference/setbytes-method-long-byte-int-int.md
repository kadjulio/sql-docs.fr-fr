---
description: setBytes, méthode (long, byte, int, int)
title: Méthode setBytes (long, octet, int, int) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
apiname:
- SQLServerBlob.setBytes (long.byte[], int, int)
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: 7def226c-b211-459e-8c1a-08592d75d4a4
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 7210c363f8fefca7022fa018378f5d1bceeaa375
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/30/2021
ms.locfileid: "99173780"
---
# <a name="setbytes-method-long-byte-int-int"></a>setBytes, méthode (long, byte, int, int)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Enregistre tout ou partie du tableau d'octets spécifié dans l'objet BLOB, en démarrant à la position, au décalage et à la longueur spécifiés, puis retourne le nombre d'octets écrits.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
public int setBytes(long pos,  
                    byte[] bytes,  
                    int offset,  
                    int len)  
```  
  
#### <a name="parameters"></a>Paramètres  
 *pos*  
  
 Position (base 1) dans l'objet BLOB à laquelle démarrer l'écriture des données.  
  
 *bytes*  
  
 Tableau d'octets à écrire dans le BLOB.  
  
 *offset*  
  
 Décalage dans le tableau d’octets auquel la lecture des données commencera dans le tableau **d’octets**.  
  
 *len*  
  
 Nombre d'octets à lire depuis le tableau d'octets dans l'objet BLOB.  
  
## <a name="return-value"></a>Valeur de retour  
 **int** contenant le nombre d’octets écrits.  
  
## <a name="exceptions"></a>Exceptions  
 java.sql.SQLException  
  
## <a name="remarks"></a>Notes  
 Cette méthode setBytes est spécifiée par la méthode setBytes de l’interface java.sql.Blob.  
  
 Les données sont remplacées en démarrant à la position spécifiée et peuvent dépasser la longueur initiale de l'objet BLOB. La spécification d'une valeur position+1 permet d'ajouter des octets. Le passage d'une valeur position+2 ou supérieure (ou inférieure ou égale à zéro) génère une erreur de position. Si un tableau **d’octets** de longueur zéro est transmis, la méthode retourne zéro, car aucun octet n’a été écrit.  
  
## <a name="see-also"></a>Voir aussi  
 [Méthode setBytes &#40;SQLServerBlob&#41;](../../../connect/jdbc/reference/setbytes-method-sqlserverblob.md)   
 [SQLServerBlob, méthodes](../../../connect/jdbc/reference/sqlserverblob-methods.md)   
 [SQLServerBlob, membres](../../../connect/jdbc/reference/sqlserverblob-members.md)   
 [SQLServerBlob, classe](../../../connect/jdbc/reference/sqlserverblob-class.md)  
  
  
