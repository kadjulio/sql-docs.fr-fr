---
title: Présentation de la gestion des exceptions dans Reporting Services | Microsoft Docs
description: Découvrez comment gérer les exceptions levées par le service Web Report Server afin de retourner des informations utiles aux utilisateurs lorsque des erreurs se produisent.
ms.date: 03/14/2017
ms.prod: reporting-services
ms.prod_service: reporting-services-native
ms.technology: report-server-web-service-net-framework-exception-handling
ms.topic: reference
helpviewer_keywords:
- Web service [Reporting Services], exception handling
- errors [Reporting Services]
- exceptions [Reporting Services]
- Report Server Web service, exception handling
- XML Web service [Reporting Services], exception handling
ms.assetid: 54381870-ce67-482b-aa83-6a838cdbf9b9
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: edaacc97dae131afbc0a9b9f3651877e4952754d
ms.sourcegitcommit: ff82f3260ff79ed860a7a58f54ff7f0594851e6b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/29/2020
ms.locfileid: "80215721"
---
# <a name="introducing-exception-handling-in-reporting-services"></a>Présentation de la gestion des exceptions dans Reporting Services
  Si votre application [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] envoie un demande au service Web Report Server, mais que ce dernier ne parvient pas à la traiter, le service retourne une exception SOAP au client. La gestion des exceptions levées par le service Web Report Server est une composante importante des applications que vous développez car vous avez la possibilité de retourner des informations utiles aux utilisateurs lorsque des erreurs se produisent.  
  
 Cette section contient des informations sur la gestion des exceptions, la manière d'éviter les entrées utilisateur non valides et l'envoi d'informations pertinentes sur les erreurs aux utilisateurs. Pour obtenir des informations générales sur la gestion des exceptions, consultez « Gestion et levée des exceptions » dans la documentation du SDK [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)].  
  
## <a name="in-this-section"></a>Dans cette section  
  
|Rubrique|Description|  
|-----------|-----------------|  
|[Gestion des exceptions dans Reporting Services](../../reporting-services/report-server-web-service-net-framework-exception-handling/handling-exceptions-in-reporting-services.md)|Fournit une vue d'ensemble des exceptions dans [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] et le rôle de SOAP dans le renvoi d'erreurs depuis un service Web.|  
|[Meilleures pratiques pour la gestion des exceptions dans Reporting Services](../../reporting-services/report-server-web-service-net-framework-exception-handling/best-practices/best-practices-for-reporting-services-exception-handling.md)|Fournit des recommandations sur la manière de gérer les exceptions dans [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].|  
|[Classe SoapException Reporting Services](../../reporting-services/report-server-web-service-net-framework-exception-handling/soapexception-class/reporting-services-soapexception-class.md)|Décrit la classe **SoapException** dans [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].|  
  
## <a name="see-also"></a>Voir aussi  
 [Génération d’applications à l’aide du service web et de .NET Framework](../../reporting-services/report-server-web-service/net-framework/building-applications-using-the-web-service-and-the-net-framework.md)  
  
  
