---
description: MSsub_identity_range (Transact-SQL)
title: MSsub_identity_range (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: replication
ms.topic: reference
f1_keywords:
- MSsub_identity_range_TSQL
- MSsub_identity_range
dev_langs:
- TSQL
helpviewer_keywords:
- MSsub_identity_range system table
ms.assetid: 26e20d28-14ed-44fc-af3b-4de386de4bb8
author: cawrites
ms.author: chadam
ms.openlocfilehash: b57fc0593298e38f6db8969e742127c007411246
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/30/2021
ms.locfileid: "99156797"
---
# <a name="mssub_identity_range-transact-sql"></a>MSsub_identity_range (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  Le tableau **MSsub_identity_range** fournit la prise en charge de la gestion des plages d’identité pour les abonnements. Cette table est stockée dans la base de données d'abonnement.  
  
|Nom de la colonne|Type de données|Description|  
|-----------------|---------------|-----------------|  
|**objid**|**int**|ID de la table dont la colonne d'identité est gérée par la réplication.|  
|**range**|**bigint**|Contrôle la taille de la plage des valeurs d'identité consécutives qui seraient attribuées à l'abonné dans un ajustement.|  
|**last_seed**|**bigint**|Limite inférieure de la plage actuelle.|  
|**threshold**|**int**|Valeur de pourcentage qui contrôle le moment où l'Agent de distribution affecte une nouvelle plage d'identité. Lorsque le pourcentage de valeurs spécifié dans *seuil* est utilisé, la agent de distribution crée une nouvelle plage d’identité.|  
  
## <a name="see-also"></a>Voir aussi  
 [Tables de réplication &#40;&#41;Transact-SQL ](../../relational-databases/system-tables/replication-tables-transact-sql.md)   
 [Vues de réplication &#40;Transact-SQL&#41;](../../relational-databases/system-views/replication-views-transact-sql.md)  
  
  
