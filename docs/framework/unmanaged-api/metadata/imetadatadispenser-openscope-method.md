---
title: IMetaDataDispenser::OpenScope-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataDispenser.OpenScope
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataDispenser::OpenScope
helpviewer_keywords:
- IMetaDataDispenser::OpenScope method [.NET Framework metadata]
- OpenScope method, IMetaDataDispenser interface [.NET Framework metadata]
ms.assetid: 65063ad5-e0d9-4c01-8f8b-9a5950109fa6
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 09c057f42bb849b89d78d2d32af6637640ad22ec
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="imetadatadispenseropenscope-method"></a><span data-ttu-id="7cc4e-102">IMetaDataDispenser::OpenScope-Methode</span><span class="sxs-lookup"><span data-stu-id="7cc4e-102">IMetaDataDispenser::OpenScope Method</span></span>
<span data-ttu-id="7cc4e-103">Öffnet eine Datei vorhandene, auf dem Datenträger, und seine Metadaten in den Arbeitsspeicher zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="7cc4e-103">Opens an existing, on-disk file and maps its metadata into memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7cc4e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7cc4e-104">Syntax</span></span>  
  
```  
HRESULT OpenScope (  
    [in]  LPCWSTR     szScope,   
    [in]  DWORD       dwOpenFlags,   
    [in]  REFIID      riid,   
    [out] IUnknown    **ppIUnk  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7cc4e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="7cc4e-105">Parameters</span></span>  
 `szScope`  
 <span data-ttu-id="7cc4e-106">[in] Der Name der Datei geöffnet werden.</span><span class="sxs-lookup"><span data-stu-id="7cc4e-106">[in] The name of the file to be opened.</span></span> <span data-ttu-id="7cc4e-107">Die Datei muss die common Language Runtime (CLR)-Metadaten enthalten.</span><span class="sxs-lookup"><span data-stu-id="7cc4e-107">The file must contain common language runtime (CLR) metadata.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="7cc4e-108">[in] Der Wert der [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) Enumeration zum Öffnen den Modus (Lesen, schreiben und so weiter) angeben.</span><span class="sxs-lookup"><span data-stu-id="7cc4e-108">[in] A value of the [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) enumeration to specify the mode (read, write, and so on) for opening.</span></span>  
  
 `riid`  
 <span data-ttu-id="7cc4e-109">[in] Die IID der Metadatenschnittstelle für die gewünschten zurückgegeben werden sollen; der Aufrufer verwendet die Schnittstelle zum Importieren (Lesen) oder Ausgeben von Metadaten (Schreiben).</span><span class="sxs-lookup"><span data-stu-id="7cc4e-109">[in] The IID of the desired metadata interface to be returned; the caller will use the interface to import (read) or emit (write) metadata.</span></span>  
  
 <span data-ttu-id="7cc4e-110">Der Wert des `riid` müssen eine der Schnittstellen "Import" oder "Ausgabe" angeben.</span><span class="sxs-lookup"><span data-stu-id="7cc4e-110">The value of `riid` must specify one of the "import" or "emit" interfaces.</span></span> <span data-ttu-id="7cc4e-111">Gültige Werte sind IID_IMetaDataEmit, IID_IMetaDataImport auf, IID_IMetaDataAssemblyEmit, IID_IMetaDataAssemblyImport, IID_IMetaDataEmit2 oder IID_IMetaDataImport2.</span><span class="sxs-lookup"><span data-stu-id="7cc4e-111">Valid values are IID_IMetaDataEmit, IID_IMetaDataImport, IID_IMetaDataAssemblyEmit, IID_IMetaDataAssemblyImport, IID_IMetaDataEmit2, or IID_IMetaDataImport2.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="7cc4e-112">[out] Der Zeiger auf die zurückgegebene Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="7cc4e-112">[out] The pointer to the returned interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7cc4e-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7cc4e-113">Remarks</span></span>  
 <span data-ttu-id="7cc4e-114">Die in-Memory-Kopie der Metadaten kann abgefragt werden, mithilfe der Methoden aus einer der Schnittstellen "Importieren" oder mit Methoden aus dem der "Ausgabe"-Schnittstellen hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="7cc4e-114">The in-memory copy of the metadata can be queried using methods from one of the "import" interfaces, or added to using methods from the one of the "emit" interfaces.</span></span>  
  
 <span data-ttu-id="7cc4e-115">Wenn die Zieldatei keine CLR-Metadaten enthält die `OpenScope` Methode fehl.</span><span class="sxs-lookup"><span data-stu-id="7cc4e-115">If the target file does not contain CLR metadata, the `OpenScope` method will fail.</span></span>  
  
 <span data-ttu-id="7cc4e-116">In .NET Framework, Version 1.0 und Version 1.1, wenn ein Bereich wird mit geöffnet `dwOpenFlags` auf festgelegt, ist es für die Freigabe.</span><span class="sxs-lookup"><span data-stu-id="7cc4e-116">In the .NET Framework version 1.0 and version 1.1, if a scope is opened with `dwOpenFlags` set to ofRead, it is eligible for sharing.</span></span> <span data-ttu-id="7cc4e-117">D. h., wenn nachfolgende Aufrufe von `OpenScope` übergeben Sie den Namen einer Datei, die zuvor geöffnet wurde, wird der vorhandene Bereich wiederverwendet und ein neuer Satz von Datenstrukturen nicht erstellt.</span><span class="sxs-lookup"><span data-stu-id="7cc4e-117">That is, if subsequent calls to `OpenScope` pass in the name of a file that was previously opened, the existing scope is reused and a new set of data structures is not created.</span></span> <span data-ttu-id="7cc4e-118">Allerdings können Probleme aufgrund dieser Freigabe entstehen.</span><span class="sxs-lookup"><span data-stu-id="7cc4e-118">However, problems can arise due to this sharing.</span></span>  
  
 <span data-ttu-id="7cc4e-119">In .NET Framework, Version 2.0, Bereiche mit geöffnet `dwOpenFlags` Satz auf nicht mehr freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="7cc4e-119">In the .NET Framework version 2.0, scopes opened with `dwOpenFlags` set to ofRead are no longer shared.</span></span> <span data-ttu-id="7cc4e-120">Verwenden Sie den OfReadOnly-Wert, den Bereich freigegeben werden können.</span><span class="sxs-lookup"><span data-stu-id="7cc4e-120">Use the ofReadOnly value to allow the scope to be shared.</span></span> <span data-ttu-id="7cc4e-121">Wenn ein Bereich freigegeben ist, schlagen Abfragen, die verwenden "Metadatenschnittstellen Schreib-Lese" fehl.</span><span class="sxs-lookup"><span data-stu-id="7cc4e-121">When a scope is shared, queries that use "read/write" metadata interfaces will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7cc4e-122">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7cc4e-122">Requirements</span></span>  
 <span data-ttu-id="7cc4e-123">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7cc4e-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7cc4e-124">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="7cc4e-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7cc4e-125">**Bibliothek:** als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="7cc4e-125">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7cc4e-126">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7cc4e-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7cc4e-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7cc4e-127">See Also</span></span>  
 [<span data-ttu-id="7cc4e-128">IMetaDataDispenser-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7cc4e-128">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)  
 [<span data-ttu-id="7cc4e-129">IMetaDataDispenserEx-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7cc4e-129">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)  
 [<span data-ttu-id="7cc4e-130">IMetaDataAssemblyEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7cc4e-130">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)  
 [<span data-ttu-id="7cc4e-131">IMetaDataAssemblyImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7cc4e-131">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)  
 [<span data-ttu-id="7cc4e-132">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7cc4e-132">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="7cc4e-133">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7cc4e-133">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)  
 [<span data-ttu-id="7cc4e-134">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7cc4e-134">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="7cc4e-135">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7cc4e-135">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)