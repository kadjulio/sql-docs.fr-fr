---
description: Méthode RemoveURL (WMI MSReportServer_ConfigurationSetting)
title: RemoveURL, méthode (WMI MSReportServer_ConfigurationSetting) | Microsoft Docs
ms.date: 03/01/2017
ms.prod: reporting-services
ms.prod_service: reporting-services-native
ms.technology: wmi-provider-library-reference
ms.topic: conceptual
helpviewer_keywords:
- RemoveURL method
ms.assetid: 3d98bd97-e152-48ce-ab1c-bd2c4f8b7fe9
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: 69112a88d00af4c82e10471addc32eff6d3e7cde
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/17/2020
ms.locfileid: "88423153"
---
# <a name="configurationsetting-method---removeurl"></a>Méthode ConfigurationSetting - RemoveURL
  Supprime une URL réservée pour le serveur de rapports. Si plusieurs URL doivent être supprimées, elles doivent l'être l'une après l'autre en appelant cette API.  
  
## <a name="syntax"></a>Syntaxe  
  
```vb  
Public Sub RemoveURL(ByVal Application As String, _  
    ByVal UrlString As String, ByVal Lcid As Int32, _  
    ByRef [Error] As String, ByRef HRESULT As Int32)  
```  
  
```csharp  
public void RemoveURL(string Application, string UrlString, int Lcid,   
    out string Error, out int HRESULT);  
```  
  
## <a name="parameters"></a>Paramètres  
 *Application*  
 Nom de l'application pour laquelle supprimer la réservation.  
  
 *URLString*  
 URL pour la réservation.  
  
 *lcid*  
 Paramètres régionaux à utiliser pour les messages d'erreur retournés.  
  
 *Error*  
 [out] Description de l'erreur qui s'est produite.  
  
 *HRESULT*  
 [out] Valeur indiquant si l'appel a réussi ou échoué.  
  
## <a name="return-value"></a>Valeur de retour  
 Retourne un paramètre *HRESULT* qui indique si l'appel de la méthode a réussi ou a échoué. La valeur 0 indique que l'appel de la méthode a abouti ; un code d'erreur indique que l'appel n'a pas abouti.  
  
## <a name="remarks"></a>Notes  
 *UrlString* n’inclut pas le nom du répertoire virtuel. La [méthode SetVirtualDirectory &#40;WMI MSReportServer_ConfigurationSetting&#41;](../../reporting-services/wmi-provider-library-reference/configurationsetting-method-setvirtualdirectory.md) est fournie à cet effet.  
  
 Avant d’appeler la méthode [ReserveURL](../../reporting-services/wmi-provider-library-reference/configurationsetting-method-reserveurl.md) , vous devez fournir une valeur pour la propriété de configuration VirtualDirectory du paramètre *Application* . Utilisez la [méthode SetVirtualDirectory &#40;WMI MSReportServer_ConfigurationSetting&#41;](../../reporting-services/wmi-provider-library-reference/configurationsetting-method-setvirtualdirectory.md) pour définir la propriété VirtualDirectory.  
  
 Si un certificat TLS/SSL a été fourni par [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] et qu'aucune autre URL n'en a besoin, il est supprimé.  
  
 Cette méthode entraîne un recyclage et un arrêt forcés de tous les domaines d'application autres que de configuration au cours de cette opération ; les domaines d'application sont redémarrés une fois cette opération terminée.  
  
## <a name="requirements"></a>Spécifications  
 **Espace de noms :** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]  
  
## <a name="see-also"></a>Voir aussi  
 [Membres MSReportServer_ConfigurationSetting](../../reporting-services/wmi-provider-library-reference/msreportserver-configurationsetting-members.md)  
  
  
