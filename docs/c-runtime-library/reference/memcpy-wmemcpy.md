---
title: memcpy、wmemcpy
ms.date: 11/04/2016
apiname:
- memcpy
- wmemcpy
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
- ntoskrnl.exe
apitype: DLLExport
f1_keywords:
- wmemcpy
- memcpy
helpviewer_keywords:
- wmemcpy function
- memcpy function
ms.assetid: 34abb90b-bffb-46dc-a2f3-a5e9940839d6
ms.openlocfilehash: f687e231060c287e206017dc61fe1d5193d8f0de
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/15/2019
ms.locfileid: "69499641"
---
# <a name="memcpy-wmemcpy"></a>memcpy、wmemcpy

バッファー間でバイトをコピーします。 これらの関数のセキュリティを強化したバージョンについては、「[memcpy_s、wmemcpy_s](memcpy-s-wmemcpy-s.md)」をご覧ください。

## <a name="syntax"></a>構文

```C
void *memcpy(
   void *dest,
   const void *src,
   size_t count
);
wchar_t *wmemcpy(
   wchar_t *dest,
   const wchar_t *src,
   size_t count
);
```

### <a name="parameters"></a>パラメーター

*dest*<br/>
コピー先のバッファー。

*src*<br/>
コピー元のバッファー。

*count*<br/>
コピーする文字数。

## <a name="return-value"></a>戻り値

*Dest*の値。

## <a name="remarks"></a>Remarks

**memcpy**は、 *src*から*dest*へのバイト*数*をコピーします。**wmemcpy**は、*数*のワイド文字 (2 バイト) をコピーします。 コピー元とコピー先が重複する場合、 **memcpy**の動作は未定義です。 重複する領域を処理するには、 **memmove**を使用します。

> [!IMPORTANT]
> コピー先のバッファーが、ソース バッファーと同じサイズ、または大きいサイズであることを確認してください。 詳しくは、「 [バッファー オーバーランの回避](/windows/win32/SecBP/avoiding-buffer-overruns)」をご覧ください。

> [!IMPORTANT]
> 多くのバッファーオーバーランが発生し、セキュリティ攻撃の可能性があるため、 **memcpy**の不適切な使用に対してトレースされているので、この関数は、セキュリティ開発ライフサイクル (SDL) によって "禁止されている" 機能の中に一覧表示されます。  一部の VC + + ライブラリクラスでは、引き続き**memcpy**が使用されていることがわかります。  さらに、VC + + コンパイラオプティマイザーが**memcpy**の呼び出しを生成することがあります。  Visual C++ 製品は SDL のプロセスに従って開発されているため、この禁止関数の利用は綿密に評価されてきました。  ライブラリがこれを使用する場合、これらの呼び出しによってバッファー オーバーランが許可されないよう、慎重に調査されてきました。  コンパイラの場合、場合によっては、特定のコードパターンが**memcpy**のパターンと同一であると認識され、その結果、関数の呼び出しに置き換えられることがあります。  このような場合、 **memcpy**の使用は元の手順よりも安全ではありません。これらは、パフォーマンスチューニングされた**memcpy**関数の呼び出しに最適化されています。  「安全」な CRT 関数を使用しても安全性が保証されるわけではない (安全でない状態になりにくいということに過ぎない) ように、「禁止された」関数を使用しても、危険であると保証されるわけではありません (安全性を保障するのに、より大きな監視が必要になるに過ぎません)。
>
> VC + + コンパイラとライブラリによる**memcpy**の使用は慎重に調査されているため、これらの呼び出しは、他の方法で SDL に準拠しているコード内で許可されます。  アプリケーションのソースコードで導入された**memcpy**呼び出しは、その使用がセキュリティの専門家によって確認されている場合にのみ、SDL に準拠しています。

次の例のように、関数を非推奨にするために、_CRT_SECURE_DEPRECATE_MEMORY 関数は、include ステートメントの前に定数が定義されている場合にのみ非推奨となります。

```C
#define _CRT_SECURE_DEPRECATE_MEMORY
#include <memory.h>
```

または

```C
#define _CRT_SECURE_DEPRECATE_MEMORY
#include <wchar.h>
```

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**memcpy**|\<memory.h> または \<string.h>|
|**wmemcpy**|\<wchar.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

**Memcpy**の使用方法のサンプルについては、「 [memmove](memmove-wmemmove.md) 」を参照してください。

## <a name="see-also"></a>関連項目

[バッファー操作](../../c-runtime-library/buffer-manipulation.md)<br/>
[_memccpy](memccpy.md)<br/>
[memchr、wmemchr](memchr-wmemchr.md)<br/>
[memcmp、wmemcmp](memcmp-wmemcmp.md)<br/>
[memmove、wmemmove](memmove-wmemmove.md)<br/>
[memset、wmemset](memset-wmemset.md)<br/>
[strcpy_s、wcscpy_s、_mbscpy_s](strcpy-s-wcscpy-s-mbscpy-s.md)<br/>
[strncpy_s、_strncpy_s_l、wcsncpy_s、_wcsncpy_s_l、_mbsncpy_s、_mbsncpy_s_l](strncpy-s-strncpy-s-l-wcsncpy-s-wcsncpy-s-l-mbsncpy-s-mbsncpy-s-l.md)<br/>
