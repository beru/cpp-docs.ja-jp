---
title: コンパイラ エラー C2831
ms.date: 11/04/2016
f1_keywords:
- C2831
helpviewer_keywords:
- C2831
ms.assetid: c8c04288-0889-4265-a077-17f94cbcdcc9
ms.openlocfilehash: b0708a7c45f33e30280666cf9bc903723d6a9c26
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62227832"
---
# <a name="compiler-error-c2831"></a>コンパイラ エラー C2831

'operator 演算子' は、既定のパラメーターを含めることはできません。

演算子の 3 つだけでは、既定のパラメーターを持つことができます。

- [new](../../cpp/new-operator-cpp.md)

- 割り当て =

- 左かっこ (

次の例では、C2831 が生成されます。

```
// C2831.cpp
// compile with: /c
#define BINOP <=
class A {
public:
   int i;
   int operator BINOP(int x = 1) {   // C2831
   // try the following line instead
   // int operator BINOP(int x) {
      return i+x;
   }
};
```