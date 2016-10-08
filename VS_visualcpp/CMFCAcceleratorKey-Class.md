---
title: "CMFCAcceleratorKey Class"
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
ms.assetid: d140fbf7-23db-45ea-a63e-414a5ec7b3d5
caps.latest.revision: 32
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
# CMFCAcceleratorKey Class
A helper class that implements virtual key mapping and formatting.  
  
## Syntax  
  
```  
class CMFCAcceleratorKey : public CObject  
```  
  
## Members  
  
### Public Constructors  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCAcceleratorKey::CMFCAcceleratorKey](#cmfcacceleratorkey__cmfcacceleratorkey)|Constructs a `CMFCAcceleratorKey` object.|  
  
### Public Methods  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCAcceleratorKey::Format](#cmfcacceleratorkey__format)|Translates the ACCEL structure to its visual representation.|  
|[CMFCAcceleratorKey::SetAccelerator](#cmfcacceleratorkey__setaccelerator)|Sets the shortcut key for the `CMFCAcceleratorKey` object.|  
  
## Remarks  
 Accelerator keys are also known as shortcut keys. If you want to display keyboard shortcuts that a user enters, the [CMFCAcceleratorKeyAssignCtrl Class](../VS_visualcpp/CMFCAcceleratorKeyAssignCtrl-Class.md) maps keyboard shortcuts, such as Alt+Shift+S, to a custom text format, such as "Alt + Shift + S". Each `CMFCAcceleratorKey` object maps a single shortcut key to a text format.  
  
 For more information about how to use shortcut keys and accelerator tables, see                [CKeyboardManager Class](../VS_visualcpp/CKeyboardManager-Class.md).  
  
## Example  
 The following example demonstrates how to construct a `CMFCAcceleratorKey` object and how to use its `Format` method.  
  
 [!CODE [NVC_MFC_RibbonApp#30](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_RibbonApp#30)]  
  
## Inheritance Hierarchy  
 [CObject](../VS_visualcpp/CObject-Class.md)  
  
 [CMFCAcceleratorKey](../VS_visualcpp/CMFCAcceleratorKey-Class.md)  
  
## Requirements  
 **Header:** afxacceleratorkey.h  
  
##  <a name="cmfcacceleratorkey__cmfcacceleratorkey"></a>  CMFCAcceleratorKey::CMFCAcceleratorKey  
 Constructs a [CMFCAcceleratorKey](../VS_visualcpp/CMFCAcceleratorKey-Class.md) object.  
  
```  
CMFCAcceleratorKey();  
  
CMFCAcceleratorKey(  
    LPACCEL lpAccel );  
```  
  
### Parameters  
 [in] `lpAccel`  
 A pointer to a shortcut key.  
  
### Remarks  
 If you do not provide a shortcut key when you create a `CMFCAccleratorKey`, use the [CMFCAcceleratorKey::SetAccelerator](#cmfcacceleratorkey__setaccelerator) method to associate a shortcut key with your `CMFCAcceleratorKey` object.  
  
##  <a name="cmfcacceleratorkey__format"></a>  CMFCAcceleratorKey::Format  
 Translates the ACCEL structure to its associated string value.  
  
```  
void Format( CString& str ) const;  
```  
  
### Parameters  
 [out] `str`  
 A reference to a `CString` object where the method writes the translated shortcut key.  
  
### Remarks  
 This method retrieves the string format of the associated shortcut key. You can set the string format of a [CMFCAcceleratorKey](../VS_visualcpp/CMFCAcceleratorKey-Class.md) object using either the constructor or the method [CMFCAcceleratorKey::SetAccelerator](#cmfcacceleratorkey__setaccelerator).  
  
##  <a name="cmfcacceleratorkey__setaccelerator"></a>  CMFCAcceleratorKey::SetAccelerator  
 Sets the shortcut key for the [CMFCAcceleratorKey](../VS_visualcpp/CMFCAcceleratorKey-Class.md) object.  
  
```  
void SetAccelerator( LPACCEL lpAccel );  
```  
  
### Parameters  
 [in] `lpAccel`  
 A pointer to a shortcut key.  
  
### Remarks  
 Use this method to set the shortcut key for a `CMFCAcceleratorKey` if you did not provide a shortcut key when you created the `CMFCAcceleratorKey`.  
  
## See Also  
 [Hierarchy Chart](../VS_visualcpp/Hierarchy-Chart.md)   
 [Classes](../VS_visualcpp/MFC-Classes.md)   
 [CKeyboardManager Class](../VS_visualcpp/CKeyboardManager-Class.md)