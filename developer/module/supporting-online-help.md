---
title: オンライン ヘルプのサポート |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3204599c-7159-47aa-82ec-4a476f461027
caps.latest.revision: 7
ms.openlocfilehash: b76f45299d11dc10c8b16ed80f87c7f1fcc5ed65
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56857918"
---
# <a name="supporting-online-help"></a><span data-ttu-id="2081e-102">オンライン ヘルプのサポート</span><span class="sxs-lookup"><span data-stu-id="2081e-102">Supporting Online Help</span></span>

<span data-ttu-id="2081e-103">Windows PowerShell 3.0 以降でサポートするために 2 つの方法がある、`Get-Help`の Windows PowerShell コマンドのオンライン機能。</span><span class="sxs-lookup"><span data-stu-id="2081e-103">Beginning in Windows PowerShell 3.0, there are two ways to support the `Get-Help` Online feature for Windows PowerShell commands.</span></span> <span data-ttu-id="2081e-104">このトピックでは、さまざまなコマンドの種類に対してこの機能を実装する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2081e-104">This topic explains how to implement this feature for different command types.</span></span>

## <a name="about-online-help"></a><span data-ttu-id="2081e-105">オンライン ヘルプについて</span><span class="sxs-lookup"><span data-stu-id="2081e-105">About Online Help</span></span>

<span data-ttu-id="2081e-106">オンライン ヘルプには、Windows PowerShell の重要な部分がきました。</span><span class="sxs-lookup"><span data-stu-id="2081e-106">Online help has always been a vital part of Windows PowerShell.</span></span> <span data-ttu-id="2081e-107">ですが、`Get-Help`コマンドレットは、コマンド プロンプトでヘルプ トピックを表示、多くのユーザーは、色分け、ハイパーリンク、およびコミュニティ コンテンツと wiki ベースのドキュメントのアイディアを共有などのオンラインの読み取りのエクスペリエンスを優先します。</span><span class="sxs-lookup"><span data-stu-id="2081e-107">Although the `Get-Help` cmdlet displays help topics at the command prompt, many users prefer the experience of reading online, including color-coding, hyperlinks, and sharing ideas in Community Content and wiki-based documents.</span></span> <span data-ttu-id="2081e-108">最も重要なは、更新可能なヘルプの登場によって、前にオンライン ヘルプは、ヘルプ ファイルの最新バージョンを提供します。</span><span class="sxs-lookup"><span data-stu-id="2081e-108">Most importantly, before the advent of Updatable Help, online help provided the most up-to-date version of the help files.</span></span>

<span data-ttu-id="2081e-109">Windows PowerShell 3.0 では更新可能なヘルプの登場によって、オンライン ヘルプはまだ重要な役割を果たします。</span><span class="sxs-lookup"><span data-stu-id="2081e-109">With the advent of Updatable Help in Windows PowerShell 3.0, online help still plays a vital role.</span></span> <span data-ttu-id="2081e-110">だけでなく、柔軟なユーザー エクスペリエンスは、オンライン ヘルプは、しない、またはヘルプ トピックをダウンロードする更新可能なヘルプを使用できないユーザーにヘルプを提供します。</span><span class="sxs-lookup"><span data-stu-id="2081e-110">In addition to the flexible user experience, online help provides help to users who do not or cannot use Updatable Help to download help topics.</span></span>

## <a name="how-get-help--online-works"></a><span data-ttu-id="2081e-111">どの Get-help-Online Works</span><span class="sxs-lookup"><span data-stu-id="2081e-111">How Get-Help -Online Works</span></span>

<span data-ttu-id="2081e-112">コマンドについては、オンラインのヘルプ トピックを見つけられるようにする、`Get-Help`コマンドには、ユーザーの既定のインターネット ブラウザーで、コマンドのヘルプ トピックのオンライン バージョンを開き、オンライン パラメーターが含まれています。</span><span class="sxs-lookup"><span data-stu-id="2081e-112">To help users find the online help topics for commands, the `Get-Help` command has an Online parameter that opens the online version of help topic for a command in the user's default Internet browser.</span></span>

<span data-ttu-id="2081e-113">たとえば、次のコマンドがのオンライン ヘルプ トピックが表示されます、`Invoke-Command`コマンドレット。</span><span class="sxs-lookup"><span data-stu-id="2081e-113">For example, the following command opens the online help topic for the `Invoke-Command` cmdlet.</span></span>

```powershell
Get-Help Invoke-Command -Online
```

<span data-ttu-id="2081e-114">実装する`Get-Help`-オンラインで、`Get-Help`コマンドレットは、次の場所でオンライン バージョンのヘルプ トピックの統一リソース識別子 (URI) を次になります。</span><span class="sxs-lookup"><span data-stu-id="2081e-114">To implement `Get-Help` -Online, the `Get-Help` cmdlet looks for a Uniform Resource Identifier (URI) for the online version help topic in the following locations.</span></span>

- <span data-ttu-id="2081e-115">コマンドのヘルプ トピックの「関連リンク」の最初のリンク。</span><span class="sxs-lookup"><span data-stu-id="2081e-115">The first link in the Related Links section of the help topic for the command.</span></span> <span data-ttu-id="2081e-116">ヘルプ トピックでは、ユーザーのコンピューターにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2081e-116">The help topic must be installed on the user's computer.</span></span> <span data-ttu-id="2081e-117">この機能は、Windows PowerShell 2.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="2081e-117">This feature was introduced in Windows PowerShell 2.0.</span></span>

- <span data-ttu-id="2081e-118">任意のコマンドの HelpUri プロパティ。</span><span class="sxs-lookup"><span data-stu-id="2081e-118">The HelpUri property of any command.</span></span> <span data-ttu-id="2081e-119">HelpUri プロパティは、コマンドのヘルプ トピックがユーザーのコンピューターにインストールされていない場合でもアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="2081e-119">The HelpUri property is accessible even when the help topic for the command is not installed on the user's computer.</span></span> <span data-ttu-id="2081e-120">この機能は、Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="2081e-120">This feature was introduced in Windows PowerShell 3.0.</span></span>

  <span data-ttu-id="2081e-121">`Get-Help` HelpUri プロパティの値を取得する前に、関連リンク」セクションの最初のエントリの URI を検索します。</span><span class="sxs-lookup"><span data-stu-id="2081e-121">`Get-Help` looks for a URI in the first entry in the Related Links section before getting the HelpUri property value.</span></span> <span data-ttu-id="2081e-122">プロパティの値が間違っているかが変更された場合は、最初の関連リンクで、別の値を入力してオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="2081e-122">If the property value is incorrect or has changed, you can override it by entering a different value in the first Related Link.</span></span> <span data-ttu-id="2081e-123">ただし、最初の関連リンクは、ヘルプ トピックは、ユーザーのコンピューターにインストールされている場合にのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="2081e-123">However, the first Related Link works only when the help topics are installed on the user's computer.</span></span>

## <a name="adding-a-uri-to-the-first-related-link-of-a-command-help-topic"></a><span data-ttu-id="2081e-124">コマンドのヘルプ トピックの最初の関連リンクへの URI の追加</span><span class="sxs-lookup"><span data-stu-id="2081e-124">Adding a URI to the first related link of a command help topic</span></span>

<span data-ttu-id="2081e-125">サポートできる`Get-Help`-コマンドの XML ベースのヘルプ トピックの「関連リンク」の最初のエントリを有効な URI を追加することで、任意のコマンドは、オンラインです。</span><span class="sxs-lookup"><span data-stu-id="2081e-125">You can support `Get-Help` -Online for any command by adding a valid URI to the first entry in the Related Links section of the XML-based help topic for the command.</span></span> <span data-ttu-id="2081e-126">このオプションは、XML ベースのヘルプ トピックでのみ有効ですが、ヘルプ トピックがユーザーのコンピューターにインストールされている場合にだけ機能します。</span><span class="sxs-lookup"><span data-stu-id="2081e-126">This option is valid only in XML-based help topics and works only when the help topic is installed on the user's computer.</span></span> <span data-ttu-id="2081e-127">ヘルプ トピックがインストールされているし、URI が設定されて、この値よりも優先、 **HelpUri**コマンドのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="2081e-127">When the help topic is installed and the URI is populated, this value takes precedence over the **HelpUri** property of the command.</span></span> <span data-ttu-id="2081e-128">コマンドの XML ベースのヘルプ トピックについては、次を参照してください。[コマンドのヘルプ トピックを Writing XML-Based](../help/writing-xml-based-help-topics-for-commands.md)します。</span><span class="sxs-lookup"><span data-stu-id="2081e-128">For information about XML-based help topics for commands, see [Writing XML-Based Help Topics for Commands](../help/writing-xml-based-help-topics-for-commands.md).</span></span>

<span data-ttu-id="2081e-129">この機能をサポートするためには、URI に表示する必要があります、`maml:uri`最初要素`maml:relatedLinks/maml:navigationLink`内の要素、`maml:relatedLinks`要素。</span><span class="sxs-lookup"><span data-stu-id="2081e-129">To support this feature, the URI must appear in the `maml:uri` element under the first `maml:relatedLinks/maml:navigationLink` element in the `maml:relatedLinks` element.</span></span>

<span data-ttu-id="2081e-130">次の XML は、URI の正しい位置を示しています。</span><span class="sxs-lookup"><span data-stu-id="2081e-130">The following XML shows the correct placement of the URI.</span></span> <span data-ttu-id="2081e-131">"オンライン バージョン:"内のテキスト、`maml:linkText`要素は、ベスト プラクティスが、必須ではありません。</span><span class="sxs-lookup"><span data-stu-id="2081e-131">The "Online version:" text in the `maml:linkText` element is a best practice, but it is not required.</span></span>

```xml

<maml:relatedLinks>
    <maml:navigationLink>
        <maml:linkText>Online version:</maml:linkText>
        <maml:uri>http://go.microsoft.com/fwlink/?LinkID=113279</maml:uri>
    </maml:navigationLink>
    <maml:navigationLink>
        <maml:linkText>about_History</maml:linkText>
        <maml:uri/>
    </maml:navigationLink>
</maml:relatedLinks>
```

## <a name="adding-the-helpuri-property-to-a-command"></a><span data-ttu-id="2081e-132">コマンドへの HelpUri プロパティの追加</span><span class="sxs-lookup"><span data-stu-id="2081e-132">Adding the HelpUri property to a command</span></span>

<span data-ttu-id="2081e-133">このセクションでは、さまざまな種類のコマンドに HelpUri プロパティを追加する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="2081e-133">This section shows how to add the HelpUri property to commands of different types.</span></span>

### <a name="adding-a-helpuri-property-to-a-cmdlet"></a><span data-ttu-id="2081e-134">HelpUri プロパティをコマンドレットに追加します。</span><span class="sxs-lookup"><span data-stu-id="2081e-134">Adding a HelpUri Property to a Cmdlet</span></span>

<span data-ttu-id="2081e-135">記述されたコマンドレットのC#、追加、 **HelpUri**属性をコマンドレット クラス。</span><span class="sxs-lookup"><span data-stu-id="2081e-135">For cmdlets written in C#, add a **HelpUri** attribute to the Cmdlet class.</span></span> <span data-ttu-id="2081e-136">属性の値は、"http"または"https"で始まる URI である必要があります。</span><span class="sxs-lookup"><span data-stu-id="2081e-136">The value of the attribute must be a URI that begins with "http" or "https".</span></span>

<span data-ttu-id="2081e-137">次のコードの HelpUri 属性を示しています、`Get-History`コマンドレット クラス。</span><span class="sxs-lookup"><span data-stu-id="2081e-137">The following code shows the HelpUri attribute of the `Get-History` cmdlet class.</span></span>

```
[Cmdlet(VerbsCommon.Get, "History", HelpUri = "http://go.microsoft.com/fwlink/?LinkID=001122")]
```

### <a name="adding-a-helpuri-property-to-an-advanced-function"></a><span data-ttu-id="2081e-138">高度な関数の HelpUri プロパティの追加</span><span class="sxs-lookup"><span data-stu-id="2081e-138">Adding a HelpUri Property to an Advanced Function</span></span>

<span data-ttu-id="2081e-139">高度な関数は、追加、 **HelpUri**プロパティを**CmdletBinding**属性。</span><span class="sxs-lookup"><span data-stu-id="2081e-139">For advanced functions, add a **HelpUri** property to the **CmdletBinding** attribute.</span></span> <span data-ttu-id="2081e-140">プロパティの値は、"http"または"https"で始まる URI である必要があります。</span><span class="sxs-lookup"><span data-stu-id="2081e-140">The value of the property must be a URI that begins with "http" or "https".</span></span>

<span data-ttu-id="2081e-141">次のコードは、新規カレンダー関数の HelpUri 属性を示しています。</span><span class="sxs-lookup"><span data-stu-id="2081e-141">The following code shows the HelpUri attribute of the New-Calendar function</span></span>

```powershell

function New-Calendar {
    [CmdletBinding(SupportsShouldProcess=$true,
    HelpURI="http://go.microsoft.com/fwlink/?LinkID=01122")]
```

### <a name="adding-a-helpuri-attribute-to-a-cim-command"></a><span data-ttu-id="2081e-142">CIM コマンドに HelpUri 属性を追加します。</span><span class="sxs-lookup"><span data-stu-id="2081e-142">Adding a HelpUri Attribute to a CIM Command</span></span>

<span data-ttu-id="2081e-143">CIM コマンド、追加、 **HelpUri**属性を**CmdletMetadata** CDXML ファイル内の要素。</span><span class="sxs-lookup"><span data-stu-id="2081e-143">For CIM commands, add a **HelpUri** attribute to the **CmdletMetadata** element in the CDXML file.</span></span> <span data-ttu-id="2081e-144">属性の値は、"http"または"https"で始まる URI である必要があります。</span><span class="sxs-lookup"><span data-stu-id="2081e-144">The value of the attribute must be a URI that begins with "http" or "https".</span></span>

<span data-ttu-id="2081e-145">次のコードは、開始デバッグ CIM コマンドの HelpUri 属性を示しています。</span><span class="sxs-lookup"><span data-stu-id="2081e-145">The following code shows the HelpUri attribute of the Start-Debug CIM command</span></span>

```
<CmdletMetadata Verb="Debug" HelpUri="http://go.microsoft.com/fwlink/?LinkID=001122"/>
```

### <a name="adding-a-helpuri-attribute-to-a-workflow"></a><span data-ttu-id="2081e-146">ワークフローに HelpUri 属性を追加します。</span><span class="sxs-lookup"><span data-stu-id="2081e-146">Adding a HelpUri Attribute to a Workflow</span></span>

<span data-ttu-id="2081e-147">Windows PowerShell 言語で記述されたワークフローでは、追加、**します。ExternalHelp**ワークフロー コードにディレクティブをコメントします。</span><span class="sxs-lookup"><span data-stu-id="2081e-147">For workflows that are written in the Windows PowerShell language, add an **.ExternalHelp** comment directive to the workflow code.</span></span> <span data-ttu-id="2081e-148">ディレクティブの値は、"http"または"https"で始まる URI である必要があります。</span><span class="sxs-lookup"><span data-stu-id="2081e-148">The value of the directive must be a URI that begins with "http" or "https".</span></span>

> [!NOTE]
> <span data-ttu-id="2081e-149">Windows PowerShell での XAML ベースのワークフローの HelpUri プロパティはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="2081e-149">The HelpUri property is not supported for XAML-based workflows in Windows PowerShell.</span></span>

<span data-ttu-id="2081e-150">次のコードは、します。ワークフロー ファイルで ExternalHelp ディレクティブです。</span><span class="sxs-lookup"><span data-stu-id="2081e-150">The following code shows the .ExternalHelp directive in a workflow file.</span></span>

```powershell
# .ExternalHelp "http://go.microsoft.com/fwlink/?LinkID=138338"
```