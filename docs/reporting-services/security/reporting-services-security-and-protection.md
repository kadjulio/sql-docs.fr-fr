---
description: Sécurité et protection de Reporting Services
title: Sécurité et protection de Reporting Services | Microsoft Docs
ms.date: 08/26/2016
ms.prod: reporting-services
ms.prod_service: reporting-services-native
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- security [Reporting Services]
- Reporting Services, security
ms.assetid: 270075c5-bf12-4467-a775-abbda3d954a5
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: e81ddb5a5255f8f7f03491709ae77da47a398de9
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/17/2020
ms.locfileid: "88480702"
---
# <a name="reporting-services-security-and-protection"></a>Sécurité et protection de Reporting Services
  Utilisez les informations de cette section pour en savoir plus sur les fonctionnalités de sécurité de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]. Cette section décrit également les modèles d’autorisation et les fournisseurs d’authentification pris en charge dans [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].  
  
## <a name="extended-protection-for-authentication"></a>Protection étendue de l'authentification  
 À compter de [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], la prise en charge de la protection étendue de l'authentification est disponible. La fonctionnalité [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] prend en charge l'utilisation de la liaison de canal et la liaison de service pour améliorer la protection de l'authentification. Les fonctionnalités [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] doivent être utilisées avec un système d'exploitation qui prend en charge la protection étendue. Pour plus d’informations, consultez [Extended Protection for Authentication with Reporting Services](../../reporting-services/security/extended-protection-for-authentication-with-reporting-services.md).  
  
## <a name="authentication-and-authorization"></a>Authentification et autorisation  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] fournit différents types d’authentification pour que les utilisateurs et les applications clientes puissent être authentifiés par le serveur de rapports. L'utilisation du bon type d'authentification pour votre serveur de rapports permet à votre organisation d'obtenir le niveau de sécurité approprié requis par votre organisation. Pour plus d’informations, consultez [Authentification avec le serveur de rapports](../../reporting-services/security/authentication-with-the-report-server.md).  
  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] utilise également les rôles et les autorisations pour contrôler l’accès au contenu dans le catalogue du serveur de rapports (en d’autres termes, qui peut accéder à quoi, et comment y accéder). Pour plus d’informations, consultez [Rôles et autorisations &#40;Reporting Services&#41;](../../reporting-services/security/roles-and-permissions-reporting-services.md).  
  
## <a name="related-tasks"></a>Tâches associées  
  
|Descriptions de tâche|Liens|  
|-----------------------|-----------|  
|Configurez le protocole TLS (Transport Layer Security), anciennement SSL (Secure Sockets Layer), pour sécuriser les connexions au serveur de rapports.|[Configurer des connexions TLS sur un serveur de rapports en mode natif](../../reporting-services/security/configure-ssl-connections-on-a-native-mode-report-server.md)|  
  
  
