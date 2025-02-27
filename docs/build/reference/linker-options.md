---
title: MSVC リンカー オプション
ms.date: 08/20/2018
f1_keywords:
- link
helpviewer_keywords:
- linker [C++]
- linker [C++], options listed
- libraries [C++], linking to COFF
- LINK tool [C++], linker options
ms.assetid: c1d51b8a-bd23-416d-81e4-900e02b2c129
ms.openlocfilehash: 7ff8ecd6a607aac59fca6d32fa2784e7e3e4268f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62301761"
---
# <a name="linker-options"></a>リンカー オプション

LINK.exe は、COFF (Common Object File Format) オブジェクト ファイルとライブラリをリンクし、実行可能ファイル (.exe) やダイナミック リンク ライブラリ (DLL: Dynamic-Link Library) を生成します。

LINK.exe のオプションの一覧を次の表に示します。 LINK の詳細については、下記を参照してください。

- [コンパイラで制御される LINK オプション](compiler-controlled-link-options.md)

- [LINK の入力ファイル](link-input-files.md)

- [LINK 出力](link-output.md)

- [予約語](reserved-words.md)

コマンドラインでリンカー オプションは; 大文字小文字を区別できません。たとえば、/base と/BASE は同じ意味です。 コマンド ラインまたは Visual Studio で各オプションを指定する方法の詳細については、そのオプションのドキュメントを参照してください。

[comment](../../preprocessor/comment-c-cpp.md) プラグマを使用して、一部のリンカー オプションを指定できます。

|オプション|目的|
|------------|-------------|
|[@](at-specify-a-linker-response-file.md)|応答ファイルを指定します。|
|[/ALIGN](align-section-alignment.md)|各セクションのアラインメントを指定します。|
|[/ALLOWBIND](allowbind-prevent-dll-binding.md)|DLL をバインディングできないことを指定します。|
|[/ALLOWISOLATION](allowisolation-manifest-lookup.md)|マニフェスト検索の動作を指定します。|
|[/APPCONTAINER](appcontainer-windows-store-app.md)|アプリケーションが appcontainer プロセス環境内で実行される必要があるかどうかを指定します。|
|[/ASSEMBLYDEBUG](assemblydebug-add-debuggableattribute.md)|<xref:System.Diagnostics.DebuggableAttribute> をマネージド イメージに追加します。|
|[/ASSEMBLYLINKRESOURCE](assemblylinkresource-link-to-dotnet-framework-resource.md)|マネージド リソースへのリンクを作成します。|
|[/ASSEMBLYMODULE](assemblymodule-add-a-msil-module-to-the-assembly.md)|MSIL (Microsoft Intermediate Language) モジュールをアセンブリにインポートする必要があることを指定します。|
|[/ASSEMBLYRESOURCE](assemblyresource-embed-a-managed-resource.md)|マネージド リソース ファイルをアセンブリに埋め込みます。|
|[/BASE](base-base-address.md)|プログラムのベース アドレスを設定します。|
|[/CGTHREADS](cgthreads-compiler-threads.md)|リンク時のコード生成を指定するときに、最適化およびコード生成に使用する cl.exe スレッド数を設定します。|
|[/CLRIMAGETYPE](clrimagetype-specify-type-of-clr-image.md)|CLR イメージの種類 (IJW、純粋、または安全) を設定します。|
|[/CLRSUPPORTLASTERROR](clrsupportlasterror-preserve-last-error-code-for-pinvoke-calls.md)|P/Invoke 機構を通じて呼び出された関数の最終エラー コードを保持します。|
|[/CLRTHREADATTRIBUTE](clrthreadattribute-set-clr-thread-attribute.md)|CLR プログラムのエントリ ポイントに適用するスレッド処理属性を指定します。|
|[/CLRUNMANAGEDCODECHECK](clrunmanagedcodecheck-add-suppressunmanagedcodesecurityattribute.md)|マネージド コードからネイティブ DLL への呼び出しを行う、リンカーによって生成された PInvoke スタブに、SuppressUnmanagedCodeSecurity 属性を適用するかどうかを指定します。|
|[/DEBUG](debug-generate-debug-info.md)|デバッグ情報を作成します。|
|[/DEBUGTYPE](debugtype-debug-info-options.md)|デバッグ情報に含めるデータを指定します。|
|[/DEF](def-specify-module-definition-file.md)|モジュール定義 (.def) ファイルをリンカーに渡します。|
|[/DEFAULTLIB](defaultlib-specify-default-library.md)|外部参照を解決するときに、指定したライブラリを検索します。|
|[/DELAY](delay-delay-load-import-settings.md)|DLL の遅延読み込みを制御します。|
|[/DELAYLOAD](delayload-delay-load-import.md)|指定した DLL に遅延読み込みを発生させます。|
|[/DELAYSIGN](delaysign-partially-sign-an-assembly.md)|アセンブリに部分署名します。|
|[/DEPENDENTLOADFLAG](dependentloadflag.md)|依存 DLL の読み込みには、既定のフラグを設定します。|
|[/DLL](dll-build-a-dll.md)|DLL をビルドします。|
|[/DRIVER](driver-windows-nt-kernel-mode-driver.md)|カーネル モード ドライバーを作成します。|
|[/DYNAMICBASE](dynamicbase-use-address-space-layout-randomization.md)|ASLR (Address Space Layout Randomization) 機能を使用してロード時にランダムに再ベースできる実行可能イメージを生成するかどうかを指定します。|
|[/ENTRY](entry-entry-point-symbol.md)|開始アドレスを設定します。|
|[/errorReport](errorreport-report-internal-linker-errors.md)|内部リンカー エラーを Microsoft に報告します。|
|[/EXPORT](export-exports-a-function.md)|関数をエクスポートします。|
|[/FILEALIGN](filealign.md)|指定された値の倍数で出力ファイル内のセクションを配置します。|
|[/FIXED](fixed-fixed-base-address.md)|指定のベース アドレスだけに読み込まれるプログラムを作成します。|
|[/FORCE](force-force-file-output.md)|未解決のシンボルまたは複数定義のシンボルがある場合でも、リンクを強制的に終了します。|
|[/FUNCTIONPADMIN](functionpadmin-create-hotpatchable-image.md)|ホット パッチ可能なイメージを作成します。|
|[/GENPROFILE、/FASTGENPROFILE](genprofile-fastgenprofile-generate-profiling-instrumented-build.md)|これらのオプションは、ガイド付き最適化のプロファイル (PGO) をサポートするために、どちらもリンカーによる .pgd ファイルの生成を指定します。 /GENPROFILE と /FASTGENPROFILE は、それぞれに異なる既定のパラメーターを使用します。|
|[/GUARD](guard-enable-guard-checks.md)|制御フロー ガードによる保護を有効にします。|
|[/HEAP](heap-set-heap-size.md)|ヒープ サイズをバイト単位で設定します。|
|[/HIGHENTROPYVA](highentropyva-support-64-bit-aslr.md)|高エントロピの 64 ビット ASLR (Address Space Layout Randomization) のサポートを指定します。|
|[/IDLOUT](idlout-name-midl-output-files.md)|.idl ファイル名およびその他の MIDL の出力ファイル名を指定します。|
|[/IGNORE](ignore-ignore-specific-warnings.md)|指定されたリンカー警告の出力を抑制します。|
|[/IGNOREIDL](ignoreidl-don-t-process-attributes-into-midl.md)|.idl ファイル内に属性情報を挿入しません。|
|[/IMPLIB](implib-name-import-library.md)|既定のインポート ライブラリ名をオーバーライドします。|
|[/INCLUDE](include-force-symbol-references.md)|シンボルを明示的に参照します。|
|[/INCREMENTAL](incremental-link-incrementally.md)|インクリメンタル リンクの処理方法を制御します。|
|[/INTEGRITYCHECK](integritycheck-require-signature-check.md)|モジュールが読み込み時に署名の確認を要求することを指定します。|
|[/KEYCONTAINER](keycontainer-specify-a-key-container-to-sign-an-assembly.md)|アセンブリに署名するためのキー コンテナーを指定します。|
|[/KEYFILE](keyfile-specify-key-or-key-pair-to-sign-an-assembly.md)|アセンブリに署名するキーまたはキー ペアを指定します。|
|[/LARGEADDRESSAWARE](largeaddressaware-handle-large-addresses.md)|アプリケーションが 2 GB を超えるアドレスをサポートしていることをコンパイラに指定します。|
|[/LIBPATH](libpath-additional-libpath.md)|環境ライブラリ パスの前に検索するパスを指定します。|
|[/LTCG](ltcg-link-time-code-generation.md)|リンク時のコード生成を指定します。|
|[/MACHINE](machine-specify-target-platform.md)|ターゲット プラットフォームを指定します。|
|[/MANIFEST](manifest-create-side-by-side-assembly-manifest.md)|side-by-side マニフェスト ファイルを作成し、バイナリに埋め込むことができるようにします。|
|[/MANIFESTDEPENDENCY](manifestdependency-specify-manifest-dependencies.md)|指定します、 \<dependentAssembly > セクションで、マニフェスト ファイル。|
|[/MANIFESTFILE](manifestfile-name-manifest-file.md)|マニフェスト ファイルの既定の名前を変更します。|
|[/MANIFESTINPUT](manifestinput-specify-manifest-input.md)|リンカーが処理を行い、バイナリに埋め込むための、マニフェスト入力ファイルを指定します。 このオプションを複数回使用して、複数のマニフェストの入力ファイルを指定できます。|
|[/MANIFESTUAC](manifestuac-embeds-uac-information-in-manifest.md)|ユーザー アカウント制御 (UAC) 情報をプログラム マニフェストに組み込むかどうかを指定します。|
|[/MAP](map-generate-mapfile.md)|マップファイルを作成します。|
|[/MAPINFO](mapinfo-include-information-in-mapfile.md)|指定した情報をマップ ファイルに格納します。|
|[/MERGE](merge-combine-sections.md)|セクションを結合します。|
|[/MIDL](midl-specify-midl-command-line-options.md)|MIDL コマンド ライン オプションを指定します。|
|[/NATVIS](natvis-add-natvis-to-pdb.md)|PDB に Natvis ファイルからデバッガー ビジュアライザーを追加します。|
|[/NOASSEMBLY](noassembly-create-a-msil-module.md)|.NET Framework アセンブリを作成しません。|
|[/NODEFAULTLIB](nodefaultlib-ignore-libraries.md)|外部参照を解決するときに、すべてのまたは指定した既定のライブラリを無視します。|
|[/NOENTRY](noentry-no-entry-point.md)|リソースだけの DLL を作成します。|
|[/NOLOGO](nologo-suppress-startup-banner-linker.md)|開始メッセージを表示しません。|
|[/NXCOMPAT](nxcompat-compatible-with-data-execution-prevention.md)|Windows データ実行防止機能との互換性が確認済みとして実行可能ファイルをマークします。|
|[/OPT](opt-optimizations.md)|LINK の最適化を制御します。|
|[/ORDER](order-put-functions-in-order.md)|指定された順序で COMDAT をイメージに取り込みます。|
|[/OUT](out-output-file-name.md)|出力ファイル名を指定します。|
|[/PDB](pdb-use-program-database.md)|プログラム データベース (PDB) ファイルを作成します。|
|[/PDBALTPATH](pdbaltpath-use-alternate-pdb-path.md)|別の場所を使用して PDB ファイルを保存します。|
|[/PDBSTRIPPED](pdbstripped-strip-private-symbols.md)|プログラム データベース (PDB) ファイルの作成時にプライベート シンボルを含めません。|
|[/PGD](pgd-specify-database-for-profile-guided-optimizations.md)|ガイド付き最適化のプロファイル用の .pgd ファイルを指定します。|
|[/POGOSAFEMODE](pogosafemode-linker-option.md)|**古い**スレッド セーフのインストルメント化 PGO ビルドを作成します。|
|[/PROFILE](profile-performance-tools-profiler.md)|パフォーマンス ツール プロファイラーで使用できる出力ファイルを作成します。|
|[/RELEASE](release-set-the-checksum.md)|.exe ヘッダーにチェックサムを設定します。|
|[/SAFESEH](safeseh-image-has-safe-exception-handlers.md)|安全な例外ハンドラーのテーブルがイメージに含まれるように指定します。|
|[/SECTION](section-specify-section-attributes.md)|セクションの属性をオーバーライドします。|
|[/SOURCELINK](sourcelink.md)|Pdb ファイルに追加する SourceLink ファイルを指定します。|
|[/STACK](stack-stack-allocations.md)|スタック サイズをバイト単位で設定します。|
|[/STUB](stub-ms-dos-stub-file-name.md)|MS-DOS スタブ プログラムを Win32 プログラムにアタッチします。|
|[/SUBSYSTEM](subsystem-specify-subsystem.md)|オペレーティング システムに対して、.exe ファイルの実行方法を指定します。|
|[/SWAPRUN](swaprun-load-linker-output-to-swap-file.md)|リンカー出力をスワップ ファイルにコピーしてから実行します。|
|[/TLBID](tlbid-specify-resource-id-for-typelib.md)|リンカーによって生成されたタイプ ライブラリのリソース ID を指定します。|
|[/TLBOUT](tlbout-name-dot-tlb-file.md)|.tlb ファイル名およびその他の MIDL の出力ファイル名を指定します。|
|[/TSAWARE](tsaware-create-terminal-server-aware-application.md)|ターミナル サーバーでの実行専用のアプリケーションを作成します。|
|[/USEPROFILE](useprofile.md)|最適化されたイメージを作成するには、最適化トレーニング データをプロファイル ガイド付きの使用。|
|[/VERBOSE](verbose-print-progress-messages.md)|リンカーの進行状況メッセージを出力します。|
|[/VERSION](version-version-information.md)|バージョン番号を割り当てます。|
|[/WHOLEARCHIVE](wholearchive-include-all-library-object-files.md)|指定された静的ライブラリからすべてのオブジェクト ファイルが含まれています。|
|[/WINMD](winmd-generate-windows-metadata.md)|Windows ランタイム メタデータ ファイルの生成を有効にします。|
|[/WINMDFILE](winmdfile-specify-winmd-file.md)|[/WINMD](winmd-generate-windows-metadata.md) のリンカー オプションによって生成される Windows のランタイム メタデータ (winmd) の出力ファイルの名前を指定します。|
|[/WINMDKEYFILE](winmdkeyfile-specify-winmd-key-file.md)|Windows ランタイム メタデータに署名するキーまたはキー ペアを指定します。|
|[/WINMDKEYCONTAINER](winmdkeycontainer-specify-key-container.md)|Windows メタデータ ファイルに署名するキー コンテナーを指定します。|
|[/WINMDDELAYSIGN](winmddelaysign-partially-sign-a-winmd.md)|winmd ファイルに公開キーを設定して、Windows のランタイム メタデータ (.winmd) ファイルに部分的に署名します。|
|[/WX](wx-treat-linker-warnings-as-errors.md)|リンカー警告をエラーとして扱います。|

詳細については、「 [Compiler-Controlled LINK Options](compiler-controlled-link-options.md)」を参照してください。

## <a name="see-also"></a>関連項目

[C/C++ ビルドのリファレンス](c-cpp-building-reference.md)<br/>
[MSVC リンカーのリファレンス](linking.md)
