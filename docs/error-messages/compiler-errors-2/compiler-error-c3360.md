---
title: コンパイラ エラー C3360
ms.date: 11/04/2016
f1_keywords:
- C3360
helpviewer_keywords:
- C3360
ms.assetid: 6acf983a-dbb6-422b-b045-a34bb4ba6761
ms.openlocfilehash: 1d08c53aad50d2cbc10c8c0e398fe3a18de3849d
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/24/2019
ms.locfileid: "64345503"
---
# <a name="compiler-error-c3360"></a>コンパイラ エラー C3360

'string': 名前を作成できません

[uuid](../../windows/uuid-cpp-attributes.md) 属性に渡された値は無効です。

次の例では C3360 が生成されます。

```
// C3360.cpp
[ uuid("1") ]
// try this line instead
// [ uuid("12341234-1234-1234-1234-123412341234") ]
struct A   // C3360
{
};

int main()
{
}
```