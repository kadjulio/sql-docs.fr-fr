---
title: Protection de votre propriété intellectuelle SQL Server | Microsoft Docs
description: Découvrez les options de protection de la propriété intellectuelle dans une application de données SQL Server qui est distribuée aux clients.
ms.custom: ''
ms.date: 01/31/2017
ms.prod: sql
ms.prod_service: security
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- protecting intellectual property
- intellectual property
ms.assetid: 174a646a-d65c-4074-8249-d783e91be2dd
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 4619b4bd72258e67388ee7498eff63b28a1f3b03
ms.sourcegitcommit: 4d370399f6f142e25075b3714e5c2ce056b1bfd0
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/09/2020
ms.locfileid: "91869015"
---
# <a name="protecting-your-sql-server-intellectual-property"></a>Protection de votre propriété intellectuelle SQL Server
 [!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

Les développeurs demandent souvent comment distribuer leur application de données [!INCLUDE[ssNoVersion_md](../../includes/ssnoversion-md.md)] aux clients tout en empêchant ceux-ci d’analyser et de déconstruire leur application. La protection de votre propriété intellectuelle est un aspect juridique, et cette protection doit être stipulée dans votre contrat de licence. Quand [!INCLUDE[ssNoVersion_md](../../includes/ssnoversion-md.md)] est installé sur un ordinateur administré par d’autres personnes, vous perdez, par nature, certains aspects du contrôle. 

## <a name="nature-of-the-problem"></a>Nature du problème
L’administrateur/propriétaire d’un ordinateur peut toujours accéder à l’instance de [!INCLUDE[ssNoVersion_md](../../includes/ssnoversion-md.md)] qui est installée sur cet ordinateur. Si vous déployez votre application sur l’ordinateur d’un client, dans la mesure où celui-ci est administrateur, il peut se connecter à [!INCLUDE[ssNoVersion_md](../../includes/ssnoversion-md.md)] en tant que membre du rôle serveur fixe **sysadmin**. Cela inclut la possibilité d’accorder des autorisations, de gérer les sauvegardes (notamment de restaurer des sauvegardes sur d’autres ordinateurs), de déchiffrer et de déplacer des fichiers de données, etc. Pour plus d’informations, consultez [Se connecter à SQL Server lorsque les administrateurs système n’y ont plus accès](../../database-engine/configure-windows/connect-to-sql-server-when-system-administrators-are-locked-out.md). 

Les procédures stockées et les données peuvent être chiffrées, mais la structure de données ne peut pas être masquée, et les utilisateurs qui peuvent attacher un débogueur au processus serveur peuvent récupérer les procédures déchiffrées et les données en mémoire au moment de l’exécution.

Si les clients ne sont pas des administrateurs sur les ordinateurs, vous pouvez empêcher l’accès par les clients. Vous pouvez utiliser [Transparent Data Encryption](../../relational-databases/security/encryption/transparent-data-encryption.md) pour chiffrer les fichiers de données, vous pouvez chiffrer les sauvegardes et vous pouvez auditer les actions de tous les utilisateurs. Mais les administrateurs de [!INCLUDE[ssNoVersion_md](../../includes/ssnoversion-md.md)] et les administrateurs de l’ordinateur [!INCLUDE[ssNoVersion_md](../../includes/ssnoversion-md.md)] peuvent annuler ces opérations.

## <a name="solution"></a>Solution
Il existe différentes manières de configurer l’accès aux données par les clients sans installer [!INCLUDE[ssNoVersion_md](../../includes/ssnoversion-md.md)] sur vos ordinateurs clients. Le plus simple consiste probablement à utiliser [!INCLUDE[ssSDSfull_md](../../includes/sssdsfull-md.md)] pour faire en sorte que les clients ne soient pas administrateurs, par exemple en association avec [Always Encrypted](../../relational-databases/security/encryption/always-encrypted-database-engine.md). Pour plus d’informations sur la prise en main de [!INCLUDE[ssSDS_md](../../includes/sssds-md.md)], consultez [Définition de la base de données SQL Présentation de SQL Database](/azure/sql-database/sql-database-technical-overview).  

Vous pouvez également héberger un ordinateur [!INCLUDE[ssNoVersion_md](../../includes/ssnoversion-md.md)] sur votre propre réseau, et autoriser les clients à accéder aux données par l’intermédiaire de votre réseau, soit directement, soit via une application web.

## <a name="see-also"></a>Voir aussi

[Centre de sécurité pour le moteur de base de données SQL Server et Azure SQL Database](../../relational-databases/security/security-center-for-sql-server-database-engine-and-azure-sql-database.md)  
[Sécurisation de SQL Server](../../relational-databases/security/securing-sql-server.md)