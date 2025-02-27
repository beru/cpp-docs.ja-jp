---
title: aligned_union クラス
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::aligned_union
helpviewer_keywords:
- aligned_union
ms.assetid: 9931a44d-3a67-4f29-a0f6-d47a7cf560ac
ms.openlocfilehash: b9ffb4aff4d4d5667ab8d626ea13a21da94ca0c1
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2019
ms.locfileid: "68456463"
---
# <a name="alignedunion-class"></a>aligned_union クラス

共用体型を格納するのに十分な大きさと適切に配置された POD 型と必要なサイズを提供します。

## <a name="syntax"></a>構文

```cpp
template <std::size_t Len, class... Types>
struct aligned_union;

template <std::size_t Len, class... Types>
using aligned_union_t = typename aligned_union<Len, Types...>::type;
```

### <a name="parameters"></a>パラメーター

*Len*\
共用体内の最大の型に関するアラインメント値を指定します。

*型*\
基になる共用体内の個別の型。

## <a name="remarks"></a>Remarks

テンプレート クラスを使用して、初期化されていない記憶域に共用体を格納するために必要なサイズと配置を取得します。 メンバー typedef `type`は、*型*に一覧表示されている任意の型のストレージに適した POD 型に名前を付いています。最小サイズは*Len*です。 型`alignment_value` の`std::size_t`静的メンバーには、*型*に示されているすべての型で必要とされる最も厳密なアラインメントが含まれています。

## <a name="example"></a>例

次の例は、共用体を配置するため、`aligned_union` を使用して配置されたスタック バッファーを割り当てる方法を示しています。

```cpp
// std__type_traits__aligned_union.cpp
#include <iostream>
#include <type_traits>

union U_type
{
    int i;
    float f;
    double d;
    U_type(float e) : f(e) {}
};

typedef std::aligned_union<16, int, float, double>::type aligned_U_type;

int main()
{
    // allocate memory for a U_type aligned on a 16-byte boundary
    aligned_U_type au;
    // do placement new in the aligned memory on the stack
    U_type* u = new (&au) U_type(1.0f);
    if (nullptr != u)
    {
        std::cout << "value of u->i is " << u->i << std::endl;
        // must clean up placement objects manually!
        u->~U_type();
    }
}
```

```Output
value of u->i is 1065353216
```

## <a name="requirements"></a>必要条件

**ヘッダー:** \<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)\
[alignment_of クラス](../standard-library/alignment-of-class.md)
