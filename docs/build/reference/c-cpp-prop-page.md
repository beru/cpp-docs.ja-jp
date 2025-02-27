---
title: C/C++プロジェクトのプロパティ (Visual Studio)
ms.date: 7/18/2019
ms.topic: article
ms.assetid: 16375038-4917-4bd0-9a2a-26343c1708b7
ms.openlocfilehash: 91edf30ef0e5f38088727c0280d2edf07cdebfa5
ms.sourcegitcommit: 7b039b5f32f6c59be6c6bb1cffafd69c3bfadd35
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/26/2019
ms.locfileid: "68537563"
---
# <a name="cc-property-pages"></a>C/C++プロパティページ

次のプロパティページは、[**プロジェクト** > の**プロパティ** > ] [**構成プロパティ** > ] **[C++C/]** の下にあります。

## <a name="cc-general-properties"></a>C/C++全般プロパティ

### <a name="additional-include-directories"></a>追加のインクルード ディレクトリ

インクルード パスに追加するディレクトリを 1 つ以上指定します。複数指定する場合には、セミコロンで区切ってください。 [/I (追加のインクルードディレクトリ)](i-additional-include-directories.md)を設定します。

### <a name="additional-using-directories"></a>追加の #using ディレクトリ

#Using ディレクティブに渡される名前を解決するために検索する1つ以上のディレクトリを指定します (個別のディレクトリ名はセミコロンで区切ります)。 [/Ai](ai-specify-metadata-directories.md)を設定します。

### <a name="debug-information-format"></a>デバッグ情報の形式

コンパイラによって生成されるデバッグ情報の種類を指定します。  これには、互換性のあるリンカー設定が必要です。 [/Z7、/zi、/zi (デバッグ情報の形式)](z7-zi-zi-debug-information-format.md)を設定します。

**いずれ**

- **なし** - デバッグ情報が生成されないため、コンパイルが高速になる可能性があります。
- **[C7 互換]** -プログラム用に作成されたデバッグ情報の種類、およびこの情報をオブジェクト (.obj) ファイルとプログラムデータベース (PDB) のどちらに保存するかを選択します。
- **プログラムデータベース**-デバッガーで使用する型情報とシンボリックデバッグ情報を含むプログラムデータベース (PDB) を生成します。 シンボリック デバッグ情報には、変数や関数の名前と型、および行番号が含まれます。
- **エディットコンティニュのプログラムデータベース**-[エディットコンティニュ](/visualstudio/debugger/edit-and-continue)機能をサポートする形式で、前述のようにプログラムデータベースを生成します。

### <a name="support-just-my-code-debugging"></a>デバッグのサポートマイコードのみ

このコンパイル単位で[マイコードのみ](/visualstudio/debugger/just-my-code)デバッグを有効にするためのサポートコードを追加します。 [/JMC](jmc.md)を設定します。

### <a name="common-language-runtime-support"></a>共通言語ランタイムサポート

.NET ランタイムサービスを使用します。  このスイッチは、他のいくつかのスイッチと互換性がありません。詳細については、スイッチの[/clr](clr-common-language-runtime-compilation.md)ファミリに関するドキュメントを参照してください。

**いずれ**

- **共通言語ランタイムサポートがありませ**ん-共通言語ランタイムサポートがありません
- **共通言語ランタイムサポート**-他の clr アプリケーションで使用できるアプリケーションのメタデータを作成し、他の clr コンポーネントのメタデータの型とデータをアプリケーションで使用できるようにします。
- **純粋 Msil 共通言語ランタイムサポート**-ネイティブの実行可能コードを含まない[msil](/dotnet/standard/managed-code)のみの出力ファイルを生成します。ただし、msil にコンパイルされたネイティブ型を含めることはできます。
- **安全な Msil 共通言語ランタイムサポート**-msil のみ (ネイティブの実行可能コードを含まない) と検証可能な出力ファイルを生成します。

### <a name="consume-windows-runtime-extension"></a>Windows ランタイム拡張機能の使用

Windows ランタイム言語拡張機能を使用します。 [/ZW](zw-windows-runtime-compilation.md)を設定します。

### <a name="suppress-startup-banner"></a>著作権情報の非表示

コンパイル時に、コンパイラが起動して情報メッセージを表示したときに、サインオンバナーが表示されないようにします。

### <a name="warning-level"></a>警告レベル

コード エラーに対するコンパイラの警告レベルを指定します。 [/W0/W4](compiler-option-warning-level.md)を設定します。

**いずれ**

- **すべての警告を無効にする**-レベル0はすべての警告を無効にします。
- **Level1**レベル1では、重大な警告が表示されます。 レベル1は、コマンドラインでの既定の警告レベルです。
- **Level2**レベル2では、レベル1の警告およびレベル1より重大度の低い警告がすべて表示されます。
- **Level3**レベル3では、すべてのレベル2の警告と、運用のために推奨されるその他のすべての警告が表示されます。
- **Level4**レベル4には、すべてのレベル3の警告と情報に関する警告が表示されます。ほとんどの場合、この警告は無視しても安全です。
- **警告をすべて有効にする** - 既定で無効にされている警告を含む、すべての警告を有効にします。

### <a name="treat-warnings-as-errors"></a>警告をエラーとして扱う

コンパイラ警告をすべてエラーとして扱います。 新しいプロジェクトの場合は、すべてのコンパイルで[/wx](wx-treat-linker-warnings-as-errors.md)を使用することをお勧めします。すべての警告を解決することで、コードの欠陥が発見される可能性が最小限に抑えられます。

### <a name="warning-version"></a>警告バージョン

コンパイラの特定のバージョンより後に導入された警告を非表示にします。 [/Wv\[:.yy \[.zzzzzを設定\]\]](wx-treat-linker-warnings-as-errors.md)します。

### <a name="diagnostics-format"></a>診断形式

診断メッセージに列情報とソースコンテキストを使用して、豊富な診断機能を有効にします。

**いずれ**

- **キャレット**-診断メッセージに列情報を提供するだけでなく、関連するソースコード行を、問題のある列を示すキャレットと共に出力します。
- **[列情報]** -さらに、必要に応じて、診断が発行された行内の列番号が表示されます。
- **Classic** -以前の簡潔な診断メッセージを行番号と共に保持します。

### <a name="sdl-checks"></a>SDL チェック

追加のセキュリティ開発ライフサイクル (SDL) の推奨チェックセキュリティで保護された追加のコード生成機能を有効にし、エラーとしてセキュリティ関連の警告を追加できるようにします。 [/Sdl、/sdl-を](sdl-enable-additional-security-checks.md)設定します。

### <a name="multi-processor-compilation"></a>複数プロセッサによるコンパイル

複数プロセッサによるコンパイルです。

## <a name="cc-optimization-properties"></a>C/C++最適化プロパティ

### <a name="optimization"></a>Optimization

コード最適化のオプションを選択します。特定の最適化オプションを使用するには、[カスタム] を選択します。 [/Od](od-disable-debug.md)、 [/O1、/O2 を](o-options-optimize-code.md)設定します。

**いずれ**

- **カスタム** - カスタムの最適化。
- **無効** - 最適化を無効にします。
- **最大最適化 (サイズを優先)** -/Og/Os/Oy/ob2/Gs/gf/Gy に相当します。
- **最大の最適化 (速度を優先)** -/Og/Oi/Ot/Oy/ob2/Gs/Gf/Gy と同じです
- **最適化 (速度を優先)** -/Og/Oi/Ot/Oy/ob2 に相当します。

### <a name="inline-function-expansion"></a>インライン関数の展開

ビルドの[インライン関数](../../cpp/inline-functions-cpp.md)の展開レベルを選択します。 [/Ob1,/ob2 を](ob-inline-function-expansion.md)設定します。

**いずれ**

- **[Default]**
- **Disabled** -既定でオンになっているインライン展開を無効にします。
- Inline、__ inline、__forceinline、または __ inline としてマークされている関数、またC++はクラス宣言内で定義されているメンバー関数内の関数のみが、 **\_\_インライン** 展開されます。
- インラインまたは __ インラインとしてマークされている **適切**な展開関数、およびコンパイラが選択したその他の関数 (拡張は、コンパイラの判断では、多くの場合、自動インライン展開と呼ばれます)。

### <a name="enable-intrinsic-functions"></a>組み込み関数を有効にする

組み込み関数を有効にします。  組み込み関数を使用すると、コードがより高速に生成されますが、サイズが大きくなる可能性があります。 [/Oi](oi-generate-intrinsic-functions.md)を設定します。

### <a name="favor-size-or-speed"></a>サイズまたは速度を優先する

コードサイズとコード速度のどちらを優先するか[グローバル最適化] をオンにする必要があります。 [/Ot,/os を](os-ot-favor-small-code-favor-fast-code.md)設定します。

**いずれ**

- **小さいコードを優先**する-小さいコードを優先します。 速度よりもサイズを優先するようコンパイラに指示することによって、Exe と Dll のサイズを最小限に抑えます。
- **高速コードを優先**します。高速コードを優先します。 サイズよりも速い速度を優先するようコンパイラに指示することにより、Exe と Dll の速度を最大にします。 (これが既定値です)。
- **どちら**の場合も、サイズや速度の最適化は行われません。

### <a name="omit-frame-pointers"></a>フレームポインターを省略する

呼び出し履歴にフレーム ポインターが作成されなくなります。

### <a name="enable-fiber-safe-optimizations"></a>ファイバーセーフの最適化を有効にする

ファイバーとスレッドローカルストレージアクセスを使用するときに、メモリ領域の最適化を有効にします。 [/Gt](gt-support-fiber-safe-thread-local-storage.md)を設定します。

### <a name="whole-program-optimization"></a>プログラム全体の最適化

コード生成をリンク時間に遅延させることで、モジュール間の最適化を有効にします。リンカーオプションの [リンク時のコード生成] をオンにする必要があります。 [/Gl](gl-whole-program-optimization.md)を設定します。

## <a name="cc-preprocessor-properties"></a>C/C++プリプロセッサのプロパティ

### <a name="preprocessor-definitions"></a>プリプロセッサの定義

ソース ファイルの前処理シンボルを定義します。

### <a name="undefine-preprocessor-definitions"></a>指定したプリプロセッサ定義の無効化

1 つ以上のプリプロセッサ定義の無効化を指定します。 [/U](u-u-undefine-symbols.md)を設定します。

### <a name="undefine-all-preprocessor-definitions"></a>すべてのプリプロセッサ定義の無効化

すべてのプリプロセッサの定義済み定義を無効にします。 [/U](u-u-undefine-symbols.md)を設定します。

### <a name="ignore-standard-include-paths"></a>標準インクルードパスを無視する

INCLUDE 環境変数で指定されたディレクトリ内のインクルードファイルをコンパイラが検索できないようにします。

### <a name="preprocess-to-a-file"></a>ファイルへの前処理

C とC++ソースファイルを前処理し、前処理された出力をファイルに書き込みます。 このオプションを指定するとコンパイルが抑制されるため、.obj ファイルは生成されません。

### <a name="preprocess-suppress-line-numbers"></a>行番号の前処理の抑制

#Line ディレクティブを使用せずに前処理します。

### <a name="keep-comments"></a>コメントを残す

ソースコードからコメントを削除しません。' 前処理 ' オプションの1つを設定する必要があります。 [/C](c-preserve-comments-during-preprocessing.md)を設定します。

## <a name="cc-code-generation-properties"></a>C/C++コード生成のプロパティ

### <a name="enable-string-pooling"></a>文字列プールを有効にする

を使用すると、プログラムイメージおよび実行中のメモリに同一の文字列の読み取り専用コピーを1つ作成できます。これにより、プログラムは文字列プールと呼ばれる最適化されます。 [/O1、/O2](o-options-optimize-code.md)、および[/zi](z7-zi-zi-debug-information-format.md)は、自動的に[/gf](gf-eliminate-duplicate-strings.md)オプションを設定します。

### <a name="enable-minimal-rebuild"></a>最小リビルドを有効にする

最小リビルドを有効にします。最小リビルドにより、(ヘッダー (.h) ファイルに格納されている) 変更された C++ クラス定義を含む C++ ソース ファイルを再コンパイルする必要があるかどうかが決定されます。

### <a name="enable-c-exceptions"></a>C++ の例外を有効にする

コンパイラで使用する例外処理のモデルを指定します。

**いずれ**

- **はい (SEH 例外**あり): 非同期 (構造化) 例外と同期 (C++) 例外をキャッチする例外処理モデル。 [/Eha](eh-exception-handling-model.md)を設定します。
- **はい**-例外のみをキャッチC++し、extern C 関数が例外をC++スローしないと想定するようにコンパイラに指示する例外処理モデル。 [/Ehsc](eh-exception-handling-model.md)を設定します。
- **はい (Extern c 関数を使用**する場合)-例外のみC++をキャッチし、Extern c 関数が例外をスローすることを前提としてコンパイラに指示する例外処理モデル。 [/Ehs](eh-exception-handling-model.md)を設定します。
- **いいえ**-例外処理はありません。

### <a name="smaller-type-check"></a>小さい型のチェック

小さい型への変換のチェックを有効にします。デバッグ以外の最適化の種類と互換性がありません。 [/RTCc](rtc-run-time-error-checks.md)を設定します。

### <a name="basic-runtime-checks"></a>基本ランタイムチェック

基本のランタイムエラーチェックを実行します。 debug 以外の最適化の種類と互換性がありません。 [/RTCs、/RTCu、/RTC1](rtc-run-time-error-checks.md)を設定します。

**いずれ**

- **スタックフレーム**-スタックフレームの実行時エラーチェックを有効にします。
- **初期**化されていない変数-変数が初期化されずに使用された場合に報告します。
- **Both (/RTC1, Http-equiv/RTCsu)** -/Rtcsu と同等です。
- **既定**-既定のランタイムチェック。

### <a name="runtime-library"></a>ランタイム ライブラリ

リンクするランタイム ライブラリを指定します。 [/Mt、/MTd、/md、/mdd](md-mt-ld-use-run-time-library.md)を設定します。

**いずれ**

- **マルチスレッド**-アプリケーションで、ランタイムライブラリのマルチスレッドの静的バージョンを使用します。
- **マルチスレッドデバッグ**-_DEBUG と _MT を定義します。 このオプションによって、リンカーが LIBCMTD.lib を使用して外部シンボルを解決できるように、コンパイラによりライブラリ名 LIBCMTD.lib が .obj ファイルに挿入されます。
- **マルチスレッド dll** -アプリケーションで、ランタイムライブラリのマルチスレッドおよび dll 固有のバージョンを使用します。 _MT および _DLL を定義し、コンパイラにライブラリ名 MSVCRT.lib を .obj ファイルに挿入させます。
- **マルチスレッドデバッグ DLL** -_DEBUG、_MT、および dll を定義し、アプリケーションでマルチスレッドおよび dll 固有バージョンのランタイムライブラリを使用するようにします。 また、コンパイラによって、ライブラリ名 MSVCRTD.lib が .obj ファイルに挿入されます。

### <a name="struct-member-alignment"></a>構造体メンバーのアラインメント

構造体メンバーのアラインメントに1、2、4、または8バイトの境界を指定します。 [/Zp](zp-struct-member-alignment.md)を設定します。

**いずれ**

- 1バイトの境界に**1 バイト**の構造体があります。 /Zp. と同じ
- **2**バイト境界で構造をパックします。
- 4バイトの境界に**4 バイト**の構造体。
- **8 バイト**の場合は、構造体を8バイト境界でパックします (既定)。
- **16 バイト**の境界で構造体を16バイトでパックします。
- **既定**値の配置設定。

### <a name="security-check"></a>セキュリティ チェック

セキュリティ チェックでは、プログラムのセキュリティに対する一般的な攻撃であるスタックバッファー オーバーランを検出できます。 

**いずれ**

- **セキュリティ チェックを無効にします** - セキュリティ チェックを無効にします。 [/GS-](gs-buffer-security-check.md)を設定します。
- **セキュリティ チェックを有効にします** - セキュリティ チェックを有効にします。 [/Gs](gs-buffer-security-check.md)を設定します。

### <a name="control-flow-guard"></a>制御フローガード

ガードセキュリティチェックは、コードの不正なブロックにディスパッチする試行を検出するのに役立ちます。 

**いずれ**

- **はい**-ガードセット[/ガード: cf](guard-enable-control-flow-guard.md)を使用してセキュリティチェックを有効にします。
- **No**

### <a name="enable-function-level-linking"></a>関数レベルでリンクする

コンパイラが個々の関数をパッケージ関数 (COMDAT) の形式でパッケージ化できるようになります。 エディット コンティニュの機能に必要です。 [/Gy](gy-enable-function-level-linking.md)を設定します。

### <a name="enable-parallel-code-generation"></a>並列コード生成を有効にする

最適化が有効な場合、コンパイラが #pragma ループ (hint_parallel\[(n)]) を使用して識別されたループに対して並列コードを生成できるようにします。

### <a name="enable-enhanced-instruction-set"></a>拡張命令セットを有効にする

拡張命令セットをサポートするプロセッサで検出された命令の使用を有効にします。たとえば、SSE、SSE2、AVX、AVX2 などの IA-32 の機能強化を行います。AVX と AVX2 を x64 にします。 現在、 **/arch: SSE**と **/arch: SSE2**は、x86 アーキテクチャ用にビルドする場合にのみ使用できます。 オプションが指定されていない場合、コンパイラは、SSE2 をサポートするプロセッサで検出された命令を使用します。 /Arch: IA32 では拡張命令の使用を無効にすることができます。 詳細については、「 [/arch (x86)](arch-x86.md)、 [/arch (x64)](arch-x64.md) 、および[/arch (ARM)](arch-arm.md) 」を参照してください。

**いずれ**

- **ストリーミング Simd 拡張機能**-ストリーミング simd 拡張。 **/Arch: SSE**を設定します
- **ストリーミング Simd 拡張命令 2** -ストリーミング simd 拡張命令2。 **/Arch: SSE2**を設定します。
- **高度なベクター拡張機能**-高度なベクター拡張機能。 **/Arch: AVX**を設定します。
- **Advanced Vector extensions 2** -Advanced vector extensions 2。 **/Arch: AVX2**を設定します。
- **拡張命令がありませ**ん-拡張命令はありません。 **/Arch: IA32**を設定します。
- **設定されて**いません-設定されていません。

### <a name="floating-point-model"></a>浮動小数点モデル

浮動小数点モデルを設定します。 [/Fp: 精密、/fp: strict、/fp: fast](fp-specify-floating-point-behavior.md)を設定します。

**いずれ**

- **正確**-既定値。 等価性と非等値の浮動小数点テストの一貫性を向上させます。
- **Strict-厳密**な浮動小数点モデル。 /fp: strict は、fp_contract を OFF にし、fenv_access を ON にします。 /fp: except は暗黙的に指定され、/fp: except-を明示的に指定することによって無効にすることができます。 /Fp: except-で使用する場合、/fp: strict は厳密な浮動小数点セマンティクスを適用しますが、例外的なイベントには適用しません。
- **高速**-ほとんどのケースで最速のコードを作成します。

### <a name="enable-floating-point-exceptions"></a>浮動小数点例外を有効にする

信頼性の高い浮動小数点例外モデル。 例外は発生直後にスローされます。  [/Fp: except](fp-specify-floating-point-behavior.md)を設定します。

### <a name="create-hotpatchable-image"></a>Hotpatchable イメージの作成

ホットパッチがオンになっている場合、コンパイラは各関数の最初の命令が2バイトであることを確認します。これはホットパッチに必要です。  [/Hotpatch](hotpatch-create-hotpatchable-image.md)を設定します。

### <a name="spectre-mitigation"></a>Spectre 軽減策

CVE 2017-5753 の Spectre 軽減策。 [/Qspectre](qspectre.md)を設定します。

**いずれ**

- **Enabled** -Spectre 軽減機能を CVE 2017-5753 に対して有効にします。
- **Disabled** -設定されていません。

## <a name="cc-language-properties"></a>C/C++言語プロパティ

### <a name="disable-language-extensions"></a>言語拡張機能を無効にする

言語拡張を抑制または有効にします。 [/Za](za-ze-disable-language-extensions.md)を設定します。

### <a name="conformance-mode"></a>適合性モード

準拠モードを有効または非表示にします。 [/Permissive-](permissive-standards-conformance.md)を設定します。

### <a name="treat-wchar_t-as-built-in-type"></a>WChar_t をビルトイン型として扱う

指定した場合、wchar_t 型は、short が __int16 にマップされるのと同じ方法で、__ wchar_t にマップされるネイティブ型になります。 [/Zc: wchar_t](zc-wchar-t-wchar-t-is-native-type.md)は既定でオンになっています。

### <a name="force-conformance-in-for-loop-scope"></a>For ループスコープの強制準拠

Microsoft 拡張機能をC++使用した for ステートメントループの標準動作を実装するために使用されます。 [/Za、/ze (言語拡張を無効にする) を](za-ze-disable-language-extensions.md)設定します。 [/Zc:forScope](zc-forscope-force-conformance-in-for-loop-scope.md) は既定でオンになります。

### <a name="remove-unreferenced-code-and-data"></a>参照されていないコードとデータの削除

指定した場合、コンパイラは、参照されていないコードおよびデータのシンボル情報を生成しなくなります。

### <a name="enforce-type-conversion-rules"></a>適用 (型変換規則を)

C++ 11 標準に従って、キャスト演算の結果として右辺値参照型を識別するために使用されます。

### <a name="enable-run-time-type-information"></a>ランタイム型情報を有効にする

実行時に C++ のオブジェクト型をチェックするコードを追加します (ランタイム型情報)。 [/Gr,/GR-](gr-enable-run-time-type-information.md)を設定します。

### <a name="open-mp-support"></a>MP サポートを開く

OpenMP 2.0 言語拡張を有効にします。 [/Openmp](openmp-enable-openmp-2-0-support.md)を設定します。

### <a name="c-language-standard"></a>C++ 言語標準

コンパイラにC++よって適用される言語標準を決定します。 可能な場合は、最新バージョンを使用することをお勧めします。 [/Std: c++ 14、/std: c++ 17、/std: c + + latest](std-specify-language-standard-version.md)を設定します。

**いずれ**

- **[Default]**
- **ISO C++ 14 標準**
- **ISO C++ 17 標準**
- **プレビュー-最新C++の作業ドラフトからの機能**

### <a name="enable-c-modules-experimental"></a>モジュールC++を有効にする (試験段階)

C++モジュール TS および標準ライブラリモジュールの試験的なサポート。

## <a name="cc-precompiled-headers-properties"></a>C/C++プリコンパイル済みヘッダーのプロパティ

### <a name="precompiled-header"></a>プリコンパイル済みヘッダー オプション

プリコンパイル済みヘッダーの作成/使用:プリコンパイル済みヘッダーをビルド中に作成または使用できるようになります。 [/Yc](yc-create-precompiled-header-file.md), [/yu](yu-use-precompiled-header-file.md)を設定します。

**いずれ**

- **Create** -特定の時点でのコンパイルの状態を表すプリコンパイル済みヘッダー (.pch) ファイルを作成するようにコンパイラに指示します。
- **Use** -現在のコンパイルで既存のプリコンパイル済みヘッダー (.pch) ファイルを使用するようにコンパイラに指示します。
- **プリコンパイル済みヘッダーを使用しません**-プリコンパイル済みヘッダーを使用していません。

### <a name="precompiled-header-file"></a>プリコンパイル済みヘッダー ファイル

プリコンパイル済みヘッダーファイルを作成または使用するときに使用するヘッダーファイル名を指定します。 [/Yc](yc-create-precompiled-header-file.md)、[/yu]] (file.md) を設定します。

### <a name="precompiled-header-output-file"></a>プリコンパイル済みヘッダーの出力ファイル

生成されたプリコンパイル済みヘッダーファイルのパスと名前のどちらかまたは両方を指定します。 [/Fp](fp-name-dot-pch-file.md)を設定します。

## <a name="cc-output-files-properties"></a>C/C++出力ファイルのプロパティ

### <a name="expand-attributed-source"></a>属性ソースの展開

展開された属性をソースファイルに挿入して、リスティングファイルを作成します。 [/Fx](fx-merge-injected-code.md)を設定します。

### <a name="assembler-output"></a>アセンブラ出力

アセンブリ言語の出力ファイルの内容を指定します。 [/Fa、/FAc、/fa、/facs](fa-fa-listing-file.md)を設定します。

**いずれ**

- **リスティング**がありません。一覧はありません。
- **アセンブリのみのリスティング**-アセンブリコード、.asm
- **アセンブリとコンピューターコード**-コンピューターとアセンブリコード、. cod
- **アセンブリとソースコード**-ソースとアセンブリコード (.asm)
- **アセンブリ、コンピューターコードとソース**アセンブリ、コンピューターコード、ソースコード、および cod

### <a name="use-unicode-for-assembler-listing"></a>アセンブラーリストに Unicode を使用する

出力ファイルが UTF-8 形式で作成されます。

### <a name="asm-list-location"></a>ASM リストの場所

ASM リスティングファイルの相対パスと名前のどちらかまたは両方を指定します。ファイル名またはディレクトリ名を指定できます。 [/Fa](fa-fa-listing-file.md)を設定します。

### <a name="object-file-name"></a>オブジェクト ファイル名

既定のオブジェクト ファイル名をオーバーライドする名前を指定します。ファイル名またはディレクトリ名を指定できます。 [/Fo](fo-object-file-name.md)を設定します。

### <a name="program-database-file-name"></a>プログラムデータベースファイル名

コンパイラによって生成される PDB ファイルの名前を指定します。また、必要なコンパイラによって生成された .IDB ファイルの基本名も指定します。ファイル名またはディレクトリ名を指定できます。 [/Fd](fd-program-database-file-name.md)を設定します。

### <a name="generate-xml-documentation-files"></a>XML ドキュメントファイルの生成

コンパイラが XML ドキュメントコメントファイル () を生成することを指定します.XDC)。 [/Doc](doc-process-documentation-comments-c-cpp.md)を設定します。

### <a name="xml-documentation-file-name"></a>XML ドキュメントファイル名

生成された XML ドキュメントファイルの名前を指定します。ファイル名またはディレクトリ名を指定できます。 [/Doc:\<name >](doc-process-documentation-comments-c-cpp.md)を設定します。

## <a name="cc-browse-information-properties"></a>C/C++ブラウザー情報のプロパティ

### <a name="enable-browse-information"></a>ブラウザー情報の有効化

ブラウザー情報を有効にする:.Bsc ファイル内のブラウザー情報のレベルを指定します。 [/Fr](fr-fr-create-dot-sbr-file.md)を設定します。

### <a name="browse-information-file"></a>情報ファイルの参照

ファイルの参照:ブラウザー情報ファイルの省略可能な名前を指定します。 [/Fr\<name >](fr-fr-create-dot-sbr-file.md)を設定します。

## <a name="cc-advanced-properties"></a>C/C++詳細プロパティ

### <a name="calling-convention"></a>呼び出し規則

アプリケーションの既定の呼び出し規約を選択します (関数によってオーバーライドできます)。 [/Gd、/gr、/Gz、/Gv](gd-gr-gv-gz-calling-convention.md)を設定します。

**いずれ**

- **__cdecl** -メンバー関数および __stdcall または __fastcall とマークC++されている関数を除くすべての関数の __cdecl 呼び出し規約を指定します。
- **__fastcall** -メンバー関数および __cdecl または __stdcall とマークC++された関数を除くすべての関数に対する __fastcall 呼び出し規約を指定します。 すべての __fastcall 関数にはプロトタイプが必要です。
- **__stdcall** -メンバー関数および __cdecl または __fastcall とマークC++された関数を除くすべての関数に対する __stdcall 呼び出し規約を指定します。 すべての __stdcall 関数にはプロトタイプが必要です。
- **__vectorcall** -メンバー関数と __cdecl、__fastcall、またはC++ __stdcall とマークされた関数を除くすべての関数の __vectorcall 呼び出し規約を指定します。 すべての __vectorcall 関数にはプロトタイプが必要です。

### <a name="compile-as"></a>コンパイル言語の選択

.c および .cpp ファイルのコンパイル言語オプションを選択します。 [/Tc、/tp を](tc-tp-tc-tp-specify-source-file-type.md)設定します。

**いずれ**

- **既定** - 既定。
- **C コードとしてコンパイル** - C コードとしてコンパイルします。
- **C++ コードとしてコンパイル** - C++ コードとしてコンパイルします。

### <a name="disable-specific-warnings"></a>特定の警告を無効にする

目的の警告番号を無効にします。セミコロンで区切られたリストに数値を入力します。 [/Wd\<num >](compiler-option-warning-level.md)を設定します。

### <a name="forced-include-file"></a>強制インクルードファイル

1 つ以上の必ず使用されるインクルード ファイル。 [/Fi\<名 >](fi-name-forced-include-file.md)を設定します。

### <a name="forced-using-file"></a>強制 #using ファイル

1つ以上の強制 #using ファイルを指定します。 [/Fu\<名 >](fu-name-forced-hash-using-file.md)を設定します。

### <a name="show-includes"></a>インクルード ファイルの表示

コンパイラ出力を持つインクルード ファイルのリストを生成します。 [/ShowIncludes](showincludes-list-include-files.md)を設定します。

### <a name="use-full-paths"></a>完全パスを使用する

診断メッセージで完全パスを使用します。 [/Fc](fc-full-path-of-source-code-file-in-diagnostics.md)を設定します。

### <a name="omit-default-library-name"></a>既定のライブラリ名を省略する

.Obj ファイルに既定のライブラリ名を含めないでください。 [/Zl](zl-omit-default-library-name.md)を設定します。

### <a name="internal-compiler-error-reporting"></a>内部コンパイラエラー報告

内部ツールエラーを Microsoft に報告する方法を指定します。  IDE の既定値は prompt です。  コマンドラインビルドの既定値は queue です。 [/Errorreport:\[method]] (errorReport-errors.md) を設定します。

**いずれ**

- **レポートを送信**しない: 内部コンパイラエラーに関するレポートは、収集されず、マイクロソフトに送信されません。
- **プロンプトがすぐに**表示されます-内部コンパイルエラーが発生したときにレポートを送信するように求めるメッセージが表示されます。
- **[次のログインのキュー** ]-エラーレポートをキューにします。 管理者特権でサインインすると、ポップアップウィンドウが表示され、最後にログインした後に発生したエラーを報告することができます (エラーの報告を3日ごとに複数回送信するように求めるメッセージは表示されません)。 queue は、コマンドラインでアプリケーションをコンパイルするときの既定の設定です。
- **自動的に送信**-内部コンパイラエラーのレポートを Microsoft に自動的に送信します。 このオプションを有効にするには、最初に Microsoft% 27s データ収集ポリシーに同意する必要があります。 コンピューターで/errorReport: send を初めて指定すると、コンパイラメッセージによって、Microsoft% 27s データ収集ポリシーを含む web サイトが参照されます。

### <a name="treat-specific-warnings-as-errors"></a>特定の警告をエラーとして扱う

特定のコンパイラ警告をエラーとして扱います。 n はコンパイラの警告です。

### <a name="additional-options"></a>追加オプション

その他のオプションです。
