---
title: freelist クラス
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::freelist
- allocators/stdext::freelist::pop
- allocators/stdext::freelist::push
helpviewer_keywords:
- stdext::freelist
- stdext::freelist [C++], pop
- stdext::freelist [C++], push
ms.assetid: 8ad7e35c-4c80-4479-8ede-1a2497b06d71
ms.openlocfilehash: 8a504f58f9f64aa8b0d26b17090387c5c2b5de21
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2019
ms.locfileid: "68454141"
---
# <a name="freelist-class"></a>freelist クラス

メモリ ブロックのリストを管理します。

## <a name="syntax"></a>構文

```cpp
template <std::size_t Sz, class Max>
class freelist : public Max
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*Sz*|割り当てられる配列内の要素の数。|
|*Max*|フリー リストに格納される要素の最大数を示す最大クラス。 最大クラスは、[max_none](../standard-library/max-none-class.md)、[max_unbounded](../standard-library/max-unbounded-class.md)、[max_fixed_size](../standard-library/max-fixed-size-class.md)、[max_variable_size](../standard-library/max-variable-size-class.md) のいずれかにすることができます。|

## <a name="remarks"></a>Remarks

このテンプレートクラスは、最大値として渡された最大クラスによって決定されるリストの最大長を持つサイズ*Sz*のメモリブロックのリストを管理し*ます。*

### <a name="constructors"></a>コンストラクター

|コンストラクター|説明|
|-|-|
|[freelist](#freelist)|`freelist` 型のオブジェクトを構築します。|

### <a name="member-functions"></a>メンバー関数

|メンバー関数|説明|
|-|-|
|[pop](#pop)|フリー リストから最初のメモリ ブロックを削除します。|
|[push](#push)|メモリ ブロックをリストに追加します。|

## <a name="requirements"></a>必要条件

**ヘッダー:** \<allocators>

**名前空間:** stdext

## <a name="freelist"></a>  freelist::freelist

`freelist` 型のオブジェクトを構築します。

```cpp
freelist();
```

### <a name="remarks"></a>Remarks

## <a name="pop"></a>  freelist::pop

フリー リストから最初のメモリ ブロックを削除します。

```cpp
void *pop();
```

### <a name="return-value"></a>戻り値

一覧から削除するメモリ ブロックへのポインターを返します。

### <a name="remarks"></a>Remarks

このメンバー関数は、リストが空の場合、NULL を返します。 それ以外の場合は、空き一覧から最初のメモリ ブロックを削除します。

## <a name="push"></a>  freelist::push

メモリ ブロックをリストに追加します。

```cpp
bool push(void* ptr);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*ptr*|フリー リストに追加するメモリ ブロックへのポインター。|

### <a name="return-value"></a>戻り値

max クラスの`full`関数が**false**を返す場合は true。それ以外`push`の場合、関数は**false**を返します。

### <a name="remarks"></a>Remarks

Max クラス`full`の関数が**false**を返す場合、このメンバー関数は、 *ptr*が指すメモリブロックをリストの先頭に追加します。

## <a name="see-also"></a>関連項目

[\<allocators>](../standard-library/allocators-header.md)
