---
title: _fseek_nolock、_fseeki64_nolock
ms.date: 11/04/2016
apiname:
- _fseek_nolock
- _fseeki64_nolock
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _fseek_nolock
- _fseeki64_nolock
- fseek_nolock
- fseeki64_nolock
helpviewer_keywords:
- _fseek_nolock function
- fseeki64_nolock function
- file pointers [C++], moving
- fseek_nolock function
- _fseeki64_nolock function
- seek file pointers
ms.assetid: 2dd4022e-b715-462b-b935-837561605a02
ms.openlocfilehash: 57e9a57223d6af620f4f9160923675b4873ab3ad
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62287702"
---
# <a name="fseeknolock-fseeki64nolock"></a>_fseek_nolock、_fseeki64_nolock

指定した場所にファイル ポインターを移動します。

## <a name="syntax"></a>構文

```C
int _fseek_nolock(
   FILE *stream,
   long offset,
   int origin
);
int _fseeki64_nolock(
   FILE *stream,
   __int64 offset,
   int origin
);
```

### <a name="parameters"></a>パラメーター

*stream*<br/>
**FILE** 構造体へのポインター。

*オフセット*<br/>
*配信元*からのバイト数。

*配信元*<br/>
最初の位置。

## <a name="return-value"></a>戻り値

同じ[fseek](fseek-fseeki64.md)と[_fseeki64](fseek-fseeki64.md)、それぞれします。

## <a name="remarks"></a>Remarks

これらの関数は、ロックしないバージョンの[fseek](fseek-fseeki64.md)と[_fseeki64](fseek-fseeki64.md)、それぞれします。 これらは同じ[fseek](fseek-fseeki64.md)と[_fseeki64](fseek-fseeki64.md)する点を除いて、他のスレッドによる干渉から保護されません。 これらの関数では他のスレッドをロックアウトするオーバーヘッドが発生しないため、処理が速くなる場合があります。 これらの関数は、シングルスレッド アプリケーション、呼び出し元のスコープで既にスレッド分離を処理している場合などのスレッドセーフなコンテキストでのみ使用してください。

## <a name="requirements"></a>必要条件

|関数|必須ヘッダー|
|--------------|---------------------|
|**_fseek_nolock**、 **_fseeki64_nolock**|\<stdio.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[ストリーム入出力](../../c-runtime-library/stream-i-o.md)<br/>
[ftell、_ftelli64](ftell-ftelli64.md)<br/>
[_lseek、_lseeki64](lseek-lseeki64.md)<br/>
[rewind](rewind.md)<br/>
