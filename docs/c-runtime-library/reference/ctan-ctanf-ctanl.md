---
title: ctan、ctanf、ctanl
ms.date: 11/04/2016
apiname:
- ctan
- ctanf
- ctanl
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
- ctan
- ctanf
- ctanl
- complex/ctan
- complex/ctanf
- complex/ctanl
helpviewer_keywords:
- ctan function
- ctanf function
- ctanl function
ms.assetid: d3cbd25c-1e93-4a6d-8154-da42921f7223
ms.openlocfilehash: 2d4da5a39658e46bc633ae3bd9c8f6f0a01555aa
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62288755"
---
# <a name="ctan-ctanf-ctanl"></a>ctan、ctanf、ctanl

複素数のタンジェントを取得します。

## <a name="syntax"></a>構文

```C
_Dcomplex ctan(
   _Dcomplex z
);
_Fcomplex ctan(
   _Fcomplex z
);  // C++ only
_Lcomplex ctan(
   _Lcomplex z
);  // C++ only
_Fcomplex ctanf(
   _Fcomplex z
);
_Lcomplex ctanl(
   _Lcomplex z
);
```

### <a name="parameters"></a>パラメーター

*z*<br/>
角度をラジアンで表す複素数。

## <a name="return-value"></a>戻り値

タンジェント*z*します。

|入力|SEH 例外|**_matherr**例外|
|-----------|-------------------|--------------------------|
|± ∞、QNAN、IND|none|_DOMAIN|
|± ∞ (**tan**、 **tanf**)|INVALID|_DOMAIN|

## <a name="remarks"></a>Remarks

C++では、オーバー ロードのオーバー ロードを呼び出すことができます**ctan**を受け取って返す **_Fcomplex**と **_Lcomplex**値。 C プログラムで**ctan**は、 **_Dcomplex**値。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|C ヘッダー|C++ ヘッダー|
|-------------|--------------|------------------|
|**ctan**、 **ctanf**、 **ctanl**|\<complex.h>|\<ccomplex>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[関数リファレンス (アルファベット順)](crt-alphabetical-function-reference.md)<br/>
[catanh、catanhf、catanhl](catanh-catanhf-catanhl.md)<br/>
[ctanh、ctanhf、ctanhl](ctanh-ctanhf-ctanhl.md)<br/>
[catan、catanf、catanl](catan-catanf-catanl.md)<br/>
[csinh、csinhf、csinhl](csinh-csinhf-csinhl.md)<br/>
[casinh、casinhf、casinhl](casinh-casinhf-casinhl.md)<br/>
[ccosh、ccoshf、ccoshl](ccosh-ccoshf-ccoshl.md)<br/>
[cacosh、cacoshf、cacoshl](cacosh-cacoshf-cacoshl.md)<br/>
[cacos、cacosf、cacosl](cacos-cacosf-cacosl.md)<br/>
[csin、csinf、csinl](csin-csinf-csinl.md)<br/>
[casin、casinf、casinl](casin-casinf-casinl.md)<br/>
[ccos、ccosf、ccosl](ccos-ccosf-ccosl.md)<br/>
[csqrt、csqrtf、csqrtl](csqrt-csqrtf-csqrtl.md)<br/>
