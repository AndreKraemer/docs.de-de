---
title: 'Vorgehensweise: Installieren einer Assembly in den globalen Assemblycache | Microsoft-Dokumentation'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- assemblies [.NET Framework], global assembly cache
- Gacutil.exe
- strong-named assemblies, global assembly cache
- global assembly cache, installing assemblies
- Global Assembly Cache tool
ms.assetid: a7e6f091-d02c-49ba-b736-7295cb0eb743
caps.latest.revision: 24
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 63e1c2273e85117fd5419e63e823da6d2137726a
ms.contentlocale: de-de
ms.lasthandoff: 06/02/2017

---
# <a name="how-to-install-an-assembly-into-the-global-assembly-cache"></a>Gewusst wie: Installieren einer Assembly in den globalen Assemblycache
Es gibt zwei Möglichkeiten, eine Assembly mit starkem Namen im globalen Assemblycache (GAC) zu installieren:  
  
> [!IMPORTANT]
>  Nur Assemblys mit starkem Namen können im GAC installiert werden. Informationen zum Erstellen einer Assembly mit starkem Namen finden Sie unter [How to: Sign an Assembly with a Strong Name (Vorgehensweise: Signieren einer Assembly mit einem starken Namen)](../../../docs/framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md).  
  
-   Verwenden des [Windows Installer](http://msdn.microsoft.com/library/windows/desktop/cc185688.aspx)  
  
     Hierzu erstellen Sie in Visual Studio 2012 und Visual Studio 2013 ein InstallShield Limited Edition-Projekt.  
  
     Dies ist die empfohlene und auch gebräuchlichste Art, Assemblys zum globalen Assemblycache hinzuzufügen. Der Installer bietet neben einem Verweiszähler für Assemblys im globalen Assemblycache noch weitere Vorteile.  
  
-   Verwenden des [Global Assembly Cache-Tools (Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md)  
  
     Mit Gacutil.exe können Sie Assemblys mit starkem Namen zum globalen Assemblycache hinzufügen und sich dessen Inhalt anzeigen lassen.  
  
    > [!NOTE]
    >  Gacutil.exe ist Entwicklungszwecken vorbehalten und nicht für die Installation von Produktionsassemblys im globalen Assemblycache vorgesehen.  
  
> [!NOTE]
>  In früheren Versionen von .NET Framework ermöglichte die Windows Shell-Erweiterung "Shfusion.dll" das Installieren von Assemblys durch Ziehen in Datei-Explorer. Ab [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] ist Shfusion.dll veraltet.  
  
### <a name="to-use-the-global-assembly-cache-tool-gacutilexe"></a>So verwenden Sie das Global Assembly Cache-Tool (Gacutil.exe)  
  
1.  Geben Sie an der Eingabeaufforderung folgenden Befehl ein:  
  
     **gacutil -i** \<*assemblyname*>  
  
     In diesem Befehl bezeichnet *Assemblyname* den Namen der Assembly, die im globalen Assemblycache installiert werden soll.  
  
 Im folgenden Beispiel wird eine Assembly mit dem Dateinamen `hello.dll` im globalen Assemblycache installiert.  
  
```  
gacutil -i hello.dll  
```  
  
 Weitere Informationen finden Sie unter [Global Assembly Cache-Tool (Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md).  
  
### <a name="to-use-an-installshield-limited-edition-project"></a>So verwenden Sie ein InstallShield Limited Edition-Projekt  
  
1.  Fügen Sie Ihrer Projektmappe ein Setup- und Bereitstellungspaket hinzu. Öffnen Sie hierfür das Kontextmenü Ihrer Projektmappe, und wählen Sie dann **Hinzufügen**, **Neues Projekt** aus.  
  
2.  Wählen Sie im Dialogfeld **Neues Projekt hinzufügen** im Ordner **Installiert** nacheinander **Andere Projekttypen**, **Setup und Bereitstellung** und dann **InstallShield Limited Edition** aus, und geben Sie Ihrem Projekt einen Namen. Wenn Sie dazu aufgefordert werden, laden Sie InstallShield herunter und installieren und aktivieren Sie es.  
  
3.  Sie können die allgemeine Konfiguration des Setup- und Bereitstellungsprojekts entweder mit dem Projekt-Assistent im **Projektmappen-Explorer** ausführen, oder indem Sie die Teilschritte der nummerierten Schritte im **Projektmappen-Explorer** auswählen. Konfigurieren Sie das Setup genauso, als wenn Sie keine Assemblys in den GAC hinzufügen würden.  
  
4.  Beginnen Sie, dem GAC eine Assembly hinzuzufügen, indem Sie **Dateien** (unter dem Schritt **Anwendungsdaten angeben** im **Projektmappen-Explorer**) auswählen.  
  
5.  Öffnen Sie im Bereich **Ordner des Zielcomputers** das Kontextmenü für **Zielcomputer**, und wählen Sie dann **Vordefinierten Ordner anzeigen**, **[GlobalAssemblyCache]** aus.  
  
6.  Führen Sie folgende Schritte für jedes Projekt in der Projektmappe aus, das eine Assembly enthält, die Sie im globalen Assemblycache installieren möchten:  
  
    1.  Wählen Sie im Bereich **Ordner des Quellcomputers** das Projekt aus.  
  
    2.  Wählen Sie im Bereich **Ordner des Zielcomputers** den Eintrag **[GlobalAssemblyCache]** aus.  
  
    3.  Wählen Sie im Bereich **Dateien des Quellcomputers** den Eintrag **Primäre Ausgabe von** *<projekt_name>* aus.  
  
    4.  Ziehen Sie die Datei in Schritt c in den Bereich **Dateien des Zielcomputers** (oder verwenden Sie die Befehle **Kopieren** und **Einfügen** im Kontextmenü der Datei).  
  
## <a name="see-also"></a>Siehe auch  
 [Arbeiten mit Assemblys und dem globalen Assemblychache](../../../docs/framework/app-domains/working-with-assemblies-and-the-gac.md)   
 [Vorgehensweise: Entfernen einer Assembly aus dem globalen Assemblycache](../../../docs/framework/app-domains/how-to-remove-an-assembly-from-the-gac.md)   
 [Gacutil.exe (Global Assembly Cache-Tool)](../../../docs/framework/tools/gacutil-exe-gac-tool.md)   
 [Vorgehensweise: Signieren einer Assembly mit einem starken Namen](../../../docs/framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md)   
 [Windows Installer-Bereitstellung](http://msdn.microsoft.com/en-us/121be21b-b916-43e2-8f10-8b080516d2a0)