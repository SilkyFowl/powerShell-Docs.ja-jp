---
title: Windows への PowerShell のインストール
description: Windows への PowerShell のインストールに関する情報
ms.date: 09/14/2020
ms.openlocfilehash: 8f1b60ef6bfef5c2434b0affabb5e0e7af392b96
ms.sourcegitcommit: 30c0c1563f8e840f24b65297e907f3583d90e677
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90574455"
---
# <a name="installing-powershell-on-windows"></a>Windows への PowerShell のインストール

Windows に PowerShell をインストールする方法は複数あります。

## <a name="prerequisites"></a>前提条件

PowerShell の最新リリースは、Windows 7 SP1、Server 2008 R2、およびそれ以降のバージョンでサポートされています。

WSMan を介して PowerShell のリモート処理を有効にするには、次の前提条件を満たす必要があります。

- Windows 10 より前のバージョンの Windows に[ユニバーサル C ランタイム](https://www.microsoft.com/download/details.aspx?id=50410)をインストールします。 これは、直接ダウンロードすることも、Windows Update 経由で入手することもできます。 完全にパッチが適用されたシステムには、既にこのパッケージがインストールされています。
- Windows Management Framework (WMF) 4.0 以降を Windows 7 と Windows Server 2008 R2 にインストールします。 WMF の詳細については、[WMF の概要](/powershell/scripting/wmf/overview)に関する記事を参照してください。

## <a name="download-the-installer-package"></a>インストーラー パッケージをダウンロードする

Windows に PowerShell をインストールするには、GitHub の[リリース][releases] ページからインストール パッケージをダウンロードします。 リリース ページの **[Assets]** セクションまで下にスクロールします。 **[Assets]** セクションは折りたたまれている場合があります。その場合は、クリックして展開する必要があります。

## <a name="installing-the-msi-package"></a><a id="msi" />MSI パッケージのインストール

MSI ファイルは、`PowerShell-<version>-win-<os-arch>.msi` のようになります。 次に例を示します。

- `PowerShell-7.0.3-win-x64.msi`
- `PowerShell-7.0.3-win-x86.msi`

ダウンロードしたら、インストーラーをダブルクリックし、プロンプトの指示に従います。

インストーラーにより、Windows の [スタート] メニューにショートカットが作成されます。

- パッケージは、既定で `$env:ProgramFiles\PowerShell\<version>` にインストールされます。
- PowerShell は、スタート メニューまたは  `$env:ProgramFiles\PowerShell\<version>\pwsh.exe` から起動できます。

> [!NOTE]
> PowerShell 7 は新しいディレクトリにインストールされ、Windows PowerShell 5.1 と side-by-side 実行されます。 PowerShell Core 6.x がインストールされている場合、PowerShell 7 にインプレース アップグレードされ、PowerShell Core 6.x は削除されます。
>
> - PowerShell 7 は `$env:ProgramFiles\PowerShell\7` にインストールされます
> - `$env:ProgramFiles\PowerShell\7` フォルダーは `$env:PATH` に追加されます
> - `$env:ProgramFiles\PowerShell\6` フォルダーは削除されます
>
> PowerShell 6 を PowerShell 7 と side-by-side 実行する必要がある場合は、[ZIP インストール](#zip)方法を使用して PowerShell 6 を再インストールします。

### <a name="administrative-install-from-the-command-line"></a>コマンド ラインからの管理者インストール

MSI パッケージはコマンド ラインからインストールできるため、管理者はユーザーの介入なしにパッケージを展開できます。 MSI パッケージには、インストールのオプションを制御するための次のプロパティが含まれます。

- **ADD_EXPLORER_CONTEXT_MENU_OPENPOWERSHELL** - このプロパティでは、エクスプローラーのコンテキスト メニューに **[Open PowerShell]\(PowerShell を開く\)** 項目を追加するためのオプションを制御します。
- **ENABLE_PSREMOTING** - このプロパティでは、インストール中に PowerShell リモート処理を有効にするためのオプションを制御します。
- **REGISTER_MANIFEST** - このプロパティでは、Windows イベント ログのマニフェストを登録するためのオプションを制御します。

すべてのインストール オプションを有効にして PowerShell をサイレント インストールする方法を、次の例に示します。

```powershell
msiexec.exe /package PowerShell-7.0.3-win-x64.msi /quiet ADD_EXPLORER_CONTEXT_MENU_OPENPOWERSHELL=1 ENABLE_PSREMOTING=1 REGISTER_MANIFEST=1
```

`Msiexec.exe` 用のコマンド ライン オプションの完全な一覧については、[コマンド ライン オプション](/windows/desktop/Msi/command-line-options)に関するページをご覧ください。

### <a name="registry-keys-created-during-installation"></a>インストール時に作成されるレジストリ キー

PowerShell 7.1 以降では、MSI パッケージによって、インストール場所と PowerShell のバージョンを格納するレジストリ キーが作成されます。 これらの値は `HKLM\Software\Microsoft\PowerShellCore\InstalledVersions\<GUID>` にあります。 `<GUID>` の値は、ビルドの種類 (リリースまたはプレビュー)、メジャー バージョン、およびアーキテクチャごとに一意です。

|    Release    | アーキテクチャ |                                          レジストリ キー                                           |
| ------------- | :----------: | ----------------------------------------------------------------------------------------------- |
| 7.1.x リリース |     x86      | `HKLM\Software\Microsoft\PowerShellCore\InstalledVersions\1d00683b-0f84-4db8-a64f-2f98ad42fe06` |
| 7.1.x リリース |     X64      | `HKLM\Software\Microsoft\PowerShellCore\InstalledVersions\31ab5147-9a97-4452-8443-d9709f0516e1` |
| 7.1.x プレビュー |     x86      | `HKLM\Software\Microsoft\PowerShellCore\InstalledVersions\86abcfbd-1ccc-4a88-b8b2-0facfde29094` |
| 7.1.x プレビュー |     X64      | `HKLM\Software\Microsoft\PowerShellCore\InstalledVersions\39243d76-adaf-42b1-94fb-16ecf83237c8` |

これは、管理者と開発者が PowerShell へのパスを見つけるために使用できます。 `<GUID>` の値は、すべてのプレビューおよびマイナー バージョンのリリースで同じになります。 `<GUID>` の値はメジャー リリースごとに変更されます。

## <a name="installing-the-msix-package"></a><a id="msix" />MSIX パッケージのインストール

> [!NOTE]
> 現時点では、MSIX パッケージは公式にサポートされていません。 私たちは引き続き、内部テストのみを目的としてパッケージをビルドします。

Windows 10 クライアントに MSIX パッケージを手動でインストールするには、Microsoft の GitHub [リリース][releases] ページから MSIX パッケージをダウンロードしてください。 インストールしたいリリースの **[Assets]** セクションまでスクロールダウンします。 [Assets] セクションは折りたたまれている場合があります。その場合は、クリックして展開する必要があります。

MSIX ファイルは、`PowerShell-<version>-win-<os-arch>.msix` のようになります。

パッケージをインストールするには、`Add-AppxPackage` コマンドレットを使用する必要があります。

```powershell
Add-AppxPackage PowerShell-<version>-win-<os-arch>.msix
```

## <a name="installing-the-zip-package"></a><a id="zip" />ZIP パッケージのインストール

PowerShell バイナリ ZIP アーカイブは、高度な展開シナリオ用に用意されています。 ZIP アーカイブをインストールしても、MSI パッケージのように前提条件は確認されません。 [リリース][releases] ページから ZIP アーカイブをダウンロードします。 ファイルのダウンロード方法によっては、`Unblock-File` コマンドレットを使用して、ファイルのブロックを解除することが必要になる場合があります。 任意の場所にコンテンツを解凍し、そこから `pwsh.exe` を実行します。 WSMan 経由でのリモート処理を正常に動作させるために、[前提条件](#prerequisites)を満たしていることを確かめてください。

## <a name="deploying-on-windows-10-iot-enterprise"></a>Windows 10 IoT Enterprise への展開

Windows 10 IoT Enterprise には、PowerShell 7 の展開に使用できる Windows PowerShell が付属しています。

1. ターゲット デバイスに対して `PSSession` を作成します

   ```powershell
   Set-Item -Path WSMan:\localhost\Client\TrustedHosts <deviceip>
   $S = New-PSSession -ComputerName <deviceIp> -Credential Administrator
   ```

1. ZIP パッケージをデバイスにコピーします

   ```powershell
   # change the destination to however you had partitioned it with sufficient
   # space for the zip and the unzipped contents
   # the path should be local to the device
   Copy-Item .\PowerShell-<version>-win-<os-arch>.zip -Destination u:\users\administrator\Downloads -ToSession $s
   ```

1. デバイスに接続してアーカイブを展開します

   ```powershell
   Enter-PSSession $s
   Set-Location u:\users\administrator\downloads
   Expand-Archive .\PowerShell-<version>-win-<os-arch>.zip
   ```

1. PowerShell 7 へのリモート処理を設定します

   ```powershell
   Set-Location .\PowerShell-<version>-win-<os-arch>
   # Be sure to use the -PowerShellHome parameter otherwise it'll try to create a new
   # endpoint with Windows PowerShell 5.1
   .\Install-PowerShellRemoting.ps1 -PowerShellHome .
   # You'll get an error message and will be disconnected from the device because it has to restart WinRM
   ```

1. デバイス上の PowerShell 7 エンドポイントに接続します

   ```powershell
   # Be sure to use the -Configuration parameter.  If you omit it, you will connect to Windows PowerShell 5.1
   Enter-PSSession -ComputerName <deviceIp> -Credential Administrator -Configuration powershell.<version>
   ```

## <a name="deploying-on-windows-10-iot-core"></a>Windows 10 IoT Core への展開

PowerShell 7 の展開に使用できる *IOT_POWERSHELL* 機能を取り込む場合、Windows 10 IoT Core によって Windows PowerShell が追加されます。
上記で Windows 10 IoT Enterprise に対して定義した手順は、IoT Core にも適用できます。

配布イメージに最新の powershell を追加する場合は、[Import-PSCoreRelease](https://github.com/ms-iot/iot-adk-addonkit/blob/master/Tools/IoTCoreImaging/Docs/Import-PSCoreRelease.md#Import-PSCoreRelease) コマンドを使用して、ワークスペースにパッケージを取り込み、さらに *OPENSRC_POWERSHELL* 機能をご利用のイメージに追加します。

> [!NOTE]
> ARM64 アーキテクチャの場合、*IOT_POWERSHELL* を取り込むときに、Windows Powershell は追加されません。 そのため、zip ベースのインストールは機能しません。
> イメージに追加するには、Import-PSCoreRelease コマンドを使用する必要があります。

## <a name="deploying-on-nano-server"></a>Nano Server への展開

以下の手順では、Nano Server が "ヘッドレス" OS であり、あるバージョンの PowerShell が既に実行されていることを前提としています。 詳細については、[Nano Server Image Builder](/windows-server/get-started/deploy-nano-server) のドキュメントをご覧ください。

PowerShell バイナリを展開するには、2 つの方法があります。

1. オフライン: Nano Server VHD をマウントし、zip ファイルの中身をマウント イメージ内の選択した場所に展開します。
1. オンライン: zip ファイルを PowerShell セッションを介して転送し、選択した場所にそれを展開します。

どちらの場合も、Windows 10 x64 の ZIP リリース パッケージが必要です。 PowerShell の "管理者" インスタンス内でコマンドを実行してください。

### <a name="offline-deployment-of-powershell"></a>PowerShell のオフラインでの展開

1. お好みの zip ユーティリティを使用して、マウントされた Nano Server イメージ内のディレクトリにパッケージを解凍します。
1. イメージをマウント解除し、ブートします。
1. Windows PowerShell の組み込みインスタンスに接続します。
1. 「[別のインスタンスのテクニック](../learn/remoting/wsman-remoting-in-powershell-core.md#executed-by-another-instance-of-powershell-on-behalf-of-the-instance-that-it-will-register)」の、リモート エンドポイントを作成する手順に従います。

### <a name="online-deployment-of-powershell"></a>PowerShell のオンラインでの展開

次の手順に従って、PowerShell を Nano Server に展開します。

- Windows PowerShell の組み込みインスタンスに接続します

  ```powershell
  $session = New-PSSession -ComputerName <Nano Server IP address> -Credential <An Administrator account on the system>
  ```

- Nano Server のインスタンスにファイルをコピーする

  ```powershell
  Copy-Item <local PS Core download location>\powershell-<version>-win-x64.zip c:\ -ToSession $session
  ```

- セッションに入る

  ```powershell
  Enter-PSSession $session
  ```

- ZIP ファイルを解凍します

  ```powershell
  # Insert the appropriate version.
  Expand-Archive -Path C:\powershell-<version>-win-x64.zip -DestinationPath "C:\PowerShell_<version>"
  ```

- WSMan を使用してリモート処理を行う場合、「[別のインスタンスのテクニック](../learn/remoting/WSMan-Remoting-in-PowerShell-Core.md#executed-by-another-instance-of-powershell-on-behalf-of-the-instance-that-it-will-register)」の、リモート エンドポイントを作成する手順に従います。

## <a name="install-as-a-net-global-tool"></a>.NET グローバル ツールとしてインストールする

[.NET Core SDK](/dotnet/core/sdk) が既にインストールされている場合は、PowerShell を [.NET グローバル ツール](/dotnet/core/tools/global-tools)として簡単にインストールできます。

```
dotnet tool install --global PowerShell
```

dotnet tool install によって、`$env:PATH` 環境変数に `$env:USERPROFILE\dotnet\tools` が追加されます。 ただし、現在実行中のシェルには更新された `$env:PATH` が設定されていません。 新しいシェルからは、「`pwsh`」と入力すると PowerShell を起動できます。

## <a name="install-powershell-via-winget"></a>Winget を使用して PowerShell をインストールする

開発者は、`winget` コマンド ライン ツールを使用して、Windows 10 コンピューター上のアプリケーションの検出、インストール、アップグレード、削除、および構成を行うことができます。 このツールは、Windows パッケージ マネージャー サービスに対するクライアント インターフェイスです。

> [!NOTE]
> `winget` ツールは現在プレビュー段階です。 現時点では、計画されたすべての機能を使用できるわけではありません。
> ツールのオプションと機能は変更される可能性があります。 運用環境の展開シナリオでは、この方法を使用しないでください。 システム要件とインストール手順の一覧については、[winget] に関するドキュメントを参照してください。

次のコマンドを使用すると、公開済みの `winget` パッケージを使用して PowerShell をインストールできます。

1. 最新バージョンの PowerShell を検索します

   ```powershell
   winget search Microsoft.PowerShell
   ```

   ```Output
   Name               Id                           Version
   ---------------------------------------------------------------
   PowerShell         Microsoft.PowerShell         7.0.3
   PowerShell-Preview Microsoft.PowerShell-Preview 7.1.0-preview.5
   ```

1. `--exact` パラメーターを使用して、いずれかのバージョンの PowerShell をインストールします

   ```powershell
   winget install --name PowerShell --exact
   winget install --name PowerShell-Preview --exact
   ```

## <a name="how-to-create-a-remoting-endpoint"></a>リモート エンドポイントの作成方法

PowerShell では、WSMan と SSH の両方について PowerShell Remoting Protocol (PSRP) がサポートされています。 詳細については、次を参照してください。

- [PowerShell Core での SSH リモート処理][ssh-remoting]
- [PowerShell Core での WSMan リモート処理][wsman-remoting]

## <a name="installation-support"></a>インストールのサポート

Microsoft では、このドキュメントのインストール方法をサポートしています。 他のソースから別の方法でインストールできる場合もあります。 そのようなツールと方法は機能しても、Microsoft ではそれらの方法をサポートできません。

<!-- link references -->

[releases]: https://github.com/PowerShell/PowerShell/releases
[ssh-remoting]: ../learn/remoting/SSH-Remoting-in-PowerShell-Core.md
[wsman-remoting]: ../learn/remoting/WSMan-Remoting-in-PowerShell-Core.md
[AppVeyor]: https://ci.appveyor.com/project/PowerShell/powershell
[winget]: /windows/package-manager/winget
