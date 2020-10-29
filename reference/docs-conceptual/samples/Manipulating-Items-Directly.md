---
ms.date: 06/05/2017
keywords: powershell,コマンドレット
title: 項目を直接操作する
description: PowerShell には、ローカル コンピューター上およびリモート コンピューター上の項目を管理するのに役立つコマンドレットがいくつか用意されています。 項目は、ファイル システム、レジストリ、証明書など、PowerShell プロバイダーによって公開されるオブジェクトです。
ms.openlocfilehash: 20132b63a8ff4ef24b1d8346066315dbb053e59c
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2020
ms.locfileid: "92500319"
---
# <a name="manipulating-items-directly"></a>項目を直接操作する

ファイル システムのドライブ内のファイルやフォルダー、Windows PowerShell レジストリ ドライブのレジストリ キーなど、Windows PowerShell のドライブに表示される要素は、Windows PowerShell の *項目* と呼ばれます。 項目を操作するためのコマンドレットは、名前に **Item** という名詞の部分があります。

**Get-Command -Noun Item** コマンドの出力では、Windows PowerShell 項目のコマンドレットが 9 個あることが示されています。

```
PS> Get-Command -Noun Item

CommandType     Name                            Definition
-----------     ----                            ----------
Cmdlet          Clear-Item                      Clear-Item [-Path] <String[]...
Cmdlet          Copy-Item                       Copy-Item [-Path] <String[]>...
Cmdlet          Get-Item                        Get-Item [-Path] <String[]> ...
Cmdlet          Invoke-Item                     Invoke-Item [-Path] <String[...
Cmdlet          Move-Item                       Move-Item [-Path] <String[]>...
Cmdlet          New-Item                        New-Item [-Path] <String[]> ...
Cmdlet          Remove-Item                     Remove-Item [-Path] <String[...
Cmdlet          Rename-Item                     Rename-Item [-Path] <String>...
Cmdlet          Set-Item                        Set-Item [-Path] <String[]> ...
```

## <a name="creating-new-items-new-item"></a>新しい項目の作成 (New-Item)

ファイル システムで新しい項目を作成するには、 **New-Item** コマンドレットを使用します。 項目のパスを指定した **Path** パラメーターと、"file" または "directory" という値を指定した **ItemType** パラメーターを組み込みます。

たとえば、C:\\Temp ディレクトリに "New.Directory" という名前の新しいディレクトリを作成するには、次のように入力します。

```
PS> New-Item -Path c:\temp\New.Directory -ItemType Directory

    Directory: Microsoft.Windows PowerShell.Core\FileSystem::C:\temp

Mode                LastWriteTime     Length Name
----                -------------     ------ ----
d----        2006-05-18  11:29 AM            New.Directory
```

ファイルを作成するには、 **ItemType** パラメーターの値を "file" に変更します。 たとえば、New.Directory ディレクトリに "file1.txt" という名前の新しいファイルを作成するには、次のように入力します。

```
PS> New-Item -Path C:\temp\New.Directory\file1.txt -ItemType file

    Directory: Microsoft.Windows PowerShell.Core\FileSystem::C:\temp\New.Directory

Mode                LastWriteTime     Length Name
----                -------------     ------ ----
-a---        2006-05-18  11:44 AM          0 file1
```

同じ手法を使用して、新しいレジストリ キーを作成できます。 実際には、Windows レジストリの項目の種類はキーしかないため、レジストリ キーの作成は簡単です。 (レジストリ エントリは項目の *プロパティ* です。)たとえば、CurrentVersion サブキーに "_Test" という名前のキーを作成するには、次のように入力します。

```
PS> New-Item -Path HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion_Test

   Hive: Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\SOFTWARE\Micros
oft\Windows\CurrentVersion

SKC  VC Name                           Property
---  -- ----                           --------
  0   0 _Test                          {}
```

レジストリ パスを入力するときは、Windows PowerShell のドライブ名 HKLM: と HKCU:に、必ずコロン ( **:** ) を含めます。 コロンがないと、Windows PowerShell では、パス内のドライブ名を認識しません。

## <a name="why-registry-values-are-not-items"></a>レジストリ値が項目ではない理由

**Get-ChildItem** コマンドレットを使用してレジストリ キーの項目を検索する場合は、実際のレジストリ エントリやその値は表示されません。

たとえば、レジストリ キー **HKEY_LOCAL_MACHINE\\Software\\Microsoft\\Windows\\CurrentVersion\\Run** には通常、システムの起動時に実行するアプリケーションを表すいくつかのレジストリ エントリが含まれます。

ただし、 **Get-ChildItem** を使用してキーの子要素を参照する場合、キーの **OptionalComponents** サブキーのみが表示されます。

```
PS> Get-ChildItem HKLM:\Software\Microsoft\Windows\CurrentVersion\Run

   Hive: Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\Software\Micros
oft\Windows\CurrentVersion\Run
SKC  VC Name                           Property
---  -- ----                           --------
  3   0 OptionalComponents             {}
```

レジストリ エントリを項目として処理することは便利ですが、レジストリ エントリへのパスを一意な方法で指定できません。 パスの表記法では、 **Run** という名前のレジストリ サブキーと、 **Run** サブキーの **(Default)** レジストリ エントリを区別しません。 さらに、レジストリ エントリの名前にバックスラッシュ文字 ( **\\** ) を含めることができるので、レジストリ エントリが項目だった場合は、パスの表記法を使用して **Windows\\CurrentVersion\\Run** という名前のレジストリ エントリとそのパスに配置されているサブキーを区別することはできません。

## <a name="renaming-existing-items-rename-item"></a>既存の項目の名前を変更する (Rename-Item)

ファイルまたはフォルダーの名前を変更するには、 **Rename-Item** コマンドレットを使用します。 次のコマンドは、 **file1.txt** ファイルの名前を **fileOne.txt** に変更します。

```powershell
Rename-Item -Path C:\temp\New.Directory\file1.txt fileOne.txt
```

**Rename-Item** コマンドレットは、ファイルまたはフォルダーの名前を変更できますが、項目を移動することはできません。 次のコマンドは、New.Directory ディレクトリから Temp ディレクトリにファイルを移動しようとするため失敗します。

```
PS> Rename-Item -Path C:\temp\New.Directory\fileOne.txt c:\temp\fileOne.txt
Rename-Item : Cannot rename because the target specified is not a path.
At line:1 char:12
+ Rename-Item  <<<< -Path C:\temp\New.Directory\fileOne c:\temp\fileOne.txt
```

## <a name="moving-items-move-item"></a>項目の移動 (Move-Item)

ファイルまたはフォルダーを移動するには、 **Move-Item** コマンドレットを使用します。

たとえば、次のコマンドは、New.Directory ディレクトリを C:\\temp ディレクトリから C: ドライブのルートに移動します。 項目が移動されたことを確認するには、 **Move-Item** コマンドレットの **PassThru** パラメーターを含めます。 **Passthru** を指定しないと、 **Move-Item** コマンドレットで結果は表示されません。

```
PS> Move-Item -Path C:\temp\New.Directory -Destination C:\ -PassThru

    Directory: Microsoft.Windows PowerShell.Core\FileSystem::C:\

Mode                LastWriteTime     Length Name
----                -------------     ------ ----
d----        2006-05-18  12:14 PM            New.Directory
```

## <a name="copying-items-copy-item"></a>項目のコピー (Copy-Item)

他のシェルでのコピー操作を使い慣れている場合は、Windows PowerShell の **Copy-Item** コマンドレットの動作が普通ではないように思えるかもしれません。 1 つの場所から別の場所に項目をコピーする場合、Copy-Item は既定ではその内容をコピーしません。

たとえば、 **New.Directory** ディレクトリを C: ドライブから C:\\temp ディレクトリにコピーすると、コマンドは成功しますが、New.Directory ディレクトリのファイルはコピーされません。

```powershell
Copy-Item -Path C:\New.Directory -Destination C:\temp
```

**C:\\temp\\New.Directory** の内容を表示すると、ファイルが含まれていないことがわかります。

```
PS> Get-ChildItem -Path C:\temp\New.Directory
PS>
```

なぜ **Copy-Item** コマンドレットは内容を新しい場所にコピーしないのでしょうか?

**Copy-Item** コマンドレットは、汎用になるように設計されており、ファイルやフォルダーをコピーするだけではありません。 また、ファイルとフォルダーをコピーする場合でも、コンテナーのみをコピーして、その中の項目はコピーしないようにすることが望ましいことがあります。

フォルダーのすべての内容をコピーするには、コマンドに **Copy-Item** コマンドレットの **Recurse** パラメーターを含めます。 既に内容なしでディレクトリをコピーした場合は、 **Force** パラメーターを追加すると、空のフォルダーを上書きできます。

```
PS> Copy-Item -Path C:\New.Directory -Destination C:\temp -Recurse -Force -Passthru

    Directory: Microsoft.Windows PowerShell.Core\FileSystem::C:\temp

Mode                LastWriteTime     Length Name
----                -------------     ------ ----
d----        2006-05-18   1:53 PM            New.Directory

    Directory: Microsoft.Windows PowerShell.Core\FileSystem::C:\temp\New.Directory

Mode                LastWriteTime     Length Name
----                -------------     ------ ----
-a---        2006-05-18  11:44 AM          0 file1
```

## <a name="deleting-items-remove-item"></a>項目の削除 (Remove-Item)

ファイルおよびフォルダーを削除するには、 **Remove-Item** コマンドレットを使用します。 **Remove-Item** など、元に戻せない重要な変更が可能な Windows PowerShell コマンドレットでは、コマンドを入力したときに確認のプロンプトを表示することがあります。 たとえば、 **New.Directory** フォルダーを削除しようとする場合、フォルダーにファイルが含まれているため、コマンドの確認が求められます。

```
PS> Remove-Item C:\New.Directory

Confirm
The item at C:\temp\New.Directory has children and the -recurse parameter was not
specified. If you continue, all children will be removed with the item. Are you
 sure you want to continue?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help
(default is "Y"):
```

[ **はい** ] が既定の応答であるので、フォルダーとファイルを削除するには、 **Enter** キーを押します。 確認せずにフォルダーを削除するには、 **-Recurse** パラメーターを使用します。

```powershell
Remove-Item C:\temp\New.Directory -Recurse
```

## <a name="executing-items-invoke-item"></a>項目の実行 (Invoke-Item)

Windows PowerShell は、 **Invoke-Item** コマンドレットを使用して、ファイルまたはフォルダーの既定のアクションを実行します。 この既定のアクションは、レジストリの既定のアプリケーション ハンドラーによって決定されます。効果はファイル エクスプローラー内で項目をダブルクリックする場合と同じです。

たとえば、次のコマンドを実行するとします。

```powershell
Invoke-Item C:\WINDOWS
```

C:\\Windows にあるエクスプローラー ウィンドウが、C:\\Windows のフォルダーをダブルクリックしたときのように表示されます。

Windows Vista より前のシステムで **Boot.ini** ファイルを起動する場合:

```powershell
Invoke-Item C:\boot.ini
```

.ini のファイル タイプがメモ帳と関連付けられている場合、boot.ini ファイルはメモ帳で開きます。
