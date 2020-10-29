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
# <a name="manipulating-items-directly"></a><span data-ttu-id="56ea1-105">項目を直接操作する</span><span class="sxs-lookup"><span data-stu-id="56ea1-105">Manipulating Items Directly</span></span>

<span data-ttu-id="56ea1-106">ファイル システムのドライブ内のファイルやフォルダー、Windows PowerShell レジストリ ドライブのレジストリ キーなど、Windows PowerShell のドライブに表示される要素は、Windows PowerShell の *項目* と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="56ea1-106">The elements that you see in Windows PowerShell drives, such as the files and folders in the file system drives, and the registry keys in the Windows PowerShell registry drives, are called *items* in Windows PowerShell.</span></span> <span data-ttu-id="56ea1-107">項目を操作するためのコマンドレットは、名前に **Item** という名詞の部分があります。</span><span class="sxs-lookup"><span data-stu-id="56ea1-107">The cmdlets for working with them item have the noun **Item** in their names.</span></span>

<span data-ttu-id="56ea1-108">**Get-Command -Noun Item** コマンドの出力では、Windows PowerShell 項目のコマンドレットが 9 個あることが示されています。</span><span class="sxs-lookup"><span data-stu-id="56ea1-108">The output of the **Get-Command -Noun Item** command shows that there are nine Windows PowerShell item cmdlets.</span></span>

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

## <a name="creating-new-items-new-item"></a><span data-ttu-id="56ea1-109">新しい項目の作成 (New-Item)</span><span class="sxs-lookup"><span data-stu-id="56ea1-109">Creating New Items (New-Item)</span></span>

<span data-ttu-id="56ea1-110">ファイル システムで新しい項目を作成するには、 **New-Item** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="56ea1-110">To create a new item in the file system, use the **New-Item** cmdlet.</span></span> <span data-ttu-id="56ea1-111">項目のパスを指定した **Path** パラメーターと、"file" または "directory" という値を指定した **ItemType** パラメーターを組み込みます。</span><span class="sxs-lookup"><span data-stu-id="56ea1-111">Include the **Path** parameter with path to the item, and the **ItemType** parameter with a value of "file" or "directory".</span></span>

<span data-ttu-id="56ea1-112">たとえば、C:\\Temp ディレクトリに "New.Directory" という名前の新しいディレクトリを作成するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="56ea1-112">For example, to create a new directory named "New.Directory"in the C:\\Temp directory,  type:</span></span>

```
PS> New-Item -Path c:\temp\New.Directory -ItemType Directory

    Directory: Microsoft.Windows PowerShell.Core\FileSystem::C:\temp

Mode                LastWriteTime     Length Name
----                -------------     ------ ----
d----        2006-05-18  11:29 AM            New.Directory
```

<span data-ttu-id="56ea1-113">ファイルを作成するには、 **ItemType** パラメーターの値を "file" に変更します。</span><span class="sxs-lookup"><span data-stu-id="56ea1-113">To create a file, change the value of the **ItemType** parameter to "file".</span></span> <span data-ttu-id="56ea1-114">たとえば、New.Directory ディレクトリに "file1.txt" という名前の新しいファイルを作成するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="56ea1-114">For example, to create a file named "file1.txt" in the New.Directory directory, type:</span></span>

```
PS> New-Item -Path C:\temp\New.Directory\file1.txt -ItemType file

    Directory: Microsoft.Windows PowerShell.Core\FileSystem::C:\temp\New.Directory

Mode                LastWriteTime     Length Name
----                -------------     ------ ----
-a---        2006-05-18  11:44 AM          0 file1
```

<span data-ttu-id="56ea1-115">同じ手法を使用して、新しいレジストリ キーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="56ea1-115">You can use the same technique to create a new registry key.</span></span> <span data-ttu-id="56ea1-116">実際には、Windows レジストリの項目の種類はキーしかないため、レジストリ キーの作成は簡単です。</span><span class="sxs-lookup"><span data-stu-id="56ea1-116">In fact, a registry key is easier to create because the only item type in the Windows registry is a key.</span></span> <span data-ttu-id="56ea1-117">(レジストリ エントリは項目の *プロパティ* です。)たとえば、CurrentVersion サブキーに "_Test" という名前のキーを作成するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="56ea1-117">(Registry entries are item *properties* .) For example, to create a key named "_Test" in the CurrentVersion subkey, type:</span></span>

```
PS> New-Item -Path HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion_Test

   Hive: Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\SOFTWARE\Micros
oft\Windows\CurrentVersion

SKC  VC Name                           Property
---  -- ----                           --------
  0   0 _Test                          {}
```

<span data-ttu-id="56ea1-118">レジストリ パスを入力するときは、Windows PowerShell のドライブ名 HKLM: と HKCU:に、必ずコロン ( **:** ) を含めます。</span><span class="sxs-lookup"><span data-stu-id="56ea1-118">When typing a registry path, be sure to include the colon ( **:** ) in the Windows PowerShell drive names, HKLM: and HKCU:.</span></span> <span data-ttu-id="56ea1-119">コロンがないと、Windows PowerShell では、パス内のドライブ名を認識しません。</span><span class="sxs-lookup"><span data-stu-id="56ea1-119">Without the colon, Windows PowerShell does not recognize the drive name in the path.</span></span>

## <a name="why-registry-values-are-not-items"></a><span data-ttu-id="56ea1-120">レジストリ値が項目ではない理由</span><span class="sxs-lookup"><span data-stu-id="56ea1-120">Why Registry Values are not Items</span></span>

<span data-ttu-id="56ea1-121">**Get-ChildItem** コマンドレットを使用してレジストリ キーの項目を検索する場合は、実際のレジストリ エントリやその値は表示されません。</span><span class="sxs-lookup"><span data-stu-id="56ea1-121">When you use the **Get-ChildItem** cmdlet to find the items in a registry key, you will never see actual registry entries or their values.</span></span>

<span data-ttu-id="56ea1-122">たとえば、レジストリ キー **HKEY_LOCAL_MACHINE\\Software\\Microsoft\\Windows\\CurrentVersion\\Run** には通常、システムの起動時に実行するアプリケーションを表すいくつかのレジストリ エントリが含まれます。</span><span class="sxs-lookup"><span data-stu-id="56ea1-122">For example, the registry key **HKEY_LOCAL_MACHINE\\Software\\Microsoft\\Windows\\CurrentVersion\\Run** usually contains several registry entries that represent applications that run when the system starts.</span></span>

<span data-ttu-id="56ea1-123">ただし、 **Get-ChildItem** を使用してキーの子要素を参照する場合、キーの **OptionalComponents** サブキーのみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="56ea1-123">However, when you use **Get-ChildItem** to look for child items in the key, all you will see is the **OptionalComponents** subkey of the key:</span></span>

```
PS> Get-ChildItem HKLM:\Software\Microsoft\Windows\CurrentVersion\Run

   Hive: Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\Software\Micros
oft\Windows\CurrentVersion\Run
SKC  VC Name                           Property
---  -- ----                           --------
  3   0 OptionalComponents             {}
```

<span data-ttu-id="56ea1-124">レジストリ エントリを項目として処理することは便利ですが、レジストリ エントリへのパスを一意な方法で指定できません。</span><span class="sxs-lookup"><span data-stu-id="56ea1-124">Although it would be convenient to treat registry entries as items, you cannot specify a path to a registry entry in a way that ensures that it is unique.</span></span> <span data-ttu-id="56ea1-125">パスの表記法では、 **Run** という名前のレジストリ サブキーと、 **Run** サブキーの **(Default)** レジストリ エントリを区別しません。</span><span class="sxs-lookup"><span data-stu-id="56ea1-125">The path notation does not distinguish between the registry subkey named **Run** and the **(Default)** registry entry in the **Run** subkey.</span></span> <span data-ttu-id="56ea1-126">さらに、レジストリ エントリの名前にバックスラッシュ文字 ( **\\** ) を含めることができるので、レジストリ エントリが項目だった場合は、パスの表記法を使用して **Windows\\CurrentVersion\\Run** という名前のレジストリ エントリとそのパスに配置されているサブキーを区別することはできません。</span><span class="sxs-lookup"><span data-stu-id="56ea1-126">Furthermore, because registry entry names can contain the backslash character ( **\\** ), if registry entries were items, then you could not use the path notation to distinguish a registry entry named **Windows\\CurrentVersion\\Run** from the subkey that is located in that path.</span></span>

## <a name="renaming-existing-items-rename-item"></a><span data-ttu-id="56ea1-127">既存の項目の名前を変更する (Rename-Item)</span><span class="sxs-lookup"><span data-stu-id="56ea1-127">Renaming Existing Items (Rename-Item)</span></span>

<span data-ttu-id="56ea1-128">ファイルまたはフォルダーの名前を変更するには、 **Rename-Item** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="56ea1-128">To change the name of a file or folder, use the **Rename-Item** cmdlet.</span></span> <span data-ttu-id="56ea1-129">次のコマンドは、 **file1.txt** ファイルの名前を **fileOne.txt** に変更します。</span><span class="sxs-lookup"><span data-stu-id="56ea1-129">The following command changes the name of the **file1.txt** file to **fileOne.txt** .</span></span>

```powershell
Rename-Item -Path C:\temp\New.Directory\file1.txt fileOne.txt
```

<span data-ttu-id="56ea1-130">**Rename-Item** コマンドレットは、ファイルまたはフォルダーの名前を変更できますが、項目を移動することはできません。</span><span class="sxs-lookup"><span data-stu-id="56ea1-130">The **Rename-Item** cmdlet can change the name of a file or a folder, but it cannot move an item.</span></span> <span data-ttu-id="56ea1-131">次のコマンドは、New.Directory ディレクトリから Temp ディレクトリにファイルを移動しようとするため失敗します。</span><span class="sxs-lookup"><span data-stu-id="56ea1-131">The following command fails because it attempts to move the file from the New.Directory directory to the Temp directory.</span></span>

```
PS> Rename-Item -Path C:\temp\New.Directory\fileOne.txt c:\temp\fileOne.txt
Rename-Item : Cannot rename because the target specified is not a path.
At line:1 char:12
+ Rename-Item  <<<< -Path C:\temp\New.Directory\fileOne c:\temp\fileOne.txt
```

## <a name="moving-items-move-item"></a><span data-ttu-id="56ea1-132">項目の移動 (Move-Item)</span><span class="sxs-lookup"><span data-stu-id="56ea1-132">Moving Items (Move-Item)</span></span>

<span data-ttu-id="56ea1-133">ファイルまたはフォルダーを移動するには、 **Move-Item** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="56ea1-133">To move a file or folder, use the **Move-Item** cmdlet.</span></span>

<span data-ttu-id="56ea1-134">たとえば、次のコマンドは、New.Directory ディレクトリを C:\\temp ディレクトリから C: ドライブのルートに移動します。</span><span class="sxs-lookup"><span data-stu-id="56ea1-134">For example, the following command moves the New.Directory directory from the C:\\temp directory to the root of the C: drive.</span></span> <span data-ttu-id="56ea1-135">項目が移動されたことを確認するには、 **Move-Item** コマンドレットの **PassThru** パラメーターを含めます。</span><span class="sxs-lookup"><span data-stu-id="56ea1-135">To verify that the item was moved, include the **PassThru** parameter of the **Move-Item** cmdlet.</span></span> <span data-ttu-id="56ea1-136">**Passthru** を指定しないと、 **Move-Item** コマンドレットで結果は表示されません。</span><span class="sxs-lookup"><span data-stu-id="56ea1-136">Without **Passthru** , the **Move-Item** cmdlet does not display any results.</span></span>

```
PS> Move-Item -Path C:\temp\New.Directory -Destination C:\ -PassThru

    Directory: Microsoft.Windows PowerShell.Core\FileSystem::C:\

Mode                LastWriteTime     Length Name
----                -------------     ------ ----
d----        2006-05-18  12:14 PM            New.Directory
```

## <a name="copying-items-copy-item"></a><span data-ttu-id="56ea1-137">項目のコピー (Copy-Item)</span><span class="sxs-lookup"><span data-stu-id="56ea1-137">Copying Items (Copy-Item)</span></span>

<span data-ttu-id="56ea1-138">他のシェルでのコピー操作を使い慣れている場合は、Windows PowerShell の **Copy-Item** コマンドレットの動作が普通ではないように思えるかもしれません。</span><span class="sxs-lookup"><span data-stu-id="56ea1-138">If you are familiar with the copy operations in other shells, you might find the behavior of the **Copy-Item** cmdlet in Windows PowerShell to be unusual.</span></span> <span data-ttu-id="56ea1-139">1 つの場所から別の場所に項目をコピーする場合、Copy-Item は既定ではその内容をコピーしません。</span><span class="sxs-lookup"><span data-stu-id="56ea1-139">When you copy an item from one location to another, Copy-Item does not copy its contents by default.</span></span>

<span data-ttu-id="56ea1-140">たとえば、 **New.Directory** ディレクトリを C: ドライブから C:\\temp ディレクトリにコピーすると、コマンドは成功しますが、New.Directory ディレクトリのファイルはコピーされません。</span><span class="sxs-lookup"><span data-stu-id="56ea1-140">For example, if you copy the **New.Directory** directory from the C: drive to the C:\\temp directory, the command succeeds, but the files in the New.Directory directory are not copied.</span></span>

```powershell
Copy-Item -Path C:\New.Directory -Destination C:\temp
```

<span data-ttu-id="56ea1-141">**C:\\temp\\New.Directory** の内容を表示すると、ファイルが含まれていないことがわかります。</span><span class="sxs-lookup"><span data-stu-id="56ea1-141">If you display the contents of **C:\\temp\\New.Directory** , you will find that it contains no files:</span></span>

```
PS> Get-ChildItem -Path C:\temp\New.Directory
PS>
```

<span data-ttu-id="56ea1-142">なぜ **Copy-Item** コマンドレットは内容を新しい場所にコピーしないのでしょうか?</span><span class="sxs-lookup"><span data-stu-id="56ea1-142">Why doesn't the **Copy-Item** cmdlet copy the contents to the new location?</span></span>

<span data-ttu-id="56ea1-143">**Copy-Item** コマンドレットは、汎用になるように設計されており、ファイルやフォルダーをコピーするだけではありません。</span><span class="sxs-lookup"><span data-stu-id="56ea1-143">The **Copy-Item** cmdlet was designed to be generic; it is not just for copying files and folders.</span></span> <span data-ttu-id="56ea1-144">また、ファイルとフォルダーをコピーする場合でも、コンテナーのみをコピーして、その中の項目はコピーしないようにすることが望ましいことがあります。</span><span class="sxs-lookup"><span data-stu-id="56ea1-144">Also, even when copying files and folders, you might want to copy only the container and not the items within it.</span></span>

<span data-ttu-id="56ea1-145">フォルダーのすべての内容をコピーするには、コマンドに **Copy-Item** コマンドレットの **Recurse** パラメーターを含めます。</span><span class="sxs-lookup"><span data-stu-id="56ea1-145">To copy all of the contents of a folder, include the **Recurse** parameter of the **Copy-Item** cmdlet in the command.</span></span> <span data-ttu-id="56ea1-146">既に内容なしでディレクトリをコピーした場合は、 **Force** パラメーターを追加すると、空のフォルダーを上書きできます。</span><span class="sxs-lookup"><span data-stu-id="56ea1-146">If you have already copied the directory without its contents, add the **Force** parameter, which allows you to overwrite the empty folder.</span></span>

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

## <a name="deleting-items-remove-item"></a><span data-ttu-id="56ea1-147">項目の削除 (Remove-Item)</span><span class="sxs-lookup"><span data-stu-id="56ea1-147">Deleting Items (Remove-Item)</span></span>

<span data-ttu-id="56ea1-148">ファイルおよびフォルダーを削除するには、 **Remove-Item** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="56ea1-148">To delete files and folders, use the **Remove-Item** cmdlet.</span></span> <span data-ttu-id="56ea1-149">**Remove-Item** など、元に戻せない重要な変更が可能な Windows PowerShell コマンドレットでは、コマンドを入力したときに確認のプロンプトを表示することがあります。</span><span class="sxs-lookup"><span data-stu-id="56ea1-149">Windows PowerShell cmdlets, such as **Remove-Item** , that can make significant, irreversible changes will often prompt for confirmation when you enter its commands.</span></span> <span data-ttu-id="56ea1-150">たとえば、 **New.Directory** フォルダーを削除しようとする場合、フォルダーにファイルが含まれているため、コマンドの確認が求められます。</span><span class="sxs-lookup"><span data-stu-id="56ea1-150">For example, if you try to remove the **New.Directory** folder, you will be prompted to confirm the command, because the folder contains files:</span></span>

```
PS> Remove-Item C:\New.Directory

Confirm
The item at C:\temp\New.Directory has children and the -recurse parameter was not
specified. If you continue, all children will be removed with the item. Are you
 sure you want to continue?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help
(default is "Y"):
```

<span data-ttu-id="56ea1-151">[ **はい** ] が既定の応答であるので、フォルダーとファイルを削除するには、 **Enter** キーを押します。</span><span class="sxs-lookup"><span data-stu-id="56ea1-151">Because **Yes** is the default response, to delete the folder and its files, press the **Enter** key.</span></span> <span data-ttu-id="56ea1-152">確認せずにフォルダーを削除するには、 **-Recurse** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="56ea1-152">To remove the folder without confirming, use the **-Recurse** parameter.</span></span>

```powershell
Remove-Item C:\temp\New.Directory -Recurse
```

## <a name="executing-items-invoke-item"></a><span data-ttu-id="56ea1-153">項目の実行 (Invoke-Item)</span><span class="sxs-lookup"><span data-stu-id="56ea1-153">Executing Items (Invoke-Item)</span></span>

<span data-ttu-id="56ea1-154">Windows PowerShell は、 **Invoke-Item** コマンドレットを使用して、ファイルまたはフォルダーの既定のアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="56ea1-154">Windows PowerShell uses the **Invoke-Item** cmdlet to perform a default action for a file or folder.</span></span> <span data-ttu-id="56ea1-155">この既定のアクションは、レジストリの既定のアプリケーション ハンドラーによって決定されます。効果はファイル エクスプローラー内で項目をダブルクリックする場合と同じです。</span><span class="sxs-lookup"><span data-stu-id="56ea1-155">This default action is determined by the default application handler in the registry; the effect is the same as if you double-click the item in File Explorer.</span></span>

<span data-ttu-id="56ea1-156">たとえば、次のコマンドを実行するとします。</span><span class="sxs-lookup"><span data-stu-id="56ea1-156">For example, suppose you run the following command:</span></span>

```powershell
Invoke-Item C:\WINDOWS
```

<span data-ttu-id="56ea1-157">C:\\Windows にあるエクスプローラー ウィンドウが、C:\\Windows のフォルダーをダブルクリックしたときのように表示されます。</span><span class="sxs-lookup"><span data-stu-id="56ea1-157">An Explorer window that is located in C:\\Windows appears, just as if you had double-clicked the C:\\Windows folder.</span></span>

<span data-ttu-id="56ea1-158">Windows Vista より前のシステムで **Boot.ini** ファイルを起動する場合:</span><span class="sxs-lookup"><span data-stu-id="56ea1-158">If you invoke the **Boot.ini** file on a system prior to Windows Vista:</span></span>

```powershell
Invoke-Item C:\boot.ini
```

<span data-ttu-id="56ea1-159">.ini のファイル タイプがメモ帳と関連付けられている場合、boot.ini ファイルはメモ帳で開きます。</span><span class="sxs-lookup"><span data-stu-id="56ea1-159">If the .ini file type is associated with Notepad, the boot.ini file opens in Notepad.</span></span>
