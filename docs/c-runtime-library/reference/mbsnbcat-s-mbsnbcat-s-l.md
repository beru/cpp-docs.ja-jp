---
title: _mbsnbcat_s、_mbsnbcat_s_l
ms.date: 11/04/2016
apiname:
- _mbsnbcat_s_l
- _mbsnbcat_s
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
- api-ms-win-crt-multibyte-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _mbsnbcat_s
- mbsnbcat_s
- _mbsnbcat_s_l
- mbsnbcat_s_l
helpviewer_keywords:
- _tcsncat function
- mbsnbcat_s function
- _mbsnbcat_s function
- _mbsnbcat_s_l function
- _tcsncat_s_l function
- tcsncat_s_l function
- mbsnbcat_s_l function
- tcsncat function
ms.assetid: 2c9e9be7-d979-4a54-8ada-23428b6648a9
ms.openlocfilehash: d7e7a9d121336486e590ca3bd9e3967b02a2df08
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62331526"
---
# <a name="mbsnbcats-mbsnbcatsl"></a>_mbsnbcat_s、_mbsnbcat_s_l

最大で 1 つ目のマルチバイト文字の文字列に追加します**n**もう 1 つのマルチバイト文字列のバイト数。 これらは、「[CRT のセキュリティ機能](../../c-runtime-library/security-features-in-the-crt.md)」の説明にあるとおり、セキュリティが強化されたバージョンの [_mbsnbcat、_mbsnbcat_l](mbsnbcat-mbsnbcat-l.md) です。

> [!IMPORTANT]
> この API は、Windows ランタイムで実行するアプリケーションでは使用できません。 詳細については、「[ユニバーサル Windows プラットフォーム アプリでサポートされていない CRT 関数](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)」を参照してください。

## <a name="syntax"></a>構文

```C
errno_t _mbsnbcat_s(
   unsigned char *dest,
   size_t sizeInBytes,
   const unsigned char *src,
   size_t count
);
errno_t _mbsnbcat_s_l(
   unsigned char *dest,
   size_t sizeInBytes,
   const unsigned char *src,
   size_t count,
   _locale_t locale
);
template <size_t size>
errno_t _mbsnbcat_s(
   unsigned char (&dest)[size],
   const unsigned char *src,
   size_t count
); // C++ only
template <size_t size>
errno_t _mbsnbcat_s_l(
   unsigned char (&dest)[size],
   const unsigned char *src,
   size_t count,
   _locale_t locale
); // C++ only
```

### <a name="parameters"></a>パラメーター

*dest*<br/>
NULL で終わるマルチバイト文字のコピー先文字列。

*sizeInBytes*<br/>
サイズ、 *dest*バッファー (バイト単位)。

*src*<br/>
NULL で終わるマルチバイト文字のコピー元文字列。

*count*<br/>
バイト数*src*に追加する*dest*します。

*locale*<br/>
使用するロケール。

## <a name="return-value"></a>戻り値

正常に終了した場合は 0 を返し、それ以外の場合はエラー コードを返します。

### <a name="error-conditions"></a>エラー条件

|**追加先**|*sizeInBytes*|*src*|戻り値|
|------------|-------------------|-----------|------------------|
|**NULL**|任意|任意|**EINVAL**|
|どれでも可|<= 0|任意|**EINVAL**|
|どれでも可|任意|**NULL**|**EINVAL**|

いずれかのエラー条件が発生すると、この関数は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」の説明にあるとおり無効なパラメーター エラーを生成します。 エラーが処理されるかどうか、関数を返します**EINVAL**設定と**errno**に**EINVAL**します。

## <a name="remarks"></a>Remarks

**_Mbsnbcat_s**に関数を追加します*dest*、最大で 1 つ目*カウント*バイトの*src*します。場合は、null 文字の直前にあるバイト*dest*が先行バイトの最初のバイトによって上書きされます*src*します。それ以外の場合、最初のバイトの*src*の終端の null 文字を上書き*dest*します。 Null バイトが表示される場合*src*する前に*カウント*バイトが追加され、 **_mbsnbcat_s**からすべてのバイトを追加します*src*、まで、null。文字。 場合*カウント*がの長さより大きい*src*の長さ*src*の代わりに使用されます*カウント*します。 結果の文字列は null 文字で終了します。 重なり合う文字列間でコピーした場合の動作は未定義です。

出力値の設定に影響は、 **LC_CTYPE**ロケールのカテゴリの設定; を参照してください[setlocale、_wsetlocale](setlocale-wsetlocale.md)詳細についてはします。 いないことを除いて、これらの関数のバージョンは同じですが、 **_l**サフィックスを使用して、現在のロケールが付いている、 **_l**サフィックスは、ロケール パラメーターを代わりに使用します。渡されます。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

C++ では、テンプレートのオーバーロードを利用すると、これらの関数の使用が簡素化されます。オーバーロードでは、バッファー長が自動的に推論されるのでサイズ引数を指定する必要がなくなるだけでなく、古くてセキュリティが万全ではない関数を新しくてセキュリティが強化された関数に自動的に置き換えることができます。 詳細については、「 [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md)」を参照してください。

これらの関数のデバッグ バージョンは、最初にバッファーを 0xFD で埋めます。 この動作を無効にするには、[_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md) を使用します。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|Tchar.h のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tcsncat**|[strncat](strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)|**_mbsnbcat_s**|[wcsncat](strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)|
|**_tcsncat_s_l**|**_strncat_s_l**|**_mbsnbcat_s_l**|**_wcsncat_s_l**|

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_mbsnbcat_s**|\<mbstring.h>|
|**_mbsnbcat_s_l**|\<mbstring.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[文字列操作](../../c-runtime-library/string-manipulation-crt.md)<br/>
[_mbsnbcmp、_mbsnbcmp_l](mbsnbcmp-mbsnbcmp-l.md)<br/>
[_strncnt、_wcsncnt、_mbsnbcnt、_mbsnbcnt_l、_mbsnccnt、_mbsnccnt_l](strncnt-wcsncnt-mbsnbcnt-mbsnbcnt-l-mbsnccnt-mbsnccnt-l.md)<br/>
[_mbsnbcpy、_mbsnbcpy_l](mbsnbcpy-mbsnbcpy-l.md)<br/>
[_mbsnbcpy_s、_mbsnbcpy_s_l](mbsnbcpy-s-mbsnbcpy-s-l.md)<br/>
[_mbsnbset、_mbsnbset_l](mbsnbset-mbsnbset-l.md)<br/>
[strncat、_strncat_l、wcsncat、_wcsncat_l、_mbsncat、_mbsncat_l](strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)<br/>
[strncat_s、_strncat_s_l、wcsncat_s、_wcsncat_s_l、_mbsncat_s、_mbsncat_s_l](strncat-s-strncat-s-l-wcsncat-s-wcsncat-s-l-mbsncat-s-mbsncat-s-l.md)<br/>
