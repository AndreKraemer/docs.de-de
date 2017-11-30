---
title: ICorProfilerModuleEnum-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerModuleEnum
api_location: mscorwks.cll
api_type: COM
f1_keywords: ICorProfilerModuleEnum
helpviewer_keywords: ICorProfilerModuleEnum interface [.NET Framework profiling]
ms.assetid: 24d0fcfa-1601-4fba-868f-da8c97303467
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 43cc6afc42fc1a02fd7d7b3df2973cc9b3e31251
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilermoduleenum-interface"></a><span data-ttu-id="13f42-102">ICorProfilerModuleEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="13f42-102">ICorProfilerModuleEnum Interface</span></span>
<span data-ttu-id="13f42-103">Stellt Methoden bereit, um eine Auflistung von Modulen, die von der Anwendung oder dem Profiler geladen wurden, sequenziell zu durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="13f42-103">Provides methods to sequentially iterate through a collection of modules loaded by the application or the profiler.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="13f42-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="13f42-104">Methods</span></span>  
  
|<span data-ttu-id="13f42-105">Methode</span><span class="sxs-lookup"><span data-stu-id="13f42-105">Method</span></span>|<span data-ttu-id="13f42-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="13f42-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="13f42-107">Clone-Methode</span><span class="sxs-lookup"><span data-stu-id="13f42-107">Clone Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-clone-method.md)|<span data-ttu-id="13f42-108">Ruft einen Schnittstellenzeiger auf eine Kopie dieser `ICorProfilerModuleEnum`-Schnittstelle ab.</span><span class="sxs-lookup"><span data-stu-id="13f42-108">Gets an interface pointer to a copy of this `ICorProfilerModuleEnum` interface.</span></span>|  
|[<span data-ttu-id="13f42-109">GetCount-Methode</span><span class="sxs-lookup"><span data-stu-id="13f42-109">GetCount Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-getcount-method.md)|<span data-ttu-id="13f42-110">Ruft die Anzahl der verwalteten Module ab, die in die Anwendung geladen wurden.</span><span class="sxs-lookup"><span data-stu-id="13f42-110">Gets the number of managed modules that were loaded into the application.</span></span>|  
|[<span data-ttu-id="13f42-111">Next-Methode</span><span class="sxs-lookup"><span data-stu-id="13f42-111">Next Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-next-method.md)|<span data-ttu-id="13f42-112">Ruft die angegebene Anzahl zusammenhängender Module aus einer sequenziellen Auflistung von Objekten ab und beginnt damit an der aktuellen Position des Enumerators in der Sequenz.</span><span class="sxs-lookup"><span data-stu-id="13f42-112">Gets the specified number of contiguous modules from a sequential collection of objects, starting at the enumerator's current position in the sequence.</span></span>|  
|[<span data-ttu-id="13f42-113">Reset-Methode</span><span class="sxs-lookup"><span data-stu-id="13f42-113">Reset Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-reset-method.md)|<span data-ttu-id="13f42-114">Verschiebt den Cursor des Enumerators an die Anfangsposition der Sequenz.</span><span class="sxs-lookup"><span data-stu-id="13f42-114">Moves the enumerator's cursor to the starting position of the sequence.</span></span>|  
|[<span data-ttu-id="13f42-115">Skip-Methode</span><span class="sxs-lookup"><span data-stu-id="13f42-115">Skip Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-skip-method.md)|<span data-ttu-id="13f42-116">Verschiebt die Cursorposition des Enumerators so, dass die angegebene Anzahl von Elementen übersprungen wird.</span><span class="sxs-lookup"><span data-stu-id="13f42-116">Advances the position of the enumerator's cursor so that the specified number of elements are skipped.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="13f42-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="13f42-117">Remarks</span></span>  
 <span data-ttu-id="13f42-118">Die `ICorProfilerModuleEnum`-Schnittstelle ist ein Enumerator.</span><span class="sxs-lookup"><span data-stu-id="13f42-118">The `ICorProfilerModuleEnum` interface is an enumerator.</span></span> <span data-ttu-id="13f42-119">Hiermit kann der Empfänger eines Arrays mit einer Rate, die für den Empfänger geeignet ist, Elemente vom Absender abrufen.</span><span class="sxs-lookup"><span data-stu-id="13f42-119">It allows the receiver of an array to pull elements from the sender at a rate that is appropriate for the receiver.</span></span> <span data-ttu-id="13f42-120">Anders ausgedrückt: Der Empfänger kann explizit den Fluss der Arrayelemente steuern und auf diese Weise Probleme im Zusammenhang mit der Übergabe großer Arrays als Methodenparameter vermeiden.</span><span class="sxs-lookup"><span data-stu-id="13f42-120">In other words, the receiver is able to explicitly control the flow of array elements, thereby avoiding the problems associated with passing large arrays as method parameters.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="13f42-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="13f42-121">Requirements</span></span>  
 <span data-ttu-id="13f42-122">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="13f42-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="13f42-123">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="13f42-123">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="13f42-124">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="13f42-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="13f42-125">**.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="13f42-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13f42-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="13f42-126">See Also</span></span>  
 [<span data-ttu-id="13f42-127">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="13f42-127">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="13f42-128">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="13f42-128">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="13f42-129">EnumModules-Methode</span><span class="sxs-lookup"><span data-stu-id="13f42-129">EnumModules Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enummodules-method.md)