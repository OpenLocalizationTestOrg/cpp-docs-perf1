---
title: "_get_daylight"
ms.custom: na
ms.date: "10/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
apiname: 
  - "__daylight"
  - "_get_daylight"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-time-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "get_daylight"
  - "_get_daylight"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "get_daylight function"
  - "daylight saving time offset"
  - "_get_daylight function"
ms.assetid: f85a6ba3-e187-4ca7-aed7-ffc694c8ac4c
caps.latest.revision: 17
ms.author: "corob"
manager: "ghogen"
translation.priority.ht: 
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
# _get_daylight
Retrieves the daylight saving time offset in hours.  
  
## Syntax  
  
```  
  
      error_t _get_daylight(   
    int* hours  
);  
```  
  
#### Parameters  
 `hours`  
 The offset in hours of daylight saving time.  
  
## Return Value  
 Zero if successful or an `errno` value if an error occurs.  
  
## Remarks  
 The `_get_daylight` function retrieves the number of hours in daylight saving time as an integer. If daylight saving time is in effect, the default offset is one hour (although a few regions do observe a two-hour offset).  
  
 If `hours` is `NULL`, the invalid parameter handler is invoked as described in [Parameter Validation](../crt/parameter-validation.md). If execution is allowed to continue, this function sets `errno` to `EINVAL` and returns `EINVAL`.  
  
 We recommend you use this function instead of the macro `_daylight` or the deprecated function `__daylight`.  
  
## .NET Framework Equivalent  
 Not applicable. To call the standard C function, use `PInvoke`. For more information, see [Platform Invoke Examples](../Topic/Platform%20Invoke%20Examples.md).  
  
## Requirements  
  
|Routine|Required header|  
|-------------|---------------------|  
|`_get_daylight`|\<time.h>|  
  
 For more information, see [Compatibility](../crt/compatibility.md).  
  
## See Also  
 [Time Management](../crt/time-management.md)   
 [errno, _doserrno, _sys_errlist, and _sys_nerr](../crt/errno--_doserrno--_sys_errlist--and-_sys_nerr.md)   
 [_get_dstbias](../crt/_get_dstbias.md)   
 [_get_timezone](../crt/_get_timezone.md)   
 [_get_tzname](../crt/_get_tzname.md)