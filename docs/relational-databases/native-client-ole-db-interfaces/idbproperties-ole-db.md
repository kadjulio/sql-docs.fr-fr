---
description: IDBProperties (Native Client OLE DB fournisseur)
title: IDBProperties (Native Client OLE DB fournisseur) | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
ms.assetid: 2e5a4fd8-5164-495a-9986-3477aef8d8a5
author: markingmyname
ms.author: maghan
monikerRange: '>=aps-pdw-2016||=azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||>=sql-server-linux-2017||=azuresqldb-mi-current'
ms.openlocfilehash: b053d4d1ec270fedc0a136d3aada29ed63a87071
ms.sourcegitcommit: 1a544cf4dd2720b124c3697d1e62ae7741db757c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/14/2020
ms.locfileid: "97462180"
---
# <a name="idbproperties-native-client-ole-db-provider"></a>IDBProperties (Native Client OLE DB fournisseur)
[!INCLUDE[SQL Server Azure SQL Database Synapse Analytics PDW ](../../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw.md)]

  La spécification standard OLE DB permet aux fournisseurs de spécifier VT_EMPTY pour **DBPROPINFO::vValues**. Toutefois, OLE DB pour [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client retourne toujours VT_EMPTY lorsque vous appelez **IDBProperties::GetPropertyInfo** avec **DBPROPSET_ROWSETALL** pour récupérer des propriétés de l'ensemble de lignes.  
  
## <a name="see-also"></a>Voir aussi  
 [Interfaces &#40;OLE DB&#41;](./sql-server-native-client-ole-db-interfaces.md)  
  
