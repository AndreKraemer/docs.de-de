---
title: Vergleich von Knoten mit XPathNavigator
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: e6848c47-ee5d-401a-89a5-50b5eed40f30
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 06849e20386f0eecb55fdf906f78896828b9946e
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="matching-nodes-using-xpathnavigator"></a>Vergleich von Knoten mit XPathNavigator
Die <xref:System.Xml.XPath.XPathNavigator>-Klasse stellt die <xref:System.Xml.XPath.XPathNavigator.Matches%2A>-Methode bereit, um zu bestimmen, ob ein Knoten einem XPath-Ausdruck entspricht. Die <xref:System.Xml.XPath.XPathNavigator.Matches%2A>-Methode verwendet einen XPath-Ausdruck als Eingabe und gibt einen <xref:System.Boolean>-Wert zurück, der angibt, ob der aktuelle Knoten dem angegebenen XPath-Ausdruck oder dem angegebenen kompilierten <xref:System.Xml.XPath.XPathExpression>-Objekt entspricht.  
  
## <a name="matching-nodes"></a>Vergleich von Knoten  
 Die <xref:System.Xml.XPath.XPathNavigator.Matches%2A>-Methode gibt `true` zurück, wenn der aktuelle Knoten dem angegebenen XPath-Ausdruck entspricht. Im folgenden Codebeispiel gibt z. B. die <xref:System.Xml.XPath.XPathNavigator.Matches%2A>-Methode `true` zurück, wenn es sich beim aktuellen Knoten um das `b`-Element handelt und das `b`-Element ein `c`-Attribut aufweist.  
  
> [!NOTE]
>  Die <xref:System.Xml.XPath.XPathNavigator.Matches%2A>-Methode ändert den Status des <xref:System.Xml.XPath.XPathNavigator> nicht.  
  
```vb  
Dim document as XPathDocument = New XPathDocument("input.xml")  
Dim navigator as XPathNavigator = document.CreateNavigator()  
  
navigator.Matches("b[@c]")  
```  
  
```csharp  
XPathDocument document = new XPathDocument("input.xml");  
XPathNavigator navigator = document.CreateNavigator();  
  
navigator.Matches("b[@c]");  
```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Xml.XmlDocument>  
 <xref:System.Xml.XPath.XPathDocument>  
 <xref:System.Xml.XPath.XPathNavigator>  
 [Verarbeiten von XML-Daten mithilfe des XPath-Datenmodells](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)  
 [Auswählen von XML-Daten mit XPathNavigator](../../../../docs/standard/data/xml/select-xml-data-using-xpathnavigator.md)  
 [Auswerten von XPath-Ausdrücken mit XPathNavigator](../../../../docs/standard/data/xml/evaluate-xpath-expressions-using-xpathnavigator.md)  
 [In XPath-Abfragen erkannte Knotentypen](../../../../docs/standard/data/xml/node-types-recognized-with-xpath-queries.md)  
 [XPath-Abfragen und Namespaces](../../../../docs/standard/data/xml/xpath-queries-and-namespaces.md)  
 [Kompilierte XPath-Ausdrücke](../../../../docs/standard/data/xml/compiled-xpath-expressions.md)
