---
title: '[^] Caractère générique pour exclure des caractères'
description: Caractère générique T-SQL pour les caractères à exclure de la recherche de correspondance
titleSuffix: SQL Server (Transact-SQL)
ms.custom: seo-lt-2019
ms.date: 12/06/2016
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: t-sql
ms.topic: reference
f1_keywords:
- wildcard
- '[^]_TSQL'
- '[^]'
- Not Match
dev_langs:
- TSQL
helpviewer_keywords:
- wildcard characters [SQL Server]
- '[^] (wildcard - character(s) not to match)'
ms.assetid: b970038f-f4e7-4a5d-96f6-51e3248c6aef
author: cawrites
ms.author: chadam
ms.openlocfilehash: 2e8d08c6398558b96b7f3a5e162e12a9322c7cde
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/10/2021
ms.locfileid: "100062194"
---
# <a name="-wildcard---characters-not-to-match-transact-sql"></a>\[^\] (Caractère générique - Caractères à exclure) (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx_md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

  Recherche la correspondance de chaque caractère ne se trouvant pas dans la plage ou dans l’ensemble spécifié entre crochets droits `[^]`. Ces caractères génériques peuvent être utilisés dans des comparaisons de chaînes qui impliquent des critères spéciaux tels que `LIKE` et `PATINDEX`. 
  
## <a name="examples"></a>Exemples  
### <a name="a-simple-example"></a>A : Exemple simple   
 L’exemple suivant utilise l’opérateur [^] afin de retrouver les cinq premières personnes de la table `Contact` dont le prénom commence par `Al`, mais dont la troisième lettre du prénom n’est pas la lettre `a`.  
  
```sql
-- Uses AdventureWorks  
  
SELECT TOP 5 FirstName, LastName  
FROM Person.Person  
WHERE FirstName LIKE 'Al[^a]%';  
```  
[!INCLUDE[ssResult_md](../../includes/ssresult-md.md)]  

```
FirstName     LastName
---------     --------
Alex          Adams
Alexandra     Adams
Allison       Adams
Alisha        Alan
Alexandra     Alexander
```
### <a name="b-searching-for-ranges-of-characters"></a>B : Recherche de plages de caractères

Un jeu de caractères génériques peut inclure des caractères uniques ou des plages de caractères, ainsi que des combinaisons de caractères et de plages. L’exemple suivant utilise l’opérateur [^] pour rechercher une chaîne qui ne commence pas par une lettre ou un chiffre.

```sql
SELECT [object_id], OBJECT_NAME(object_id) AS [object_name], name, column_id 
FROM sys.columns 
WHERE name LIKE '[^0-9A-z]%';
```

[!INCLUDE[ssResult_md](../../includes/ssresult-md.md)]  

```
object_id     object_name   name    column_id
---------     -----------   ----    ---------
1591676718    JunkTable     _xyz    1
```
  
## <a name="see-also"></a>Voir aussi  
 [LIKE &#40;Transact-SQL&#41;](../../t-sql/language-elements/like-transact-sql.md)   
 [PATINDEX &#40;Transact-SQL&#41;](../../t-sql/functions/patindex-transact-sql.md)   
 [% &#40;Caractère générique - Caractères à rechercher &#41; &#40;Transact-SQL&#41;](../../t-sql/language-elements/percent-character-wildcard-character-s-to-match-transact-sql.md)   
  [&#91; &#93; &#40;Caractère générique - Caractères à rechercher&#41; &#40;Transact-SQL&#41;](../../t-sql/language-elements/wildcard-character-s-to-match-transact-sql.md)   
 [\_ &#40;Caractère générique - Recherche d’un seul caractère&#41; &#40;Transact-SQL&#41;](../../t-sql/language-elements/wildcard-match-one-character-transact-sql.md)  
  
  
