---
title: _cgets_s、_cgetws_s
ms.date: 11/04/2016
apiname:
- _cgetws_s
- _cgets_s
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
- api-ms-win-crt-conio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _cgets_s
- cgets_s
- cgetws_s
- _cgetws_s
helpviewer_keywords:
- strings [C++], getting from console
- console, getting strings from
- _cgets_s function
- cget_s function
- _cgetws_s function
- cgetws_s function
ms.assetid: 38b74897-afe6-4dd9-a43f-36a3c0d72c5c
ms.openlocfilehash: 8341b775df3b9cbaececdfaa1f17e075d7c7416c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62340586"
---
# <a name="cgetss-cgetwss"></a>_cgets_s、_cgetws_s

コンソールから文字列を取得します。 これらのバージョンの [_cgets および _cgetws](../../c-runtime-library/cgets-cgetws.md) は、「[CRT のセキュリティ機能](../../c-runtime-library/security-features-in-the-crt.md)」の説明にあるとおり、セキュリティが強化されたバージョンです。

> [!IMPORTANT]
> この API は、Windows ランタイムで実行するアプリケーションでは使用できません。 詳細については、「[ユニバーサル Windows プラットフォーム アプリでサポートされていない CRT 関数](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)」を参照してください。

## <a name="syntax"></a>構文

```C
errno_t _cgets_s(
   char *buffer,
   size_t numberOfElements,
   size_t *pSizeRead
);
errno_t _cgetws_s(
   wchar_t *buffer
   size_t numberOfElements,
   size_t *pSizeRead
);
template <size_t size>
errno_t _cgets_s(
   char (&buffer)[size],
   size_t *pSizeRead
); // C++ only
template <size_t size>
errno_t _cgetws_s(
   wchar_t (&buffer)[size],
   size_t *pSizeRead
); // C++ only
```

### <a name="parameters"></a>パラメーター

*バッファー*<br/>
データの格納場所。

*numberOfElements*<br/>
バッファーのサイズです。単位はバイト数またワイド文字数です。これは、読み取る最大の文字数でもあります。

*pSizeRead*<br/>
実際に読み取った文字数。

## <a name="return-value"></a>戻り値

成功した場合の戻り値は 0 です。それ以外の場合 (エラー発生時) は、エラー コードです。

### <a name="error-conditions"></a>エラー条件

|*バッファー*|*numberOfElements*|*pSizeRead*|Return|内容*バッファー*|
|--------------|------------------------|-----------------|------------|--------------------------|
|**NULL**|任意|任意|**EINVAL**|適用なし|
|いない**NULL**|ゼロ|任意|**EINVAL**|変更されない|
|いない**NULL**|任意|**NULL**|**EINVAL**|長さゼロの文字列|

## <a name="remarks"></a>Remarks

**_cgets_s**と **_cgetws_s**コンソールから文字列を読み取るし、(null 終端文字の場合)、文字列をコピー*バッファー*します。 **_cgetws_s**はこの関数のワイド文字バージョンは、以外の文字のサイズ、これら 2 つの関数の動作は同じです。 読み取る文字列の最大サイズとして渡される、 *numberOfElements*パラメーター。 このサイズには、終端の null に対応する追加の文字を含める必要があります。 読み取られた文字数が実際に配置されます*読み取ら*します。

操作中に、またはパラメーターを検証する際にエラーが発生した場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」の説明にあるとおり無効なパラメーター ハンドラーが呼び出されます。 続けるには、実行が許可された場合**errno**に設定されている**EINVAL**と**EINVAL**が返されます。

C++ では、テンプレートのオーバーロードを利用すると、これらの関数の使用が簡素化されます。オーバーロードでは、バッファー長が自動的に推論されるのでサイズ引数を指定する必要がなくなるだけでなく、古くてセキュリティが万全ではない関数を新しくてセキュリティが強化された関数に自動的に置き換えることができます。 詳細については、「 [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md)」を参照してください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|Tchar.h のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_cgetts_s**|**_cgets_s**|**_cgets_s**|**_cgetws_s**|

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_cgets_s**|\<conio.h>|
|**_cgetws_s**|\<conio.h> または \<wchar.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[コンソール入出力とポート入出力](../../c-runtime-library/console-and-port-i-o.md)<br/>
[_getch、_getwch](getch-getwch.md)<br/>
