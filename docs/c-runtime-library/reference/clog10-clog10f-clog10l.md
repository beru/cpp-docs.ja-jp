---
title: clog10、clog10f、clog10l
ms.date: 11/04/2016
apiname:
- clog10
- clog10f
- clog10l
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-math-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- clog10
- clog10f
- clog10l
- complex/clog10
- complex/clog10f
- complex/clog10l
helpviewer_keywords:
- clog10 function
- clog10f function
- clog10l function
ms.assetid: 2ddae00d-ef93-4441-add3-f4d58358401b
ms.openlocfilehash: 195f4be80f0320e83cc9455a598185ce281bbf59
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62335455"
---
# <a name="clog10-clog10f-clog10l"></a>clog10、clog10f、clog10l

複素数の底 10 の対数を取得します。

## <a name="syntax"></a>構文

```C
_Dcomplex clog10( _Dcomplex z );
_Fcomplex clog10f( _Fcomplex z );
_Lcomplex clog10l( _Lcomplex z );
```

```cpp
_Fcomplex clog10( _Fcomplex z );  // C++ only
_Lcomplex clog10( _Lcomplex z );  // C++ only
```

### <a name="parameters"></a>パラメーター

*z*<br/>
対数の底。

## <a name="return-value"></a>戻り値

戻り値には次のようなものがあります。

|z パラメーター|戻り値|
|-----------------|------------------|
|正|z の底 10 の対数|
|0|- ∞|
|負|NaN|
|NaN|NaN|
|+ ∞|+ ∞|

## <a name="remarks"></a>Remarks

C++では、オーバー ロードのオーバー ロードを呼び出すことができます**clog10**を受け取って返す **_Fcomplex**と **_Lcomplex**値。 C プログラムで**clog10**は、 **_Dcomplex**値。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|C ヘッダー|C++ ヘッダー|
|-------------|--------------|------------------|
|**clog10**、 **clog10f**、 **clogl**|\<complex.h>|\<ccomplex>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[関数リファレンス (アルファベット順)](crt-alphabetical-function-reference.md)<br/>
[cexp、cexpf、cexpl](cexp-cexpf-cexpl.md)<br/>
[cpow、cpowf、cpowl](cpow-cpowf-cpowl.md)<br/>
[clog、clogf、clogl](clog-clogf-clogl.md)<br/>
