---
title: /libpath
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- libpath compiler option [Visual Basic]
- /libpath compiler option [Visual Basic]
- -libpath compiler option [Visual Basic]
ms.assetid: 5f1c26c9-3455-4e89-bdf3-b12d6c2e655b
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4f8a87ea3f3e551dfc84212e92f1409ef61bcba2
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="libpath"></a>/libpath
Gibt den Speicherort der Assemblys verwiesen wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
/libpath:dirList  
```  
  
## <a name="arguments"></a>Argumente  
  
|Begriff|Definition|  
|---|---|  
|`dirList`|Erforderlich. Durch Semikolons getrennte Liste von Verzeichnissen für den Compiler an, sucht, wenn einer referenzierten Assembly nicht gefunden wird entweder in das aktuelle Arbeitsverzeichnis (das Verzeichnis, aus dem Sie den Compiler aufrufen) oder die common Language Runtime-Systemverzeichnis. Wenn Sie den Namen des Verzeichnisses ein Leerzeichen enthält, schließen Sie den Namen in Anführungszeichen ("").|  
  
## <a name="remarks"></a>Hinweise  
 Die `/libpath` Option gibt den Speicherort der Assemblys, auf die verwiesen wird durch die [/reference](../../../visual-basic/reference/command-line-compiler/reference.md) Option.  
  
 Der Compiler sucht in folgender Reihenfolge nach Assemblyverweisen, die nicht voll qualifiziert sind:  
  
1.  Aktuelles Arbeitsverzeichnis Dies ist das Arbeitsverzeichnis, aus dem der Compiler abgerufen wird.  
  
2.  Das Verzeichnis des CLR-Systems (Common Language Runtime)  
  
3.  Vom angegebenen Verzeichnissen `/libpath`.  
  
4.  Von den LIB-Umgebungsvariablen angegebene Verzeichnisse  
  
 Die `/libpath` -Option ist kumulativ; Angabe es mehr als einmal an die vorherigen Werte angefügt.  
  
 Verwendung `/reference` einen Assemblyverweis an.  
  
|Zum Festlegen von/LIBPATH in Visual Studio integrierte Entwicklungsumgebung|  
|---|  
|1.  Ein Projekt auswählen in **Projektmappen-Explorer**. Klicken Sie im Menü **Projekt** auf **Eigenschaften**. <br />2.  Klicken Sie auf die Registerkarte **Verweise**.<br />3.  Klicken Sie auf die **Verweispfade...**  Schaltfläche.<br />4.  In der **Verweispfade** Dialogfeld Geben Sie den Namen des Verzeichnisses, in dem **Ordner:** Feld.<br />5.  Klicken Sie auf **Ordner hinzufügen**.|  
  
## <a name="example"></a>Beispiel  
 Der folgende code kompiliert `T2.vb` eine .exe-Datei zu erstellen. Der Compiler sucht Assemblyverweise in das Arbeitsverzeichnis, im Stammverzeichnis des Laufwerks "c:" und im neuen Assemblys Verzeichnis des Laufwerks "c:".  
  
```  
vbc /libpath:c:\;"c:\New Assemblies" /reference:t2.dll t2.vb  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Assemblys und der globale Assemblycache](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)  
 [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
