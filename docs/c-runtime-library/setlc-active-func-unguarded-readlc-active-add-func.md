---
title: ___setlc_active_func、___unguarded_readlc_active_add_func
ms.date: 11/04/2016
apiname:
- ___setlc_active_func
- ___unguarded_readlc_active_add_func
apilocation:
- msvcr90.dll
- msvcr110_clr0400.dll
- msvcrt.dll
- msvcr110.dll
- msvcr80.dll
- msvcr120.dll
- msvcr100.dll
apitype: DLLExport
f1_keywords:
- ___unguarded_readlc_active_add_func
- ___setlc_active_func
helpviewer_keywords:
- ___setlc_active_func
- ___unguarded_readlc_active_add_func
ms.assetid: 605ec4e3-81e5-4ece-935a-f434768cc702
ms.openlocfilehash: 244bb5b0bd6a15dab2de1ad2d6b71c2ae2f850bb
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/11/2019
ms.locfileid: "57743977"
---
# <a name="setlcactivefunc-unguardedreadlcactiveaddfunc"></a>___setlc_active_func、___unguarded_readlc_active_add_func

互換性のために残されています。 バイナリの互換性を維持するためにのみ、これらの内部関数は CRT によってエクスポートされます。

## <a name="syntax"></a>構文

```cpp
int ___setlc_active_func(void);
int * ___unguarded_readlc_active_add_func(void);
```

## <a name="return-value"></a>戻り値

戻される値は重要ではありません。

## <a name="remarks"></a>解説

内部 CRT 関数 `___setlc_active_func` および `___unguarded_readlc_active_add_func` は互換性のために残されており、使用されなくなりましたが、バイナリの互換性を維持するために CRT ライブラリによってエクスポートされます。 `___setlc_active_func` の本来の目的は、`setlocale` 関数の現在アクティブな呼び出しの数を返すことでした。 `___unguarded_readlc_active_add_func` の本来の目的は、ロケールをロックしないで参照した関数の数を返すことでした。

## <a name="requirements"></a>要件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|`___setlc_active_func`、 `___unguarded_readlc_active_add_func`|none|

## <a name="see-also"></a>関連項目

[setlocale、_wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)
