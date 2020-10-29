---
ms.date: 06/05/2017
keywords: powershell,コマンドレット
title: ファイルとフォルダーの操作
description: この記事では、PowerShell を使用して特定のファイルとフォルダーを操作するタスクについて説明します。
ms.openlocfilehash: c0c3abb082b05296daa480ac06bcbfa3a784e0c9
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2020
ms.locfileid: "92500030"
---
# <a name="working-with-files-and-folders"></a>ファイルとフォルダーの操作

Windows PowerShell ドライブ間を移動したり、Windows PowerShell ドライブ上の項目を操作したりすることは、Windows の物理ディスク ドライブ上のファイルやフォルダーを操作することと似ています。 この記事では、PowerShell を使用して特定のファイルとフォルダーを操作するタスクについて説明します。

## <a name="listing-all-the-files-and-folders-within-a-folder"></a>フォルダー内のすべてのファイルとフォルダーの一覧表示

`Get-ChildItem` を使用することにより、フォルダー内のすべての項目を直接取得することができます。 非表示の項目やシステム項目を表示するには、オプションの **Force** パラメーターを追加します。 たとえば、このコマンドは、Windows PowerShell ドライブ C (Windows の物理ドライブ C と同じ) に直接含まれるコンテンツを表示します。

```powershell
Get-ChildItem -Path C:\ -Force
```

このコマンドは、`Cmd.exe` の `DIR` コマンドや UNIX シェルの `ls` を使用したときと同様に、直接含まれている項目のみを一覧表示します。 内包されている項目を表示するには、`-Recurse` パラメーターも指定する必要があります。 (完了までにかなりの時間がかかることがあります。)C ドライブ上のすべての項目を一覧表示するには、次のように入力します。

```powershell
Get-ChildItem -Path C:\ -Force -Recurse
```

`Get-ChildItem` は、 **Path** 、 **Filter** 、 **Include** 、 **Exclude** の各パラメーターを使用して項目をフィルター処理できますが、通常、これらは名前にのみ基づいています。 `Where-Object` を使用することにより、項目の他のプロパティに基づいた複雑なフィルター処理を実行できます。

次のコマンドは、Program Files フォルダー内にある、2005 年 10 月 1 日より後に最終更新され、1 メガバイト以上、10 メガバイト以下のすべての実行可能ファイルを検出します。

```powershell
Get-ChildItem -Path $env:ProgramFiles -Recurse -Include *.exe | Where-Object -FilterScript {($_.LastWriteTime -gt '2005-10-01') -and ($_.Length -ge 1mb) -and ($_.Length -le 10mb)}
```

## <a name="copying-files-and-folders"></a>ファイルとフォルダーのコピー

コピーは `Copy-Item` を使用して行われます。 次のコマンドは、C:\\boot.ini to C:\\boot.bak にバックアップします。

```powershell
Copy-Item -Path C:\boot.ini -Destination C:\boot.bak
```

コピー先のファイルが既に存在する場合、コピー操作は失敗します。 既存のコピー先ファイルを上書きするには、 **Force** パラメーターを使用します。

```powershell
Copy-Item -Path C:\boot.ini -Destination C:\boot.bak -Force
```

このコマンドは、コピー先が読み取り専用である場合にも使用できます。

フォルダーのコピーも同様に動作します。 このコマンドは、フォルダー `C:\temp\test1` を新しいフォルダー `C:\temp\DeleteMe` 再帰的にコピーします。

```powershell
Copy-Item C:\temp\test1 -Recurse C:\temp\DeleteMe
```

選択した項目をコピーすることもできます。 次のコマンドでは、`C:\data` 内のすべての場所に格納されているすべての .txt ファイルを `C:\temp\text` にコピーします。

```powershell
Copy-Item -Filter *.txt -Path c:\data -Recurse -Destination C:\temp\text
```

ファイル システムのコピー操作には、他のツールを使用することもできます。 XCOPY、ROBOCOPY、および COM オブジェクト ( **Scripting.FileSystemObject** など) はすべて Windows PowerShell で動作します。 たとえば、Windows Script Host の **Scripting.FileSystem COM** クラスを使用して、`C:\boot.ini` を `C:\boot.bak` にバックアップするには、次のように入力します。

```powershell
(New-Object -ComObject Scripting.FileSystemObject).CopyFile('C:\boot.ini', 'C:\boot.bak')
```

## <a name="creating-files-and-folders"></a>ファイルとフォルダーの作成

新しい項目の作成は、すべての Windows PowerShell プロバイダーで同じ方法で行われます。 Windows PowerShell プロバイダーに複数の種類の項目が含まれている場合 (たとえば、FileSystem Windows PowerShell プロバイダーではディレクトリとファイルが区別されます)、項目の種類を指定する必要があります。

このコマンドは新しいフォルダー `C:\temp\New Folder` を作成します。

```powershell
New-Item -Path 'C:\temp\New Folder' -ItemType Directory
```

このコマンドは新しい空のファイル `C:\temp\New Folder\file.txt` を作成します

```powershell
New-Item -Path 'C:\temp\New Folder\file.txt' -ItemType File
```

> [!IMPORTANT]
> **Force** スイッチを `New-Item` コマンドで使用してフォルダーを作成し、そのフォルダーが既に存在している場合は、フォルダーが上書きされたり、置き換えたりすることは _ありません_ 。 単に既存のフォルダー オブジェクトを返します。 ただし、既に存在するファイルに対して `New-Item -Force` を使用すると、ファイルは完全に上書き _されます_ 。

## <a name="removing-all-files-and-folders-within-a-folder"></a>フォルダー内のすべてのファイルとフォルダーの削除

内包されている項目を削除するには、`Remove-Item` を使用します。ただし、その項目に他の何らかの項目が含まれている場合は、削除の確認を求められます。 たとえば、他の項目を含むフォルダー `C:\temp\DeleteMe` を削除しようとすると、フォルダーが削除される前に、Windows PowerShell から次のような確認メッセージが表示されます。

```
Remove-Item -Path C:\temp\DeleteMe

Confirm
The item at C:\temp\DeleteMe has children and the Recurse parameter was not
specified. If you continue, all children will be removed with the item. Are you
sure you want to continue?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help
(default is "Y"):
```

内包されている項目ごとに削除の確認が行われないようにする場合は、 **Recurse** パラメーターを使用します。

```powershell
Remove-Item -Path C:\temp\DeleteMe -Recurse
```

## <a name="mapping-a-local-folder-as-a-drive"></a>ローカル フォルダーをドライブとしてマップする

`New-PSDrive` コマンドを使用することにより、ローカル フォルダーをマッピングすることもできます。 次のコマンドでは、ローカルの Program Files ディレクトリをルートとする PowerShell セッションからのみ参照できる、ローカル ドライブ `P:` が作成されます。

```powershell
New-PSDrive -Name P -Root $env:ProgramFiles -PSProvider FileSystem
```

ネットワーク ドライブと同様に、Windows PowerShell 内でマッピングされたドライブは、直ちに Windows PowerShell シェルに表示されます。 エクスプローラーから参照できるマッピングされたドライブを作成するには、`-Persist` のパラメーターが必要です。 ただし、Persist で使用できるのはリモートのパスのみです。

## <a name="reading-a-text-file-into-an-array"></a>配列へのテキスト ファイルの読み込み

テキスト データの一般的な格納形式の 1 つに、個々の行を個別のデータ要素として扱うファイルを使用する方法があります。 `Get-Content` コマンドレットを使用することにより、1 つのステップでファイル全体を読み取ることができます。以下にその例を示します。

```
PS> Get-Content -Path C:\boot.ini
[boot loader]
timeout=5
default=multi(0)disk(0)rdisk(0)partition(1)\WINDOWS
[operating systems]
multi(0)disk(0)rdisk(0)partition(1)\WINDOWS="Microsoft Windows XP Professional"
 /noexecute=AlwaysOff /fastdetect
multi(0)disk(0)rdisk(0)partition(1)\WINDOWS=" Microsoft Windows XP Professional
with Data Execution Prevention" /noexecute=optin /fastdetect
```

`Get-Content` は、ファイルから読み取ったデータを、1 行のファイル内容につき 1 つの要素を含む配列として扱います。 これを確認するには、返された内容の **Length** をチェックします。

```
PS> (Get-Content -Path C:\boot.ini).Length
6
```

このコマンドは、情報の一覧を Windows PowerShell に直接取得するときに最も役立ちます。 たとえば、コンピューター名または IP アドレスの一覧を、ファイルの各行に 1 つの名前を入力して `C:\temp\domainMembers.txt` ファイルに保存できます。 `Get-Content` を使用してファイルの内容を取得し、変数 `$Computers` に格納するには、次のように入力します。

```powershell
$Computers = Get-Content -Path C:\temp\DomainMembers.txt
```

`$Computers` には、各要素に 1 つのコンピューター名が含まれた配列が格納されます。
