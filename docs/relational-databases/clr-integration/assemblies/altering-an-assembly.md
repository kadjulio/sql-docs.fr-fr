---
title: Modification d’un assembly | Microsoft Docs
description: Utilisez ALTER ASSEMBLy pour mettre à jour les assemblys inscrits dans SQL Server. Vous pouvez également modifier le jeu d’autorisations et ajouter du code source ou d’autres fichiers pour un assembly.
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- assemblies [CLR integration], modifying
- permissions [CLR integration]
- altering assemblies
- ALTER ASSEMBLY statement
ms.assetid: 9e765fbd-f339-473c-8537-22f478e79696
author: rothja
ms.author: jroth
ms.openlocfilehash: b378f5a57b964521e511c99a7432017183076177
ms.sourcegitcommit: f7ac1976d4bfa224332edd9ef2f4377a4d55a2c9
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/02/2020
ms.locfileid: "85885954"
---
# <a name="altering-an-assembly"></a>Modification d'un assembly
[!INCLUDE [SQL Server](../../../includes/applies-to-version/sqlserver.md)]
  Les assemblys inscrits dans [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] peuvent être mis à jour à partir d'une version plus récente via l'instruction ALTER ASSEMBLY. Pour mettre à jour un assembly, utilisez l'instruction ALTER ASSEMBLY avec la syntaxe suivante :  
  
```  
ALTER ASSEMBLY SQLCLRTest  
FROM 'C:\MyDBApp\SQLCLRTest.dll'  
```  
  
 ALTER ASSEMBLY n'interrompt pas les processus en cours d'exécution qui utilisent l'assembly ; ces processus continuent à s'exécuter avec l'assembly non modifié. ALTER ASSEMBLY ne peut pas être utilisé pour modifier les signatures des fonctions CLR (Common Language Runtime), des fonctions d'agrégation, des procédures stockées et des déclencheurs. De nouvelles méthodes publiques peuvent être ajoutées à l'assembly, les méthodes privées peuvent être modifiées librement ; par ailleurs, les méthodes publiques peuvent être modifiées à condition que les signatures ou les attributs ne soient pas modifiés. Les champs qui se trouvent dans un type défini par l'utilisateur sérialisé de façon native (notamment les membres de données ou les classes de base) ne peuvent pas être modifiés via ALTER ASSEMBLY. Aucune autre modification n'est prise en charge. Pour plus d’informations, consultez [ALTER assembly &#40;Transact-SQL&#41;](../../../t-sql/statements/alter-assembly-transact-sql.md).  
  
## <a name="changing-the-permission-set-of-an-assembly"></a>Modification du jeu d'autorisations d'un assembly  
 Le jeu d'autorisations d'un assembly peut également être modifié à l'aide de l'instruction ALTER ASSEMBLY. L’instruction suivante modifie le jeu d’autorisations de l’assembly SQLCLRTest en **EXTERNAL_ACCESS**.  
  
```  
ALTER ASSEMBLY SQLCLRTest  
WITH PERMISSION_SET = EXTERNAL_ACCESS   
```  
  
 Si le jeu d’autorisations d’un assembly passe de **Safe** à **EXTERNAL_ACCESS** ou **unsafe**, une clé asymétrique et une connexion correspondante avec l’autorisation **External Access assembly** ou **unsafe assembly** pour l’assembly doivent d’abord être créées. Pour plus d’informations, consultez [Creating an Assembly](../../../relational-databases/clr-integration/assemblies/creating-an-assembly.md).  
  
## <a name="adding-the-source-code-of-an-assembly"></a>Ajout du code source d'un assembly  
 La clause ADD FILE de la syntaxe ALTER ASSEMBLY n'est pas présente dans CREATE ASSEMBLY. Vous pouvez l'utiliser pour ajouter le code source ou tout autre fichier associé à un assembly. Les fichiers sont copiés depuis leur emplacement d'origine et stockés dans les tables système de la base de données. Le code source et autres fichiers est toujours à portée de main dans l'éventualité où vous deviez recréer ou documenter la version actuelle de l'UDT.  
  
 L'instruction suivante ajoute le code source de la classe Point.cs pour le type défini par l'utilisateur Point. Le texte contenu dans le fichier Point.cs est alors copié et stocké dans la base de données sous le nom PointSource.  
  
 `ALTER ASSEMBLY Point`  
  
 `ADD FILE FROM 'C:\Projects\Point\Point.cs' AS PointSource`  
  
## <a name="see-also"></a>Voir aussi  
 [Gestion des assemblys d’intégration du CLR](../../../relational-databases/clr-integration/assemblies/managing-clr-integration-assemblies.md)   
 [Création d’un assembly](../../../relational-databases/clr-integration/assemblies/creating-an-assembly.md)   
 [Suppression d’un assembly](../../../relational-databases/clr-integration/assemblies/dropping-an-assembly.md)   
 [ALTER ASSEMBLY &#40;Transact-SQL&#41;](../../../t-sql/statements/alter-assembly-transact-sql.md)  
  
  
