---
title: _except_handler3
ms.date: 11/04/2016
apiname:
- _except_handler3
apilocation:
- msvcrt.dll
- msvcr90.dll
- msvcr80.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr100.dll
- msvcr110.dll
apitype: DLLExport
f1_keywords:
- _except_handler3
- except_handler3
helpviewer_keywords:
- _except_handler3 function
- except_handler3 function
ms.assetid: b0c64898-0ae5-48b7-9724-80135a0813e2
ms.openlocfilehash: 0dfe007d7b444401accbf547674f96f7f7d54ac1
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/11/2019
ms.locfileid: "57741318"
---
# <a name="excepthandler3"></a>_except_handler3

内部 CRT 関数。 現在の例外を処理する適切な例外ハンドラーを見つけるためにフレームワークによって使用されます。

## <a name="syntax"></a>構文

```
int _except_handler3(
   PEXCEPTION_RECORD exception_record,
   PEXCEPTION_REGISTRATION registration,
   PCONTEXT context,
   PEXCEPTION_REGISTRATION dispatcher
);
```

#### <a name="parameters"></a>パラメーター

*exception_record*<br/>
[in] 特定の例外に関する情報。

*registration*<br/>
[in] 例外ハンドラーを見つけるために使用する必要があるスコープ テーブルを示すレコード。

*context*<br/>
[in] 予約されています。

*dispatcher*<br/>
[in] 予約されています。

## <a name="return-value"></a>戻り値

例外を破棄する必要がある場合は、`DISPOSITION_DISMISS` を返します。 カプセル化する例外ハンドラーにレベルを上げて例外を渡す必要がある場合は、`DISPOSITION_CONTINUE_SEARCH` を返します。

## <a name="remarks"></a>解説

適切な例外ハンドラーが見つかった場合、このメソッドはそのハンドラーに例外を渡します。 この状況では、このメソッドはそれを呼び出したコードには戻らず、戻り値は無関係です。

## <a name="see-also"></a>関連項目

[関数リファレンス (アルファベット順)](../c-runtime-library/reference/crt-alphabetical-function-reference.md)
