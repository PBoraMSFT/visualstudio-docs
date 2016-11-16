---
title: "IDebugMemoryContext2::Compare | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugMemoryContext2::Compare"
helpviewer_keywords: 
  - "IDebugMemoryContext2::Compare method"
  - "Compare method"
ms.assetid: c51b5128-848e-4d8e-b2e9-1161339763c3
caps.latest.revision: 14
ms.author: "gregvanl"
manager: "ghogen"
translation.priority.mt: 
  - "cs-cz"
  - "de-de"
  - "es-es"
  - "fr-fr"
  - "it-it"
  - "ja-jp"
  - "ko-kr"
  - "pl-pl"
  - "pt-br"
  - "ru-ru"
  - "tr-tr"
  - "zh-cn"
  - "zh-tw"
---
# IDebugMemoryContext2::Compare
Compares the memory context to each context in the given array in the manner indicated by compare flags, returning an index of the first context that matches.  
  
## Syntax  
  
```cpp#  
HRESULT Compare(   
   CONTEXT_COMPARE        compare,  
   IDebugMemoryContext2** rgpMemoryContextSet,  
   DWORD                  dwMemoryContextSetLen,  
   DWORD*                 pdwMemoryContext  
);  
```  
  
```c#  
int Compare(  
   enum_CONTEXT_COMPARE   compare,   
   IDebugMemoryContext2[] rgpMemoryContextSet,   
   uint                   dwMemoryContextSetLen,   
   out uint               pdwMemoryContext  
);  
```  
  
#### Parameters  
 `compare`  
 [in] A value from the [CONTEXT_COMPARE](../../../extensibility/debugger/reference/context-compare.md) enumeration that determines the type of comparison.  
  
 `rgpMemoryContextSet`  
 [in] An array of references to the [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md) objects to compare against.  
  
 `dwMemoryContextSetLen`  
 [in] The number of contexts in the `rgpMemoryContextSet` array.  
  
 `pdwMemoryContext`  
 [out] Returns the index of the first memory context that satisfies the comparison.  
  
## Return Value  
 If successful, returns `S_OK`; otherwise, returns an error code. Returns `E_COMPARE_CANNOT_COMPARE` if the two contexts cannot be compared.  
  
## Remarks  
 A debug engine (DE) does not have to support all types of comparisons, but it must support at least `CONTEXT_EQUAL`, `CONTEXT_LESS_THAN`, `CONTEXT_GREATER_THAN` and `CONTEXT_SAME_SCOPE`.  
  
## See Also  
 [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md)   
 [CONTEXT_COMPARE](../../../extensibility/debugger/reference/context-compare.md)