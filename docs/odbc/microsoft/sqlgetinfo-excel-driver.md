---
description: SQLGetInfo (pilote Excel)
title: SQLGetInfo (pilote Excel) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- Excel driver [ODBC], SQLGetInfo
- SQLGetInfo function [ODBC], Excel Driver
ms.assetid: fed4aea2-6d3d-4199-a5db-3d033eb63927
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 4d2cb149601f9c34bb7f0c35ca980a847b7948f0
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/17/2020
ms.locfileid: "88421753"
---
# <a name="sqlgetinfo-excel-driver"></a>SQLGetInfo (pilote Excel)
> [!NOTE]  
>  Cette rubrique fournit des informations spécifiques au pilote Excel. Pour obtenir des informations générales sur cette fonction, consultez la rubrique appropriée sous référence de l' [API ODBC](../../odbc/reference/syntax/odbc-api-reference.md).  
  
 **SQLGetInfo** prend en charge le type d’informations SQL_FILE_USAGE. La valeur retournée est un entier 16 bits qui indique comment le pilote traite directement les fichiers dans une source de données :  
  
-   SQL_FILE_NOT_SUPPORTED-le pilote n’est pas un pilote à un seul niveau.  
  
-   SQL_FILE_TABLE : un pilote à niveau unique traite les fichiers d’une source de données en tant que tables.  
  
-   SQL_FILE_QUALIFIER : un pilote à niveau unique traite les fichiers d’une source de données en tant que qualificateur.  
  
 Le pilote ODBC retourne SQL_FILE_TABLE pour le Exceldriver de la table, car chaque fichier est une table.  
  
## <a name="sql_dbms_ver"></a>SQL_DBMS_VER  
  
|SÉQUENTIEL|Version|Format des numéros de version|  
|----------|-------------|-------------------------------|  
|Microsoft Excel|3.0|03.00.0000|  
||4.0|04.00.0000|  
||5.0/7.0|05.00.0000|  
||97/2000|08.00.0000|  
  
## <a name="sql_file_usage"></a>SQL_FILE_USAGE  
 SQL_FILE_TABLE (Excel 3.0/4.0)  
  
 SQL_FILE_CATALOG (Excel 5.0/7.0)  
  
## <a name="sql_max_char_literal_len"></a>SQL_MAX_CHAR_LITERAL_LEN  
 255 (Excel 3.0/4.0/5.0/7.0)  
  
 65535 (Excel 97)  
  
## <a name="sql_max_column_name_len"></a>SQL_MAX_COLUMN_NAME_LEN  
 30 (Excel 3.0/4.0)  
  
 64 (Excel 5.0/7.0/97)  
  
## <a name="sql_max_table_name_len"></a>SQL_MAX_TABLE_NAME_LEN  
 12 (Excel 3.0/4.0)  
  
 31 (Excel 5.0/7.0/97)  
  
## <a name="sql_catalog_name_separator"></a>SQL_CATALOG_NAME_SEPARATOR  
 " \\ " (Excel 3.0/4.0)  
  
 "." (Excel 5.0/7.0/97)  
  
## <a name="sql_catalog_term"></a>SQL_CATALOG_TERM  
 « Répertoire » (Excel 3.0/4.0)  
  
 « Classeur » (Excel 5.0/7.0/97)  
  
## <a name="sql_catalog_usage"></a>SQL_CATALOG_USAGE  
 SQL_QU_DML_STATEMENTS &#124; SQL_QU_TABLE_DEFINITION  
  
## <a name="sql_timedate_functions"></a>SQL_TIMEDATE_FUNCTIONS  
 SQL_FN_TD_CURDATE &#124; SQL_FN_TD_CURTIME &#124; SQL_FN_TD_DAYOFMONTH &#124; SQL_FN_TD_DAYOFWEEK &#124; SQL_FN_TD_DAYOFYEAR &#124; SQL_FN_TD_HOUR &#124; SQL_FN_TD_MINUTE &#124; SQL_FN_TD_MONTH &#124; SQL_FN_TD_NOW &#124; SQL_FN_TD_SECOND &#124; SQL_FN_TD_WEEK &#124; SQL_FN_TD_YEAR
