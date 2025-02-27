---
title: complex&lt;long double&gt;
ms.date: 11/04/2016
f1_keywords:
- std::complex<long double>
- complex<long double>
- std.complex<long double>
helpviewer_keywords:
- complex<long double> function
ms.assetid: 37591991-b385-46e9-b727-d534dbc10432
ms.openlocfilehash: 280fb4c15219b11d2325ff37a296e133810bf2b5
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2019
ms.locfileid: "68449476"
---
# <a name="complexltlong-doublegt"></a>complex&lt;long double&gt;

この明示的に特殊化されたテンプレートクラスは、順序付けされたオブジェクトのペアを格納するオブジェクトを記述します。 **long double**型の場合は、最初のオブジェクトが複素数の実数部、2番目のオブジェクトが虚数部を表します。

## <a name="syntax"></a>構文

```cpp
template <>
class complex<long double> {
public:
    constexpr complex(
    long double _RealVal = 0,
    long double _ImagVal = 0);

complex(
    constexpr complex<long double>& complexNum);

// rest same as template class complex
};
```

### <a name="parameters"></a>パラメーター

*Realval (_d)* \
構築される複素数の実数部の **long double** 型の値。

*Imagval (_c)* \
構築される複素数の虚数部の**long double**型の値。

*complexNum*\
**Double**型または**float**型の複素数。実数部と虚数部が、構築される**long double**型の複素数を初期化するために使用されます。

## <a name="return-value"></a>戻り値

**Long double**型の複素数。

## <a name="remarks"></a>Remarks

テンプレートクラス`complex`を**long double**型の複合クラスに明示的に特殊化することは、テンプレートクラスが定義するコンストラクター内でのみ、テンプレートクラスとは異なります。 **Long double**から**float**への変換は暗黙的に行うことができますが、 **double**から**long double**への変換は**明示的**に行う必要があります。 **explicit** を使用すると、割り当て構文を使用した型変換による開始は禁止されます。

テンプレートクラス`complex`とそのメンバーの詳細については、「[複合クラス](../standard-library/complex-class.md)」を参照してください。

**Microsoft 固有の仕様**:**Long double**型と**double**型の表現は同じですが、個別の型です。 詳細については、「[基本型](../cpp/fundamental-types-cpp.md)」を参照してください。

## <a name="example"></a>例

```cpp
// complex_comp_ld.cpp
// compile with: /EHsc
#include <complex>
#include <iostream>

int main( )
{
    using namespace std;
    double pi = 3.14159265359;

    // The first constructor specifies real & imaginary parts
    complex<long double> c1( 4.0 , 5.0 );
    cout << "Specifying initial real & imaginary parts,\n"
        << " as type float gives c1 = " << c1 << endl;

    // The second constructor initializes values of the real &
    // imaginary parts using those of complex number of type float
    complex<float> c2float( 1.0 , 3.0 );
    complex<long double> c2longdouble ( c2float );
    cout << "Implicit conversion from type float to type long double,"
        << "\n gives c2longdouble = " << c2longdouble << endl;

    // The third constructor initializes values of the real &
    // imaginary parts using those of a complex number
    // of type double
    complex<double> c3double( 3.0 , 4.0 );
    complex<long double> c3longdouble( c3double );
    cout << "Implicit conversion from type long double to type float,"
        << "\n gives c3longdouble = " << c3longdouble << endl;

    // The modulus and argument of a complex number can be recovered
    double absc3 = abs( c3longdouble );
    double argc3 = arg( c3longdouble );
    cout << "The modulus of c3 is recovered from c3 using: abs( c3 ) = "
        << absc3 << endl;
    cout << "Argument of c3 is recovered from c3 using:\n arg( c3 ) = "
        << argc3 << " radians, which is " << argc3 * 180 / pi
        << " degrees." << endl;
}
```

```Output
Specifying initial real & imaginary parts,
as type float gives c1 = (4,5)
Implicit conversion from type float to type long double,
gives c2longdouble = (1,3)
Implicit conversion from type long double to type float,
gives c3longdouble = (3,4)
The modulus of c3 is recovered from c3 using: abs( c3 ) = 5
Argument of c3 is recovered from c3 using:
arg( c3 ) = 0.927295 radians, which is 53.1301 degrees.
```

## <a name="requirements"></a>必要条件

**ヘッダー**: \<complex>

**名前空間:** std

## <a name="see-also"></a>関連項目

[complex クラス](../standard-library/complex-class.md)\
[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)
