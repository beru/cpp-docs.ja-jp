---
title: コンパイラ エラー C2008
ms.date: 11/04/2016
f1_keywords:
- C2008
helpviewer_keywords:
- C2008
ms.assetid: e748ccbe-ffd4-4008-aca7-e53c25225209
ms.openlocfilehash: 0bd9193d6e305a4b6c6851ef2524a68ecc056816
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62208985"
---
# <a name="compiler-error-c2008"></a>コンパイラ エラー C2008

'character' : マクロ定義内で指定された文字の使い方が間違っています。

マクロ名のすぐ後に文字が表示されます。 エラーを解決するには、必要がありますスペース マクロ名の後にします。

次の例では、C2008 が生成されます。

```
// C2008.cpp
#define TEST1"mytest1"    // C2008
```

考えられる解決方法:

```
// C2008b.cpp
// compile with: /c
#define TEST2 "mytest2"
```