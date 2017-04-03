---
title: 'Vorgehensweise: Projektieren eines anonymen Typs (C#) | Microsoft-Dokumentation'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 5cb9be13-5ac4-4373-a034-b3520a5b2dec
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 99d378ef451173bbf6e6780223cea75205c7a324
ms.lasthandoff: 03/13/2017


---
# <a name="how-to-project-an-anonymous-type-c"></a>Vorgehensweise: Projektieren eines anonymen Typs (C#)
Es gibt Fälle, in denen Sie eine Abfrage in einen neuen Typ projizieren möchten, obwohl Sie wissen, dass dieser Typ nur für kurze Zeit verwendet werden wird. Das Erstellen eines neuen Typs für die Verwendung in der Projektion bedeutet viel Zusatzarbeit. Effizienter wäre es in diesem Fall, eine Projektion in einen anonymen Typ vorzunehmen. Mit anonymen Typen können Sie eine Klasse definieren und dann ein Objekt dieser Klasse deklarieren und initialisieren, ohne der Klasse dazu einen Namen geben zu müssen.  
  
 Anonyme Typen stellen die C#-Implementierung des mathematischen Konzepts eines *Tupels* dar. Der mathematische Begriff „Tupel“ bzw. „n-Tupel“ (englisch „Tuple“) leitet sich aus dem englischen Wortbestandteil „-(t)uple“ für „-fach“ (z. B. „quadruple“ für „vierfach“ und „quintuple“ für „fünffach“) ab. Er steht für eine endliche Abfolge von Objekten, die alle von einem bestimmten Typ sind. Mitunter wird dies als Liste von Name/Wert-Paaren bezeichnet. So könnte z.B. der Inhalt einer Adresse im XML-Dokument in [Beispiel-XML-Datei: Typische Bestellung (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml-1.md) wie folgt ausgedrückt werden:  
  
```  
Name: Ellen Adams  
Street: 123 Maple Street  
City: Mill Valley  
State: CA  
Zip: 90952  
Country: USA  
```  
  
 Das Erstellen einer Instanz eines anonymen Typs können Sie sich wie das Erstellen eines Tupels n-ter Ordnung vorstellen. Wenn Sie eine Abfrage schreiben, die ein Tupel in der `select`-Klausel erstellt, gibt die Abfrage eine `IEnumerable` des Tupels zurück.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel projiziert die `select`-Klausel einen anonymen Typ. Das Beispiel verwendet dann `var`, um das `IEnumerable`-Objekt zu erstellen. Innerhalb der `foreach`-Schleife wird die Iterationsvariable zu einer Instanz des im Abfrageausdruck erstellten anonymen Typs.  
  
 In diesem Beispiel wird das folgende XML-Dokument verwendet: [Beispiel-XML-Datei: Kunden und Bestellungen (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml-2.md).  
  
```csharp  
XElement custOrd = XElement.Load("CustomersOrders.xml");  
var custList =  
    from el in custOrd.Element("Customers").Elements("Customer")  
    select new {  
        CustomerID = (string)el.Attribute("CustomerID"),  
        CompanyName = (string)el.Element("CompanyName"),  
        ContactName = (string)el.Element("ContactName")  
    };  
foreach (var cust in custList)  
    Console.WriteLine("{0}:{1}:{2}", cust.CustomerID, cust.CompanyName, cust.ContactName);  
```  
  
 Dieser Code erzeugt die folgende Ausgabe:  
  
```  
GREAL:Great Lakes Food Market:Howard Snyder  
HUNGC:Hungry Coyote Import Store:Yoshi Latimer  
LAZYK:Lazy K Kountry Store:John Steel  
LETSS:Let's Stop N Shop:Jaime Yorres  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Projektionen und Transformationen (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/projections-and-transformations-linq-to-xml.md)