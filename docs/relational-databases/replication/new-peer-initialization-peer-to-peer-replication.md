---
title: Initialisation d’un nouvel homologue (Égal à égal) | Microsoft Docs
description: Décrit la page « Initialisation d’un nouvel homologue » utilisée pour la réplication d’égal à égal dans SQL Server Management Studio (SSMS).
ms.custom: seo-lt-2019
ms.date: 03/01/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql13.rep.p2pwizard.init.f1
ms.assetid: 050c00e1-78bd-4d9c-affe-40e22feb4d94
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: a89f539aa8d03b14be4dbcd81e08c308a2c72d30
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85721216"
---
# <a name="new-peer-initialization-peer-to-peer-replication"></a>Initialisation d'un nouvel homologue (réplication d'égal à égal)
 [!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]
  Utilisez la page **Initialisation d'un nouvel homologue** pour spécifier comment les bases de données d'homologues ont été initialisées. (Les homologues doivent être initialisés avant la fin de cet Assistant.) Les homologues sont initialisés manuellement ou en utilisant la fonctionnalité **initialize with backup** fournie par la réplication transactionnelle. (La réplication transactionnelle d'égal à égal ne prend pas en charge l'initialisation d'homologues à l'aide d'un instantané.) Si différents homologues doivent être initialisés à l'aide de différentes méthodes, vous devez ajouter séparément les homologues en exécutant l'Assistant plusieurs fois.  
  
## <a name="options"></a>Options  
 **Spécifiez comment la ou les nouvelles bases de données d'homologues ont été initialisées**  
 Chaque homologue doit comporter le schéma et les données pour tous les objets publiés. Sélectionnez l’une des options suivantes :  
  
-   Sélectionnez la première option si vous avez créé manuellement le schéma pour les objets publiés ou si vous avez restauré une sauvegarde et qu'aucune modification de données n'a été apportée dans la première base de données de publication depuis la sauvegarde. Si vous avez créé le schéma manuellement, vous devez vous assurer que chaque homologue comporte toutes les données requises. Cette option correspond à une valeur de **replication support only** pour la propriété de l'abonnement **sync_type**.  
  
-   Sélectionnez la seconde option si vous avez restauré une sauvegarde et qu'aucune modification n'a été apportée aux données dans la première base de données de publication depuis la sauvegarde. La réplication doit à présent illustrer les modifications qui ont été apportées dans la première base de données de publication et qui n'étaient pas comprises dans la sauvegarde. Cette option correspond à une valeur d' **initialize with backup** pour la propriété de l'abonnement **sync_type**.  
  
     Si une publication est activée pour une réplication d'égal à égal, la propriété de publication **allow_initialize_from_backup** est définie. La réplication commence immédiatement à suivre les modifications dans la première base de données de publication. Par conséquent, ces modifications peuvent être remises à une base de données restaurée au niveau d'un ou de plusieurs homologues si l'option **initialize with backup** est sélectionnée. Cliquez sur **Parcourir** pour rechercher la sauvegarde utilisée ; la réplication lit le numéro séquentiel dans le journal depuis la sauvegarde. Toutes les modifications dans la première base de données de publication, avec un numéro de séquence d'enregistrement supérieur, sont transférées vers chaque homologue.  
  
     Il est possible que cette option ne soit pas disponible si vous créez ou enrichissez une topologie qui inclut [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] Le tableau suivant indique si l'option est disponible lorsque vous ajoutez un nœud à une topologie existante.  
  
    |Nouveau nœud|Premier nœud|Nœuds supplémentaires|Option|  
    |--------------|----------------|----------------------|------------|  
    |[!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]|[!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]|[!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]|Désactivé|  
    |[!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]|[!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]|None|Désactivé|  
    |[!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]|[!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]|[!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]|Désactivé|  
    |[!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]|[!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]|None|activé|  
    |[!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]|[!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]|None|activé|  
    |[!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]|[!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]|[!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]|activé|  
    |[!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]|[!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]|None|activé|  
  
## <a name="see-also"></a>Voir aussi  
 [Administrer une topologie d’égal à égal &#40;programmation Transact-SQL de la réplication&#41;](../../relational-databases/replication/administration/administer-a-peer-to-peer-topology-replication-transact-sql-programming.md)   
 [Peer-to-Peer Transactional Replication](../../relational-databases/replication/transactional/peer-to-peer-transactional-replication.md)  
  
  
