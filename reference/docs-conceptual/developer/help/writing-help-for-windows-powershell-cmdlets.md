---
title: PowerShell コマンドレットのヘルプの作成
ms.date: 09/13/2016
ms.openlocfilehash: 4e1070e90cf3ed83c1d97a3b620e00f65d09989e
ms.sourcegitcommit: de59ff77c6535fc772c1e327b3c823295eaed6ea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/22/2020
ms.locfileid: "86893086"
---
# <a name="writing-help-for-powershell-cmdlets"></a><span data-ttu-id="8e4a9-102">PowerShell コマンドレットのヘルプの作成</span><span class="sxs-lookup"><span data-stu-id="8e4a9-102">Writing Help for PowerShell Cmdlets</span></span>

<span data-ttu-id="8e4a9-103">PowerShell コマンドレットは役に立ちますが、コマンドレットの動作と使用方法をヘルプトピックで明確に説明していない限り、コマンドレットが使用されないか、またはユーザーに不満が生じる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8e4a9-103">PowerShell cmdlets can be useful, but unless your Help topics clearly explain what the cmdlet does and how to use it, the cmdlet may not get used or, even worse, it might frustrate users.</span></span> <span data-ttu-id="8e4a9-104">XML ベースのコマンドレットヘルプファイル形式では一貫性が向上しますが、優れたヘルプではさらに多くのことが必要になります。</span><span class="sxs-lookup"><span data-stu-id="8e4a9-104">The XML-based cmdlet Help file format enhances consistency, but great help requires much more.</span></span>

<span data-ttu-id="8e4a9-105">コマンドレットのヘルプを記述したことがない場合は、次のガイドラインを確認してください。</span><span class="sxs-lookup"><span data-stu-id="8e4a9-105">If you have never written cmdlet Help, review the following guidelines.</span></span> <span data-ttu-id="8e4a9-106">コマンドレットのヘルプトピックを作成するために必要な XML スキーマについては、次のセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="8e4a9-106">The XML schema required to author the cmdlet Help topic is described in the following section.</span></span> <span data-ttu-id="8e4a9-107">まず[、コマンドレットのヘルプファイルを作成](./how-to-create-the-cmdlet-help-file.md)します。</span><span class="sxs-lookup"><span data-stu-id="8e4a9-107">Start with [Creating the Cmdlet Help File](./how-to-create-the-cmdlet-help-file.md).</span></span> <span data-ttu-id="8e4a9-108">このトピックには、最上位レベルの XML ノードの説明が含まれています。</span><span class="sxs-lookup"><span data-stu-id="8e4a9-108">That topic includes a description of the top-level XML nodes.</span></span>

## <a name="writing-guidelines-for-cmdlet-help"></a><span data-ttu-id="8e4a9-109">コマンドレットヘルプの記述に関するガイドライン</span><span class="sxs-lookup"><span data-stu-id="8e4a9-109">Writing Guidelines for Cmdlet Help</span></span>

### <a name="write-well"></a><span data-ttu-id="8e4a9-110">適切な書き込み</span><span class="sxs-lookup"><span data-stu-id="8e4a9-110">Write well</span></span>

<span data-ttu-id="8e4a9-111">適切に記述されたトピックに代わるものはありません。</span><span class="sxs-lookup"><span data-stu-id="8e4a9-111">Nothing replaces a well-written topic.</span></span> <span data-ttu-id="8e4a9-112">プロの執筆者でない場合は、参考になるライターまたはエディターを見つけてください。</span><span class="sxs-lookup"><span data-stu-id="8e4a9-112">If you are not a professional writer, find a writer or editor to help you.</span></span> <span data-ttu-id="8e4a9-113">別の方法としては、Microsoft Word にヘルプテキストをコピーし、文法とスペルチェックを使用して作業を改善する方法があります。</span><span class="sxs-lookup"><span data-stu-id="8e4a9-113">Another alternative is to copy your Help text into Microsoft Word and use the grammar and spelling checks to improve your work.</span></span>

### <a name="write-simply"></a><span data-ttu-id="8e4a9-114">書き込みのみ</span><span class="sxs-lookup"><span data-stu-id="8e4a9-114">Write simply</span></span>

<span data-ttu-id="8e4a9-115">単純な語句と語句を使用します。</span><span class="sxs-lookup"><span data-stu-id="8e4a9-115">Use simple words and phrases.</span></span> <span data-ttu-id="8e4a9-116">専門的な用語を使わない。</span><span class="sxs-lookup"><span data-stu-id="8e4a9-116">Avoid jargon.</span></span> <span data-ttu-id="8e4a9-117">多くの読者が、外部言語の辞書とヘルプトピックのみを装備していることを考慮してください。</span><span class="sxs-lookup"><span data-stu-id="8e4a9-117">Consider that many readers are equipped only with a foreign-language dictionary and your Help topic.</span></span>

### <a name="write-consistently"></a><span data-ttu-id="8e4a9-118">一貫した書き込み</span><span class="sxs-lookup"><span data-stu-id="8e4a9-118">Write consistently</span></span>

<span data-ttu-id="8e4a9-119">関連するコマンドレットのヘルプが似ている必要があります (例: get-x と set-x)。</span><span class="sxs-lookup"><span data-stu-id="8e4a9-119">Help for related cmdlets should be similar (for example, get-x and set-x).</span></span> <span data-ttu-id="8e4a9-120">標準パラメーターの標準の説明 ( **Force** 、 **InputObject**など) を使用します。</span><span class="sxs-lookup"><span data-stu-id="8e4a9-120">Use the standard descriptions for standard parameters, like **Force** and **InputObject**.</span></span> <span data-ttu-id="8e4a9-121">(コアコマンドレットのヘルプからコピーします)。標準の使用条件を使用します。</span><span class="sxs-lookup"><span data-stu-id="8e4a9-121">(Copy them from Help for the core cmdlets.) Use standard terms.</span></span> <span data-ttu-id="8e4a9-122">たとえば、"argument" ではなく "parameter" を使用し、"command" または "command-let" ではなく "コマンドレット" を使用します。</span><span class="sxs-lookup"><span data-stu-id="8e4a9-122">For example, use "parameter", not "argument", and use "cmdlet" not "command" or "command-let."</span></span>

### <a name="start-the-synopsis-with-a-verb"></a><span data-ttu-id="8e4a9-123">動詞を使用して、概要を開始します。</span><span class="sxs-lookup"><span data-stu-id="8e4a9-123">Start the synopsis with a verb</span></span>

<span data-ttu-id="8e4a9-124">[概要] フィールドは、コマンドレットがどのように実行されているか、またどのように動作するかをユーザーに通知します。</span><span class="sxs-lookup"><span data-stu-id="8e4a9-124">The synopsis field informs the user what the cmdlet does, not what it is or how it works.</span></span> <span data-ttu-id="8e4a9-125">動詞このコマンドレットが要件を満たしているかどうかをユーザーに通知するタスクベースのステートメントを作成します。</span><span class="sxs-lookup"><span data-stu-id="8e4a9-125">Verbs create a task-based statement that informs users if this cmdlet meets their requirements.</span></span> <span data-ttu-id="8e4a9-126">"Get"、"create"、"change" などの単純な動詞を使用します。</span><span class="sxs-lookup"><span data-stu-id="8e4a9-126">Use simple verbs like "get", "create", and "change."</span></span> <span data-ttu-id="8e4a9-127">"Set" は避けてください。 "modify" のように、あいまいで凝った言葉にすることができます。</span><span class="sxs-lookup"><span data-stu-id="8e4a9-127">Avoid "set", which can be vague and fancy words like "modify".</span></span>

### <a name="focus-on-objects"></a><span data-ttu-id="8e4a9-128">オブジェクトにフォーカスする</span><span class="sxs-lookup"><span data-stu-id="8e4a9-128">Focus on objects</span></span>

<span data-ttu-id="8e4a9-129">ほとんどの "get" コマンドレットは何かを表示しますが、その主な機能はオブジェクトを取得することです。</span><span class="sxs-lookup"><span data-stu-id="8e4a9-129">Most "get" cmdlets display something, but their primary function is to get an object.</span></span> <span data-ttu-id="8e4a9-130">ヘルプでは、オブジェクトに焦点を当てることによって、既定の表示が多くなることをユーザーが理解できるようにし、さまざまな方法で取得したオブジェクトのメソッドとプロパティを使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="8e4a9-130">In your Help, focus on the object, so that users understand that the default display is one of many, and that they can use the methods and properties of the object that you retrieved for them in different ways.</span></span>

### <a name="write-detailed-descriptions"></a><span data-ttu-id="8e4a9-131">詳細な説明の書き込み</span><span class="sxs-lookup"><span data-stu-id="8e4a9-131">Write detailed descriptions</span></span>

<span data-ttu-id="8e4a9-132">コマンドレットが実行できるすべての詳細な説明を簡単に示します。</span><span class="sxs-lookup"><span data-stu-id="8e4a9-132">Briefly list everything that the cmdlet can do in the detailed description.</span></span> <span data-ttu-id="8e4a9-133">Main 関数が1つのプロパティを変更する場合でも、コマンドレットですべてのプロパティを変更できる場合は、詳細な説明でこれを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="8e4a9-133">If the main function is to change one property, but the cmdlet can change all properties, list this in the detailed description.</span></span>

### <a name="use-conventional-syntax"></a><span data-ttu-id="8e4a9-134">従来の構文を使用する</span><span class="sxs-lookup"><span data-stu-id="8e4a9-134">Use conventional syntax</span></span>

<span data-ttu-id="8e4a9-135">標準のバッカスナウア記法-Backus-naur 形式を使用します。これは、Windows および UNIX のコマンドラインヘルプでよく使用されます。</span><span class="sxs-lookup"><span data-stu-id="8e4a9-135">Use the standard Backus-Naur format which is common for Windows and UNIX command-line Help.</span></span>

### <a name="use-microsoft-net-types-for-parameter-values"></a><span data-ttu-id="8e4a9-136">パラメーター値に Microsoft .NET の型を使用する</span><span class="sxs-lookup"><span data-stu-id="8e4a9-136">Use Microsoft .NET types for parameter values</span></span>

<span data-ttu-id="8e4a9-137">パラメーター値のプレースホルダー (構文とパラメーターの説明) には、パラメーターが受け入れるオブジェクトの .NET Framework 型が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8e4a9-137">The placeholders for parameter values (in the syntax and parameter descriptions) show the .NET Framework types of the objects that the parameter will accept.</span></span> <span data-ttu-id="8e4a9-138">PowerShell チームは、.NET Framework についてユーザーに教えるために、この規則を開発しました。</span><span class="sxs-lookup"><span data-stu-id="8e4a9-138">The PowerShell team developed this convention to help teach users about the .NET Framework.</span></span>

### <a name="write-complete-parameter-descriptions"></a><span data-ttu-id="8e4a9-139">完全なパラメーターの説明の書き込み</span><span class="sxs-lookup"><span data-stu-id="8e4a9-139">Write complete parameter descriptions</span></span>

<span data-ttu-id="8e4a9-140">パラメーターの説明は、パラメーターの動作 (その効果) と、パラメーター値に対して入力する必要があることをユーザーに通知する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8e4a9-140">Parameter descriptions must inform users of two things: what the parameter does (its effect) and what they must type for the parameter values.</span></span>

### <a name="write-practical-examples"></a><span data-ttu-id="8e4a9-141">実用的な例を書く</span><span class="sxs-lookup"><span data-stu-id="8e4a9-141">Write practical examples</span></span>

<span data-ttu-id="8e4a9-142">この例では、すべてのパラメーターを使用する方法を示していますが、最も重要なのは、実際のタスクでコマンドレットを使用する方法を示すことです。</span><span class="sxs-lookup"><span data-stu-id="8e4a9-142">The examples should show how to use all of the parameters, but the most important thing is to show how to use the cmdlet in real-world tasks.</span></span> <span data-ttu-id="8e4a9-143">単純な例から始めて、徐々に複雑な例を記述します。</span><span class="sxs-lookup"><span data-stu-id="8e4a9-143">Start with a simple example and write increasingly complex examples.</span></span> <span data-ttu-id="8e4a9-144">最後の例では、パイプラインでコマンドレットを使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="8e4a9-144">In the final example, show how to use the cmdlet in a pipeline.</span></span>

### <a name="use-the-notes-field"></a><span data-ttu-id="8e4a9-145">[メモ] フィールドの使用</span><span class="sxs-lookup"><span data-stu-id="8e4a9-145">Use the Notes field</span></span>

<span data-ttu-id="8e4a9-146">[メモ] フィールドは、ユーザーがコマンドレットを理解するために必要な概念を説明するために使用します。</span><span class="sxs-lookup"><span data-stu-id="8e4a9-146">Use the Notes field to explain concepts that users need to understand the cmdlet.</span></span> <span data-ttu-id="8e4a9-147">また、ユーザーが一般的なエラーを回避できるように、メモを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="8e4a9-147">You can also use notes to help users avoid common errors.</span></span> <span data-ttu-id="8e4a9-148">Url の変更は避けてください。</span><span class="sxs-lookup"><span data-stu-id="8e4a9-148">Avoid URLs as they change.</span></span> <span data-ttu-id="8e4a9-149">代わりに、検索するユーザーの条件を指定します。</span><span class="sxs-lookup"><span data-stu-id="8e4a9-149">Instead, provide users terms to search for.</span></span>

### <a name="test-your-help"></a><span data-ttu-id="8e4a9-150">ヘルプをテストする</span><span class="sxs-lookup"><span data-stu-id="8e4a9-150">Test your Help</span></span>

<span data-ttu-id="8e4a9-151">コードをテストするのと同じようにヘルプをテストします。</span><span class="sxs-lookup"><span data-stu-id="8e4a9-151">Test the Help just like you test your code.</span></span> <span data-ttu-id="8e4a9-152">友人や同僚がヘルプコンテンツを読んで、フィードバックを提供します。</span><span class="sxs-lookup"><span data-stu-id="8e4a9-152">Have friends and colleagues read your Help content and provide feedback.</span></span> <span data-ttu-id="8e4a9-153">また、ニュースグループからフィードバックを送信することもできます。</span><span class="sxs-lookup"><span data-stu-id="8e4a9-153">You can also solicit feedback from newsgroups.</span></span>

## <a name="see-also"></a><span data-ttu-id="8e4a9-154">参照</span><span class="sxs-lookup"><span data-stu-id="8e4a9-154">See Also</span></span>

 [<span data-ttu-id="8e4a9-155">コマンドレットのヘルプ ファイルを作成する方法</span><span class="sxs-lookup"><span data-stu-id="8e4a9-155">How to Create the Cmdlet Help File</span></span>](./how-to-create-the-cmdlet-help-file.md)

 [<span data-ttu-id="8e4a9-156">コマンドレットのヘルプ トピックにコマンドレットの名前と概要を追加する方法</span><span class="sxs-lookup"><span data-stu-id="8e4a9-156">How to Add the Cmdlet Name and Synopsis to a Cmdlet Help Topic</span></span>](./how-to-add-the-cmdlet-name-and-synopsis-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="8e4a9-157">詳細な説明をコマンドレットヘルプトピックに追加する方法</span><span class="sxs-lookup"><span data-stu-id="8e4a9-157">How to Add the Detailed Description to a Cmdlet Help Topic</span></span>](./how-to-add-a-cmdlet-description.md)

 [<span data-ttu-id="8e4a9-158">コマンドレットのヘルプ トピックに構文を追加する方法</span><span class="sxs-lookup"><span data-stu-id="8e4a9-158">How to Add Syntax to a Cmdlet Help Topic</span></span>](./how-to-add-syntax-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="8e4a9-159">コマンドレットにパラメーターを追加する方法に関するヘルプトピック</span><span class="sxs-lookup"><span data-stu-id="8e4a9-159">How to Add Parameters to a Cmdlet Help Topic</span></span>](./how-to-add-parameter-information.md)

 [<span data-ttu-id="8e4a9-160">コマンドレットのヘルプトピックに入力の種類を追加する方法</span><span class="sxs-lookup"><span data-stu-id="8e4a9-160">How to add Input Types to a Cmdlet Help Topic</span></span>](./how-to-add-input-types-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="8e4a9-161">コマンドレットのヘルプ トピックに戻り値を追加する方法</span><span class="sxs-lookup"><span data-stu-id="8e4a9-161">How to Add Return Values to a Cmdlet Help Topic</span></span>](./how-to-add-return-values-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="8e4a9-162">コマンドレットのヘルプ トピックに注を追加する方法</span><span class="sxs-lookup"><span data-stu-id="8e4a9-162">How to Add Notes to a Cmdlet Help Topic</span></span>](./how-to-add-notes-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="8e4a9-163">コマンドレットのヘルプ トピックに例を追加する方法</span><span class="sxs-lookup"><span data-stu-id="8e4a9-163">How to Add Examples to a Cmdlet Help Topic</span></span>](./how-to-add-examples-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="8e4a9-164">コマンドレットのヘルプ トピックに関連リンクを追加する方法</span><span class="sxs-lookup"><span data-stu-id="8e4a9-164">How to Add Related Links to a Cmdlet Help Topic</span></span>](./how-to-add-related-links-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="8e4a9-165">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="8e4a9-165">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
