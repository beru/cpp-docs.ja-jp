---
title: Visual Studio での C++ のサポートをインストール
description: Visual Studio の Visual C サポートをインストールします。
ms.custom: mvc
ms.date: 04/02/2019
ms.topic: tutorial
ms.devlang: cpp
ms.assetid: 45138d70-719d-42dc-90d7-1d0ca31a2f54
ms.openlocfilehash: 2c2bed4063194bdc3c0f3fbc405be6bf9a4031e7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62315196"
---
# <a name="install-c-support-in-visual-studio"></a>Visual Studio での C++ のサポートをインストール

まだ Visual Studio および Visual C++ ツールをダウンロードおよびインストールしていない場合は、次の方法で作業を開始できます。


::: moniker range="vs-2019"

## <a name="visual-studio-2019-installation"></a>Visual Studio 2019 のインストール

Visual Studio 2019 へようこそ このバージョンでは、必要な機能だけを簡単に選択してインストールできます。 占有領域が最小限まで小さくなっているため、インストールが速く、システムにほとんど影響しません。

> [!NOTE]
> このトピックでは、Windows 上の Visual Studio のインストールに適用されます。 [Visual Studio Code](https://code.visualstudio.com/)は Windows、Mac、および Linux システムで実行される軽量のクロスプラット フォーム開発環境です。 Microsoft [for Visual Studio Code には、C/C++](https://marketplace.visualstudio.com/items?itemName=ms-vscode.cpptools)拡張機能は、IntelliSense、デバッグ、コードの書式設定、オート コンプリートをサポートしています。 Visual Studio for Mac では、Microsoft C でサポートされていませんは .NET 言語とクロス プラットフォーム開発をサポートします。 インストール手順については、次を参照してください。 [Visual Studio for Mac をインストール](/visualstudio/mac/installation/)します。

このバージョンの他の新機能については、 Visual studio[リリース ノート](/visualstudio/releases/2019/release-notes/)します。

インストールの準備ができたら、 各ステップを順に実行していきます。

### <a name="step-1---make-sure-your-computer-is-ready-for-visual-studio"></a>手順 1 - コンピューターで Visual Studio の準備ができていることを確認する

Visual Studio のインストールを開始する前に

1. [システム要件](/visualstudio/releases/2019/system-requirements)を確認します。 これらの要件により、ご利用のコンピューターが Visual Studio 2019 に対応しているかどうかを確認できます。

1. 最新の Windows 更新プログラムを適用します。 これらの更新プログラムにより、Visual Studio の最新のセキュリティ更新プログラムと必要なシステム コンポーネントの両方がコンピューターにインストールされます。

1. 再起動します。 この再起動により、Visual Studio のインストールの際に妨げとなる、保留中のインストールや更新プログラムがないようにします。

1. 記憶域を解放します。 ディスク クリーンアップ アプリを実行するなどして、%SystemDrive% から不要なファイルとアプリケーションを削除します。

Visual Studio 2019 と以前のバージョンの Visual Studio を共存させて実行することについて疑問点がある場合は、「[Visual Studio 2019 の対象プラットフォームと互換性](/visualstudio/releases/2019/compatibility/)」ページをご覧ください。

### <a name="step-2---download-visual-studio"></a>手順 2 - Visual Studio をダウンロードする

次に、Visual Studio ブートストラップ ファイルをダウンロードします。 これを行うには、以下のボタンを選択し、必要な Visual Studio のエディションを選択して、**[保存]**、**[フォルダーを開く]** の順に選択します。

 > [!div class="button"]
 > [Visual Studio のダウンロード](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019+rc)

### <a name="step-3---install-the-visual-studio-installer"></a>手順 3 - Visual Studio インストーラーをインストールする

ブートストラップ ファイルを実行して、Visual Studio インストーラーをインストールします。 この新しい軽量インストーラーには、Visual Studio のインストールとカスタマイズの両方に必要なすべてのものが含まれています。

1. **[ダウンロード]** フォルダーで、次のいずれかのファイルと一致する、または似ているブートストラップをダブルクリックします。

   * Visual Studio Community の場合は **vs_community.exe**
   * Visual Studio Professional の場合は **vs_professional.exe**
   * Visual Studio Enterprise の場合は **vs_enterprise.exe**

   ユーザー アカウント制御の通知を受信する場合、**[はい]** を選択します。

1. Microsoft の[ライセンス条項](https://visualstudio.microsoft.com/license-terms/)と[プライバシーに関する声明](https://privacy.microsoft.com/privacystatement)の確認を求められます。 **[続行]** を選択します。

### <a name="step-4---choose-workloads"></a>手順 4 - ワークロードを選択する

インストーラーがインストールされた後は、インストールを選択してカスタマイズするを使用できます、*ワークロード*の機能セットを使用するか。 ここではその方法を説明します。

1. **[Visual Studio のインストール]** 画面で、必要なワークロードを見つけます。

   ![Visual Studio 2019:ワークロードをインストールする](../get-started/media/vs-installer-workloads.png)

   C++ のコア サポートについては、「C++ によるデスクトップ開発」ワークロードを選択します。 これには既定のコア エディターが用意されており、20 を超える言語の基本的なコード編集サポートが含まれ、プロジェクトなしで任意のフォルダーからコードを開いて編集することができます。また、統合ソース コード管理を利用できます。

   追加のワークロードでは、C++ 開発の他の種類をサポートします。 たとえば、Windows ランタイムを使用して、Microsoft Store のアプリを作成する「ユニバーサル Windows プラットフォーム開発」ワークロードを選択します。 「C++ によるゲーム開発」を選択し、DirectX、Unreal、Cocos2d を使用してゲームを作成します。 IoT 開発を含む、ターゲットの Linux プラットフォームに「C++ による Linux 開発」を選択します。

   **インストールの詳細**ウィンドウには、各ワークロードによってインストールされた付属しており、省略可能なコンポーネントが一覧表示されます。 選択するか、この一覧でオプションのコンポーネントの選択を解除できます。 たとえば、Visual Studio 2017 または 2015年コンパイラ ツールセットを使用して開発をサポートするために、MSVC v141 または MSVC v140 の省略可能なコンポーネントを選択します。 MFC、実験のモジュールの言語拡張機能、IncrediBuild は、その他のサポートを追加することができます。

1. ワークロードとする省略可能なコンポーネントを選択した後選択**インストール**します。

    そうすると、ステータス画面が表示され、Visual Studio のインストールの進行状況が示されます。

> [!TIP]
> インストール後いつでも、最初にインストールしなかったワークロードまたはコンポーネントをインストールできます。 Visual Studio を開いている場合は、**[ツール]** > **[ツールと機能を取得]** に移動すると、Visual Studio インストーラーが開きます。 または、スタート メニューから **Visual Studio インストーラー**を開きます。 そこから、インストールするワークロードまたはコンポーネントを選択できます。 次に、**[変更]** を選択します。

## <a name="step-5---choose-individual-components-optional"></a>手順 5 - 個々のコンポーネントを選択する (省略可能)

ワークロード機能を使用して Visual Studio のインストールをカスタマイズしない場合、またはワークロードのインストール以外のコンポーネントを追加する場合は、**[個別のコンポーネント]** タブから個々のコンポーネントをインストールまたは追加することによって行うことができます。必要なものを選択した後、画面の指示に従います。

  ![Visual Studio 2019 - 個々のコンポーネントのインストール](../get-started/media/vs-installer-individual-components.png "Visual Studio の個々のコンポーネントのインストール")

## <a name="step-6---install-language-packs-optional"></a>手順 6 - 言語パックをインストールする (省略可能)

既定では、インストーラー プログラムが、最初の実行時にオペレーティング システムの言語の照合を試みます。 選択した言語で Visual Studio をインストールするには、Visual Studio インストーラーで **[言語パック]** タブをクリックした後、画面の指示に従います。

  ![Visual Studio 2019 - 言語パックのインストール](../get-started/media/vs-installer-language-packs.png "Visual Studio の言語パックのインストール")

### <a name="change-the-installer-language-from-the-command-line"></a>コマンド ラインかインストーラーの言語を変更する

コマンド ラインからインストーラーを実行して、既定の言語を変更することもできます。 たとえば、`vs_installer.exe --locale en-US` コマンドを実行して、インストーラーを英語で実行するように指定することができます。 インストーラーは、次回実行した場合、この設定が記憶されます。 インストーラーでは次の言語トークンがサポートされます。zh-cn、zh-tw、cs-cz、en-us、es-es、fr-fr、de-de、it-it、ja-jp、ko-kr、pl-pl、pt-br、ru-ru、tr-tr。

### <a name="step-7---change-the-installation-location-optional"></a>手順 7 - インストール場所の変更 (省略可能)

システム ドライブ上の Visual Studio のインストール占有領域を小さくすることができます。 ダウンロード キャッシュ、共有コンポーネント、SDK、およびツールを別のドライブに移動して、Visual Studio を最速で実行できるドライブで維持できます。

  ![Visual Studio 2019 - インストール場所を変更する](../get-started/media/vs-installer-installation-locations.png "インストール場所を変更する")

> [!IMPORTANT]
> Visual Studio を初めてインストールするときにのみ、別のドライブを選択できます。 既にインストールしてあるドライブを変更する場合は、Visual Studio をアンインストールした後、再インストールする必要があります。

## <a name="step-8---start-developing"></a>手順 8 - 開発を始める

1. Visual Studio のインストールが完了したら **[起動]** を選択して、Visual Studio を使用した開発を開始します。

1. スタート ウィンドウで、**[新しいプロジェクトの作成]** を選択します。

1. 検索ボックスに作成するアプリの種類を入力し、使用可能なテンプレートの一覧を表示します。 テンプレートの一覧は、インストール時に選択したワークロードに依存します。 別のテンプレートを表示するには、異なるワークロードを選択します。

   **[言語]** ドロップダウン リストを使用して、特定のプログラミング言語に検索をフィルター処理することもできます。 **[プラットフォーム]** の一覧や **[プロジェクトの種類]** の一覧を使用して、フィルター処理することもできます。

1. Visual Studio で新しいプロジェクトが開き、コーディングできる状態になります。

::: moniker-end

::: moniker range="<=vs-2017"

## <a name="visual-studio-2017-installation"></a>Visual Studio 2017 のインストール

Visual Studio 2017 では、簡単に選択し、必要な機能だけをインストールできますが。 占有領域が最小限まで小さくなっているため、インストールが速く、システムにほとんど影響しません。

### <a name="prerequisites"></a>必須コンポーネント

- ブロードバンド インターネットの接続。 Visual Studio インストーラーでは数ギガバイトのデータをダウンロードします。

- Microsoft Windows 7 またはそれ以降のバージョンを実行するコンピューター。 開発のベスト エクスペリエンスを実現するには Windows 10 をお勧めします。 Visual Studio をインストールする前に、システムに最新の更新プログラムが適用されることを確認します。

- 十分な空きディスク領域。 Visual Studio では、7 GB 以上のディスク領域が必要ですし、多くの一般的なオプションがインストールされている場合、50 GB 以上かかることができます。 C: ドライブにインストールすることをお勧めします。

ディスク容量とオペレーティング システムの要件の詳細については、次を参照してください。 [Visual Studio 製品ファミリのシステム要件](/visualstudio/productinfo/vs2017-system-requirements-vs)します。 インストーラーにより、選択したオプションに必要なディスク領域の量が報告されます。

### <a name="download-and-install"></a>ダウンロードしてインストールする

1. Windows の最新の Visual Studio 2017 インストーラーをダウンロードします。

   > [!div class="nextstepaction"]
   > [Visual Studio 2017 のインストールに関するコミュニティ](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)

   >[!Tip]
   > このコミュニティ版は、個人の開発者、クラス学習、学術研究、オープン ソース開発向けです。 その他の用途には、[Visual Studio 2017 Professional](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) または [Visual Studio 2017 Enterprise](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) を使用してください。

1. ダウンロードしたインストーラー ファイルを検索して実行します。 ブラウザーに表示されるか、ダウンロード フォルダーで見つかるでしょう。 インストーラーを実行するには、管理者特権が必要です。 インストーラーでシステムに変更を加えることを可能にするアクセス許可を付与するかどうかを求める **[ユーザーアカウント制御]** ダイアログが表示されます **。** ファイル エクスプ ローラーで、ダウンロードしたファイルを検索する問題がある場合、インストーラーのアイコンを右クリックし、選択**管理者として実行**コンテキスト メニュー。

   ![ダウンロードして、Visual Studio インストーラーをインストール](media/vscpp-concierge-run-installer.gif "をダウンロードして、Visual Studio インストーラーのインストール")

1. インストーラーによってワークロードの一覧が表示されます。これは、特定の開発分野の関連オプションのグループです。 C++ のサポートは、既定ではインストールされていないオプションのワークロードの一部です。

   ![C++ ワークロードによるデスクトップ開発](media/desktop-development-with-cpp.png "C++ によるデスクトップ開発")

   C++ の場合は、**[C++ ワークロードを使用したデスクトップ開発]** を選択し、それから **[インストール]** を選択してください。

   ![C++ のワークロードを使用したデスクトップ開発をインストール](media/vscpp-concierge-choose-workload.gif "C++ ワークロードでのデスクトップ開発のインストール")

1. インストールが完了したら、**[起動]** ボタンを選択して Visual Studio を起動します。

   初めて Visual Studio を実行する Microsoft アカウントでサインインするか求められます。 アカウントをお持ちでない場合は、新しいアカウントを無料で作成できます。 テーマを選択する必要もあります。 後で変更することもできるので、ご安心ください。

   Visual Studio をいくつかでかかる場合がありますを準備する分を使用して、初めて実行します。 どのようになるかを、短いコマ撮りで次に示します。


   ![Visual Studio 2017 のサインイン](media/vscpp-quickstart-first-run.gif "Visual Studio 2017 のサインイン")

   Visual Studio は、二回目の起動からは、とても高速に起動します。

1. Visual Studio が開いたらは、タイトル バーでフラグ アイコンが強調表示されているかどうかを確認します。

   ![Visual Studio 2017 の通知フラグ](media/vscpp-first-start-page-flag.png "Visual Studio 2017 の通知フラグ")

   強調表示されている場合を選択して開きます、**通知**ウィンドウ。 Visual Studio に利用可能な更新プログラムがある場合には、今すぐインストールすることをお勧めします。 インストールが完了したら、Visual Studio を再起動してください。

::: moniker-end

::: moniker range="<vs-2017"

## <a name="visual-studio-2015-installation"></a>Visual Studio 2015 のインストール

Visual Studio 2015 をインストールするには、[以前のバージョンの Visual Studio のダウンロード](https://www.visualstudio.com/vs/older-downloads/) ページに移動してください。 セットアップ プログラムを実行し、**カスタム インストール**で C++ コンポーネントを選択します。 既存の Visual Studio 2015 インストールには、C++ のサポートを追加するには、種類と Windows のスタート ボタンをクリックして**プログラムの追加と削除**します。 結果の一覧からプログラムを開き、インストールされているプログラムの一覧で、Visual Studio 2015 のインストールを検索します。 選択し、それをダブルクリックして**変更**をインストールする Visual C コンポーネントを選択します。

一般に、Visual Studio 2015 のコンパイラを使用してコードをコンパイルする必要がある場合でも、Visual Studio 2017 を使用することを強くお勧めします。 詳細については、「[Visual Studio でネイティブ マルチ ターゲットを利用し、古いプロジェクトを作成する](../porting/use-native-multi-targeting.md)」を参照してください。

::: moniker-end

Visual Studio が実行されている場合は、次の手順に進む準備ができました。

## <a name="next-steps"></a>次の手順

> [!div class="nextstepaction"]
> [C++ プロジェクトの作成](vscpp-step-1-create.md)

<iframe src="" height="0" width="0" frameborder="0" name="frameTarget" />
