---
title: コマンドレットエラー報告 |Microsoft Docs
ms.date: 09/13/2016
helpviewer_keywords:
- error records [PowerShell], terminating
- non-terminating errors [PowerShell]
- error records [PowerShell]
- terminating errors [PowerShell]
- error records [PowerShell], non-terminating
ms.openlocfilehash: 30b19914253db5f517f5ab76623b54aced0c0598
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784471"
---
# <a name="cmdlet-error-reporting"></a><span data-ttu-id="48579-102">コマンドレットのエラー報告</span><span class="sxs-lookup"><span data-stu-id="48579-102">Cmdlet error reporting</span></span>

<span data-ttu-id="48579-103">コマンドレットでは、エラーがエラーの終了または終了していないエラーであるかどうかに応じて、異なる方法でエラーを報告します。</span><span class="sxs-lookup"><span data-stu-id="48579-103">Cmdlets should report errors differently depending on whether the errors are terminating errors or nonterminating errors.</span></span> <span data-ttu-id="48579-104">終了エラーとは、パイプラインが直ちに終了するエラー、または処理を続行する理由がない場合に発生するエラーです。</span><span class="sxs-lookup"><span data-stu-id="48579-104">Terminating errors are errors that cause the pipeline to be terminated immediately, or errors that occur when there's no reason to continue processing.</span></span> <span data-ttu-id="48579-105">終了しないエラーとは、現在のエラー状態を報告するエラーですが、コマンドレットは入力オブジェクトの処理を続行できます。</span><span class="sxs-lookup"><span data-stu-id="48579-105">Nonterminating errors are those errors that report a current error condition, but the cmdlet can continue to process input objects.</span></span> <span data-ttu-id="48579-106">終了しないエラーが発生した場合、通常、ユーザーには問題が通知されますが、コマンドレットは次の入力オブジェクトの処理を続行します。</span><span class="sxs-lookup"><span data-stu-id="48579-106">With nonterminating errors, the user is typically notified of the problem, but the cmdlet continues to process the next input object.</span></span>

## <a name="terminating-and-nonterminating-errors"></a><span data-ttu-id="48579-107">終了エラーと終了しないエラー</span><span class="sxs-lookup"><span data-stu-id="48579-107">Terminating and nonterminating errors</span></span>

<span data-ttu-id="48579-108">次のガイドラインを使用して、エラー状態が終了エラーまたは終了しないエラーであるかどうかを判断できます。</span><span class="sxs-lookup"><span data-stu-id="48579-108">The following guidelines can be used to determine if an error condition is a terminating error or a nonterminating error.</span></span>

- <span data-ttu-id="48579-109">コマンドレットがそれ以上の入力オブジェクトを正常に処理できないようにするには、エラー条件を使用します。</span><span class="sxs-lookup"><span data-stu-id="48579-109">Does the error condition prevent your cmdlet from successfully processing any further input objects?</span></span> <span data-ttu-id="48579-110">その場合、終了エラーになります。</span><span class="sxs-lookup"><span data-stu-id="48579-110">If so, this is a terminating error.</span></span>

- <span data-ttu-id="48579-111">特定の入力オブジェクトまたは入力オブジェクトのサブセットに関連するエラー条件ですか。</span><span class="sxs-lookup"><span data-stu-id="48579-111">Is the error condition related to a specific input object or a subset of input objects?</span></span> <span data-ttu-id="48579-112">それ以外の場合は、終了しないエラーになります。</span><span class="sxs-lookup"><span data-stu-id="48579-112">If so, this is a nonterminating error.</span></span>

- <span data-ttu-id="48579-113">コマンドレットは、複数の入力オブジェクトを受け入れます。この場合、別の入力オブジェクトで処理が成功する可能性がありますか。</span><span class="sxs-lookup"><span data-stu-id="48579-113">Does the cmdlet accept multiple input objects, such that processing may succeed on another input object?</span></span> <span data-ttu-id="48579-114">それ以外の場合は、終了しないエラーになります。</span><span class="sxs-lookup"><span data-stu-id="48579-114">If so, this is a nonterminating error.</span></span>

- <span data-ttu-id="48579-115">複数の入力オブジェクトを受け入れることができるコマンドレットでは、特定の状況が1つの入力オブジェクトにのみ適用される場合でも、終了エラーと終了しないエラーのどちらを使用するかを決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="48579-115">Cmdlets that can accept multiple input objects should decide between what are terminating and nonterminating errors, even when a particular situation applies to only a single input object.</span></span>

- <span data-ttu-id="48579-116">コマンドレットは、任意の数の入力オブジェクトを受信し、任意の数の成功またはエラーオブジェクトを送信してから、終了例外をスローすることができます。</span><span class="sxs-lookup"><span data-stu-id="48579-116">Cmdlets can receive any number of input objects and send any number of success or error objects before throwing a terminating exception.</span></span> <span data-ttu-id="48579-117">受信した入力オブジェクトの数と、送信された成功したエラーオブジェクトの数の間にはリレーションシップがありません。</span><span class="sxs-lookup"><span data-stu-id="48579-117">There's no relationship between the number of input objects received and the number of success and error objects sent.</span></span>

- <span data-ttu-id="48579-118">0-1 の入力オブジェクトのみを受け入れ、0-1 出力オブジェクトのみを生成できるコマンドレットでは、エラーを終了エラーとして扱い、終了例外を生成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="48579-118">Cmdlets that can accept only 0-1 input objects and generate only 0-1 output objects should treat errors as terminating errors and generate terminating exceptions.</span></span>

## <a name="reporting-nonterminating-errors"></a><span data-ttu-id="48579-119">終了しないエラーの報告</span><span class="sxs-lookup"><span data-stu-id="48579-119">Reporting nonterminating errors</span></span>

<span data-ttu-id="48579-120">終了しないエラーの報告は、常に、コマンドレットによって実行されるようにする必要があり[ます。この](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)メソッドの実装には、または、システムの[管理、.](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) ........................... [...](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) ...</span><span class="sxs-lookup"><span data-stu-id="48579-120">The reporting of a nonterminating error should always be done within the cmdlet's implementation of the [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) method, the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method, or the [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) method.</span></span> <span data-ttu-id="48579-121">この種のエラーは、 [WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)メソッドを呼び出してエラーストリームにエラーレコードを送信することによって報告されます。</span><span class="sxs-lookup"><span data-stu-id="48579-121">These types of errors are reported by calling the [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) method that in turn sends an error record to the error stream.</span></span>

## <a name="reporting-terminating-errors"></a><span data-ttu-id="48579-122">終了エラーの報告</span><span class="sxs-lookup"><span data-stu-id="48579-122">Reporting terminating errors</span></span>

<span data-ttu-id="48579-123">終了エラーは、例外をスローするか、 [ThrowTerminatingError](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError)メソッドを呼び出すことによって報告されます。</span><span class="sxs-lookup"><span data-stu-id="48579-123">Terminating errors are reported by throwing exceptions or by calling the [System.Management.Automation.Cmdlet.ThrowTerminatingError](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError) method.</span></span> <span data-ttu-id="48579-124">コマンドレットでは、 **OutOfMemory**などの例外をキャッチして再スローすることもできますが、PowerShell ランタイムでも例外がキャッチされるため、例外を再スローする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="48579-124">Be aware that cmdlets can also catch and rethrow exceptions such as **OutOfMemory**, however, they aren't required to rethrow exceptions as the PowerShell runtime will catch them as well.</span></span>

<span data-ttu-id="48579-125">また、状況に固有の問題に対して独自の例外を定義したり、エラーレコードを使用して既存の例外に追加情報を追加したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="48579-125">You can also define your own exceptions for issues specific to your situation, or add additional information to an existing exception using its error record.</span></span>

## <a name="error-records"></a><span data-ttu-id="48579-126">エラーレコード</span><span class="sxs-lookup"><span data-stu-id="48579-126">Error records</span></span>

<span data-ttu-id="48579-127">PowerShell では、[システム管理](/dotnet/api/System.Management.Automation.ErrorRecord)オブジェクトを使用した終了しないエラー状態について説明します。</span><span class="sxs-lookup"><span data-stu-id="48579-127">PowerShell describes a nonterminating error condition with [System.Management.Automation.ErrorRecord](/dotnet/api/System.Management.Automation.ErrorRecord) objects.</span></span> <span data-ttu-id="48579-128">各オブジェクトは、エラーカテゴリ情報、オプションのターゲットオブジェクト、およびエラー状態に関する詳細を提供します。</span><span class="sxs-lookup"><span data-stu-id="48579-128">Each object provides error category information, an optional target object, and details about the error condition.</span></span>

### <a name="error-identifiers"></a><span data-ttu-id="48579-129">エラー識別子</span><span class="sxs-lookup"><span data-stu-id="48579-129">Error identifiers</span></span>

<span data-ttu-id="48579-130">エラー識別子は、コマンドレット内のエラー状態を識別する単純な文字列です。</span><span class="sxs-lookup"><span data-stu-id="48579-130">The error identifier is a simple string that identifies the error condition within the cmdlet.</span></span>
<span data-ttu-id="48579-131">PowerShell では、この識別子をコマンドレット識別子と組み合わせて、エラーストリームのフィルター処理やエラーのログ記録時、特定のエラーへの応答時、またはユーザー固有のその他の操作を行うときに、後で使用できる完全修飾エラー識別子を作成します。</span><span class="sxs-lookup"><span data-stu-id="48579-131">PowerShell combines this identifier with a cmdlet identifier to create a fully qualified error identifier that can be used later when filtering error streams or logging errors, when responding to specific errors, or with other user-specific activities.</span></span>

<span data-ttu-id="48579-132">エラー識別子を指定するときは、次のガイドラインに従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="48579-132">The following guidelines should be followed when specifying error identifiers:</span></span>

- <span data-ttu-id="48579-133">さまざまな固有のエラー識別子を異なるコードパスに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="48579-133">Assign different, highly specific, error identifiers to different code paths.</span></span> <span data-ttu-id="48579-134">[WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)または[ThrowTerminatingError](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError)を呼び出す各コードパスには、独自のエラー識別子を指定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="48579-134">Each code path that calls [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) or [System.Management.Automation.Cmdlet.ThrowTerminatingError](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError) should have its own error identifier.</span></span>

- <span data-ttu-id="48579-135">エラー識別子は、終了エラーと終了エラーの両方の共通言語ランタイム (CLR) 例外型に対して一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="48579-135">Error identifiers should be unique to Common Language Runtime (CLR) exception types for both terminating and nonterminating errors.</span></span>

- <span data-ttu-id="48579-136">コマンドレットまたは PowerShell プロバイダーのバージョン間でエラー識別子のセマンティクスを変更しないでください。</span><span class="sxs-lookup"><span data-stu-id="48579-136">Don't change the semantics of an error identifier between versions of your cmdlet or PowerShell provider.</span></span> <span data-ttu-id="48579-137">エラー id のセマンティクスが確立された後は、コマンドレットのライフサイクル全体にわたって一定の状態を維持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="48579-137">After the semantics of an error identifier is established, it should remain constant throughout the lifecycle of your cmdlet.</span></span>

- <span data-ttu-id="48579-138">終了エラーの場合は、特定の CLR 例外の種類に対して一意のエラー識別子を使用します。</span><span class="sxs-lookup"><span data-stu-id="48579-138">For terminating errors, use a unique error identifier for a particular CLR exception type.</span></span> <span data-ttu-id="48579-139">例外の種類が変更された場合は、新しいエラー識別子を使用します。</span><span class="sxs-lookup"><span data-stu-id="48579-139">If the exception type changes, use a new error identifier.</span></span>

- <span data-ttu-id="48579-140">終了しないエラーの場合は、特定の入力オブジェクトに対して特定のエラー識別子を使用します。</span><span class="sxs-lookup"><span data-stu-id="48579-140">For nonterminating errors, use a specific error identifier for a specific input object.</span></span>

- <span data-ttu-id="48579-141">Tersely が報告されているエラーに対応する識別子のテキストを選択します。</span><span class="sxs-lookup"><span data-stu-id="48579-141">Choose text for the identifier that tersely corresponds to the error being reported.</span></span> <span data-ttu-id="48579-142">空白や句読点は使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="48579-142">Don't use white space or punctuation.</span></span>

- <span data-ttu-id="48579-143">再現できないエラー識別子は生成しません。</span><span class="sxs-lookup"><span data-stu-id="48579-143">Don't generate error identifiers that aren't reproducible.</span></span> <span data-ttu-id="48579-144">たとえば、プロセス識別子を含む識別子は生成しません。</span><span class="sxs-lookup"><span data-stu-id="48579-144">For example, don't generate identifiers that include a process identifier.</span></span> <span data-ttu-id="48579-145">エラー識別子は、同じ問題が発生している他のユーザーによって検出された識別子に対応している場合にのみ役立ちます。</span><span class="sxs-lookup"><span data-stu-id="48579-145">Error identifiers are useful only when they correspond to identifiers that are seen by other users who are experiencing the same problem.</span></span>

### <a name="error-categories"></a><span data-ttu-id="48579-146">エラーカテゴリ</span><span class="sxs-lookup"><span data-stu-id="48579-146">Error categories</span></span>

<span data-ttu-id="48579-147">エラーカテゴリは、ユーザーのエラーをグループ化するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="48579-147">Error categories are used to group errors for the user.</span></span> <span data-ttu-id="48579-148">PowerShell では、これらのカテゴリとコマンドレットを定義します。 PowerShell プロバイダーは、エラーレコードを生成するときにこれらのカテゴリを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="48579-148">PowerShell defines these categories and cmdlets and PowerShell providers must choose between them when generating the error record.</span></span>

<span data-ttu-id="48579-149">使用可能なエラーカテゴリの説明については、 [ErrorCategory](/dotnet/api/System.Management.Automation.ErrorCategory)列挙体を参照してください。</span><span class="sxs-lookup"><span data-stu-id="48579-149">For a description of the error categories that are available, see the [System.Management.Automation.ErrorCategory](/dotnet/api/System.Management.Automation.ErrorCategory) enumeration.</span></span> <span data-ttu-id="48579-150">一般に、可能な限り**Noerror**、 **Undefinederror**、 **genericerror**の使用は避けてください。</span><span class="sxs-lookup"><span data-stu-id="48579-150">In general, you should avoid using **NoError**, **UndefinedError**, and **GenericError** whenever possible.</span></span>

<span data-ttu-id="48579-151">ユーザーは、カテゴリビューに設定されたときに、カテゴリに基づいてエラーを表示でき `$ErrorView` ます。 **CategoryView**</span><span class="sxs-lookup"><span data-stu-id="48579-151">Users can view errors based on category when they set `$ErrorView` to **CategoryView**.</span></span>

## <a name="see-also"></a><span data-ttu-id="48579-152">関連項目</span><span class="sxs-lookup"><span data-stu-id="48579-152">See also</span></span>

[<span data-ttu-id="48579-153">コマンドレットの概要</span><span class="sxs-lookup"><span data-stu-id="48579-153">Cmdlet Overview</span></span>](./cmdlet-overview.md)

[<span data-ttu-id="48579-154">コマンドレット出力の種類</span><span class="sxs-lookup"><span data-stu-id="48579-154">Types of Cmdlet Output</span></span>](./types-of-cmdlet-output.md)

[<span data-ttu-id="48579-155">Windows PowerShell リファレンス</span><span class="sxs-lookup"><span data-stu-id="48579-155">Windows PowerShell Reference</span></span>](../windows-powershell-reference.md)
