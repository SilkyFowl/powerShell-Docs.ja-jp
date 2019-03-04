---
title: コメント ベースのヘルプ キーワード |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ab90ec96-77f5-42e3-9c7e-2f4156ec207f
caps.latest.revision: 6
ms.openlocfilehash: dbb6f7c4cbefeaaaec0747511f50192bcf08c20c
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56862658"
---
# <a name="comment-based-help-keywords"></a><span data-ttu-id="62398-102">コメント ベースのヘルプのキーワード</span><span class="sxs-lookup"><span data-stu-id="62398-102">Comment-Based Help Keywords</span></span>

<span data-ttu-id="62398-103">このトピックでは、コメント ベースのヘルプのキーワードの一覧です。</span><span class="sxs-lookup"><span data-stu-id="62398-103">This topic lists and describes the keywords in comment-based help.</span></span>

## <a name="keywords-in-comment-based-help"></a><span data-ttu-id="62398-104">コメント ベースのヘルプのキーワード</span><span class="sxs-lookup"><span data-stu-id="62398-104">Keywords in Comment-Based Help</span></span>

<span data-ttu-id="62398-105">有効なコメント ベースのヘルプ キーワードを次に示します。</span><span class="sxs-lookup"><span data-stu-id="62398-105">The following are valid comment-based Help keywords.</span></span> <span data-ttu-id="62398-106">これらは、通常表示されるヘルプ トピックとその使用目的の順序で並んでいます。</span><span class="sxs-lookup"><span data-stu-id="62398-106">They are listed in the order in which they typically appear in a Help topic along with their intended use.</span></span> <span data-ttu-id="62398-107">これらのキーワードは、コメント ベースのヘルプで任意の順序で表示でき、小文字は区別されません。</span><span class="sxs-lookup"><span data-stu-id="62398-107">These keywords can appear in any order in the comment-based Help, and they are not case-sensitive.</span></span>

<span data-ttu-id="62398-108">なお、`.ExternalHelp`キーワードが他のすべてのコメント ベースのヘルプ キーワードより優先されます。</span><span class="sxs-lookup"><span data-stu-id="62398-108">Note that the `.ExternalHelp` keyword takes precedence over all other comment-based help keywords.</span></span> <span data-ttu-id="62398-109">ときに`.ExternalHelp`が存在する、 [Microsoft.Powershell.Commands.Get ヘルプ](/dotnet/api/Microsoft.PowerShell.Commands.Get-Help)キーワードの値に一致するヘルプ ファイルを見つけられない場合でも、コマンドレットでコメント ベースのヘルプが表示されません。</span><span class="sxs-lookup"><span data-stu-id="62398-109">When `.ExternalHelp` is present, the [Microsoft.Powershell.Commands.Get-Help](/dotnet/api/Microsoft.PowerShell.Commands.Get-Help) cmdlet does not display comment-based help, even when it cannot find a help file that matches the value of the keyword.</span></span>

<span data-ttu-id="62398-110">`.Synopsis` 関数またはスクリプトの簡単な説明。</span><span class="sxs-lookup"><span data-stu-id="62398-110">`.Synopsis` A brief description of the function or script.</span></span> <span data-ttu-id="62398-111">このキーワードは、各トピックで 1 回だけ使用できます。</span><span class="sxs-lookup"><span data-stu-id="62398-111">This keyword can be used only once in each topic.</span></span>

<span data-ttu-id="62398-112">`.Description` 関数またはスクリプトの詳細な説明。</span><span class="sxs-lookup"><span data-stu-id="62398-112">`.Description` A detailed description of the function or script.</span></span> <span data-ttu-id="62398-113">このキーワードは、各トピックで 1 回だけ使用できます。</span><span class="sxs-lookup"><span data-stu-id="62398-113">This keyword can be used only once in each topic.</span></span>

<span data-ttu-id="62398-114">`.Parameter` *\<パラメーター名 >* パラメーターの説明。</span><span class="sxs-lookup"><span data-stu-id="62398-114">`.Parameter` *\<Parameter-Name>* The description of a parameter.</span></span> <span data-ttu-id="62398-115">含めることができます、`.Parameter`関数またはスクリプトでは、各パラメーターのキーワード。</span><span class="sxs-lookup"><span data-stu-id="62398-115">You can include a `.Parameter` keyword for each parameter in the function or script.</span></span>

<span data-ttu-id="62398-116">`.Parameter`キーワードには、表示、コメント ブロック内の任意の順序でパラメーターが表示される順序で、`Param`ステートメントまたは関数の宣言は、パラメーター ヘルプ トピックに表示される順序を決定します。</span><span class="sxs-lookup"><span data-stu-id="62398-116">The `.Parameter` keywords can appear in any order in the comment block, but the order in which the parameters appear in the `Param` statement or function declaration determines the order in which the parameters appear in Help topic.</span></span> <span data-ttu-id="62398-117">ヘルプ トピック内のパラメーターの順序を変更するでのパラメーターの順序を変更、`Param`ステートメントまたは関数の宣言。</span><span class="sxs-lookup"><span data-stu-id="62398-117">To change the order of parameters in the Help topic, change the order of the parameters in the `Param` statement or function declaration.</span></span>

<span data-ttu-id="62398-118">内のコメントを配置することで、パラメーターの説明を指定することも、`Param`パラメーター変数名の直前のステートメント。</span><span class="sxs-lookup"><span data-stu-id="62398-118">You can also specify a parameter description by placing a comment in the `Param` statement immediately before the parameter variable name.</span></span> <span data-ttu-id="62398-119">両方を使用する場合、`Param`ステートメントのコメントと`.Parameter`キーワードに関連付けられた説明、`.Parameter`キーワードを使用して、および`Param`ステートメントのコメントは無視されます。</span><span class="sxs-lookup"><span data-stu-id="62398-119">If you use both a `Param` statement comment and a `.Parameter` keyword, the description associated with the `.Parameter` keyword is used, and the `Param` statement comment is ignored.</span></span>

<span data-ttu-id="62398-120">`.Example` 関数または出力の例と説明が続く必要に応じてスクリプトを使用するサンプル コマンド。</span><span class="sxs-lookup"><span data-stu-id="62398-120">`.Example` A sample command that uses the function or script, optionally followed by sample output and a description.</span></span> <span data-ttu-id="62398-121">それぞれの例については、このキーワードを繰り返します。</span><span class="sxs-lookup"><span data-stu-id="62398-121">Repeat this keyword for each example.</span></span>

<span data-ttu-id="62398-122">`.Inputs` 関数またはスクリプトにパイプできるオブジェクトの Microsoft .NET Framework の型。</span><span class="sxs-lookup"><span data-stu-id="62398-122">`.Inputs` The Microsoft .NET Framework types of objects that can be piped to the function or script.</span></span> <span data-ttu-id="62398-123">入力オブジェクトの説明を含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="62398-123">You can also include a description of the input objects.</span></span>

<span data-ttu-id="62398-124">`.Outputs` このコマンドレットで返されるオブジェクトの .NET Framework 型。</span><span class="sxs-lookup"><span data-stu-id="62398-124">`.Outputs` The .NET Framework type of the objects that the cmdlet returns.</span></span> <span data-ttu-id="62398-125">返されるオブジェクトの説明を含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="62398-125">You can also include a description of the returned objects.</span></span>

<span data-ttu-id="62398-126">`.Notes` 関数またはスクリプトに関する追加情報。</span><span class="sxs-lookup"><span data-stu-id="62398-126">`.Notes` Additional information about the function or script.</span></span>

<span data-ttu-id="62398-127">`.Link` 関連トピックの名前。</span><span class="sxs-lookup"><span data-stu-id="62398-127">`.Link` The name of a related topic.</span></span> <span data-ttu-id="62398-128">関連トピックごとに、このキーワードを繰り返します。</span><span class="sxs-lookup"><span data-stu-id="62398-128">Repeat this keyword for each related topic.</span></span> <span data-ttu-id="62398-129">このコンテンツは、ヘルプ トピックの「関連リンク」に表示されます。</span><span class="sxs-lookup"><span data-stu-id="62398-129">This content appears in the Related Links section of the Help topic.</span></span>

<span data-ttu-id="62398-130">`.Link`キーワードのコンテンツは、同じヘルプ トピックのオンライン バージョンを統一リソース識別子 (URI) を含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="62398-130">The `.Link` keyword content can also include a Uniform Resource Identifier (URI) to an online version of the same Help topic.</span></span> <span data-ttu-id="62398-131">使用するとオンライン バージョンが開きます、`Online`パラメーターのヘルプを表示します。</span><span class="sxs-lookup"><span data-stu-id="62398-131">The online version opens when you use the `Online` parameter of Get-Help.</span></span> <span data-ttu-id="62398-132">URI は、"http"または"https"で始まる必要があります。</span><span class="sxs-lookup"><span data-stu-id="62398-132">The URI must begin with "http" or "https".</span></span>

<span data-ttu-id="62398-133">`.Component` テクノロジまたは機能または関連する関数またはスクリプトが使用します。</span><span class="sxs-lookup"><span data-stu-id="62398-133">`.Component` The technology or feature that the function or script uses, or to which it is related.</span></span> <span data-ttu-id="62398-134">Get-help コマンドが含まれる場合、このコンテンツが表示されます、`Component`パラメーターのヘルプを表示します。</span><span class="sxs-lookup"><span data-stu-id="62398-134">This content appears when the Get-Help command includes the `Component` parameter of Get-Help.</span></span>

<span data-ttu-id="62398-135">`.Role` ヘルプ トピックでは、ユーザー ロール。</span><span class="sxs-lookup"><span data-stu-id="62398-135">`.Role` The user role for the Help topic.</span></span> <span data-ttu-id="62398-136">Get-help コマンドが含まれる場合、このコンテンツが表示されます、`Role`パラメーターのヘルプを表示します。</span><span class="sxs-lookup"><span data-stu-id="62398-136">This content appears when the Get-Help command includes the `Role` parameter of Get-Help.</span></span>

<span data-ttu-id="62398-137">`.Functionality` 関数の使用目的。</span><span class="sxs-lookup"><span data-stu-id="62398-137">`.Functionality` The intended use of the function.</span></span> <span data-ttu-id="62398-138">Get-help コマンドが含まれる場合、このコンテンツが表示されます、`Functionality`パラメーターのヘルプを表示します。</span><span class="sxs-lookup"><span data-stu-id="62398-138">This content appears when the Get-Help command includes the `Functionality` parameter of Get-Help.</span></span>

<span data-ttu-id="62398-139">`.ForwardHelpTargetName` `<Command-Name>` 指定されたコマンドのヘルプ トピックにリダイレクトします。</span><span class="sxs-lookup"><span data-stu-id="62398-139">`.ForwardHelpTargetName` `<Command-Name>` Redirects to the Help topic for the specified command.</span></span> <span data-ttu-id="62398-140">関数、スクリプト、コマンドレット、またはプロバイダーのヘルプ トピックを含む、任意のヘルプ トピックには、ユーザーをリダイレクトできます。</span><span class="sxs-lookup"><span data-stu-id="62398-140">You can redirect users to any Help topic, including Help topics for a function, script, cmdlet, or provider.</span></span>

<span data-ttu-id="62398-141">`.ForwardHelpCategory` `<Category>` ForwardHelpTargetName で項目のヘルプのカテゴリを指定します。</span><span class="sxs-lookup"><span data-stu-id="62398-141">`.ForwardHelpCategory` `<Category>` Specifies the Help category of the item in ForwardHelpTargetName.</span></span> <span data-ttu-id="62398-142">有効な値は、エイリアス、コマンドレット、HelpFile、関数、プロバイダー、全般、FAQ、用語集、ScriptCommand、ExternalScript、フィルター、またはすべてには。</span><span class="sxs-lookup"><span data-stu-id="62398-142">Valid values are Alias, Cmdlet, HelpFile, Function, Provider, General, FAQ, Glossary, ScriptCommand, ExternalScript, Filter, or All.</span></span> <span data-ttu-id="62398-143">同じ名前のコマンドがある場合は、競合を回避するのにには、このキーワードを使用します。</span><span class="sxs-lookup"><span data-stu-id="62398-143">Use this keyword to avoid conflicts when there are commands with the same name.</span></span>

<span data-ttu-id="62398-144">`.RemoteHelpRunspace` `<PSSession-variable>` ヘルプ トピックを含むセッションを指定します。</span><span class="sxs-lookup"><span data-stu-id="62398-144">`.RemoteHelpRunspace` `<PSSession-variable>` Specifies a session that contains the Help topic.</span></span> <span data-ttu-id="62398-145">PSSession を含む変数を入力します。</span><span class="sxs-lookup"><span data-stu-id="62398-145">Enter a variable that contains a PSSession.</span></span> <span data-ttu-id="62398-146">このキーワードを使用して、`Export-PSSession`コマンドレットは、エクスポートしたコマンドのヘルプ トピックが見つかりません。</span><span class="sxs-lookup"><span data-stu-id="62398-146">This keyword is used by the `Export-PSSession` cmdlet to find the Help topics for the exported commands.</span></span>

<span data-ttu-id="62398-147">`.ExternalHelp` `<XML Help File>` パス、スクリプトまたは関数に対する XML ベースのヘルプ ファイルの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="62398-147">`.ExternalHelp` `<XML Help File>` Specifies the path and/or name of an XML-based Help file for the script or function.</span></span>

<span data-ttu-id="62398-148">`.ExternalHelp`キーワードに指示、 [Microsoft.Powershell.Commands.Get ヘルプ](/dotnet/api/Microsoft.PowerShell.Commands.Get-Help)XML ベースのファイルでスクリプトまたは関数のヘルプを取得するコマンドレットです。</span><span class="sxs-lookup"><span data-stu-id="62398-148">The `.ExternalHelp` keyword tells the [Microsoft.Powershell.Commands.Get-Help](/dotnet/api/Microsoft.PowerShell.Commands.Get-Help) cmdlet to get help for the script or function in an XML-based file.</span></span> <span data-ttu-id="62398-149">**します。ExternalHelp**スクリプトまたは関数を XML ベースのヘルプ ファイルを使用する場合は、キーワードが必要です。</span><span class="sxs-lookup"><span data-stu-id="62398-149">The **.ExternalHelp** keyword is required when using an XML-based help file for a script or function.</span></span> <span data-ttu-id="62398-150">これがない`Get-Help`関数またはスクリプトのヘルプ ファイルは見つかりません。</span><span class="sxs-lookup"><span data-stu-id="62398-150">Without it, `Get-Help` will not find a help file for the function or script.</span></span>

<span data-ttu-id="62398-151">`.ExternalHelp`キーワードが他のすべてのコメント ベースのヘルプ キーワードより優先されます。</span><span class="sxs-lookup"><span data-stu-id="62398-151">The `.ExternalHelp` keyword takes precedence over all other comment-based help keywords.</span></span> <span data-ttu-id="62398-152">ときに`.ExternalHelp`が存在する、 [Microsoft.Powershell.Commands.Get ヘルプ](/dotnet/api/Microsoft.PowerShell.Commands.Get-Help)キーワードの値に一致するヘルプ ファイルを見つけられない場合でも、コマンドレットでコメント ベースのヘルプが表示されません。</span><span class="sxs-lookup"><span data-stu-id="62398-152">When `.ExternalHelp` is present, the [Microsoft.Powershell.Commands.Get-Help](/dotnet/api/Microsoft.PowerShell.Commands.Get-Help) cmdlet does not display comment-based help, even when it cannot find a help file that matches the value of the keyword.</span></span>

<span data-ttu-id="62398-153">スクリプト モジュールの場合の値によって関数をエクスポートするときに`.ExternalHelp`path を含まないファイル名にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="62398-153">When the function is exported by a script module, the value of `.ExternalHelp` should be a file name without a path.</span></span> <span data-ttu-id="62398-154">`Get-Help` モジュール ディレクトリのロケール固有のサブディレクトリにファイルを探します。</span><span class="sxs-lookup"><span data-stu-id="62398-154">`Get-Help` looks for the file in a locale-specific subdirectory of the module directory.</span></span> <span data-ttu-id="62398-155">ファイル名の要件はありませんが、ベスト プラクティスは、次のファイル名の形式を使用する:`<ScriptModule>.psm1-help.xml`します。</span><span class="sxs-lookup"><span data-stu-id="62398-155">There are no requirements for the file name, but a best practice is to use the following file name format: `<ScriptModule>.psm1-help.xml`.</span></span>

<span data-ttu-id="62398-156">関数が、モジュールに関連付けられていない場合は、値にパスとファイル名を含める、**します。ExternalHelp**キーワード。</span><span class="sxs-lookup"><span data-stu-id="62398-156">When the function is not associated with a module, include a path and file name in the value of the **.ExternalHelp** keyword.</span></span> <span data-ttu-id="62398-157">XML ファイルに指定されたパスには、UI カルチャ固有のサブディレクトリが含まれている場合`Get-Help`スクリプトまたは関数に従ってのフォールバックの標準が確立されている言語の名前を持つ XML ファイルを再帰的にサブディレクトリを検索Windows では、同じように、すべての XML ベースのヘルプ トピックは。</span><span class="sxs-lookup"><span data-stu-id="62398-157">If the specified path to the XML file contains UI-culture-specific subdirectories, `Get-Help` searches the subdirectories recursively for an XML file with the name of the script or function in accordance with the language fallback standards established for Windows, just as it does for all XML-based Help topics.</span></span>

<span data-ttu-id="62398-158">コマンドレットのヘルプの XML ベースのヘルプ ファイルの形式に関する詳細については、次を参照してください。[書き込み Windows PowerShell コマンドレットのヘルプ](./writing-help-for-windows-powershell-cmdlets.md)します。</span><span class="sxs-lookup"><span data-stu-id="62398-158">For more information about the cmdlet Help XML-based Help file format, see [Writing Windows PowerShell Cmdlet Help](./writing-help-for-windows-powershell-cmdlets.md).</span></span>