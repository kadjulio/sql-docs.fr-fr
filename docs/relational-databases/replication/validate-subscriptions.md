---
description: Valider les abonnements
title: Valider les abonnements | Microsoft Docs
ms.custom: ''
ms.date: 03/01/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql13.rep.validate.subscriptions.f1
helpviewer_keywords:
- Validate Subscriptions dialog box
ms.assetid: 0ca39a35-f22c-46c5-82a4-342e34bf5d1b
author: MashaMSFT
ms.author: mathoma
monikerRange: =azuresqldb-current||>=sql-server-2016
ms.openlocfilehash: bb8a56e2b165f5ccfa7db701a2d95792de47e19d
ms.sourcegitcommit: 1a544cf4dd2720b124c3697d1e62ae7741db757c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/14/2020
ms.locfileid: "97468680"
---
# <a name="validate-subscriptions"></a>Valider les abonnements
[!INCLUDE[sql-asdb](../../includes/applies-to-version/sql-asdb.md)]
   Utilisez la boîte de dialogue **Valider les abonnements** pour spécifier que les abonnements à une publication transactionnelle doivent être validés à la prochaine exécution de l’Agent de distribution pour chaque abonnement. Le résultat de la validation figure dans le Moniteur de réplication. Pour plus d'informations, voir [Validate Data at the Subscriber](../../relational-databases/replication/validate-data-at-the-subscriber.md).  

[!INCLUDE[azure-sql-db-replication-supportability-note](../../includes/azure-sql-db-replication-supportability-note.md)]
  
## <a name="options"></a>Options  
 **Valider tous les abonnements SQL Server**  
 Sélectionnez cette option pour valider les données pour tous les abonnements SQL Server à cette publication.  
  
 **Valider les abonnements suivants**  
 Sélectionnez cette option si vous ne souhaitez pas valider tous les abonnements. Choisissez dans la liste les abonnements que vous souhaitez valider.  
  
 **Options de validation**  
 Cliquez pour accéder à la boîte de dialogue **Options de validation d'abonnement** qui permet d'indiquer si vous voulez utiliser la validation du nombre de lignes ou la validation de somme de contrôle.  
  
## <a name="see-also"></a>Voir aussi  
 [Valider des données répliquées](../../relational-databases/replication/validate-data-at-the-subscriber.md)  
  
  
