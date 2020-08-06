---
title: Events01 サンプル |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: c7b0f759ca6f3c078649a462eac1713e8214a237
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87774459"
---
# <a name="events01-sample"></a><span data-ttu-id="c8e6c-102">Events01 サンプル</span><span class="sxs-lookup"><span data-stu-id="c8e6c-102">Events01 Sample</span></span>

<span data-ttu-id="c8e6c-103">このサンプルでは、ユーザーが、system.object[によって発生した](/dotnet/api/System.IO.FileSystemWatcher)イベントに登録できるようにするコマンドレットを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="c8e6c-103">This sample shows how to create a cmdlet that allows the user to register for events that are raised by [System.IO.FileSystemWatcher](/dotnet/api/System.IO.FileSystemWatcher).</span></span>
<span data-ttu-id="c8e6c-104">このコマンドレットを使用すると、ユーザーは、特定のディレクトリにファイルが作成されたときに実行するアクションを登録できます。</span><span class="sxs-lookup"><span data-stu-id="c8e6c-104">With this cmdlet, users can register an action to execute when a file is created under a specific directory.</span></span>
<span data-ttu-id="c8e6c-105">このサンプルは、 [ObjectEventRegistrationBase](/dotnet/api/Microsoft.PowerShell.Commands.ObjectEventRegistrationBase)基底クラスから派生します。</span><span class="sxs-lookup"><span data-stu-id="c8e6c-105">This sample derives from the [Microsoft.PowerShell.Commands.ObjectEventRegistrationBase](/dotnet/api/Microsoft.PowerShell.Commands.ObjectEventRegistrationBase) base class.</span></span>

## <a name="how-to-build-the-sample-by-using-visual-studio"></a><span data-ttu-id="c8e6c-106">Visual Studio を使用してサンプルをビルドする方法。</span><span class="sxs-lookup"><span data-stu-id="c8e6c-106">How to build the sample by using Visual Studio.</span></span>

1. <span data-ttu-id="c8e6c-107">Windows PowerShell 2.0 SDK がインストールされている状態で、Events01 フォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="c8e6c-107">With the Windows PowerShell 2.0 SDK installed, navigate to the Events01 folder.</span></span>
   <span data-ttu-id="c8e6c-108">既定の場所は `C:\Program Files (x86)\Microsoft SDKs\Windows\v7.0\Samples\sysmgmt\WindowsPowerShell\csharp\Events01` です。</span><span class="sxs-lookup"><span data-stu-id="c8e6c-108">The default location is `C:\Program Files (x86)\Microsoft SDKs\Windows\v7.0\Samples\sysmgmt\WindowsPowerShell\csharp\Events01`.</span></span>

2. <span data-ttu-id="c8e6c-109">ソリューション (.sln) ファイルのアイコンをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="c8e6c-109">Double-click the icon for the solution (.sln) file.</span></span>
   <span data-ttu-id="c8e6c-110">これにより、Microsoft Visual Studio でサンプルプロジェクトが開きます。</span><span class="sxs-lookup"><span data-stu-id="c8e6c-110">This opens the sample project in Microsoft Visual Studio.</span></span>

3. <span data-ttu-id="c8e6c-111">**[ビルド]** メニューで、 **[ソリューションのビルド]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c8e6c-111">In the **Build** menu, select **Build Solution**.</span></span>
   <span data-ttu-id="c8e6c-112">サンプルのライブラリは、既定の `\bin` フォルダーまたはフォルダーに組み込まれ `\bin\debug` ます。</span><span class="sxs-lookup"><span data-stu-id="c8e6c-112">The library for the sample will be built in the default `\bin` or `\bin\debug` folders.</span></span>

### <a name="how-to-run-the-sample"></a><span data-ttu-id="c8e6c-113">サンプルを実行する方法</span><span class="sxs-lookup"><span data-stu-id="c8e6c-113">How to run the sample</span></span>

1. <span data-ttu-id="c8e6c-114">次のモジュールフォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="c8e6c-114">Create the following module folder:</span></span>

    `[user]/documents/windowspowershell/modules/events01`

2. <span data-ttu-id="c8e6c-115">サンプルのライブラリファイルをモジュールフォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="c8e6c-115">Copy the library file for the sample to the module folder.</span></span>

3. <span data-ttu-id="c8e6c-116">Windows PowerShell を起動します。</span><span class="sxs-lookup"><span data-stu-id="c8e6c-116">Start Windows PowerShell.</span></span>

4. <span data-ttu-id="c8e6c-117">次のコマンドを実行して、Windows PowerShell にコマンドレットを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="c8e6c-117">Run the following command to load the cmdlet into Windows PowerShell:</span></span>

    ```powershell
    import-module events01
    ```

5. <span data-ttu-id="c8e6c-118">ファイルが一時ディレクトリに作成されたときにメッセージを書き込むアクションを登録するには、FileSystemEvent コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="c8e6c-118">Use the Register-FileSystemEvent cmdlet to register an action that will write a message when a file is created under the TEMP directory.</span></span>

    ```powershell
    Register-FileSystemEvent $env:temp Created -filter "*.txt" -action { Write-Host "A file was created in the TEMP directory" }
    ```

6. <span data-ttu-id="c8e6c-119">TEMP ディレクトリの下にファイルを作成し、アクションが実行されることを確認します (メッセージが表示されます)。</span><span class="sxs-lookup"><span data-stu-id="c8e6c-119">Create a file under the TEMP directory and note that the action is executed (the message is displayed).</span></span>

<span data-ttu-id="c8e6c-120">これは、次の手順に従って生成される出力サンプルです。</span><span class="sxs-lookup"><span data-stu-id="c8e6c-120">This is a sample output that results by following these steps.</span></span>

```output
Id              Name            State      HasMoreData     Location             Command
--              ----            -----      -----------     --------             -------
1               26932870-d3b... NotStarted False                                 Write-Host "A f...

```

```powershell
Set-Content $env:temp\test.txt "This is a test file"
```

```output
A file was created in the TEMP directory
```

## <a name="requirements"></a><span data-ttu-id="c8e6c-121">必要条件</span><span class="sxs-lookup"><span data-stu-id="c8e6c-121">Requirements</span></span>

<span data-ttu-id="c8e6c-122">このサンプルには、Windows PowerShell 2.0 が必要です。</span><span class="sxs-lookup"><span data-stu-id="c8e6c-122">This sample requires Windows PowerShell 2.0.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="c8e6c-123">対象</span><span class="sxs-lookup"><span data-stu-id="c8e6c-123">Demonstrates</span></span>

<span data-ttu-id="c8e6c-124">このサンプルでは、次のことを示します。</span><span class="sxs-lookup"><span data-stu-id="c8e6c-124">This sample demonstrates the following.</span></span>

### <a name="how-to-write-a-cmdlet-for-event-registration"></a><span data-ttu-id="c8e6c-125">イベント登録用のコマンドレットを記述する方法</span><span class="sxs-lookup"><span data-stu-id="c8e6c-125">How to write a cmdlet for event registration</span></span>

<span data-ttu-id="c8e6c-126">コマンドレットは、コマンドレットに共通のパラメーターをサポートする[ObjectEventRegistrationBase](/dotnet/api/Microsoft.PowerShell.Commands.ObjectEventRegistrationBase)クラスから派生します。 `Register-*Event`</span><span class="sxs-lookup"><span data-stu-id="c8e6c-126">The cmdlet derives from the [Microsoft.PowerShell.Commands.ObjectEventRegistrationBase](/dotnet/api/Microsoft.PowerShell.Commands.ObjectEventRegistrationBase) class, which provides support for parameters common to the `Register-*Event` cmdlets.</span></span>
<span data-ttu-id="c8e6c-127">[ObjectEventRegistrationBase](/dotnet/api/Microsoft.PowerShell.Commands.ObjectEventRegistrationBase)から派生したコマンドレットでは、特定のパラメーターを定義し、 `GetSourceObject` および抽象メソッドをオーバーライドするだけで済みます。 `GetSourceObjectEventName`</span><span class="sxs-lookup"><span data-stu-id="c8e6c-127">Cmdlets that are derived from [Microsoft.PowerShell.Commands.ObjectEventRegistrationBase](/dotnet/api/Microsoft.PowerShell.Commands.ObjectEventRegistrationBase) need only to define their particular parameters and override the `GetSourceObject` and `GetSourceObjectEventName` abstract methods.</span></span>

## <a name="example"></a><span data-ttu-id="c8e6c-128">例</span><span class="sxs-lookup"><span data-stu-id="c8e6c-128">Example</span></span>

<span data-ttu-id="c8e6c-129">このサンプルでは、system.object[によって](/dotnet/api/System.IO.FileSystemWatcher)生成されるイベントに登録する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="c8e6c-129">This sample shows how to register for events raised by [System.IO.FileSystemWatcher](/dotnet/api/System.IO.FileSystemWatcher).</span></span>

```csharp
namespace Sample
{
    using System;
    using System.IO;
    using System.Management.Automation;
    using System.Management.Automation.Runspaces;
    using Microsoft.PowerShell.Commands;

    [Cmdlet(VerbsLifecycle.Register, "FileSystemEvent")]
    public class RegisterObjectEventCommand : ObjectEventRegistrationBase
    {
        /// <summary>The FileSystemWatcher that exposes the events.</summary>
        private FileSystemWatcher fileSystemWatcher = new FileSystemWatcher();

        /// <summary>Name of the event to which the cmdlet registers.</summary>
        private string eventName = null;

        /// <summary>
        /// Gets or sets the path that will be monitored by the FileSystemWatcher.
        /// </summary>
        [Parameter(Mandatory = true, Position = 0)]
        public string Path
        {
            get
            {
                return this.fileSystemWatcher.Path;
            }

            set
            {
                this.fileSystemWatcher.Path = value;
            }
        }

        /// <summary>
        /// Gets or sets the name of the event to which the cmdlet registers.
        /// <para>
        /// Currently System.IO.FileSystemWatcher exposes 6 events: Changed, Created,
        /// Deleted, Disposed, Error, and Renamed. Check the MSDN documentation of
        /// FileSystemWatcher for details on each event.
        /// </para>
        /// </summary>
        [Parameter(Mandatory = true, Position = 1)]
        public string EventName
        {
            get
            {
                return this.eventName;
            }

            set
            {
                this.eventName = value;
            }
        }

        /// <summary>
        /// Gets or sets the filter that will be user by the FileSystemWatcher.
        /// </summary>
        [Parameter(Mandatory = false)]
        public string Filter
        {
            get
            {
                return this.fileSystemWatcher.Filter;
            }

            set
            {
                this.fileSystemWatcher.Filter = value;
            }
        }

        /// <summary>
        /// Derived classes must implement this method to return the object that generates
        /// the events to be monitored.
        /// </summary>
        /// <returns> This sample returns an instance of System.IO.FileSystemWatcher</returns>
        protected override object GetSourceObject()
        {
            return this.fileSystemWatcher;
        }

        /// <summary>
        /// Derived classes must implement this method to return the name of the event to
        /// be monitored. This event must be exposed by the input object.
        /// </summary>
        /// <returns> This sample returns the event specified by the user with the -EventName parameter.</returns>
        protected override string GetSourceObjectEventName()
        {
            return this.eventName;
        }
    }
}
```

## <a name="see-also"></a><span data-ttu-id="c8e6c-130">参照</span><span class="sxs-lookup"><span data-stu-id="c8e6c-130">See Also</span></span>

[<span data-ttu-id="c8e6c-131">Writing a Windows PowerShell Cmdlet (Windows PowerShell コマンドレットの記述)</span><span class="sxs-lookup"><span data-stu-id="c8e6c-131">Writing a Windows PowerShell Cmdlet</span></span>](writing-a-windows-powershell-cmdlet.md)
