---
title: XMMWORD
ms.date: 08/30/2018
f1_keywords:
- XMMWORD
helpviewer_keywords:
- XMMWORD directive
ms.assetid: 18026d32-5cab-403e-ad7e-382fb41aa9b8
ms.openlocfilehash: 59d1ba71260ed08b761c332e887cf27517762303
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62210106"
---
# <a name="xmmword"></a>XMMWORD

MMX と SSE (XMM) の手順では、128 ビットのマルチ メディア オペランドに使用されます。

## <a name="syntax"></a>構文

> XMMWORD

## <a name="remarks"></a>Remarks

`XMMWORD` 同じ型を表すために、 [_ _m128](../../cpp/m128.md)します。

## <a name="example"></a>例

```asm
    movdqa   xmm0, xmmword ptr [ebx]
```