---
title: Surveiller des Agents de réplication | Microsoft Docs
description: Le Moniteur de réplication SQL Server offre une vue systémique de l’activité de réplication, mais il permet aussi de trouver directement des informations sur un agent spécifique.
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- monitoring performance [SQL Server replication], agents
- Log Reader Agent, monitoring
- Replication Monitor, agents
- Merge Agent, monitoring
- Queue Reader Agent, monitoring
- Snapshot Agent, monitoring
- agents [SQL Server replication], monitoring
- Distribution Agent, monitoring
ms.assetid: d06ed24f-82d7-4b9e-9e40-cc9780476a71
author: MashaMSFT
ms.author: mathoma
monikerRange: =azuresqldb-mi-current||>=sql-server-2016
ms.openlocfilehash: ddaa4698033f06db589ca550f39d434173e012e7
ms.sourcegitcommit: 1a544cf4dd2720b124c3697d1e62ae7741db757c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/14/2020
ms.locfileid: "97477840"
---
# <a name="monitor-replication-agents"></a>Surveiller des Agents de réplication
[!INCLUDE[sql-asdbmi](../../../includes/applies-to-version/sql-asdbmi.md)]
  Le Moniteur de réplication [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] offre une vue systémique de l’activité de réplication, mais il permet aussi de trouver directement des informations sur un agent spécifique. La liste suivante comprend chacun des agents, les onglets du moniteur de réplication sur lesquels ils peuvent être trouvés et un lien vers une rubrique qui explique comment accéder à ces onglets :  
  
-   Les agents suivants sont associés à des publications dans le moniteur de réplication :  
  
    -   Agent d'instantané  
  
    -   l'Agent de lecture du journal ;  
  
    -   Agent de lecture de la file d'attente  
  
     Accédez aux informations et aux tâches associées à ces agents par le biais des onglets suivants : **Agents** (disponible pour chaque serveur de publication et publication) et **Avertissements** (disponible pour chaque publication). Pour plus d’informations, consultez [Afficher des informations et effectuer des tâches à l’aide du moniteur de réplication](../../../relational-databases/replication/monitor/view-information-and-perform-tasks-replication-monitor.md).  
  
-   Les agents suivants sont associés à des abonnements dans le moniteur de réplication :  
  
    -   Agent de distribution  
  
    -   Agent de fusion  
  
     Accédez aux informations et aux tâches associées à ces agents par le biais des onglets suivants : **Liste de suivi des abonnements** (disponible pour chaque serveur de publication) ou **Tous les abonnements** (disponible pour chaque publication). Pour plus d’informations, consultez [Afficher des informations et effectuer des tâches à l’aide du moniteur de réplication](../../../relational-databases/replication/monitor/view-information-and-perform-tasks-replication-monitor.md).  
  
## <a name="using-sql-server-management-studio-to-monitor-replication-agents"></a>Utiliser SQL Server Management Studio pour surveiller les agents de réplication  
 [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] fournit les boîtes de dialogue suivantes pour la surveillance des agents de réplication :  
  
-   **Afficher l'état de l'Agent d'instantané** (pour toutes les publications)  
  
-   **Afficher l'état de l'Agent de lecture du journal** (pour toutes les publications transactionnelles)  
  
-   **Afficher l'état de synchronisation** (pour tous les abonnements ; cette boîte de dialogue permet d'accéder à l'Agent de distribution et à l'Agent de fusion)  
  
 Le moniteur de réplication donne des informations supplémentaires sur chaque agent et permet la surveillance de l'Agent de lecture de la file d'attente, s'il est utilisé. Pour plus d’informations, consultez [Afficher des informations et effectuer des tâches à l’aide du moniteur de réplication](../../../relational-databases/replication/monitor/view-information-and-perform-tasks-replication-monitor.md).
  
#### <a name="to-monitor-the-snapshot-agent-and-log-reader-agent"></a>Pour surveiller l'Agent d'instantané et l'Agent de lecture du journal  
  
1.  Connectez-vous au serveur de publication dans [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)], puis développez le nœud du serveur.  
  
2.  Développez le dossier **Réplication** , puis développez le dossier **Publications locales** .  
  
3.  Cliquez avec le bouton droit sur une publication, puis cliquez sur **Afficher l'état de l'Agent de lecture du journal** ou sur **Afficher l'état de l'Agent d'instantané**.  
  
4.  Dans la boîte de dialogue **Afficher l'état de l'Agent de lecture du journal** ou **Afficher l'état de l'Agent d'instantané** :  
  
    -   Affichez l'état de l'agent.  
  
    -   Démarrez ou arrêtez l'agent si nécessaire.  
  
    -   Cliquez sur **Moniteur** pour lancer le **moniteur de réplication**.  
  
5.  Cliquez sur **Fermer**.  
  
#### <a name="to-monitor-the-distribution-agent-and-merge-agent-from-the-publisher"></a>Pour surveiller l'Agent de distribution et l'Agent de fusion (à partir du serveur de publication)  
  
1.  Connectez-vous au serveur de publication dans [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)], puis développez le nœud du serveur.  
  
2.  Développez le dossier **Réplication** , puis développez le dossier **Publications locales** .  
  
3.  Développez la publication pour l'abonnement que vous voulez surveiller.  
  
4.  Cliquez avec le bouton droit sur l'abonnement, puis sur **Afficher l'état de synchronisation**.  
  
5.  Dans la boîte de dialogue **Afficher l'état de synchronisation** :  
  
    -   Affichez l'état de l'agent.  
  
    -   Démarrez ou arrêtez l'agent si nécessaire.  
  
    -   Pour les abonnements par envoi de données (push), cliquez sur **Moniteur** pour lancer le **moniteur de réplication**.  
  
    -   Pour les abonnements par extraction de données (pull), cliquez sur **Afficher l'historique des travaux** pour lancer la **Visionneuse du fichier journal**, qui affiche le contenu du journal de l'agent.  
  
6.  Cliquez sur **Fermer**.  
  
#### <a name="to-monitor-the-distribution-agent-and-merge-agent-from-the-subscriber"></a>Pour surveiller l'Agent de distribution et l'Agent de fusion (à partir de l'Abonné)  
  
1.  Connectez-vous à l'Abonné dans [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)], puis développez le nœud du serveur.  
  
2.  Développez le dossier **Réplication** , puis développez le dossier **Abonnements locaux** .  
  
3.  Cliquez avec le bouton droit sur l'abonnement que vous voulez surveiller, puis sur **Afficher l'état de synchronisation**.  
  
4.  Dans la boîte de dialogue **Afficher l'état de synchronisation** :  
  
    -   Affichez l'état de l'agent.  
  
    -   Démarrez ou arrêtez l'agent si nécessaire.  
  
    -   Cliquez sur **Afficher l'historique des travaux** pour lancer la **Visionneuse du fichier journal**, qui affiche le contenu du journal de l'agent.  
  
5.  Cliquez sur **Fermer**.  
  
## <a name="see-also"></a>Voir aussi  
 [Présentation des Agents de réplication](../../../relational-databases/replication/agents/replication-agents-overview.md)  
  
  
