---
title: 'Étape 1 : Configurer l’environnement pymssql'
description: L’étape 1 de ce guide de prise en main implique l’installation de Python, de Microsoft ODBC Driver for SQL Server et de pymssql dans votre environnement de développement.
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
ms.assetid: 6d392a5e-b08e-4b35-9e99-61260888fc41
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: d5eb4a746cf8847c8300091677fe4e07e8173707
ms.sourcegitcommit: 8ffc23126609b1cbe2f6820f9a823c5850205372
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/17/2020
ms.locfileid: "81634611"
---
# <a name="step-1-configure-development-environment-for-pymssql-python-development"></a>Étape 1 : Configurer l’environnement de développement pour le développement Python pymssql
Vous devrez configurer votre environnement de développement avec les conditions préalables pour développer une application à l’aide du pilote Python pour SQL Server.    
  
Les pilotes Python SQL utilisent le protocole TDS, qui est activé par défaut dans SQL Server et Azure SQL Database.  Aucune configuration supplémentaire n’est nécessaire.  
  
## <a name="windows"></a>Windows  
  
1. **Installez le runtime Python et le gestionnaire de package pip.**  
a. Accédez à [python.org](https://www.python.org/downloads/)  
b. Cliquez sur le lien msi approprié du programme d'installation Windows.   
c. Une fois le téléchargement effectué, exécutez le fichier msi pour installer le runtime Python  
  
2. **Téléchargez le module pymssql** à partir d’[ici](https://www.lfd.uci.edu/~gohlke/pythonlibs/#pymssql)  
  
    Veillez choisir le bon fichier `whl`.  Par exemple : Si vous utilisez Python 2.7 sur un ordinateur 64 bits, choisissez `pymssql‑2.1.1‑cp27‑none‑win_amd64.whl`. Une fois le fichier `whl` téléchargé, placez-le dans le dossier C:\Python27.  
      
3. **Ouvrez cmd.exe**  
  
4. **Installez le module pymssql.**  
    Par exemple, si vous utilisez Python 2.7 sur un ordinateur 64 bits :  
```  
> cd c:\Python27  
> pip install pymssql‑2.1.1‑cp27‑none‑win_amd64.whl  
```  
  
## <a name="ubuntu-linux"></a>Ubuntu Linux  
  
1. **Installez le runtime Python et le gestionnaire de package pip.**  Python est préinstallé sur la plupart des distributions d’Ubuntu.  Si Python n’est pas installé sur votre ordinateur, vous pouvez télécharger la source Tarball à partir de [python.org](https://www.python.org/downloads/) et le générer localement, ou vous pouvez utiliser le gestionnaire de package :  
```  
> sudo apt-get install python   
```  
  
2.  **Ouvrir le terminal**  
  
3.  **Installer le module pymssql et les dépendances**  
```  
> sudo apt-get --assume-yes update  
> sudo apt-get --assume-yes install freetds-dev freetds-bin  
> sudo apt-get --assume-yes install python-dev python-pip  
> sudo pip install pymssql  
```  
  
## <a name="macos"></a>macOS
  
1. **Installez le runtime Python et le gestionnaire de package pip**  
a. Accédez à [python.org](https://www.python.org/downloads/)  
b. Cliquez sur le lien pkg approprié du programme d'installation macOS.   
c. Une fois le téléchargement effectué, exécutez le fichier pkg pour installer le runtime python  
  
2.  **Ouvrez le terminal**  
  
3. **Installez le gestionnaire de package Homebrew**  
```  
> ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"  
```  
  
4.  **Installez le module FreeTDS**  
```  
> brew install FreeTDS  
```  
  
5.  **Installez le module pymssql**  
```  
> sudo -H pip install pymssql  
```
