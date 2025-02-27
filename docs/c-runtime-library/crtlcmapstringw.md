---
title: __crtLCMapStringW
ms.date: 11/04/2016
apiname:
- __crtLCMapStringW
apilocation:
- msvcr90.dll
- msvcr110_clr0400.dll
- msvcr100.dll
- msvcrt.dll
- msvcr120.dll
- msvcr110.dll
- msvcr80.dll
apitype: DLLExport
f1_keywords:
- __crtLCMapStringW
helpviewer_keywords:
- __crtLCMapStringW
ms.assetid: 45b4ac0e-438c-4fa3-b4d1-34195f4467d9
ms.openlocfilehash: e79ac5d4072595ef1034a0483b9edc8eada916d8
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/15/2019
ms.locfileid: "69500216"
---
# <a name="__crtlcmapstringw"></a>__crtLCMapStringW

1 つの文字列を別の文字列にマップして、指定したロケールに依存する変換を実行します。 この関数を使用して入力文字列の並べ替えキーを生成することもできます。

## <a name="syntax"></a>構文

```cpp
int __crtLCMapStringW(
   LCID    Locale,
   DWORD   dwMapFlags,
   LPCWSTR lpSrcStr,
   int     cchSrc,
   LPWSTR  lpDestStr,
   int     cchDest)
```

#### <a name="parameters"></a>パラメーター

*ロケール*<br/>
ロケール識別子。 ロケールは、文字列のマッピングまたは並べ替えキーの生成のためのコンテキストを提供します。 アプリケーションは、 `MAKELCID` マクロを使用してロケール識別子を作成できます。

*dwMapFlags*<br/>
文字列のマッピングまたは並べ替えキーの生成時に使用する変換の種類。

*lpSrcStr*<br/>
関数によってマップされるソース文字列か、関数によって並べ替えキーの生成に使用されるソース文字列へのポインター。 このパラメーターでは、Unicode 文字列が想定されます。

*cchSrc*<br/>
`lpSrcStr` パラメーターによって示される文字列の文字のサイズ。 この数には、null 終端文字を含めることも除外することもできます。

`cchSrc` に値 -1 を設定した場合、`lpSrcStr` で指し示される文字列は null で終端します。 この指定と共にこの関数を文字列マッピング モードで使用した場合、この関数は文字列の長さをそれ自体で計算し、 `*lpDestStr`に格納されるマッピングされた文字列を null で終端します。

*lpDestStr*<br/>
マッピングされた文字列または並べ替えキーが関数によって格納されるバッファーへの long ポインター。

*cchDest*<br/>
`lpDestStr`で指し示されるバッファーのサイズ (文字単位)。

## <a name="return-value"></a>戻り値

`cchDest` の値が 0 以外の場合、バッファーに書き込まれた文字数 (または `LCMAP_SORTKEY` が指定された場合はバイト数) は成功を示します。 この数には、null 終端文字の分が含まれています。

`cchDest` の値が 0 の場合、翻訳された文字列または並べ替えキーを受け取るのに必要なバッファーのサイズ (文字数。 `LCMAP_SORTKEY` が指定された場合はバイト数) は成功を示します。 このサイズには、null 終端文字の分が含まれています。

0 は失敗を示します。 拡張されたエラー情報を取得するには、 `GetLastError` 関数を呼び出します。

## <a name="remarks"></a>解説

`cchSrc` が 0 より大きく、 `lpSrcStr` が null で終わる文字列の場合、 `__crtLCMapStringW` は `cchSrc` を文字列の長さに設定します。 次に、 `__crtLCMapStringW` は、 `LCMapString` のワイド文字列 (Unicode) バージョンを指定されたパラメーターで呼び出します。 この関数のパラメーターと戻り値の詳細については、[LCMapString](/windows/win32/api/winnls/nf-winnls-lcmapstringw)に関するページを参照してください。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|__crtLCMapStringW|awint.h|