---
title: fopen_s、_wfopen_s
ms.date: 11/04/2016
apiname:
- _wfopen_s
- fopen_s
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- fopen_s
- _tfopen_s
- _wfopen_s
helpviewer_keywords:
- _wfopen_s function
- opening files, for file I/O
- _tfopen_s function
- tfopen_s function
- wfopen_s function
- fopen_s function
- Unicode [C++], creating files
- Unicode [C++], writing files
- files [C++], opening
- Unicode [C++], files
ms.assetid: c534857e-39ee-4a3f-bd26-dfe551ac96c3
ms.openlocfilehash: e4ccce3c4a4fe1e327b7830ef03f6ab69f2d7814
ms.sourcegitcommit: 878a164fe6d550ca81ab87d8425c8d3cd52fe384
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/22/2019
ms.locfileid: "68376223"
---
# <a name="fopens-wfopens"></a>fopen_s、_wfopen_s

ファイルを開きます。 これらのバージョンの [fopen, _wfopen](fopen-wfopen.md) は、「[CRT のセキュリティ機能](../../c-runtime-library/security-features-in-the-crt.md)」の説明にあるとおり、セキュリティが強化されたバージョンです。

## <a name="syntax"></a>構文

```C
errno_t fopen_s(
   FILE** pFile,
   const char *filename,
   const char *mode
);
errno_t _wfopen_s(
   FILE** pFile,
   const wchar_t *filename,
   const wchar_t *mode
);
```

### <a name="parameters"></a>パラメーター

*pFile*<br/>
開かれたファイルへのポインターを受け取るファイル ポインターへのポインター。

*ファイル名*<br/>
ファイル名。

*モード*<br/>
アクセス許可の種類。

## <a name="return-value"></a>戻り値

正常終了した場合は 0 を返します。失敗した場合はエラー コードを返します。 これらのエラー コードの詳細については、「[errno、_doserrno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。

### <a name="error-conditions"></a>エラー条件

|*pFile*|*ファイル名*|*モード*|戻り値|*PFile*の内容|
|-------------|----------------|------------|------------------|------------------------|
|**NULL**|任意|任意|**EINVAL**|変更なし|
|任意|**NULL**|任意|**EINVAL**|変更なし|
|任意|任意|**NULL**|**EINVAL**|変更なし|

## <a name="remarks"></a>Remarks

**Fopen_s**および **_wfopen_s**によって開かれたファイルは共有できません。 ファイルを共有可能にする必要がある場合は、適切な共有モード定数 (たとえば、読み取り/書き込み**共有の場合**は[_fsopen、_wfsopen](fsopen-wfsopen.md) ) を使用してください。

**Fopen_s**関数は、 *filename*によって指定されたファイルを開きます。 **_wfopen_s**は、 **fopen_s**のワイド文字バージョンです。 **_wfopen_s**の引数はワイド文字列です。 それ以外では、 **_wfopen_s**と**fopen_s**は同じように動作します。

**fopen_s**は、実行時にファイルシステムで有効なパスを受け入れます。マップされたネットワークドライブを含む UNC パスとパスは、コードを実行しているシステムが実行時に共有またはマップされたネットワークドライブにアクセスできる限り、 **fopen_s**によって受け入れられます。 **Fopen_s**のパスを構築する場合は、実行環境でのドライブ、パス、またはネットワーク共有の可用性について想定しないでください。 ディレクトリのパス区切り記号としてスラッシュ (/) または円記号 (\\) のどちらかを使用できます。

これらの関数では、パラメーターの検証が行われます。 *PFile*、 *filename*、または*mode*が Null ポインターの場合、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、これらの関数は無効なパラメーター例外を生成します。

ファイルでその他の操作を実行する前には、必ず戻り値をチェックして関数が成功したかどうかを確認します。 エラーが発生した場合は、エラーコードが返され、グローバル変数**errno**が設定されます。 詳細については、「[errno、_doserrno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。

## <a name="unicode-support"></a>Unicode のサポート

**fopen_s**は Unicode ファイルストリームをサポートしています。 新規または既存の Unicode ファイルを開くには、目的のエンコードを指定する*ccs*フラグを**fopen_s**に渡します。

**fopen_s (& fp、"newfile"、"rw, ccs =** _encoding_ **");**

*エンコード*に使用できる値は、 **UNICODE**、 **utf-8**、および**16LE**です。 *エンコード*に値が指定されていない場合、 **fopen_s**は ANSI エンコーディングを使用します。

既に存在するファイルを読み取り用または追加用に開く場合は、ファイル内にバイト順マーク (BOM: Byte Order Mark) があれば、それによってエンコーディングが決定されます。 BOM エンコーディングは、 *ccs*フラグによって指定されたエンコーディングよりも優先されます。 *Ccs* encoding は、BOM が存在しない場合、またはファイルが新しいファイルの場合にのみ使用されます。

> [!NOTE]
> BOM 検出は、Unicode モードで開かれたファイルにのみ適用されます。つまり、 *ccs*フラグを渡します。

次の表は、 **fopen_s**に渡されるさまざまな*ccs*フラグと、ファイル内のバイト順マークのモードをまとめたものです。

### <a name="encodings-used-based-on-ccs-flag-and-bom"></a>ccs フラグおよび BOM に基づいて使用されるエンコーディング

|ccs フラグ|BOM なし (または新しいファイル)|消費UTF-8|消費UTF-16|
|----------------|----------------------------|-----------------|------------------|
|**対応**|**16LE**|**UTF-8**|**16LE**|
|**UTF-8**|**UTF-8**|**UTF-8**|**16LE**|
|**16LE**|**16LE**|**UTF-8**|**16LE**|

Unicode モードで書き込むように開かれたファイルには、自動的に BOM が書き込まれます。

*Mode*が **"a, ccs =** _encoding_ **"** の場合、 **fopen_s**は、最初に読み取りアクセスと書き込みアクセスの両方でファイルを開こうとします。 成功すると、この関数は BOM を読み取ってファイルのエンコーディングを決定します。失敗した場合は、ファイルに対して既定のエンコーディングを使用します。 どちらの場合も、 **fopen_s**は、書き込み専用アクセスでファイルを再度開きます。 (これは、 **+** ではなく **、モードのみ**に適用されます)。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tfopen_s**|**fopen_s**|**fopen_s**|**_wfopen_s**|

文字文字列*モード*では、次のように、ファイルに要求されるアクセスの種類を指定します。

|*モード*|アクセス|
|-|-|
| **"r"** | 読み取り用に開きます。 ファイルが存在しないか見つからない場合、 **fopen_s**の呼び出しは失敗します。 |
| **"w"** | 書き込み用に空のファイルを開きます。 指定したファイルが既に存在すると、そのファイルの内容は破棄されます。 |
| **"a"** | 末尾に書き込みができるようにファイルを開きます (追加モード)。EOF (end-of-file) マーカーを削除せずにファイルに新しいデータを書き込みます。 ファイルが存在しない場合は、作成します。 |
| **"r+"** | 読み取りと書き込みの両方のモードで開きます。 ファイルが存在している必要があります。 |
| **"w+"** | 読み取りと書き込みの両方のモードで空のファイルを開きます。 そのファイルが既に存在すると、そのファイルの内容は破棄されます。 |
| **"a+"** | 読み取りと追加の両方のモードでファイルを開きます。 追加操作には、新しいデータをファイルに書き込む前に EOF マーカーを削除することが含まれます。 書き込みの完了後に、EOF マーカーは復元されません。 ファイルが存在しない場合は、作成します。 |

**"A"** または **"a +"** アクセスの種類を使用してファイルを開くと、すべての書き込み操作がファイルの末尾で行われます。 ファイルポインターは、 [fseek](fseek-fseeki64.md)または[rewind](rewind.md)を使用して移動できますが、既存のデータを上書きできないように、書き込み操作が実行される前に常にファイルの末尾に戻されます。

**"A"** モードでは、ファイルに追加する前に EOF マーカーは削除されません。 追加が行われても、MS-DOS TYPE コマンドでは元の EOF マーカーまでのデータしか表示されず、ファイルに追加されたデータは表示されません。 **"A +"** モードでは、ファイルに追加する前に EOF マーカーが削除されます。 追加が終了すると、MS-DOS の TYPE コマンドでファイル内すべてのデータが表示されます。 CTRL + Z EOF マーカーを使用して終了するストリームファイルに追加するには、 **"a +"** モードが必要です。

**"R +"** 、 **"w +"** 、または **"a +"** のアクセスの種類が指定されている場合は、読み取りと書き込みの両方が許可されます。 (ファイルは "更新" モードで開きます)。ただし、読み取りから書き込みに切り替えると、入力操作は EOF マーカーを検出する必要があります。 EOF がない場合、ファイル ポジショニング関数の中間の呼び出しを使用する必要があります。 ファイルポジショニング関数は、 **fsetpos**、 [fseek](fseek-fseeki64.md)、および[rewind](rewind.md)です。 書き込みから読み取りに切り替える場合は、 **fflush**またはファイル配置関数のいずれかに介在する呼び出しを使用する必要があります。

上記の値に加えて、次の文字を*モード*で使用して、改行文字の変換モードを指定できます。

|*モード*修飾子|変換モード|
|-|-|
| **t** | ファイルをテキスト (変換) モードで開きます。 |
| **b** | バイナリ (無変換) モードで開く復帰文字と改行文字を含む翻訳は抑制されます。 |

テキスト (変換) モードでは、CTRL + Z は入力時にファイルの終端文字として解釈されます。 **"A +"** を使用して読み取り/書き込み用に開かれたファイルでは、 **fopen_s**がファイルの末尾に CTRL + Z があるかどうかを確認し、可能な場合は削除します。 この処理が行われる理由は、CTRL + Z で終わるファイル内で[fseek](fseek-fseeki64.md)と**ftell**を使用して移動すると、ファイルの末尾付近で[fseek](fseek-fseeki64.md)が正しく動作しなくなる可能性があるためです。

また、テキストモードでは、キャリッジリターンラインフィードの組み合わせは入力時に1つの改行に変換され、ラインフィード文字は出力時に復帰と改行の組み合わせに変換されます。 Unicode のストリーム入出力関数が既定のテキスト モードで動作すると、入力元または出力先のストリームはマルチバイト文字のシーケンスと仮定されます。 このため、Unicode ストリーム入力関数はマルチバイト文字をワイド文字に変換し、 **mbtowc** 関数を呼び出した場合と同様の効果を得ます。 同様の理由で、Unicode ストリーム出力関数は、 **wctomb** 関数が呼び出されたかのように、ワイド文字をマルチバイト文字に変換します。

**T**または**b**を*モード*で指定しない場合、既定の変換モードは、グローバル変数[_fmode](../../c-runtime-library/fmode.md)によって定義されます。 **T**または**b**が引数の前に付加されている場合、関数は失敗し、 **NULL**を返します。

Unicode およびマルチバイトのストリーム入出力におけるテキスト モードおよびバイナリ モードの使い方の詳細については、「[テキスト モードとバイナリ モードのファイル入出力](../../c-runtime-library/text-and-binary-mode-file-i-o.md)」および「[テキスト モードとバイナリ モードの Unicode ストリーム入出力](../../c-runtime-library/unicode-stream-i-o-in-text-and-binary-modes.md)」を参照してください。

|*モード*修飾子|動作|
|-|-|
| **c** | 関連付けられている*ファイル名*のコミットフラグを有効にして、 **fflush**または **_flushall**が呼び出された場合に、ファイルバッファーの内容がディスクに直接書き込まれるようにします。 |
| **n** | 関連付けられている*ファイル名*のコミットフラグを "コミットなし" にリセットします。 既定値です。 プログラムを COMMODE.OBJ とリンクする場合は、グローバル コミット フラグもオーバーライドします。 プログラムを明示的に COMMODE.OBJ とリンクしない場合、グローバル コミット フラグの既定の設定は "コミットなし" です (「 [Link Options](../../c-runtime-library/link-options.md)」をご覧ください)。 |
| **N** | ファイルが子プロセスによって継承されないように指定します。 |
| **S** | キャッシュがディスクからのシーケンシャル アクセスに最適化されるように指定します。ただし、シーケンシャル アクセスに限定されるわけではありません。 |
| **R** | キャッシュがディスクからのランダム アクセスに最適化されるように指定します。ただし、ランダム アクセスに限定されるわけではありません。 |
| **T** | ファイルを一時ファイルとして指定します。 可能な場合、ファイルはディスクにフラッシュされません。 |
| **D** | ファイルを一時ファイルとして指定します。 最後のファイル ポインターが閉じられると、ファイルは削除されます。 |
| **ccs =** _エンコード_ | このファイルに使用するエンコードされた文字セット ( **utf-8**、 **Utf 16LE**、 **UNICODE**のいずれか) を指定します。 何も指定しない場合は、ANSI エンコーディングが使用されます。 |

**Fopen_s**および[_fdopen](fdopen-wfdopen.md)で使用される*モード*文字列の有効な文字は、次のように、 [_open](open-wopen.md)および[_sopen](sopen-wsopen.md)で使用される*oflag*引数に対応します。

|*Mode*文字列の文字|_Open/_sopen の同等の*oflag*値|
|-------------------------------|----------------------------------------------------|
|**a**|**_O_WRONLY**&#124; **_O_APPEND** (通常は **_O_WRONLY** &#124; **_O_CREAT** &#124;* * _O_APPEND * *)|
|**+**|**_O_RDWR** &#124; **_O_APPEND** (usually **_O_RDWR** &#124; **_O_APPEND** &#124; **_O_CREAT** )|
|**r**|**_O_RDONLY**|
|**r +**|**_O_RDWR**|
|**w**|**_O_WRONLY** (usually **_O_WRONLY** &#124; **_O_CREAT** &#124;** _O_TRUNC**)|
|**w +**|**_O_RDWR**(通常は **_O_RDWR** &#124; **_O_CREAT** &#124; **_O_TRUNC**)|
|**b**|**_O_BINARY**|
|**t**|**_O_TEXT**|
|**c**|なし|
|**n**|なし|
|**S**|**_O_SEQUENTIAL**|
|**R**|**_O_RANDOM**|
|**T**|**_O_SHORTLIVED**|
|**D**|**_O_TEMPORARY**|
|**ccs = UNICODE**|**_O_WTEXT**|
|**ccs = UTF-8**|**_O_UTF8**|
|**ccs = 16LE**|**_O_UTF16**|

**Rb**モードを使用していて、コードを移植する必要がなく、大量のファイルを読み取ることが予想される場合や、ネットワークのパフォーマンスを気にしない場合は、メモリマップト Win32 ファイルもオプションになることがあります。

## <a name="requirements"></a>必要条件

|関数|必須ヘッダー|
|--------------|---------------------|
|**fopen_s**|\<stdio.h>|
|**_wfopen_s**|\<stdio.h> または \<wchar.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="libraries"></a>ライブラリ

[C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。

**C**、 **n**、および**t** *モード*のオプションは、Microsoft extensions for **fopen_s** and [_fdopen](fdopen-wfdopen.md)であり、ANSI の移植性が必要な場合は使用しないでください。

## <a name="example"></a>例

```C
// crt_fopen_s.c
// This program opens two files. It uses
// fclose to close the first file and
// _fcloseall to close all remaining files.

#include <stdio.h>

FILE *stream, *stream2;

int main( void )
{
   errno_t err;

   // Open for read (will fail if file "crt_fopen_s.c" does not exist)
   err  = fopen_s( &stream, "crt_fopen_s.c", "r" );
   if( err == 0 )
   {
      printf( "The file 'crt_fopen_s.c' was opened\n" );
   }
   else
   {
      printf( "The file 'crt_fopen_s.c' was not opened\n" );
   }

   // Open for write
   err = fopen_s( &stream2, "data2", "w+" );
   if( err == 0 )
   {
      printf( "The file 'data2' was opened\n" );
   }
   else
   {
      printf( "The file 'data2' was not opened\n" );
   }

   // Close stream if it is not NULL
   if( stream )
   {
      err = fclose( stream );
      if ( err == 0 )
      {
         printf( "The file 'crt_fopen_s.c' was closed\n" );
      }
      else
      {
         printf( "The file 'crt_fopen_s.c' was not closed\n" );
      }
   }

   // All other files are closed:
   int numclosed = _fcloseall( );
   printf( "Number of files closed by _fcloseall: %u\n", numclosed );
}
```

```Output
The file 'crt_fopen_s.c' was opened
The file 'data2' was opened
Number of files closed by _fcloseall: 1
```

## <a name="see-also"></a>関連項目

[ストリーム入出力](../../c-runtime-library/stream-i-o.md)<br/>
[fclose、_fcloseall](fclose-fcloseall.md)<br/>
[_fdopen、_wfdopen](fdopen-wfdopen.md)<br/>
[ferror](ferror.md)<br/>
[_fileno](fileno.md)<br/>
[freopen、_wfreopen](freopen-wfreopen.md)<br/>
[_open、_wopen](open-wopen.md)<br/>
[_setmode](setmode.md)<br/>
