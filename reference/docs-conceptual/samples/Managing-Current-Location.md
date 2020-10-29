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
# <a name="managing-current-location"></a><span data-ttu-id="161d1-104">現在の場所の管理</span><span class="sxs-lookup"><span data-stu-id="161d1-104">Managing Current Location</span></span>

<span data-ttu-id="161d1-105">ファイル エクスプローラーでフォルダー システムを移動している場合、通常は特定の作業場所 (現在開いているフォルダー) があります。</span><span class="sxs-lookup"><span data-stu-id="161d1-105">When navigating folder systems in File Explorer, you usually have a specific working location - namely, the current open folder.</span></span> <span data-ttu-id="161d1-106">現在のフォルダーの項目は、クリックして簡単に操作できます。</span><span class="sxs-lookup"><span data-stu-id="161d1-106">Items in the current folder can be manipulated easily by clicking them.</span></span> <span data-ttu-id="161d1-107">Cmd.exe などのコマンド ライン インターフェイスで、特定のファイルと同じフォルダーにいる場合は、ファイルへのパス全体を指定する代わりに、比較的短い形式の名前を指定することでアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="161d1-107">For command-line interfaces such as Cmd.exe, when you are in the same folder as a particular file, you can access it by specifying a relatively short name, rather than needing to specify the entire path to the file.</span></span> <span data-ttu-id="161d1-108">現在のディレクトリは、作業ディレクトリと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="161d1-108">The current directory is called the working directory.</span></span>

<span data-ttu-id="161d1-109">Windows PowerShell は、 **Location** という名詞を使用して作業ディレクトリを参照し、場所を調べて操作するコマンドレットのファミリを実装しています。</span><span class="sxs-lookup"><span data-stu-id="161d1-109">Windows PowerShell uses the noun **Location** to refer to the working directory, and implements a family of cmdlets to examine and manipulate your location.</span></span>

## <a name="getting-your-current-location-get-location"></a><span data-ttu-id="161d1-110">現在の場所の取得 (Get-Location)</span><span class="sxs-lookup"><span data-stu-id="161d1-110">Getting Your Current Location (Get-Location)</span></span>

<span data-ttu-id="161d1-111">現在のディレクトリの場所のパスを判断するには、 **Get-Location** コマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="161d1-111">To determine the path of your current directory location, enter the **Get-Location** command:</span></span>

```
PS> Get-Location
Path
----
C:\Documents and Settings\PowerUser
```

> [!NOTE]
> <span data-ttu-id="161d1-112">Get-Location コマンドレットは、BASH シェルの **pwd** コマンドと似ています。</span><span class="sxs-lookup"><span data-stu-id="161d1-112">The Get-Location cmdlet is similar to the **pwd** command in the BASH shell.</span></span> <span data-ttu-id="161d1-113">Set-Location コマンドレットは、Cmd.exe の **cd** コマンドと似ています。</span><span class="sxs-lookup"><span data-stu-id="161d1-113">The Set-Location cmdlet is similar to the **cd** command in Cmd.exe.</span></span>

## <a name="setting-your-current-location-set-location"></a><span data-ttu-id="161d1-114">現在の場所の設定 (Set-Location)</span><span class="sxs-lookup"><span data-stu-id="161d1-114">Setting Your Current Location (Set-Location)</span></span>

<span data-ttu-id="161d1-115">**Get-Location** コマンドは、 **Set-Location** コマンドと共に使用されます。</span><span class="sxs-lookup"><span data-stu-id="161d1-115">The **Get-Location** command is used with the **Set-Location** command.</span></span> <span data-ttu-id="161d1-116">**Set-Location** コマンドでは、現在のディレクトリの場所を指定できます。</span><span class="sxs-lookup"><span data-stu-id="161d1-116">The **Set-Location** command allows you to specify your current directory location.</span></span>

```powershell
Set-Location -Path C:\Windows
```

<span data-ttu-id="161d1-117">コマンドを入力した後、コマンドの効果について直接フィードバックを受信しません。</span><span class="sxs-lookup"><span data-stu-id="161d1-117">After you enter the command, you will notice that you do not receive any direct feedback about the effect of the command.</span></span> <span data-ttu-id="161d1-118">アクションを実行するほとんどの Windows PowerShell コマンドは、出力が必ずしも有益でないため、出力をほとんど、またはまったく生成しません。</span><span class="sxs-lookup"><span data-stu-id="161d1-118">Most Windows PowerShell commands that perform an action produce little or no output because the output is not always useful.</span></span> <span data-ttu-id="161d1-119">ディレクトリの移動が正常に実行されたことを確認するには、 **Set-Location** コマンドを入力する場合は、 **-PassThru** パラメーターを **Set-Location** コマンドの入力時に含めます。</span><span class="sxs-lookup"><span data-stu-id="161d1-119">To verify that a successful directory change has occurred when you enter the **Set-Location** command, include the **-PassThru** parameter when you enter the **Set-Location** command:</span></span>

```
PS> Set-Location -Path C:\Windows -PassThru

Path
----
C:\WINDOWS
```

<span data-ttu-id="161d1-120">**-PassThru** パラメーターは、Windows PowerShell の多数の Set コマンドで、既定の出力がない場合に結果についての情報を返すために使用できます。</span><span class="sxs-lookup"><span data-stu-id="161d1-120">The **-PassThru** parameter can be used with many Set commands in Windows PowerShell to return information about the result in cases in which there is no default output.</span></span>

<span data-ttu-id="161d1-121">ほとんどの UNIX や Windows のコマンド シェルと同じ方法で、現在の場所を基準にした相対パスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="161d1-121">You can specify paths relative to your current location in the same way as you would in most UNIX and Windows command shells.</span></span> <span data-ttu-id="161d1-122">相対パスの標準の表記法では、ピリオド ( **.** ) は現在のフォルダーを表し、二重のピリオド ( **..** ) は現在の場所の親ディレクトリを表します。</span><span class="sxs-lookup"><span data-stu-id="161d1-122">In standard notation for relative paths, a period ( **.** )represents your current folder, and a doubled period ( **..** ) represents the parent directory of your current location.</span></span>

<span data-ttu-id="161d1-123">たとえば、 **C:\\Windows** フォルダーの場合、ピリオド ( **.** ) は **C:\\Windows** を表し、二重のピリオド ( **..** ) は **C:** を表します。</span><span class="sxs-lookup"><span data-stu-id="161d1-123">For example, if you are in the **C:\\Windows** folder, a period ( **.** )represents **C:\\Windows** and double periods ( **..** ) represent **C:** .</span></span> <span data-ttu-id="161d1-124">現在の場所から C: ドライブのルートに移動するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="161d1-124">You can change from your current location to the root of the C: drive by typing:</span></span>

```
PS> Set-Location -Path .. -PassThru

Path
----
C:\
```

<span data-ttu-id="161d1-125">**HKLM:** のようなファイル システムのドライブでない Windows PowerShell ドライブでも、同じ手法が機能します。</span><span class="sxs-lookup"><span data-stu-id="161d1-125">The same technique works on Windows PowerShell drives that are not file system drives, such as **HKLM:** .</span></span> <span data-ttu-id="161d1-126">HKLM\\Software キーの場所をレジストリに設定するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="161d1-126">You can set your location to the HKLM\\Software key in the registry by typing:</span></span>

```
PS> Set-Location -Path HKLM:\SOFTWARE -PassThru

Path
----
HKLM:\SOFTWARE
```

<span data-ttu-id="161d1-127">次に、次の相対パスを使用して、Windows PowerShell の HKLM: ドライブのルートである親ディレクトリにディレクトリの場所を変更できます。</span><span class="sxs-lookup"><span data-stu-id="161d1-127">You can then change the directory location to the parent directory, which is the root of the Windows PowerShell HKLM: drive, by using a relative path:</span></span>

```
PS> Set-Location -Path .. -PassThru

Path
----
HKLM:\
```

<span data-ttu-id="161d1-128">Set-Location と入力するか、Set-Location に対する組み込みの Windows PowerShell のエイリアス (cd、chdir、sl) のいずれかを使用します。</span><span class="sxs-lookup"><span data-stu-id="161d1-128">You can type Set-Location or use any of the built-in Windows PowerShell aliases for Set-Location (cd, chdir, sl).</span></span> <span data-ttu-id="161d1-129">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="161d1-129">For example:</span></span>

```powershell
cd -Path C:\Windows
```

```powershell
chdir -Path .. -PassThru
```

```powershell
sl -Path HKLM:\SOFTWARE -PassThru
```

## <a name="saving-and-recalling-recent-locations-push-location-and-pop-location"></a><span data-ttu-id="161d1-130">最近使用した場所の保存と呼び出し (Push-Location と Pop-Location)</span><span class="sxs-lookup"><span data-stu-id="161d1-130">Saving and Recalling Recent Locations (Push-Location and Pop-Location)</span></span>

<span data-ttu-id="161d1-131">場所を変更する場合、これまでいた場所を把握して、以前の場所に戻るにことができるようにしておくと便利です。</span><span class="sxs-lookup"><span data-stu-id="161d1-131">When changing locations, it is helpful to keep track of where you have been and to be able to return to your previous location.</span></span> <span data-ttu-id="161d1-132">Windows PowerShell の **Push-Location** コマンドレットは、これまでいたディレクトリのパスの順序付けされた履歴 ("スタック") を作成し、補完的な **Pop-Location** コマンドレットを使用して、ディレクトリのパスの履歴を戻ることができます。</span><span class="sxs-lookup"><span data-stu-id="161d1-132">The **Push-Location** cmdlet in Windows PowerShell creates a ordered history (a "stack") of directory paths where you have been, and you can step back through the history of directory paths by using the complementary **Pop-Location** cmdlet.</span></span>

<span data-ttu-id="161d1-133">たとえば、Windows PowerShell は、通常ユーザーのホーム ディレクトリで開始されます。</span><span class="sxs-lookup"><span data-stu-id="161d1-133">For example, Windows PowerShell typically starts in the user's home directory.</span></span>

```
PS> Get-Location

Path
----
C:\Documents and Settings\PowerUser
```

> [!NOTE]
> <span data-ttu-id="161d1-134">*スタック* という単語には、.NET Framework など、多くのプログラミングの設定で特別な意味を持っています。</span><span class="sxs-lookup"><span data-stu-id="161d1-134">The word *stack* has a special meaning in many programming settings, including .NET Framework.</span></span> <span data-ttu-id="161d1-135">項目の物理的なスタックと同様、スタックに入れた最後の項目は、スタックから取り出す最初の項目になります。</span><span class="sxs-lookup"><span data-stu-id="161d1-135">Like a physical stack of items, the last item you put onto the stack is the first item that you can pull off the stack.</span></span> <span data-ttu-id="161d1-136">スタックに項目を追加することは、スタック上に項目を「プッシュ」すると表現されます。</span><span class="sxs-lookup"><span data-stu-id="161d1-136">Adding an item to a stack is colloquially known as "pushing" the item onto the stack.</span></span> <span data-ttu-id="161d1-137">スタックから項目を出すことは、スタックから項目を「ポップ」すると表現されます。</span><span class="sxs-lookup"><span data-stu-id="161d1-137">Pulling an item off the stack is colloquially known as "popping" the item off the stack.</span></span>

<span data-ttu-id="161d1-138">現在の場所をスタックにプッシュして「Local Settings」フォルダーに移動するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="161d1-138">To push the current location onto the stack, and then move to the Local Settings folder, type:</span></span>

```powershell
Push-Location -Path "Local Settings"
```

<span data-ttu-id="161d1-139">「Local Settings」の場所をスタックにプッシュして、「Temp」フォルダーに移動するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="161d1-139">You can then push the Local Settings location onto the stack and move to the Temp folder by typing:</span></span>

```powershell
Push-Location -Path Temp
```

<span data-ttu-id="161d1-140">**Get-Location** コマンドを入力すると、ディレクトリの移動を確認できます。</span><span class="sxs-lookup"><span data-stu-id="161d1-140">You can verify that you changed directories by entering the **Get-Location** command:</span></span>

```
PS> Get-Location

Path
----
C:\Documents and Settings\PowerUser\Local Settings\Temp
```

<span data-ttu-id="161d1-141">**Pop-Location** コマンドを入力すると、最後に表示したディレクトリに戻ることができ、 **Get-Location** コマンドを入力すると、移動を確認できます。</span><span class="sxs-lookup"><span data-stu-id="161d1-141">You can then pop back into the most recently visited directory by entering the **Pop-Location** command, and verify the change by entering the **Get-Location** command:</span></span>

```
PS> Pop-Location
PS> Get-Location

Path
----
C:\Documents and Settings\me\Local Settings
```

<span data-ttu-id="161d1-142">**Set-Location** コマンドレットと同様に、 **-PassThru** パラメーターを含めて ( **Pop-Location** コマンドレットを入力するときに) 、入力したディレクトリを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="161d1-142">Just as with the **Set-Location** cmdlet, you can include the **-PassThru** parameter when you enter the **Pop-Location** cmdlet to display the directory that you entered:</span></span>

```
PS> Pop-Location -PassThru

Path
----
C:\Documents and Settings\PowerUser
```

<span data-ttu-id="161d1-143">また、ネットワーク パスを指定して Location コマンドレットを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="161d1-143">You can also use the Location cmdlets with network paths.</span></span> <span data-ttu-id="161d1-144">FS01 という名前で、Public という共有名を持つサーバーがある場合、場所を移動するには次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="161d1-144">If you have a server named FS01 with an share named Public, you can change your location by typing</span></span>

```powershell
Set-Location \\FS01\Public
```

<span data-ttu-id="161d1-145">または</span><span class="sxs-lookup"><span data-stu-id="161d1-145">or</span></span>

```powershell
Push-Location \\FS01\Public
```

<span data-ttu-id="161d1-146">**Push-Location** と **Set-Location** のコマンドを使用して、利用できる任意のドライブに場所を移動できます。</span><span class="sxs-lookup"><span data-stu-id="161d1-146">You can use the **Push-Location** and **Set-Location** commands to change the location to any available drive.</span></span> <span data-ttu-id="161d1-147">たとえば、ドライブ文字が D であるローカルの CD-ROM ドライブがあり、データ CD が挿入されている場合、 **Set-Location D:** コマンドを入力すると、CD ドライブに場所を移動できます。</span><span class="sxs-lookup"><span data-stu-id="161d1-147">For example, if you have a local CD-ROM drive with drive letter D that contains a data CD, you can change the location to the CD drive by entering the **Set-Location D:** command.</span></span>

<span data-ttu-id="161d1-148">ドライブが空の場合は、次のエラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="161d1-148">If the drive is empty, you will get the following error message:</span></span>

```
PS> Set-Location D:
Set-Location : Cannot find path 'D:\' because it does not exist.
```

<span data-ttu-id="161d1-149">コマンド ライン インターフェイスを使用している場合、利用可能な物理ドライブを確認するのにファイル エクスプローラーを使用するのは便利ではありません。</span><span class="sxs-lookup"><span data-stu-id="161d1-149">When you are using a command-line interface, it is not convenient to use File Explorer to examine the available physical drives.</span></span> <span data-ttu-id="161d1-150">また、ファイル エクスプローラーは、すべての Windows PowerShell ドライブを表示するわけではありません。</span><span class="sxs-lookup"><span data-stu-id="161d1-150">Also, File Explorer would not show you the all of the Windows PowerShell drives.</span></span> <span data-ttu-id="161d1-151">Windows PowerShell は、Windows PowerShell ドライブを操作するための一連のコマンドの提供しており、それについては次で説明します。</span><span class="sxs-lookup"><span data-stu-id="161d1-151">Windows PowerShell provides a set of commands for manipulating Windows PowerShell drives, and we will talk about these next.</span></span>
