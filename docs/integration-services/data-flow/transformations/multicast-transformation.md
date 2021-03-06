---
description: transformation de multidiffusion
title: Multidiffusion, transformation | Microsoft Docs
ms.custom: ''
ms.date: 03/01/2017
ms.prod: sql
ms.prod_service: integration-services
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql13.dts.designer.multicasttrans.f1
- sql13.dts.designer.multicasttransformation.f1
helpviewer_keywords:
- multiple outputs
- Multicast transformation
- datasets [Integration Services], multiple outputs
- multiple transformations
ms.assetid: 32194784-1684-40cd-9f91-1aba4d8360d3
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 92dd1a4351c9cfdc1bedb0958e370e382b08ecc0
ms.sourcegitcommit: c5078791a07330a87a92abb19b791e950672e198
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "92197066"
---
# <a name="multicast-transformation"></a>transformation de multidiffusion

[!INCLUDE[sqlserver-ssis](../../../includes/applies-to-version/sqlserver-ssis.md)]


  La transformation de multidiffusion distribue son entrée vers une ou plusieurs sorties. Cette transformation est similaire à la transformation de fractionnement conditionnel. Les deux transformations dirigent une entrée vers plusieurs sorties. Leur différence réside dans le fait que la transformation de multidiffusion dirige chaque ligne vers chaque sortie, tandis que la transformation de fractionnement conditionnel dirige une ligne vers une seule sortie. Pour plus d'informations, consultez [Conditional Split Transformation](../../../integration-services/data-flow/transformations/conditional-split-transformation.md).  
  
 Vous configurez la transformation de multidiffusion en ajoutant des sorties.  
  
 À l'aide de la transformation de multidiffusion, un package peut créer des copies logiques des données. Cette fonctionnalité est utile lorsque le package doit appliquer plusieurs ensembles de transformations aux mêmes données. Par exemple, une copie des données est agrégée et seules les informations de résumé sont chargées à leur emplacement de destination, tandis qu'une autre copie des données est enrichie de valeurs recherchées et de colonnes dérivées avant d'être chargée à son emplacement de destination.  
  
 Cette transformation a une entrée et plusieurs sorties. Elle ne prend pas en charge de sortie d'erreur.  
  
## <a name="configuration-of-the-multicast-transformation"></a>Configuration de la transformation de multidiffusion  
 Vous pouvez définir les propriétés par le biais du concepteur [!INCLUDE[ssIS](../../../includes/ssis-md.md)] ou par programmation.  
  
 Pour plus d’informations sur les propriétés que vous pouvez définir par programmation, consultez [Propriétés communes](../set-the-properties-of-a-data-flow-component.md).  
  
## <a name="related-tasks"></a>Tâches associées  
 Pour plus d’informations sur la définition des propriétés de ce composant, consultez [Définir les propriétés d’un composant de flux de données](../../../integration-services/data-flow/set-the-properties-of-a-data-flow-component.md).  
  
## <a name="multicast-transformation-editor"></a>Éditeur de transformation de multidiffusion
  Utilisez la boîte de dialogue **Éditeur de transformation de multidiffusion** pour afficher et définir les propriétés de la transformation propre à chaque sortie.  
  
### <a name="options"></a>Options  
 **Sorties**  
 Permet de sélectionner une sortie à gauche pour en voir les propriétés dans le tableau de droite.  
  
 **Propriétés**  
 Toutes les propriétés de sortie répertoriées sont en lecture seule à l’exception des propriétés **Nom** et **Description**.  
  
## <a name="see-also"></a>Voir aussi  
 [Flux de données](../../../integration-services/data-flow/data-flow.md)   
 [Transformations Integration Services](../../../integration-services/data-flow/transformations/integration-services-transformations.md)  
  
