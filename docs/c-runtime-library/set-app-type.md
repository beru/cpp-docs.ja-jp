---
title: _set_app_type
ms.date: 11/04/2016
apiname:
- _set_app_type
apilocation:
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _set_app_type
- corecrt_startup/_set_app_type
ms.assetid: 1e7fe786-b587-4116-8c05-f7d762350100
ms.openlocfilehash: 5a29fd94cca7fdbf6bbb24699b7f510bf1465f15
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/11/2019
ms.locfileid: "57749192"
---
# <a name="setapptype"></a>_set_app_type

アプリがコンソール アプリと GUI アプリのどちらであるかを CRT に知らせるためにスタートアップ時に使用する内部関数です。

## <a name="syntax"></a>構文

```cpp
typedef enum _crt_app_type
{
    _crt_unknown_app,
    _crt_console_app,
    _crt_gui_app
} _crt_app_type;

void __cdecl _set_app_type(
    _crt_app_type appType
    );
```

## <a name="parameters"></a>パラメーター

*appType*<br/>
アプリケーションの種類を示す値。 次の値を指定できます。

|[値]|説明|
|----------------|-----------------|
|_crt_unknown_app|不明なアプリケーションの種類。|
|_crt_console_app|コンソール (コマンドライン) アプリケーション。|
|_crt_gui_app|GUI (Windows) アプリケーション。|

## <a name="remarks"></a>解説

通常は、この関数を呼び出す必要はありません。 この関数は、アプリ内での `main` の呼び出し前に実行される C のランタイム スタートアップ コードに含まれています。

## <a name="requirements"></a>要件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|_set_app_type|process.h|
