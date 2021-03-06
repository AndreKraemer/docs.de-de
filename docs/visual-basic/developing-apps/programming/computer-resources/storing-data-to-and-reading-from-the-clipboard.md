---
title: Speichern von Daten in der Zwischenablage und Lesen von Daten aus der Zwischenablage (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Clipboard, storing data to (My.Computer.Clipboard)
- Clipboard, reading from (My.Computer.Clipboard)
- Clipboard
- My.Computer.Clipboard object, tasks
- data [Visual Basic], Clipboard
- reading data, from Clipboard
ms.assetid: f690119a-4378-4f7d-b20e-d9377ef49496
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e7bb4ad56f0a039aa7b23d7f0612aaab9366cb9e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="storing-data-to-and-reading-from-the-clipboard-visual-basic"></a>Speichern von Daten in der Zwischenablage und Lesen von Daten aus der Zwischenablage (Visual Basic)
Die Zwischenablage kann zum Speichern von Daten, z.B. Texten und Bildern, verwendet werden. Da die Zwischenablage von allen aktiven Prozessen genutzt wird, kann sie zur Übertragung von Daten zwischen den Prozessen verwendet werden. Mit dem Objekt `My.Computer.Clipboard` können Sie einfach auf die Zwischenablage zugreifen, aus ihr lesen sowie in sie schreiben.  
  
## <a name="reading-from-the-clipboard"></a>Lesen aus der Zwischenablage  
 Verwenden Sie die <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.GetText%2A>-Methode, um den Text in der Zwischenablage auszulesen. Der folgende Code liest den Text aus und zeigt ihn in einem Nachrichtenfeld an. Es muss Text in der Zwischenablage gespeichert sein, damit das Beispiel richtig ausgeführt wird.  
  
 [!code-vb[VbVbcnMyClipboard#4](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/storing-data-to-and-reading-from-the-clipboard_1.vb)]  
  
 Dieses Codebeispiel ist auch als IntelliSense-Codeausschnitt verfügbar. Er befindet sich in der Codeausschnittauswahl unter **Windows Forms-Anwendungen > Zwischenablage**. Weitere Informationen finden Sie unter [Codeausschnitte](/visualstudio/ide/code-snippets).  
  
 Verwenden Sie die <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.GetImage%2A>-Methode zum Abrufen eines Bilds aus der Zwischenablage. In diesem Beispiel wird überprüft, ob ein Bild in der Zwischenablage ist, bevor es abgerufen und `PictureBox1` zugewiesen wird.  
  
 [!code-vb[VbResourceTasks#16](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/storing-data-to-and-reading-from-the-clipboard_2.vb)]  
  
 Dieses Codebeispiel ist auch als IntelliSense-Codeausschnitt verfügbar. Es befindet sich in der Codeausschnittauswahl unter **Windows Forms-Anwendungen > Zwischenablage**. Weitere Informationen finden Sie unter [Codeausschnitte](/visualstudio/ide/code-snippets).  
  
 Elemente, die in die Zwischenablage gelegt wurden, bleiben dort, auch nachdem die Anwendung heruntergefahren wurde.  
  
## <a name="determining-the-type-of-file-stored-in-the-clipboard"></a>Bestimmen des Dateityps, der in der Zwischenablage gespeichert ist  
 Daten in der Zwischenablage können eine Anzahl von verschiedenen Formen annehmen, z.B. eine Audiodatei oder ein Bild. Um zu ermitteln, welche Art von Datei sich in der Zwischenablage befindet, können Sie Methoden wie z.B. <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsAudio%2A>, <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsFileDropList%2A>, <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsImage%2A> und <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsText%2A> verwenden. Die <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsData%2A>-Methode kann verwendet werden, wenn Sie ein benutzerdefiniertes Format überprüfen möchten.  
  
 Verwenden Sie die `ContainsImage`-Funktion, um zu bestimmen, ob die Daten in der Zwischenablage ein Bild sind. Der folgende Code überprüft, ob die Daten ein Bild sind und erstattet dementsprechend Bericht.  
  
 [!code-vb[VbResourceTasks#13](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/storing-data-to-and-reading-from-the-clipboard_3.vb)]  
  
## <a name="clearing-the-clipboard"></a>Löschen der Zwischenablage  
 Die <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.Clear%2A>-Methode löscht den Inhalt der Zwischenablage. Da die Zwischenablage von anderen Prozessen gleichzeitig verwendet wird, kann sich das Löschen auf diese Prozesse auswirken.  
  
 Im folgenden Code wird die Verwendung der `Clear`-Methode veranschaulicht.  
  
 [!code-vb[VbVbcnMyClipboard#3](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/storing-data-to-and-reading-from-the-clipboard_4.vb)]  
  
## <a name="writing-to-the-clipboard"></a>In die Zwischenablage schreiben  
 Verwenden Sie die <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.SetText%2A>-Methode, um Text in die Zwischenablage zu schreiben. Der folgende Code schreibt die Zeichenfolge „Das ist eine Testzeichenfolge“ in die Zwischenablage.  
  
 [!code-vb[VbVbcnMyClipboard#1](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/storing-data-to-and-reading-from-the-clipboard_5.vb)]  
  
 Die `SetText`-Methode kann einen Formatparameter akzeptieren, der einen Typ von <xref:System.Windows.Forms.TextDataFormat> enthält. Der folgende Code schreibt die Zeichenfolge „Das ist eine Testzeichenfolge“ als RTF-Text in die Zwischenablage.  
  
 [!code-vb[VbVbcnMyClipboard#2](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/storing-data-to-and-reading-from-the-clipboard_6.vb)]  
  
 Verwenden Sie die <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.SetData%2A>-Methode, um Daten in die Zwischenablage zu schreiben. In diesem Beispiel wird das `DataObject``dataChunk` im benutzerdefiniertem Format `specialFormat` in die Zwischenablage geschrieben.  
  
 [!code-vb[VbVbcnMyClipboard#7](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/storing-data-to-and-reading-from-the-clipboard_7.vb)]  
  
 Verwenden Sie die <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.SetAudio%2A>-Methode, um Audiodaten in die Zwischenablage zu schreiben. In diesem Beispiel wird das Bytearray `musicReader` erstellt, die Datei `cool.wav` darin gelesen und anschließend in die Zwischenablage geschrieben.  
  
 [!code-vb[VbResourceTasks#5](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/storing-data-to-and-reading-from-the-clipboard_8.vb)]  
  
> [!IMPORTANT]
>  Da auf die Zwischenablage von anderen Benutzern zugegriffen werden kann, verwenden Sie sie nicht, um sensible Informationen wie Passwörter oder vertrauliche Daten zu speichern.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy>  
 <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.GetAudioStream%2A>  
 <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.SetDataObject%2A>  
 [Gewusst wie: Lesen von Objektdaten aus einer XML-Datei](../../../programming-guide/concepts/serialization/how-to-read-object-data-from-an-xml-file.md)  
 [Gewusst wie: Schreiben von Objektdaten in eine XML-Datei](../../../programming-guide/concepts/serialization/how-to-write-object-data-to-an-xml-file.md)
