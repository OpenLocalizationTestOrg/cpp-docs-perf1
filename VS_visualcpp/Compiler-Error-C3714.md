---
title: "Compiler Error C3714"
ms.custom: na
ms.date: 10/03/2016
ms.devlang: 
  - C++
ms.prod: visual-studio-dev14
ms.reviewer: na
ms.suite: na
ms.technology: 
  - devlang-cpp
ms.tgt_pltfrm: na
ms.topic: error-reference
ms.assetid: 17718f75-5a37-4e42-912b-487e91008a95
caps.latest.revision: 10
manager: ghogen
translation.priority.ht: 
  - cs-cz
  - de-de
  - es-es
  - fr-fr
  - it-it
  - ja-jp
  - ko-kr
  - pl-pl
  - pt-br
  - ru-ru
  - tr-tr
  - zh-cn
  - zh-tw
---
# Compiler Error C3714
'method': an event handler method must have the same calling convention as the source 'method'  
  
 You defined an event handler method that did not use the same calling convention as the source event method. To fix this error, give the event handler method the same calling conventions as those of the source event method. For example, in the code below, make the calling conventions of `handler1` and `event1` match ([__cdecl](../VS_visualcpp/__cdecl.md) or [__stdcall](../VS_visualcpp/__stdcall.md) or others). Removing calling convention keywords from both declarations will also solve the problem, and cause `event1` and `handler1` to default to the [thiscall](../VS_visualcpp/__thiscall.md) calling convention. See [Calling Conventions](../VS_visualcpp/Calling-Conventions.md) for more information.  
  
 The following sample generates C3714:  
  
```  
// C3714.cpp  
// compile with: /c  
// processor: x86  
[event_source(native)]  
class CEventSrc {  
public:  
   __event void __cdecl event1();  
   // try the following line instead  
   // __event void __stdcall event1();  
};  
  
[event_receiver(native)]  
class CEventRec {  
public:  
   void __stdcall handler1() {}  
  
   void HookEvents(CEventSrc* pSrc) {  
      __hook(&CEventSrc::event1, pSrc, &CEventRec::handler1);   // C3714  
   }  
  
   void UnhookEvents(CEventSrc* pSrc) {  
      __unhook(&CEventSrc::event1, pSrc, &CEventRec::handler1); // C3714  
   }  
};  
```