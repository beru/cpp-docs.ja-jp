---
title: __dllonexit
ms.date: 11/04/2016
apiname:
- __dllonexit
apilocation:
- msvcrt.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr100.dll
- msvcr80.dll
- msvcr120.dll
- msvcr90.dll
- msvcr120_clr0400.dll
apitype: DLLExport
f1_keywords:
- __dllonexit
helpviewer_keywords:
- __dllonexit
ms.assetid: 708f2ceb-f95c-46b0-a58d-d68b3fa36f12
ms.openlocfilehash: a6c077ac010c0b5d94ba21ba823441ea6ac932b9
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/11/2019
ms.locfileid: "57739378"
---
# <a name="dllonexit"></a>__dllonexit

終了時に呼び出されるルーチンを登録します。

## <a name="syntax"></a>構文

```
_onexit_t __dllonexit(   _onexit_t func,
   _PVFV **  pbegin,
   _PVFV **  pend
   )
```

#### <a name="parameters"></a>パラメーター

*func*<br/>
終了時に実行する関数へのポインター。

*pbegin*<br/>
デタッチ時に実行する関数のリストの先頭を示す変数へのポインター。

*pend*<br/>
デタッチ時に実行する関数のリストの末尾を示す変数へのポインター。

## <a name="return-value"></a>戻り値

成功した場合、ユーザーの関数へのポインター。 失敗した場合、**NULL** ポインター。

## <a name="remarks"></a>解説

`__dllonexit` 関数は [_onexit](../c-runtime-library/reference/onexit-onexit-m.md) 関数に似ていますが、_onexit 関数で使われるグローバル変数をこのルーチンでは参照できない点が異なります。 グローバル変数の代わりに、この関数は `pbegin` および `pend` パラメーターを使います。

MSVCRT.LIB とリンクされた DLL の `_onexit` および `atexit` 関数は、それ自体で atexit/_onexit リストを保持する必要があります。 このルーチンは、そのような DLL によって呼び出されるワーカーです。

`_PVFV` 型は、`typedef void (__cdecl *_PVFV)(void)` と定義されます。

## <a name="requirements"></a>要件

|ルーチンによって返される値|必要なファイル|
|-------------|-------------------|
|__dllonexit|onexit.c|

## <a name="see-also"></a>関連項目

[_onexit、_onexit_m](../c-runtime-library/reference/onexit-onexit-m.md)
