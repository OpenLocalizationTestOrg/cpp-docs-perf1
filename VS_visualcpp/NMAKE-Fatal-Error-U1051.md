---
title: "NMAKE Fatal Error U1051"
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
ms.assetid: fede5cd5-dac3-47b7-b86d-e1acfb78699f
caps.latest.revision: 6
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
# NMAKE Fatal Error U1051
out of memory  
  
 NMAKE ran out of memory, including virtual memory, because the makefile was too large or complex.  
  
### To fix by using the following possible solutions  
  
1.  Free some space on disk.  
  
2.  Increase the size of the Windows NT paging file or the Windows swap file.  
  
3.  If only part of the makefile is being used, either divide the makefile into separate files or use **!IF** preprocessing directives to limit the amount that NMAKE must process. The **!IF** directives include **!IF**, `!IFDEF`, **!IFNDEF**, **!ELSE IF**, **!ELSE** `IFDEF`, and **!ELSE** `IFNDEF`.