---
title: _lrotl、_lrotr
ms.date: 04/04/2018
apiname:
- _lrotl
- _lrotr
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
- api-ms-win-crt-utility-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- lrotr
- lrotl
- _lrotr
- _lrotl
helpviewer_keywords:
- lrotl function
- bits
- _lrotr function
- lrotr function
- rotating bits
- _lrotl function
- bits, rotating
ms.assetid: d42f295b-35f9-49d2-9ee4-c66896ffe68e
ms.openlocfilehash: 71ca61676e4551155f9f14e792c5c1cee65ddb7e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62156968"
---
# <a name="lrotl-lrotr"></a>_lrotl、_lrotr

左側のビットを回転 (**_lrotl**) または右 (**_lrotr**)。

## <a name="syntax"></a>構文

```C
unsigned long _lrotl( unsigned long value, int shift );
unsigned long _lrotr( unsigned long value, int shift );
```

### <a name="parameters"></a>パラメーター

*value*<br/>
回転させる値。

*shift*<br/>
*value* をシフトするビット数。

## <a name="return-value"></a>戻り値

どちらの関数も、回転後の値を返します。 エラーの戻り値はありません。

## <a name="remarks"></a>Remarks

**_Lrotl**と **_lrotr**関数回転*値*によって*shift*ビット。 **_lrotl**は値を最上位ビットに向かって、左に回転します。 **_lrotr**重要度の低いビットに向かって、値右方向に回転します。 どちらの関数でも、回転により *value* の一端から溢れたビットは他端に折り返されます。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_lrotl**、 **_lrotr**|\<stdlib.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_lrot.c

#include <stdlib.h>
#include <stdio.h>

int main( void )
{
   unsigned long val = 0x0fac35791;

   printf( "0x%8.8lx rotated left eight bits is 0x%8.8lx\n",
            val, _lrotl( val, 8 ) );
   printf( "0x%8.8lx rotated right four bits is 0x%8.8lx\n",
            val, _lrotr( val, 4 ) );
}
```

```Output
0xfac35791 rotated left eight bits is 0xc35791fa
0xfac35791 rotated right four bits is 0x1fac3579
```

## <a name="see-also"></a>関連項目

[浮動小数点サポート](../../c-runtime-library/floating-point-support.md)<br/>
[_rotl、_rotl64、_rotr、_rotr64](rotl-rotl64-rotr-rotr64.md)<br/>
