---
title: pointer_traits 構造体
ms.date: 11/04/2016
f1_keywords:
- memory/std::pointer_traits::element_type
- memory/std::pointer_traits::pointer
- memory/std::pointer_traits
- memory/std::pointer_traits::difference_type
- memory/std::pointer_traits::rebind
- xmemory0/std::pointer_traits::element_type
- xmemory0/std::pointer_traits::pointer
- xmemory0/std::pointer_traits
- xmemory0/std::pointer_traits::difference_type
- xmemory0/std::pointer_traits::rebind
- memory/std::pointer_traits::pointer_to
ms.assetid: 545aecf1-3561-4859-8b34-603c079fe1b3
ms.openlocfilehash: 109e51ad9eba54f31b90da9b8b85bec105c7dce6
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/16/2019
ms.locfileid: "68240415"
---
# <a name="pointertraits-struct"></a>pointer_traits 構造体

`allocator_traits` テンプレート クラスのオブジェクトが、ポインター型 `Ptr` を持つアロケーターを記述するために必要とする情報を提供します。

## <a name="syntax"></a>構文

```cpp
template <class Ptr>
    struct pointer_traits;
```

## <a name="remarks"></a>Remarks

Ptr には `Ty *` 型の生のポインターまたは次のプロパティを持つクラスを指定できます。

```cpp
struct Ptr
{ // describes a pointer type usable by allocators
   typedef Ptr pointer;
   typedef T1 element_type; // optional
   typedef T2 difference_type; // optional
   template <class Other>
   using rebind = typename Ptr<Other, Rest...>; // optional
   static pointer pointer_to(element_type& obj); // optional
};
```

## <a name="members"></a>メンバー

### <a name="typedefs"></a>Typedef

|||
|-|-|
|`typedef T2 difference_type`|`T2` 型は、その型が存在する場合は `Ptr::difference_type`、それ以外の場合は `ptrdiff_t` です。 `Ptr` が生のポインターの場合、型は `ptrdiff_t` です。|
|`typedef T1 element_type`|`T1` 型は、その型が存在する場合は `Ptr::element_type`、それ以外の場合は `Ty` です。 `Ptr` が生のポインターの場合、型は `Ty` です。|
|`typedef Ptr pointer`|型は `Ptr` です。|

### <a name="structs"></a>構造体

|||
|-|-|
|`rebind`|基になるポインター型を指定された型に変換しようとします。|

### <a name="methods"></a>メソッド

|名前|説明|
|----------|-----------------|
|[pointer_to](#pointer_to)|任意の参照をクラス `Ptr` のオブジェクトに変換します。|

### <a name="pointer_to"></a> pointer_to

その関数が存在する場合に `Ptr::pointer_to(obj)` を返す静的メソッド。 それ以外の場合は、任意の参照をクラス `Ptr` のオブジェクトに変換できません。 `Ptr` が生のポインターの場合、このメソッドは `addressof(obj)` を返します。

```cpp
static pointer pointer_to(element_type& obj);
```
