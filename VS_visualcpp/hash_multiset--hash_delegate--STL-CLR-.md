---
title: "hash_multiset::hash_delegate (STL-CLR)"
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
ms.topic: reference
H1: hash_multiset::hash_delegate (STL/CLR)
ms.assetid: 61ccfdfb-6a3c-40aa-902f-49e004a31a75
caps.latest.revision: 13
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
# hash_multiset::hash_delegate (STL-CLR)
Finds an element that matches a specified key.  
  
## Syntax  
  
```  
hasher^ hash_delegate();  
```  
  
## Remarks  
 The member function returns the delegate used to convert a key value to an integer. You use it to hash a key.  
  
## Example  
  
```  
// cliext_hash_multiset_hash_delegate.cpp   
// compile with: /clr   
#include <cliext/hash_set>   
  
typedef cliext::hash_multiset<wchar_t> Myhash_multiset;   
int main()   
    {   
    Myhash_multiset c1;   
    Myhash_multiset::hasher^ myhash = c1.hash_delegate();   
  
    System::Console::WriteLine("hash(L'a') = {0}", myhash(L'a'));   
    System::Console::WriteLine("hash(L'b') = {0}", myhash(L'b'));   
    return (0);   
    }  
  
```  
  
 **hash(L'a') = 1616896120**  
**hash(L'b') = 570892832**   
## Requirements  
 **Header:** <cliext/hash_set>  
  
 **Namespace:** cliext  
  
## See Also  
 [hash_multiset (STL/CLR)](../VS_visualcpp/hash_multiset--STL-CLR-.md)   
 [hash_multiset::hasher (STL/CLR)](../VS_visualcpp/hash_multiset--hasher--STL-CLR-.md)