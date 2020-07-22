---
title: ヘルプ ファイルに名前を付ける
ms.date: 09/12/2016
ms.openlocfilehash: ea95e6d6c87e553ed11fe6e3f058fc9a1b3d03f8
ms.sourcegitcommit: de59ff77c6535fc772c1e327b3c823295eaed6ea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/22/2020
ms.locfileid: "86893273"
---
# <a name="naming-help-files"></a><span data-ttu-id="6774d-102">ヘルプ ファイルに名前を付ける</span><span class="sxs-lookup"><span data-stu-id="6774d-102">Naming Help Files</span></span>

<span data-ttu-id="6774d-103">このトピックでは、 [get-help](/powershell/module/Microsoft.PowerShell.Core/Get-Help)コマンドレットで検索できるように、XML ベースのヘルプファイルに名前を指定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6774d-103">This topic explains how to name an XML-based help file so that the [Get-Help](/powershell/module/Microsoft.PowerShell.Core/Get-Help) cmdlet can find it.</span></span> <span data-ttu-id="6774d-104">名前の要件は、コマンドの種類によって異なります。</span><span class="sxs-lookup"><span data-stu-id="6774d-104">The name requirements differ for each command type.</span></span>

## <a name="cmdlet-help-files"></a><span data-ttu-id="6774d-105">コマンドレットのヘルプファイル</span><span class="sxs-lookup"><span data-stu-id="6774d-105">Cmdlet Help Files</span></span>

<span data-ttu-id="6774d-106">C# コマンドレットのヘルプファイルには、コマンドレットが定義されているアセンブリの名前を付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="6774d-106">The help file for a C# cmdlet must be named for the assembly in which the cmdlet is defined.</span></span> <span data-ttu-id="6774d-107">次のファイル名形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="6774d-107">Use the following filename format:</span></span>

```
<AssemblyName>.dll-help.xml
```

<span data-ttu-id="6774d-108">アセンブリが入れ子になっているモジュールの場合でも、アセンブリ名の形式が必要です。</span><span class="sxs-lookup"><span data-stu-id="6774d-108">The assembly name format is required even when the assembly is a nested module.</span></span>

<span data-ttu-id="6774d-109">たとえば、Microsoft.PowerShell.Diagnostics.dll アセンブリでは、 [Get WinEvent](/powershell/module/Microsoft.PowerShell.Diagnostics/Get-WinEvent)コマンドレットが定義されています。</span><span class="sxs-lookup"><span data-stu-id="6774d-109">For example, the [Get-WinEvent](/powershell/module/Microsoft.PowerShell.Diagnostics/Get-WinEvent) cmdlet is defined in the Microsoft.PowerShell.Diagnostics.dll assembly.</span></span> <span data-ttu-id="6774d-110">`Get-Help`コマンドレットは、 `Get-WinEvent` モジュールディレクトリ内のファイルでのみ、コマンドレットのヘルプトピックを検索し `Microsoft.PowerShell.Diagnostics.dll-help.xml` ます。</span><span class="sxs-lookup"><span data-stu-id="6774d-110">The `Get-Help` cmdlet looks for a help topic for the `Get-WinEvent` cmdlet only in the `Microsoft.PowerShell.Diagnostics.dll-help.xml` file in the module directory.</span></span>

## <a name="provider-help-files"></a><span data-ttu-id="6774d-111">プロバイダーヘルプファイル</span><span class="sxs-lookup"><span data-stu-id="6774d-111">Provider Help files</span></span>

<span data-ttu-id="6774d-112">PowerShell プロバイダーのヘルプファイルには、プロバイダーが定義されているアセンブリの名前を付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="6774d-112">The help file for a PowerShell provider must be named for the assembly in which the provider is defined.</span></span> <span data-ttu-id="6774d-113">次のファイル名形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="6774d-113">Use the following filename format:</span></span>

`<AssemblyName>.dll-help.xml`

<span data-ttu-id="6774d-114">アセンブリが入れ子になっているモジュールの場合でも、アセンブリ名の形式が必要です。</span><span class="sxs-lookup"><span data-stu-id="6774d-114">The assembly name format is required even when the assembly is a nested module.</span></span>

<span data-ttu-id="6774d-115">たとえば、証明書プロバイダーはアセンブリで定義されてい `Microsoft.PowerShell.Security.dll` ます。</span><span class="sxs-lookup"><span data-stu-id="6774d-115">For example, the Certificate provider is defined in the `Microsoft.PowerShell.Security.dll` assembly.</span></span> <span data-ttu-id="6774d-116">この `Get-Help` コマンドレットは、モジュールディレクトリ内のファイルでのみ、証明書プロバイダーのヘルプトピックを検索し `Microsoft.PowerShell.Security.dll-help.xml` ます。</span><span class="sxs-lookup"><span data-stu-id="6774d-116">The `Get-Help` cmdlet looks for a help topic for the Certificate provider only in the `Microsoft.PowerShell.Security.dll-help.xml` file in the module directory.</span></span>

## <a name="function-help-files"></a><span data-ttu-id="6774d-117">関数のヘルプファイル</span><span class="sxs-lookup"><span data-stu-id="6774d-117">Function Help Files</span></span>

<span data-ttu-id="6774d-118">関数は、[コメントベースのヘルプ](/powershell/module/microsoft.powershell.core/about/about_comment_based_help)を使用するか、XML ヘルプファイルに記載されているドキュメントに記載されています。</span><span class="sxs-lookup"><span data-stu-id="6774d-118">Functions can be documented by using [comment-based help](/powershell/module/microsoft.powershell.core/about/about_comment_based_help) or documented in an XML help file.</span></span> <span data-ttu-id="6774d-119">関数が XML ファイルに記述されている場合、関数は `.ExternalHelp` 、xml ファイルに関数を関連付ける comment キーワードを持つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="6774d-119">When the function is documented in an XML file, the function must have an `.ExternalHelp` comment keyword that associates the function with the XML file.</span></span> <span data-ttu-id="6774d-120">それ以外の場合、 `Get-Help` コマンドレットはヘルプファイルを見つけることができません。</span><span class="sxs-lookup"><span data-stu-id="6774d-120">Otherwise, the `Get-Help` cmdlet cannot find the help file.</span></span>

<span data-ttu-id="6774d-121">関数のヘルプファイルの名前に関する技術的な要件はありません。</span><span class="sxs-lookup"><span data-stu-id="6774d-121">There are no technical requirements for the name of a function help file.</span></span> <span data-ttu-id="6774d-122">ただし、関数が定義されているスクリプトモジュールのヘルプファイルには、という名前を指定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6774d-122">However, a best practice is to name the help file for the script module in which the function is defined.</span></span> <span data-ttu-id="6774d-123">たとえば、次の関数はファイルで定義されてい `MyModule.psm1` ます。</span><span class="sxs-lookup"><span data-stu-id="6774d-123">For example, the following function is defined in the `MyModule.psm1` file.</span></span>

```csharp
#.ExternalHelp MyModule.psm1-help.xml
function Test-Function { ... }
```

## <a name="cim-command-help-files"></a><span data-ttu-id="6774d-124">CIM コマンドのヘルプファイル</span><span class="sxs-lookup"><span data-stu-id="6774d-124">CIM Command Help Files</span></span>

<span data-ttu-id="6774d-125">Cim コマンドのヘルプファイルには、CIM コマンドが定義されている CDXML ファイルの名前を付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="6774d-125">The help file for a CIM command must be named for the CDXML file in which the CIM command is defined.</span></span> <span data-ttu-id="6774d-126">次のファイル名形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="6774d-126">Use the following filename format:</span></span>

`<FileName>.cdxml-help.xml`

<span data-ttu-id="6774d-127">CIM コマンドは、モジュールに入れ子になったモジュールとして含めることができる、CDXML ファイルで定義されています。</span><span class="sxs-lookup"><span data-stu-id="6774d-127">CIM commands are defined in CDXML files that can be included in modules as nested modules.</span></span> <span data-ttu-id="6774d-128">CIM コマンドが関数としてセッションにインポートされると、PowerShell によって関数定義に comment キーワードが追加され、この関数 `.ExternalHelp` は、cim コマンドが定義されている CDXML ファイルの名前が付けられた XML ヘルプファイルに関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="6774d-128">When the CIM command is imported into the session as a function, PowerShell adds an `.ExternalHelp` comment keyword to the function definition that associates the function with an XML help file that is named for the CDXML file in which the CIM command is defined.</span></span>

## <a name="script-workflow-help-files"></a><span data-ttu-id="6774d-129">スクリプトワークフローのヘルプファイル</span><span class="sxs-lookup"><span data-stu-id="6774d-129">Script Workflow Help Files</span></span>

<span data-ttu-id="6774d-130">モジュールに含まれているスクリプトワークフローは、XML ベースのヘルプファイルに記載されています。</span><span class="sxs-lookup"><span data-stu-id="6774d-130">Script workflows that are included in modules can be documented in XML-based help files.</span></span> <span data-ttu-id="6774d-131">ヘルプファイルの名前に関する技術的な要件はありません。</span><span class="sxs-lookup"><span data-stu-id="6774d-131">There are no technical requirements for the name of the help file.</span></span> <span data-ttu-id="6774d-132">ただし、スクリプトワークフローが定義されているスクリプトモジュールのヘルプファイルには、という名前を指定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6774d-132">However, a best practice is to name the help file for the script module in which the script workflow is defined.</span></span> <span data-ttu-id="6774d-133">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="6774d-133">For example:</span></span>

`<ScriptModule>.psm1-help.xml`

<span data-ttu-id="6774d-134">スクリプト化された他のコマンドとは異なり、スクリプトワークフローでは、 `.ExternalHelp` コメントキーワードを使用してヘルプファイルに関連付ける必要はありません。</span><span class="sxs-lookup"><span data-stu-id="6774d-134">Unlike other scripted commands, script workflows do not require an `.ExternalHelp` comment keyword to associate them with a help file.</span></span> <span data-ttu-id="6774d-135">代わりに、PowerShell は、モジュールディレクトリの UI カルチャ固有のサブディレクトリで XML ベースのヘルプファイルを検索し、すべてのファイルでスクリプトワークフローのヘルプを検索します。</span><span class="sxs-lookup"><span data-stu-id="6774d-135">Instead, PowerShell searches the UI-Culture-specific subdirectories of the module directory for XML-based help files and looks for help for the script workflow in all the files.</span></span> <span data-ttu-id="6774d-136">`.ExternalHelp`comment キーワードは無視されます。</span><span class="sxs-lookup"><span data-stu-id="6774d-136">`.ExternalHelp` comment keyword are ignored.</span></span>

<span data-ttu-id="6774d-137">`.ExternalHelp`Comment キーワードは無視されるため、 `Get-Help` コマンドレットは、モジュールに含まれている場合にのみスクリプトワークフローのヘルプを見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="6774d-137">Because the `.ExternalHelp` comment keyword is ignored, the `Get-Help` cmdlet can find help for script workflows only when they are included in modules.</span></span>
