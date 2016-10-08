---
title: "Explicit Overrides  (C++ Component Extensions)"
ms.custom: na
ms.date: 10/04/2016
ms.devlang: 
  - C++
ms.prod: visual-studio-dev14
ms.reviewer: na
ms.suite: na
ms.technology: 
  - devlang-cpp
ms.tgt_pltfrm: na
ms.topic: language-reference
ms.assetid: 4ec3eaf5-163b-4df8-8f16-7a2ec04c3d0f
caps.latest.revision: 19
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
# Explicit Overrides  (C++ Component Extensions)
This topic discusses how to explicitly override a member of a base class or interface. A named (explicit) override should only be used to override a method with a derived method that has a different name.  
  
## All Runtimes  
 **Syntax**  
  
```  
  
      overriding-function-declarator = type::function [,type::function] { overriding-function-definition }  
overriding-function-declarator = function { overriding-function-definition }  
```  
  
 **Parameters**  
  
 *overriding-function-declarator*  
 The return type, name, and argument list of the overriding function.  Note that the overriding function does not have to have the same name as the function being overridden.  
  
 *type*  
 The base type that contains a function to override.  
  
 *function*  
 A comma-delimited list of one or more function names to override.  
  
 *overriding-function-definition*  
 The function body statements that define the overriding function.  
  
 **Remarks**  
  
 Use explicit overrides to create an alias for a method signature, or to provide different implementations for methods witht the same signature.  
  
 For information about modifying the behavior of inherited types and inherited type members, see [Override Specifiers](../VS_visualcpp/Override-Specifiers---C---Component-Extensions-.md).  
  
## Windows Runtime  
  
### Requirements  
 Compiler option: **/ZW**  
  
## Common Language Runtime  
 **Remarks**  
  
 For information about explicit overrides in native code or code compiled with **/clr:oldSyntax**, see [Explicit Overrides](../VS_visualcpp/Explicit-Overrides--C---.md).  
  
### Requirements  
 Compiler option: **/clr**  
  
### Examples  
 **Example**  
  
 The following code example shows a simple, implicit override and implementation of a member in a base interface, not using explicit overrides.  
  
```  
// explicit_override_1.cpp  
// compile with: /clr  
interface struct I1 {  
   virtual void f();  
};  
  
ref class X : public I1 {  
public:  
   virtual void f() {  
      System::Console::WriteLine("X::f override of I1::f");  
   }  
};  
  
int main() {  
   I1 ^ MyI = gcnew X;  
   MyI -> f();  
}  
```  
  
 **Output**  
  
 **X::f override of I1::f** **Example**  
  
 The following code example shows how to implement all interface members with a common signature, using explicit override syntax.  
  
```  
  
// explicit_override_2.cpp  
// compile with: /clr  
interface struct I1 {  
   virtual void f();  
};  
  
interface struct I2 {  
   virtual void f();  
};  
  
ref struct X : public I1, I2 {  
   virtual void f() = I1::f, I2::f {  
      System::Console::WriteLine("X::f override of I1::f and I2::f");  
   }  
};  
  
int main() {  
   I1 ^ MyI = gcnew X;  
   I2 ^ MyI2 = gcnew X;  
   MyI -> f();  
   MyI2 -> f();  
}  
```  
  
 **Output**  
  
 **X::f override of I1::f and I2::f**   
**X::f override of I1::f and I2::f** **Example**  
  
 The following code example shows how a function override can have a different name from the function it is implementing.  
  
```  
// explicit_override_3.cpp  
// compile with: /clr  
interface struct I1 {  
   virtual void f();  
};  
  
ref class X : public I1 {  
public:  
   virtual void g() = I1::f {  
      System::Console::WriteLine("X::g");  
   }  
};  
  
int main() {  
   I1 ^ a = gcnew X;  
   a->f();  
}  
```  
  
 **Output**  
  
 **X::g** **Example**  
  
 The following code example shows an explicit interface implementation that implements a type safe collection.  
  
```  
// explicit_override_4.cpp  
// compile with: /clr /LD  
using namespace System;  
ref class R : ICloneable {  
   int X;  
  
   virtual Object^ C() sealed = ICloneable::Clone {  
      return this->Clone();  
   }  
  
public:  
   R() : X(0) {}  
   R(int x) : X(x) {}  
  
   virtual R^ Clone() {  
      R^ r = gcnew R;  
      r->X = this->X;  
      return r;  
   }  
};  
```  
  
## See Also  
 [Component Extensions for Runtime Platforms](../VS_visualcpp/Component-Extensions-for-Runtime-Platforms.md)