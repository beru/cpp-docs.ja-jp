---
title: '&lt;regex&gt;'
ms.date: 11/04/2016
f1_keywords:
- <regex>
helpviewer_keywords:
- regex header
ms.assetid: 5dd4ef74-6063-4dbc-b692-1960bb736f0b
ms.openlocfilehash: 3e3f3b49b3672042e0376e7738a8cf8924e1c2a8
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2019
ms.locfileid: "68451448"
---
# <a name="ltregexgt"></a>&lt;regex&gt;

[正規表現 (C++)](../standard-library/regular-expressions-cpp.md) を解析するテンプレート クラスと、正規表現オブジェクトに一致するテキストを検索するテンプレート クラスおよび関数を定義します。

## <a name="syntax"></a>構文

```cpp
#include <regex>
```

## <a name="remarks"></a>Remarks

正規表現オブジェクトを作成するには、[basic_regex クラス](../standard-library/basic-regex-class.md) テンプレート クラスを使用するか、これを特化した [regex](../standard-library/regex-typedefs.md#regex) や [wregex](../standard-library/regex-typedefs.md#wregex) を [regex_constants::syntax_option_type](../standard-library/regex-constants-class.md#syntax_option_type) 型の構文フラグと一緒に使用します。

正規表現オブジェクトと一致するテキストを検索するには、テンプレート関数[regex_match](../standard-library/regex-functions.md#regex_match)と[regex_search](../standard-library/regex-functions.md#regex_search)を、 [regex_constants:: match_flag_type](../standard-library/regex-constants-class.md#match_flag_type)型の一致フラグと共に使用します。 これらの関数は、テンプレート クラス [match_results クラス](../standard-library/match-results-class.md) と、これを特化した [cmatch](../standard-library/regex-typedefs.md#cmatch)、[wcmatch](../standard-library/regex-typedefs.md#wcmatch)、[smatch](../standard-library/regex-typedefs.md#smatch)、および [wsmatch](../standard-library/regex-typedefs.md#wsmatch) を、テンプレート クラス [sub_match クラス](../standard-library/sub-match-class.md) と、これを特化した [csub_match](../standard-library/regex-typedefs.md#csub_match)、[wcsub_match](../standard-library/regex-typedefs.md#wcsub_match)、[ssub_match](../standard-library/regex-typedefs.md#ssub_match)、および [wssub_match](../standard-library/regex-typedefs.md#wssub_match) と一緒に使用して結果を返します。

正規表現オブジェクトと一致するテキストを置換するには、テンプレート関数[regex_replace](../standard-library/regex-functions.md#regex_replace)を、 [regex_constants:: match_flag_type](../standard-library/regex-constants-class.md#match_flag_type)型の一致フラグと共に使用します。

正規表現オブジェクトとの複数の一致を反復処理するには、テンプレート クラス [regex_iterator クラス](../standard-library/regex-iterator-class.md) と [regex_token_iterator クラス](../standard-library/regex-token-iterator-class.md) を使用するか、これらを特殊化した [cregex_iterator](../standard-library/regex-typedefs.md#cregex_iterator)、[sregex_iterator](../standard-library/regex-typedefs.md#sregex_iterator)、[wcregex_iterator](../standard-library/regex-typedefs.md#wcregex_iterator)、[wsregex_iterator](../standard-library/regex-typedefs.md#wsregex_iterator)、[cregex_token_iterator](../standard-library/regex-typedefs.md#cregex_token_iterator)、[sregex_token_iterator](../standard-library/regex-typedefs.md#sregex_token_iterator)、[wcregex_token_iterator](../standard-library/regex-typedefs.md#wcregex_token_iterator)、または [wsregex_token_iterator](../standard-library/regex-typedefs.md#wsregex_token_iterator) のいずれか 1 つを、[regex_constants::match_flag_type](../standard-library/regex-constants-class.md#match_flag_type) 型の一致フラグと一緒に使用します。

正規表現の文法の詳細を変更するには、正規表現の特徴を実装するクラスを記述します。

### <a name="classes"></a>クラス

|クラス|説明|
|-|-|
|[basic_regex](../standard-library/basic-regex-class.md)|正規表現をラップします。|
|[match_results](../standard-library/match-results-class.md)|サブマッチのシーケンスを保持します。|
|[regex_constants](../standard-library/regex-constants-class.md)|各種の定数を保持します。|
|[regex_error](../standard-library/regex-error-class.md)|無効な正規表現を通知します。|
|[regex_iterator](../standard-library/regex-iterator-class.md)|一致した結果を反復処理します。|
|[regex_traits](../standard-library/regex-traits-class.md)|照合する要素の特性を記述します。|
|[regex_traits\<char>](../standard-library/regex-traits-char-class.md)|照合用の**char**の特性について説明します。|
|[regex_traits<wchar_t>](../standard-library/regex-traits-wchar-t-class.md)|一致するための**wchar_t**の特性について説明します。|
|[regex_token_iterator](../standard-library/regex-token-iterator-class.md)|サブマッチを反復処理します。|
|[sub_match](../standard-library/sub-match-class.md)|サブマッチを記述します。|

### <a name="type-definitions"></a>型定義

|||
|-|-|
|[cmatch](../standard-library/regex-typedefs.md#cmatch)|Char`match_results`の型定義。|
|[cregex_iterator](../standard-library/regex-typedefs.md#cregex_iterator)|Char`regex_iterator`の型定義。|
|[cregex_token_iterator](../standard-library/regex-typedefs.md#cregex_token_iterator)|Char`regex_token_iterator`の型定義。|
|[csub_match](../standard-library/regex-typedefs.md#csub_match)|Char`sub_match`の型定義。|
|[regex](../standard-library/regex-typedefs.md#regex)|Char`basic_regex`の型定義。|
|[smatch](../standard-library/regex-typedefs.md#smatch)|`string``match_results` の型定義。|
|[sregex_iterator](../standard-library/regex-typedefs.md#sregex_iterator)|`string``regex_iterator` の型定義。|
|[sregex_token_iterator](../standard-library/regex-typedefs.md#sregex_token_iterator)|`string``regex_token_iterator` の型定義。|
|[ssub_match](../standard-library/regex-typedefs.md#ssub_match)|`string``sub_match` の型定義。|
|[wcmatch](../standard-library/regex-typedefs.md#wcmatch)|Wchar_t`match_results`の型定義。|
|[wcregex_iterator](../standard-library/regex-typedefs.md#wcregex_iterator)|Wchar_t`regex_iterator`の型定義。|
|[wcregex_token_iterator](../standard-library/regex-typedefs.md#wcregex_token_iterator)|Wchar_t`regex_token_iterator`の型定義。|
|[wcsub_match](../standard-library/regex-typedefs.md#wcsub_match)|Wchar_t`sub_match`の型定義。|
|[wregex](../standard-library/regex-typedefs.md#wregex)|Wchar_t`basic_regex`の型定義。|
|[wsmatch](../standard-library/regex-typedefs.md#wsmatch)|`wstring``match_results` の型定義。|
|[wsregex_iterator](../standard-library/regex-typedefs.md#wsregex_iterator)|`wstring``regex_iterator` の型定義。|
|[wsregex_token_iterator](../standard-library/regex-typedefs.md#wsregex_token_iterator)|`wstring``regex_token_iterator` の型定義。|
|[wssub_match](../standard-library/regex-typedefs.md#wssub_match)|`wstring``sub_match` の型定義。|

### <a name="functions"></a>関数

|関数|説明|
|-|-|
|[regex_match](../standard-library/regex-functions.md#regex_match)|正規表現と完全に一致します。|
|[regex_replace](../standard-library/regex-functions.md#regex_replace)|一致した正規表現を置換します。|
|[regex_search](../standard-library/regex-functions.md#regex_search)|正規表現との一致を検索します。|
|[swap](../standard-library/regex-functions.md#swap)|`basic_regex` または `match_results` オブジェクトをスワップします。|

### <a name="operators"></a>演算子

|演算子|説明|
|-|-|
|[operator==](../standard-library/regex-operators.md#op_eq_eq)|さまざまなオブジェクトが等しいかどうかの比較|
|[operator!=](../standard-library/regex-operators.md#op_neq)|さまざまなオブジェクトが等しくないかどうかの比較|
|[operator<](../standard-library/regex-operators.md#op_lt)|さまざまなオブジェクトが他方より小さいかどうかの比較|
|[operator\<=](../standard-library/regex-operators.md#op_gt_eq)|さまざまなオブジェクトが他方以下かどうかの比較|
|[operator>](../standard-library/regex-operators.md#op_gt)|さまざまなオブジェクトが他方より大きいかどうかの比較|
|[operator>=](../standard-library/regex-operators.md#op_gt_eq)|さまざまなオブジェクトが他方以上かどうかの比較|
|[operator<<](../standard-library/regex-operators.md#op_lt_lt)|ストリームに `sub_match` を挿入します。|

## <a name="see-also"></a>関連項目

[正規表現 (C++)](../standard-library/regular-expressions-cpp.md)\
[regex_constants クラス](../standard-library/regex-constants-class.md)\
[regex_error クラス](../standard-library/regex-error-class.md)\
[\<regex > 関数](../standard-library/regex-functions.md)\
[regex_iterator クラス](../standard-library/regex-iterator-class.md)\
[\<regex > 演算子](../standard-library/regex-operators.md)\
[regex_token_iterator クラス](../standard-library/regex-token-iterator-class.md)\
[regex_traits クラス](../standard-library/regex-traits-class.md)\
[\<regex> typedefs](../standard-library/regex-typedefs.md)
