---
description: Gestionnaire de connexions d’abonnement Azure
title: Gestionnaire de connexions d’abonnement Azure | Microsoft Docs
ms.custom: ''
ms.date: 03/02/2017
ms.prod: sql
ms.prod_service: integration-services
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql13.dts.designer.afpsubscrconn.f1
- sql14.dts.designer.afpsubscrconn.f1
ms.assetid: e1225327-c308-4c50-8f44-c411f52ef378
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 277e92a906acb89960e16c941fbd71df023ddb23
ms.sourcegitcommit: 22e97435c8b692f7612c4a6d3fe9e9baeaecbb94
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92678988"
---
# <a name="azure-subscription-connection-manager"></a>Gestionnaire de connexions d’abonnement Azure

[!INCLUDE[sqlserver-ssis](../../includes/applies-to-version/sqlserver-ssis.md)]


  Le **gestionnaire de connexions d’abonnement Azure** permet à un package SSIS de se connecter à un abonnement Azure en utilisant les valeurs spécifiées pour les propriétés : ID d’abonnement Azure et certificat de gestion.  
  
 Le **gestionnaire de connexions d’abonnement Azure** est un composant de [SQL Server Integration Services (SSIS) Feature Pack pour Azure](../../integration-services/azure-feature-pack-for-integration-services-ssis.md).
  
1.  Dans la boîte de dialogue **Ajout d’un gestionnaire de connexions SSIS** ci-dessus, sélectionnez **Abonnement Azure** , puis cliquez sur **Ajouter** .  Vous devez voir s’afficher la boîte de dialogue **Éditeur du gestionnaire de connexions d’abonnement Azure** .  
  
    ![Capture d’écran montrant la boîte de dialogue Éditeur du gestionnaire de connexions d’abonnement Azure.](../../integration-services/connection-manager/media/ssis-azuresubscriptionconnectionmanager.png)
  
2.  Entrez votre ID d’abonnement Azure, qui identifie de façon unique un abonnement Azure, pour l’ **ID d’abonnement Azure** .  Cette valeur est indiquée sur le [portail de gestion Azure](https://manage.windowsazure.com) , à la page **Paramètres** :  
  
    ![Capture d’écran du portail de gestion Azure montrant l’onglet ABONNEMENTS de la page Paramètres.](../../integration-services/connection-manager/media/ssis-azuresettings-subscriptionid.png "SSIS-AzureSettings-SubscriptionID")  
  
3.  Choisissez **Emplacement du magasin de certificats de gestion** et **Nom du magasin de certificats de gestion** dans les listes déroulantes.  
  
4.  Entrez l’ **empreinte numérique du certificat de gestion** ou cliquez sur **Parcourir...** pour choisir un certificat dans le magasin sélectionné. Le certificat doit être téléchargé en tant que certificat de gestion pour l’abonnement. Pour ce faire, cliquez sur **Télécharger** dans la page suivante du portail Azure (voir cet [article MSDN](/previous-versions/azure/gg551722(v=azure.100)) pour plus de détails).  
  
     ![Capture d’écran du portail de gestion Azure montrant l’onglet CERTIFICATS DE GESTION de la page Paramètres.](../../integration-services/connection-manager/media/ssis-azuresettings-managementcertificate.png "SSIS-AzureSettings-ManagementCertificate")  
  
5.  Cliquez sur **Tester la connexion** pour tester la connexion.  
  
6.  Cliquez sur **OK** pour fermer la boîte de dialogue.  
  
