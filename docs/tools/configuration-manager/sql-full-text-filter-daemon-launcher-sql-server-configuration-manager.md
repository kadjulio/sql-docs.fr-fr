---
title: Lanceur de démon de filtre de texte intégral SQL (Gestionnaire de configuration SQL Server)
description: En savoir plus sur le Lanceur de démon de filtre de texte intégral SQL, un service que SQL Server utilise pour démarrer un processus requis pour la recherche en texte intégral.
ms.custom: seo-lt-2019
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: sql-tools
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
ms.assetid: d0dc03db-5f76-4558-b041-1ac7b9b5bb16
author: markingmyname
ms.author: maghan
monikerRange: '>=sql-server-2016'
ms.openlocfilehash: daa9105d52212a0f03ca05879885b712e34c56d0
ms.sourcegitcommit: 1a544cf4dd2720b124c3697d1e62ae7741db757c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/14/2020
ms.locfileid: "97481580"
---
# <a name="sql-full-text-filter-daemon-launcher-sql-server-configuration-manager"></a>Lanceur de démon de filtre de texte intégral SQL (Gestionnaire de configuration SQL Server)
[!INCLUDE [SQL Server Windows Only - ASDBMI ](../../includes/applies-to-version/sql-windows-only-asdbmi.md)]
  À compter de [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], le service du lanceur de démon de filtre de texte intégral SQL (lanceur FDHOST) est utilisé par la recherche en texte intégral dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour démarrer le processus hôte de démon de filtre, qui gère l'analyse lexicale et le filtrage de recherche en texte intégral. Ce service doit être en cours d'exécution pour que la recherche en texte intégral puisse être utilisée. Le service du lanceur FDHOST est un service dépendant d’une instance qui est associé à une instance spécifique de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Le service du lanceur FDHOST propage les informations sur le compte de service à chaque processus hôte de démon de filtre démarré. Pour plus d'informations sur les processus hôte de démon de filtre, consultez « Architecture de la recherche en texte intégral » dans la documentation en ligne de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .  
  
  
