---
ms.date: 06/05/2017
keywords: powershell,コマンドレット
title: 現在の場所の管理
description: PowerShell では、Location という名詞を使用して作業ディレクトリが参照され、場所を調べたり操作したりするためのコマンドレットのファミリが実装されています。
ms.openlocfilehash: 0ce9ed1269921233b0d6b07da832c12e159a84dc
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2020
ms.locfileid: "92500472"
---
# <a name="managing-current-location"></a>現在の場所の管理

ファイル エクスプローラーでフォルダー システムを移動している場合、通常は特定の作業場所 (現在開いているフォルダー) があります。 現在のフォルダーの項目は、クリックして簡単に操作できます。 Cmd.exe などのコマンド ライン インターフェイスで、特定のファイルと同じフォルダーにいる場合は、ファイルへのパス全体を指定する代わりに、比較的短い形式の名前を指定することでアクセスできます。 現在のディレクトリは、作業ディレクトリと呼ばれます。

Windows PowerShell は、 **Location** という名詞を使用して作業ディレクトリを参照し、場所を調べて操作するコマンドレットのファミリを実装しています。

## <a name="getting-your-current-location-get-location"></a>現在の場所の取得 (Get-Location)

現在のディレクトリの場所のパスを判断するには、 **Get-Location** コマンドを入力します。

```
PS> Get-Location
Path
----
C:\Documents and Settings\PowerUser
```

> [!NOTE]
> Get-Location コマンドレットは、BASH シェルの **pwd** コマンドと似ています。 Set-Location コマンドレットは、Cmd.exe の **cd** コマンドと似ています。

## <a name="setting-your-current-location-set-location"></a>現在の場所の設定 (Set-Location)

**Get-Location** コマンドは、 **Set-Location** コマンドと共に使用されます。 **Set-Location** コマンドでは、現在のディレクトリの場所を指定できます。

```powershell
Set-Location -Path C:\Windows
```

コマンドを入力した後、コマンドの効果について直接フィードバックを受信しません。 アクションを実行するほとんどの Windows PowerShell コマンドは、出力が必ずしも有益でないため、出力をほとんど、またはまったく生成しません。 ディレクトリの移動が正常に実行されたことを確認するには、 **Set-Location** コマンドを入力する場合は、 **-PassThru** パラメーターを **Set-Location** コマンドの入力時に含めます。

```
PS> Set-Location -Path C:\Windows -PassThru

Path
----
C:\WINDOWS
```

**-PassThru** パラメーターは、Windows PowerShell の多数の Set コマンドで、既定の出力がない場合に結果についての情報を返すために使用できます。

ほとんどの UNIX や Windows のコマンド シェルと同じ方法で、現在の場所を基準にした相対パスを指定できます。 相対パスの標準の表記法では、ピリオド ( **.** ) は現在のフォルダーを表し、二重のピリオド ( **..** ) は現在の場所の親ディレクトリを表します。

たとえば、 **C:\\Windows** フォルダーの場合、ピリオド ( **.** ) は **C:\\Windows** を表し、二重のピリオド ( **..** ) は **C:** を表します。 現在の場所から C: ドライブのルートに移動するには、次のように入力します。

```
PS> Set-Location -Path .. -PassThru

Path
----
C:\
```

**HKLM:** のようなファイル システムのドライブでない Windows PowerShell ドライブでも、同じ手法が機能します。 HKLM\\Software キーの場所をレジストリに設定するには、次のように入力します。

```
PS> Set-Location -Path HKLM:\SOFTWARE -PassThru

Path
----
HKLM:\SOFTWARE
```

次に、次の相対パスを使用して、Windows PowerShell の HKLM: ドライブのルートである親ディレクトリにディレクトリの場所を変更できます。

```
PS> Set-Location -Path .. -PassThru

Path
----
HKLM:\
```

Set-Location と入力するか、Set-Location に対する組み込みの Windows PowerShell のエイリアス (cd、chdir、sl) のいずれかを使用します。 次に例を示します。

```powershell
cd -Path C:\Windows
```

```powershell
chdir -Path .. -PassThru
```

```powershell
sl -Path HKLM:\SOFTWARE -PassThru
```

## <a name="saving-and-recalling-recent-locations-push-location-and-pop-location"></a>最近使用した場所の保存と呼び出し (Push-Location と Pop-Location)

場所を変更する場合、これまでいた場所を把握して、以前の場所に戻るにことができるようにしておくと便利です。 Windows PowerShell の **Push-Location** コマンドレットは、これまでいたディレクトリのパスの順序付けされた履歴 ("スタック") を作成し、補完的な **Pop-Location** コマンドレットを使用して、ディレクトリのパスの履歴を戻ることができます。

たとえば、Windows PowerShell は、通常ユーザーのホーム ディレクトリで開始されます。

```
PS> Get-Location

Path
----
C:\Documents and Settings\PowerUser
```

> [!NOTE]
> *スタック* という単語には、.NET Framework など、多くのプログラミングの設定で特別な意味を持っています。 項目の物理的なスタックと同様、スタックに入れた最後の項目は、スタックから取り出す最初の項目になります。 スタックに項目を追加することは、スタック上に項目を「プッシュ」すると表現されます。 スタックから項目を出すことは、スタックから項目を「ポップ」すると表現されます。

現在の場所をスタックにプッシュして「Local Settings」フォルダーに移動するには、次のように入力します。

```powershell
Push-Location -Path "Local Settings"
```

「Local Settings」の場所をスタックにプッシュして、「Temp」フォルダーに移動するには、次のように入力します。

```powershell
Push-Location -Path Temp
```

**Get-Location** コマンドを入力すると、ディレクトリの移動を確認できます。

```
PS> Get-Location

Path
----
C:\Documents and Settings\PowerUser\Local Settings\Temp
```

**Pop-Location** コマンドを入力すると、最後に表示したディレクトリに戻ることができ、 **Get-Location** コマンドを入力すると、移動を確認できます。

```
PS> Pop-Location
PS> Get-Location

Path
----
C:\Documents and Settings\me\Local Settings
```

**Set-Location** コマンドレットと同様に、 **-PassThru** パラメーターを含めて ( **Pop-Location** コマンドレットを入力するときに) 、入力したディレクトリを表示することができます。

```
PS> Pop-Location -PassThru

Path
----
C:\Documents and Settings\PowerUser
```

また、ネットワーク パスを指定して Location コマンドレットを使用することもできます。 FS01 という名前で、Public という共有名を持つサーバーがある場合、場所を移動するには次のように入力します。

```powershell
Set-Location \\FS01\Public
```

または

```powershell
Push-Location \\FS01\Public
```

**Push-Location** と **Set-Location** のコマンドを使用して、利用できる任意のドライブに場所を移動できます。 たとえば、ドライブ文字が D であるローカルの CD-ROM ドライブがあり、データ CD が挿入されている場合、 **Set-Location D:** コマンドを入力すると、CD ドライブに場所を移動できます。

ドライブが空の場合は、次のエラー メッセージが表示されます。

```
PS> Set-Location D:
Set-Location : Cannot find path 'D:\' because it does not exist.
```

コマンド ライン インターフェイスを使用している場合、利用可能な物理ドライブを確認するのにファイル エクスプローラーを使用するのは便利ではありません。 また、ファイル エクスプローラーは、すべての Windows PowerShell ドライブを表示するわけではありません。 Windows PowerShell は、Windows PowerShell ドライブを操作するための一連のコマンドの提供しており、それについては次で説明します。
