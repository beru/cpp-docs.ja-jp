---
title: コンパイラ エラー C2447
ms.date: 11/04/2016
f1_keywords:
- C2447
helpviewer_keywords:
- C2447
ms.assetid: d1bd6e9a-ee42-4510-ae5e-6b0378f7b931
ms.openlocfilehash: 64dca8313af8b640b7b03c1ab27a1a31fa90de09
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62301969"
---
# <a name="compiler-error-c2447"></a>コンパイラ エラー C2447

'{' : 対応する関数ヘッダーがありません (旧形式の仮引数リスト?)

グローバル スコープで予期しない始め中かっこが見つかりました。 この問題は、ほとんどの場合、形式が正しくない関数のヘッダー、誤った場所にある宣言、または無効なセミコロンが原因で発生します。 この問題を解決するには、始め中かっこの前にある関数ヘッダーの形式が正しいこと、および始め中かっこの前に宣言や無効なセミコロンがないことを確認します。

このエラーは、旧形式の C 言語仮引数リストが原因で発生する場合もあります。 この問題を解決するには、最新の形式を使用するように、つまり、かっこで囲むように引数リストをリファクタリングします。

次の例では、C2447 が生成されます。

```
// C2447.cpp
int c;
{}       // C2447
```