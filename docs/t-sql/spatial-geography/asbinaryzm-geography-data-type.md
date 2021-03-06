---
description: AsBinaryZM (type de données geography)
title: AsBinaryZM (type de données geography) | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: t-sql
ms.topic: reference
f1_keywords:
- AsBinaryZM
- AsBinaryZM_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- AsBinaryZM, geography
- AsBinaryZM
ms.assetid: 37246adb-814d-4113-9983-4d336de8182c
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: 3bff9ed0acf12b1bd8d20c42b17ae59cd07cf5df
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/30/2021
ms.locfileid: "99189227"
---
# <a name="asbinaryzm-geography-data-type"></a>AsBinaryZM (type de données geography)
[!INCLUDE [SQL Server Azure SQL Database ](../../includes/applies-to-version/sql-asdb.md)]

  Retourne la représentation OGC (Open Geospatial Consortium) WKB (Well-Known Binary) d’une instance **geometry**, à laquelle s’ajoutent les valeurs **Z** (élévation) et **M** (mesure) apportées par l’instance.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
.AsBinaryZM()  
```  

[!INCLUDE[sql-server-tsql-previous-offline-documentation](../../includes/sql-server-tsql-previous-offline-documentation.md)]

## <a name="return-types"></a>Types de retour  
 Type de retour [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] : **varbinary(max)**  
  
 Type de retour CLR : **SqlBytes**  
  
## <a name="remarks"></a>Notes  
  
## <a name="examples"></a>Exemples  
  
```sql  
DECLARE @g1 GEOGRAPHY = 'Point(1 1 2 3)';  
  
SELECT @g1.STAsBinary();  
-- Returns: 0x0101000000000000000000F03F000000000000F03F  
  
SELECT @g1.AsBinaryZM();  
--Returns: 0x01B90B0000000000000000F03F000000000000F03F00000000000000400000000000000840  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Méthodes étendues sur des instances Geography](../../t-sql/spatial-geography/extended-methods-on-geography-instances.md)   
 [M &#40;type de données geography&#41;](../../t-sql/spatial-geography/m-geography-data-type.md)   
 [Z &#40;type de données geography&#41;](../../t-sql/spatial-geography/z-geography-data-type.md)  
  
  
