---
title: コンパイラ エラー C2549
ms.date: 11/04/2016
f1_keywords:
- C2549
helpviewer_keywords:
- C2549
ms.assetid: 29310094-54a3-4605-bc6d-a312a68daf5d
ms.openlocfilehash: 1aebe5a2e9e9f4e3ac290876b271806bbf65789b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62353340"
---
# <a name="compiler-error-c2549"></a>コンパイラ エラー C2549

ユーザー定義の変換は、戻り値の型を指定できません。

次の例では、C2549 が生成されます。

```
// C2549.cpp
// compile with: /c
class X {
public:
   int operator int() { return value; }   // C2549

   // try the following line instead
   // operator int() { return value; }
private:
   int value;
};
```