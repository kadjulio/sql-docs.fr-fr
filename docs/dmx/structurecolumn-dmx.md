---
description: StructureColumn (DMX)
title: StructureColumn (DMX) | Microsoft Docs
ms.date: 06/07/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: dmx
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
ms.openlocfilehash: 43e02efd8594497ad4f3c02679a475531489141c
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/17/2020
ms.locfileid: "88500765"
---
# <a name="structurecolumn-dmx"></a>StructureColumn (DMX)
[!INCLUDE[ssas](../includes/applies-to-version/ssas.md)]

  Retourne la valeur de la colonne de structure qui correspond au cas spécifié, ou la valeur de table pour une table imbriquée dans le cas spécifié.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
StructureColumn('structure column name')  
```  
  
## <a name="arguments"></a>Arguments  
 structure-colonne-nom.  
 Nom d'une colonne de structure d'exploration de données de table imbriquée ou de cas.  
  
## <a name="result-type"></a>Type de résultat  
 Le type retourné dépend du type de la colonne référencée dans le \<structure column name> paramètre. Par exemple, si la colonne de structure d'exploration de données référencée contient une valeur scalaire, la fonction renvoie une valeur scalaire.  
  
 Si la colonne de structure d'exploration de données référencée est une table imbriquée, la fonction renvoie une valeur de table. La valeur de table retournée peut être utilisée dans la clause FROM d'une instruction sub-SELECT.  
  
## <a name="remarks"></a>Notes  
 Cette fonction est polymorphe et peut être utilisée n'importe où dans une instruction qui autorise des expressions, y compris une liste d'expressions SELECT, une expression de condition WHERE et une expression ORDER BY.  
  
 Le nom de la colonne dans la structure d’exploration de données est une valeur de chaîne et, par conséquent, doit être placé entre guillemets simples : par exemple, `StructureColumn('` **colonne 1** `')` . S'il y a plusieurs colonnes qui ont le même nom, le nom est résolu dans le contexte de l'instruction SELECT englobante.  
  
 Les résultats retournés à partir d’une requête à l’aide de la fonction **StructureColumn** sont affectés par la présence de filtres sur le modèle. Autrement dit, le filtre de modèle contrôle les cas inclus dans le modèle d'exploration de données. Par conséquent, une requête sur la colonne de structure retourne uniquement les cas qui sont utilisés dans le modèle d'exploration de données. Consultez la section Exemples de cette rubrique pour un exemple de code qui affiche l'effet des filtres de modèle d'exploration de données sur les tables de cas et une table imbriquée.  
  
 Pour plus d’informations sur l’utilisation de cette fonction dans une instruction DMX SELECT, consultez [SELECT FROM &#60;model&#62;. Les cas &#40;&#41;DMX ](../dmx/select-from-model-cases-dmx.md) ou [SELECT dans &#60;&#62; de structure. CAS](../dmx/select-from-structure-cases.md).  
  
## <a name="error-messages"></a>Messages d'erreur  
 L'erreur de sécurité suivante est déclenchée si l'utilisateur ne dispose pas d'autorisations d'extraction sur la structure d'exploration de données parent :  
  
 L’utilisateur'% {User/} 'n’a pas l’autorisation d’extraire la structure d’exploration de données parente du modèle d’exploration de données'% {model/} '.  
  
 Le message d'erreur suivant est généré si un nom de colonne de structure non valide est spécifié :  
  
 La colonne de structure d’exploration de données'% {Column-Name/} 'est introuvable dans la structure d’exploration de données parente'% {structure/} 'dans le contexte actuel (ligne% {Line/}, colonne% {column/}).  
  
## <a name="examples"></a>Exemples  
 Nous utiliserons la structure d'exploration de données suivante pour ces exemples. Notez que la structure d'exploration de données contient deux colonnes de table imbriquée, `Products` et `Hobbies`. La table imbriquée dans la colonne `Hobbies` à une colonne unique utilisée comme clé pour la table imbriquée. La table imbriquée dans la colonne `Products` est une table imbriquée complexe qui possède à la fois une colonne clé et d'autres colonnes utilisées pour l'entrée. Les exemples suivants illustrent comment une structure d'exploration de données peut être conçue pour inclure plusieurs colonnes différentes, même si un modèle peut ne pas utiliser chaque colonne. Certaines de ces colonnes peuvent ne pas être utiles au niveau du modèle pour généraliser des modèles, mais peuvent être très utiles pour l'extraction.  
  
```  
CREATE MINING STRUCTURE [MyStructure]   
(  
CustomerName TEXT KEY,  
Occupation TEXT DISCRETE,  
Age LONG CONTINUOUS,  
MaritalStatus TEXT DISCRETE,  
Income LONG CONTINUOUS,  
Products  TABLE  
 (  
    ProductNameTEXT KEY,  
    Quantity LONG CONTINUOUS,  
    OnSale BOOLEAN  DISCRETE  
)  
 Hobbies  TABLE  
 (  
    Hobby KEY  
 ))  
```  
  
 Vous allez créer ensuite un modèle d'exploration de données basé sur la structure que vous venez de créer, à l'aide de l'exemple de code suivant :  
  
```  
ALTER MINING STRUCTURE [MyStructure] ADD MINING MODEL [MyModel] (  
CustomerName,  
Age,  
MaritalStatus,  
Income PREDICT,  
Products   
(  
ProductName  
) WITH FILTER(NOT OnSale)  
) USING Microsoft_Decision_Trees   
WITH FILTER(EXISTS (Products))  
```  
  
### <a name="sample-query-1-returning-a-column-from-the-mining-structure"></a>Exemple de requête 1 : retourner une colonne de la structure d'exploration de données  
 L'exemple de requête suivant retourne les colonnes `CustomerName` et `Age`, définies comme faisant une partie intégrante du modèle d'exploration de données. Cependant, la requête retourne également la colonne `Age` qui appartient à la structure mais pas au modèle d'exploration de données.  
  
```  
SELECT CustomerName, Age, StructureColumn('Occupation') FROM MyModel.CASES   
WHERE Age > 30  
```  
  
 Notez que le filtrage de lignes pour restreindre les cas aux clients âgés de plus 30 ans a lieu au niveau du modèle. Par conséquent, cette expression ne retournerait pas les cas qui sont inclus dans les données de structure mais ne sont pas utilisés par le modèle. Comme la condition de filtre utilisée pour créer le modèle (`EXISTS (Products)`) restreint les cas uniquement aux clients qui ont acheté des produits, il peut y avoir des cas dans la structure qui ne sont pas retournés par cette requête.  
  
### <a name="sample-query-2-applying-a-filter-to-the-structure-column"></a>Exemple de requête 2 : application d'un filtre à la colonne de structure  
 L'exemple de requête suivant ne retourne pas que les colonnes du modèle `CustomerName` et `Age`, et le table imbriquée `Products`, mais il retourne aussi la valeur de la colonne `Quantity` dans la table imbriquée qui ne fait pas partie du modèle.  
  
```  
SELECT CustomerName, Age,  
(SELECT ProductName, StructureColumn('Quantity') FROM Products) FROM MA.CASES   
WHERE StructureColumn('Occupation') = 'Architect'  
```  
  
 Notez que, dans cet exemple, un filtre est appliqué à la colonne de structure pour limiter les cas aux clients dont l’occupation est « architecte » ( `WHERE StructureColumn('Occupation') = 'Architect'` ). Étant donné que la condition de filtre de modèle est toujours appliquée aux cas lorsque le modèle est créé, seuls les cas qui contiennent au moins une ligne éligible dans la table `Products` sont inclus dans les cas de modèles. Par conséquent, le filtre de la table imbriquée `Products` et le filtre sur le cas `('Occupation')` sont appliqués.  
  
### <a name="sample-query-3-selecting-columns-from-a-nested-table"></a>Exemple de requête 3 : sélection de colonnes dans une table imbriquée  
 L'exemple de requête ci-dessous retourne les noms des clients qui ont été utilisés comme cas d'apprentissage à partir du modèle. Pour chaque client, la requête retourne également une table imbriquée qui contient les détails d'achat. Bien que le modèle comprenne la `ProductName` colonne, le modèle n’utilise pas la valeur de la `ProductName` colonne. Le modèle vérifie uniquement si le produit a été acheté au tarif normal ( `NOT``OnSale` ). Cette requête retourne non seulement le nom du produit mais aussi la quantité achetée, qui n'est pas incluse dans le modèle.  
  
```  
SELECT CustomerName,    
(SELECT ProductName, StructureColumn('Quantity')FROM Products)   
FROM MyModel.CASES  
```  
  
 Notez que vous ne pouvez pas retourner la colonne `ProductName` ou la colonne `Quantity` sauf si l'extraction est activée sur le modèle d'exploration de données.  
  
### <a name="sample-query-4-filtering-on-and-returning-nested-table-columns"></a>Exemple de requête 4 : filtrer sur et retourner les colonnes dans une table imbriquée  
 L'exemple de requête suivant retourne les colonnes de cas et de table imbriquée inclus dans la structure d'exploration de données mais pas dans le modèle. Le modèle a déjà fait l'objet d'un filtre sur la présence de produits `OnSale`, mais cette requête ajoute un filtre sur la colonne de structure d'exploration de données, `Quantity` :  
  
```  
SELECT CustomerName, Age, StructureColumn('Occupation'),   
(SELECT ProductName, StructureColumn('Quantity') FROM Products)   
FROM MyModel.CASES   
WHERE EXISTS (SELECT * FROM Products WHERE StructureColumn('Quantity')>1)  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Informations de référence sur les fonctions DMX&#41; Data Mining Extensions &#40;](../dmx/data-mining-extensions-dmx-function-reference.md)   
 [Fonctions &#40;&#41;DMX ](../dmx/functions-dmx.md)   
 [Fonctions de prédiction générales &#40;&#41;DMX ](../dmx/general-prediction-functions-dmx.md)  
  
  
