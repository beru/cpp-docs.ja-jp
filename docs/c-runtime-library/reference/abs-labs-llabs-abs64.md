---
title: abs、labs、llabs、_abs64
ms.date: 04/05/2018
apiname:
- abs
- _abs64
- labs
- llabs
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
- stdlib/_abs64
- math/abs
- _abs64
- abs
- labs
- math/labs
- llabs
- math/llabs
- cmath/abs
helpviewer_keywords:
- absolute values
- abs function
- abs64 function
- _abs64 function
- calculating absolute values
ms.assetid: 60f789d1-4a1e-49f5-9e4e-0bdb277ea26a
ms.openlocfilehash: 61aa0a48757a35708ffb85d2c0525bb4eac82d56
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62341991"
---
# <a name="abs-labs-llabs-abs64"></a>abs、labs、llabs、_abs64

引数の絶対値を計算します。

## <a name="syntax"></a>構文

```C
int abs( int n );
long labs( long n );
long long llabs( long long n );
__int64 _abs64( __int64 n );
```

```cpp
long abs( long n );   // C++ only
long long abs( long long n );   // C++ only
double abs( double n );   // C++ only
long double abs( long double n );   // C++ only
float abs( float n );   // C++ only
```

### <a name="parameters"></a>パラメーター

*n*<br/>
数値。

## <a name="return-value"></a>戻り値

**Abs**、 **labs**、 **llabs**と **_abs64**関数がパラメーターの絶対値を返す*n*. エラーの戻り値はありません。

## <a name="remarks"></a>Remarks

オーバー ロードを呼び出すことができますので、C++ ではオーバー ロード、 **abs**を受け取って返す**長い**、**長い** **長い**、 **float**、**二重**、および**長い** **二重**値。 これらのオーバーロードは \<cmath> ヘッダーで定義されています。 C プログラムで**abs**は、 **int**します。

**Microsoft 固有の仕様**:整数型を使用して表すことができる負の整数の範囲は、正の整数が表すことができる範囲より大きいため、変換できないこれらの関数に引数を指定できます。 引数の絶対値を戻り値の型で表すことができない場合、 **abs**関数が変更されていない引数の値を返します。 具体的には、`abs(INT_MIN)` は `INT_MIN` を返し、`labs(LONG_MIN)` は `LONG_MIN` を返します。また `llabs(LLONG_MIN)` は `LLONG_MIN` を返し、`_abs64(_I64_MIN)` は `_I64_MIN` を返します。 つまり、 **abs**関数を使用して、正の値を保証することはできません。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須の C ヘッダー|必須の C++ ヘッダー|
|-------------|-----------------------|---------------------------|
|**abs**、 **labs**、 **llabs**|\<math.h> または \<stdlib.h>|\<cmath>、\<cstdlib>、\<stdlib.h>、または \<math.h>|
|**_abs64**|\<stdlib.h>|\<cstdlib> または \<stdlib.h>|

オーバー ロードされたバージョンを使用する**abs** C++ では、含める必要がありますが、 \<cmath > ヘッダー。

## <a name="example"></a>例

次のプログラムでは、複数の数値の絶対値を計算して表示します。

```C
// crt_abs.c
// Build: cl /W3 /TC crt_abs.c
// This program demonstrates the use of the abs function
// by computing and displaying the absolute values of
// several numbers.

#include <stdio.h>
#include <math.h>
#include <stdlib.h>
#include <limits.h>

int main( void )
{
    int ix = -4;
    long lx = -41567L;
    long long llx = -9876543210LL;
    __int64 wx = -1;

    // absolute 32 bit integer value
    printf_s("The absolute value of %d is %d\n", ix, abs(ix));

    // absolute long integer value
    printf_s("The absolute value of %ld is %ld\n", lx, labs(lx));

    // absolute long long integer value
    printf_s("The absolute value of %lld is %lld\n", llx, llabs(llx));

    // absolute 64 bit integer value
    printf_s("The absolute value of 0x%.16I64x is 0x%.16I64x\n", wx,
        _abs64(wx));

    // Integer error cases:
    printf_s("Microsoft implementation-specific results:\n");
    printf_s(" abs(INT_MIN) returns %d\n", abs(INT_MIN));
    printf_s(" labs(LONG_MIN) returns %ld\n", labs(LONG_MIN));
    printf_s(" llabs(LLONG_MIN) returns %lld\n", llabs(LLONG_MIN));
    printf_s(" _abs64(_I64_MIN) returns 0x%.16I64x\n", _abs64(_I64_MIN));
}
```

```Output
The absolute value of -4 is 4
The absolute value of -41567 is 41567
The absolute value of -9876543210 is 9876543210
The absolute value of 0xffffffffffffffff is 0x0000000000000001
Microsoft implementation-specific results:
abs(INT_MIN) returns -2147483648
labs(LONG_MIN) returns -2147483648
llabs(LLONG_MIN) returns -9223372036854775808
_abs64(_I64_MIN) returns 0x8000000000000000
```

## <a name="see-also"></a>関連項目

[データ変換](../../c-runtime-library/data-conversion.md)<br/>
[浮動小数点サポート](../../c-runtime-library/floating-point-support.md)<br/>
[_cabs](cabs.md)<br/>
[fabs、fabsf、fabsl](fabs-fabsf-fabsl.md)<br/>
[imaxabs](imaxabs.md)