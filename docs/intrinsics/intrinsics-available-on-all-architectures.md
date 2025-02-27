---
title: すべてのアーキテクチャで使用可能な組み込みクラス
ms.date: 09/02/2019
helpviewer_keywords:
- cl.exe compiler, intrinsics
ms.assetid: 1fe3958e-d2fe-4188-8e34-5896738246eb
ms.openlocfilehash: 6550c97a8d4efae29318d48ed8cab43b85b135f4
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/03/2019
ms.locfileid: "70217533"
---
# <a name="intrinsics-available-on-all-architectures"></a>すべてのアーキテクチャで使用可能な組み込みクラス

Microsoft C/C++コンパイラとユニバーサル C ランタイムライブラリ (ucrt) は、一部の組み込みをすべてのアーキテクチャで使用できるようにします。

## <a name="compiler-intrinsics"></a>コンパイラの組み込み

X86、AMD64、ARM、および ARM64 の各アーキテクチャでは、次の組み込み関数を使用できます。

|組み込み|Header|
|---------------|------------|
|[_AddressOfReturnAddress](../intrinsics/addressofreturnaddress.md)|intrin.h|
|[_BitScanForward](../intrinsics/bitscanforward-bitscanforward64.md)|intrin.h|
|[_BitScanReverse](../intrinsics/bitscanreverse-bitscanreverse64.md)|intrin.h|
|[_bittest](../intrinsics/bittest-bittest64.md)|intrin.h|
|[_bittestandcomplement](../intrinsics/bittestandcomplement-bittestandcomplement64.md)|intrin.h|
|[_bittestandreset](../intrinsics/bittestandreset-bittestandreset64.md)|intrin.h|
|[_bittestandset](../intrinsics/bittestandset-bittestandset64.md)|intrin.h|
__ codeseg |[__debugbreak](../intrinsics/debugbreak.md)|. h | |[disable](../intrinsics/disable.md)| @ in .h | |[_enable](../intrinsics/enable.md)|. h | |[__ fastfail](../intrinsics/fastfail.md)| 自分の. h | |[_InterlockedAnd](../intrinsics/interlockedand-intrinsic-functions.md)|. h | |[_InterlockedAnd16](../intrinsics/interlockedand-intrinsic-functions.md)|. h | |[_InterlockedAnd8](../intrinsics/interlockedand-intrinsic-functions.md)|. h | |[_interlockedbittestandreset](../intrinsics/interlockedbittestandreset-intrinsic-functions.md)|. h | |[_interlockedbittestandset](../intrinsics/interlockedbittestandset-intrinsic-functions.md)|. h | |[_InterlockedCompareExchange](../intrinsics/interlockedcompareexchange-intrinsic-functions.md)|. h | |[_InterlockedCompareExchange16](../intrinsics/interlockedcompareexchange-intrinsic-functions.md)|. h | |[_InterlockedCompareExchange8](../intrinsics/interlockedcompareexchange-intrinsic-functions.md)|. h | |[_InterlockedCompareExchangePointer](../intrinsics/interlockedcompareexchangepointer-intrinsic-functions.md)|. h | |[_InterlockedDecrement](../intrinsics/interlockeddecrement-intrinsic-functions.md)|. h | |[_InterlockedDecrement16](../intrinsics/interlockeddecrement-intrinsic-functions.md)|. h | |[_InterlockedExchange](../intrinsics/interlockedexchange-intrinsic-functions.md)|. h | |[_InterlockedExchange16](../intrinsics/interlockedexchange-intrinsic-functions.md)|. h | |[_InterlockedExchange8](../intrinsics/interlockedexchange-intrinsic-functions.md)|. h | |[_InterlockedExchangeAdd](../intrinsics/interlockedexchangeadd-intrinsic-functions.md)|. h | |[_InterlockedExchangeAdd16](../intrinsics/interlockedexchangeadd-intrinsic-functions.md)|. h | |[_InterlockedExchangeAdd8](../intrinsics/interlockedexchangeadd-intrinsic-functions.md)|. h | |[_InterlockedExchangePointer](../intrinsics/interlockedexchangepointer-intrinsic-functions.md)|. h | |[_InterlockedIncrement](../intrinsics/interlockedincrement-intrinsic-functions.md)|. h | |[_InterlockedIncrement16](../intrinsics/interlockedincrement-intrinsic-functions.md)|. h | |[_InterlockedOr](../intrinsics/interlockedor-intrinsic-functions.md)|. h | |[_InterlockedOr16](../intrinsics/interlockedor-intrinsic-functions.md)|. h | |[_InterlockedOr8](../intrinsics/interlockedor-intrinsic-functions.md)|. h | |[_InterlockedXor](../intrinsics/interlockedxor-intrinsic-functions.md)|. h | |[_InterlockedXor16](../intrinsics/interlockedxor-intrinsic-functions.md)|. h | |[_InterlockedXor8](../intrinsics/interlockedxor-intrinsic-functions.md)|. h | |[__ nop](../intrinsics/nop.md)| に含まれています。[Readバリア](../intrinsics/readbarrier.md)| 存在する. h | |[Readwriteバリア](../intrinsics/readwritebarrier.md)| 存在します。 h | |[Returnaddress](../intrinsics/returnaddress.md)| @ in .h | |[_rotl16](../intrinsics/rotl8-rotl16.md)|. h | |[_rotl8](../intrinsics/rotl8-rotl16.md)|. h | |[rotr16](../intrinsics/rotr8-rotr16.md)| イントラネット内の. h | |[rotr8](../intrinsics/rotr8-rotr16.md)| 自分の. h | |[Writeバリア](../intrinsics/writebarrier.md)| 自分の場所. h |

## <a name="ucrt-intrinsics"></a>UCRT 組み込み

次の UCRT 関数には、すべてのアーキテクチャに固有のフォームがあります。

|組み込み|Header|
|---------------|------------|
|[abs](../c-runtime-library/reference/abs-labs-llabs-abs64.md)|stdlib.h|
|[_abs64](../c-runtime-library/reference/abs-labs-llabs-abs64.md)|stdlib.h|
|[acos](../c-runtime-library/reference/acos-acosf-acosl.md)|math.h|
|[acosf](../c-runtime-library/reference/acos-acosf-acosl.md)|math.h|
|[acosl](../c-runtime-library/reference/acos-acosf-acosl.md)|math.h|
|[_alloca](../c-runtime-library/reference/alloca.md)|malloc.h|
|[asin](../c-runtime-library/reference/asin-asinf-asinl.md)|math.h|
|[asinf](../c-runtime-library/reference/asin-asinf-asinl.md)|math.h|
|[asinl](../c-runtime-library/reference/asin-asinf-asinl.md)|math.h|
|[atan](../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)|math.h|
|[atan2](../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)|math.h|
|[atan2f](../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)|math.h|
|[atan2l](../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)|math.h|
|[atanf](../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)|math.h|
|[atanl](../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)|math.h|
|[_byteswap_uint64](../c-runtime-library/reference/byteswap-uint64-byteswap-ulong-byteswap-ushort.md)|stdlib.h|
|[_byteswap_ulong](../c-runtime-library/reference/byteswap-uint64-byteswap-ulong-byteswap-ushort.md)|stdlib.h|
|[_byteswap_ushort](../c-runtime-library/reference/byteswap-uint64-byteswap-ulong-byteswap-ushort.md)|stdlib.h|
|[ceil](../c-runtime-library/reference/ceil-ceilf-ceill.md)|math.h|
|[ceilf](../c-runtime-library/reference/ceil-ceilf-ceill.md)|math.h|
|[ceill](../c-runtime-library/reference/ceil-ceilf-ceill.md)|math.h|
|[cos](../c-runtime-library/reference/cos-cosf-cosl.md)|math.h|
|[cosf](../c-runtime-library/reference/cos-cosf-cosl.md)|math.h|
|[cosh](../c-runtime-library/reference/cosh-coshf-coshl.md)|math.h|
|[coshf](../c-runtime-library/reference/cosh-coshf-coshl.md)|math.h|
|[coshl](../c-runtime-library/reference/cosh-coshf-coshl.md)|math.h|
|[cosl](../c-runtime-library/reference/cos-cosf-cosl.md)|math.h|
|[exp](../c-runtime-library/reference/exp-expf.md)|math.h|
|[expf](../c-runtime-library/reference/exp-expf.md)|math.h|
|[expl](../c-runtime-library/reference/exp-expf.md)|math.h|
|[fabs](../c-runtime-library/reference/fabs-fabsf-fabsl.md)|math.h|
|[fabsf](../c-runtime-library/reference/fabs-fabsf-fabsl.md)|math.h|
|[floor](../c-runtime-library/reference/floor-floorf-floorl.md)|math.h|
|[floorf](../c-runtime-library/reference/floor-floorf-floorl.md)|math.h|
|[floorl](../c-runtime-library/reference/floor-floorf-floorl.md)|math.h|
|[fmod](../c-runtime-library/reference/fmod-fmodf.md)|math.h|
|[fmodf](../c-runtime-library/reference/fmod-fmodf.md)|math.h|
|[fmodl](../c-runtime-library/reference/fmod-fmodf.md)|math.h|
|[labs](../c-runtime-library/reference/abs-labs-llabs-abs64.md)|stdlib.h|
|[llabs](../c-runtime-library/reference/abs-labs-llabs-abs64.md)|stdlib.h|
|[log](../c-runtime-library/reference/log-logf-log10-log10f.md)|math.h|
|[log10](../c-runtime-library/reference/log-logf-log10-log10f.md)|math.h|
|[log10f](../c-runtime-library/reference/log-logf-log10-log10f.md)|math.h|
|[log10l](../c-runtime-library/reference/log-logf-log10-log10f.md)|math.h|
|[logf](../c-runtime-library/reference/log-logf-log10-log10f.md)|math.h|
|[logl](../c-runtime-library/reference/log-logf-log10-log10f.md)|math.h|
|[_lrotl](../c-runtime-library/reference/lrotl-lrotr.md)|stdlib.h|
|[_lrotr](../c-runtime-library/reference/lrotl-lrotr.md)|stdlib.h|
|[memcmp](../c-runtime-library/reference/memcmp-wmemcmp.md)|string.h|
|[memcpy](../c-runtime-library/reference/memcpy-wmemcpy.md)|string.h|
|[memset](../c-runtime-library/reference/memset-wmemset.md)|string.h|
|[pow](../c-runtime-library/reference/pow-powf-powl.md)|math.h|
|[powf](../c-runtime-library/reference/pow-powf-powl.md)|math.h|
|[powl](../c-runtime-library/reference/pow-powf-powl.md)|math.h|
|[_rotl](../c-runtime-library/reference/rotl-rotl64-rotr-rotr64.md)|stdlib.h|
|[_rotl64](../c-runtime-library/reference/rotl-rotl64-rotr-rotr64.md)|stdlib.h|
|[_rotr](../c-runtime-library/reference/rotl-rotl64-rotr-rotr64.md)|stdlib.h|
|[_rotr64](../c-runtime-library/reference/rotl-rotl64-rotr-rotr64.md)|stdlib.h|
|[sin](../c-runtime-library/reference/sin-sinf-sinl.md)|math.h|
|[sinf](../c-runtime-library/reference/sin-sinf-sinl.md)|math.h|
|[sinh](../c-runtime-library/reference/sinh-sinhf-sinhl.md)|math.h|
|[sinhf](../c-runtime-library/reference/sinh-sinhf-sinhl.md)|math.h|
|[sinhl](../c-runtime-library/reference/sinh-sinhf-sinhl.md)|math.h|
|[sinl](../c-runtime-library/reference/sin-sinf-sinl.md)|math.h|
|[sqrt](../c-runtime-library/reference/sqrt-sqrtf-sqrtl.md)|math.h|
|[sqrtf](../c-runtime-library/reference/sqrt-sqrtf-sqrtl.md)|math.h|
|[sqrtl](../c-runtime-library/reference/sqrt-sqrtf-sqrtl.md)|math.h|
|[strcat](../c-runtime-library/reference/strcat-wcscat-mbscat.md)|string.h|
|[strcmp](../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md)|string.h|
|[strcpy](../c-runtime-library/reference/strcpy-wcscpy-mbscpy.md)|string.h|
|[strlen](../c-runtime-library/reference/strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l.md)|string.h|
|[_strset](../c-runtime-library/reference/strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)|string.h|
|[strset](../c-runtime-library/reference/strset-wcsset.md)|string.h|
|[tan](../c-runtime-library/reference/tan-tanf-tanl.md)|math.h|
|[tanf](../c-runtime-library/reference/tan-tanf-tanl.md)|math.h|
|[tanh](../c-runtime-library/reference/tanh-tanhf-tanhl.md)|math.h|
|[tanhf](../c-runtime-library/reference/tanh-tanhf-tanhl.md)|math.h|
|[tanhl](../c-runtime-library/reference/tanh-tanhf-tanhl.md)|math.h|
|[tanl](../c-runtime-library/reference/tan-tanf-tanl.md)|math.h|
|[wcscat](../c-runtime-library/reference/strcat-wcscat-mbscat.md)|string.h|
|[wcscmp](../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md)|string.h|
|[wcscpy](../c-runtime-library/reference/strcpy-wcscpy-mbscpy.md)|string.h|
|[wcslen](../c-runtime-library/reference/strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l.md)|string.h|
|[_wcsset](../c-runtime-library/reference/strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)|string.h|

## <a name="see-also"></a>関連項目

[ARM 組み込み](../intrinsics/arm-intrinsics.md)<br/>
[x86 組み込み一覧](../intrinsics/x86-intrinsics-list.md)<br/>
[x64 (amd64) 組み込み一覧](../intrinsics/x64-amd64-intrinsics-list.md)<br/>
