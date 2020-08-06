---
title: コマンドレットコードの例 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 2d2597d3d3f64cae1c1494eb2f05873f6feae5e0
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784335"
---
# <a name="examples-of-cmdlet-code"></a><span data-ttu-id="2197f-102">コマンドレット コードの例</span><span class="sxs-lookup"><span data-stu-id="2197f-102">Examples of Cmdlet Code</span></span>

<span data-ttu-id="2197f-103">このセクションには、独自のコマンドレットの記述を開始するために使用できるコマンドレットコードの例が含まれています。</span><span class="sxs-lookup"><span data-stu-id="2197f-103">This section contains examples of cmdlet code that you can use to start writing your own cmdlets.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2197f-104">コマンドレットを記述するための詳細な手順については、[コマンドレットの作成に関するチュートリアル](./tutorials-for-writing-cmdlets.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2197f-104">If you want step-by-step instructions for writing cmdlets, see [Tutorials for Writing Cmdlets](./tutorials-for-writing-cmdlets.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="2197f-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="2197f-105">In This Section</span></span>

<span data-ttu-id="2197f-106">[方法: 簡単なコマンドレットを記述する](./how-to-write-a-simple-cmdlet.md)この例は、コマンドレットコードの基本的な構造を示しています。</span><span class="sxs-lookup"><span data-stu-id="2197f-106">[How to Write a Simple Cmdlet](./how-to-write-a-simple-cmdlet.md) This example shows the basic structure of cmdlet code.</span></span>

<span data-ttu-id="2197f-107">[コマンドレットのパラメーターを宣言する方法](./how-to-declare-cmdlet-parameters.md)この例では、さまざまな種類のパラメーターを宣言する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="2197f-107">[How to Declare Cmdlet Parameters](./how-to-declare-cmdlet-parameters.md) This example shows how to declare the different types of parameters.</span></span>

<span data-ttu-id="2197f-108">[パラメーターセットを宣言する方法](./how-to-declare-parameter-sets.md)この例では、コマンドレットで実行されるアクションを変更できるパラメーターのセットを宣言する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="2197f-108">[How to Declare Parameter Sets](./how-to-declare-parameter-sets.md) This example shows how to declare sets of parameters that can change the action a cmdlet performs.</span></span>

<span data-ttu-id="2197f-109">[パラメーター入力を検証する方法](./how-to-validate-parameter-input.md)これらの例では、パラメーター入力を検証する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="2197f-109">[How to Validate Parameter Input](./how-to-validate-parameter-input.md) These examples show how to validate parameter input.</span></span>

<span data-ttu-id="2197f-110">[動的パラメーターを宣言する方法](./how-to-declare-dynamic-parameters.md)この例では、実行時に追加されるパラメーターを宣言する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="2197f-110">[How to Declare Dynamic Parameters](./how-to-declare-dynamic-parameters.md) This example shows how to declare a parameter that is added at runtime.</span></span>

<span data-ttu-id="2197f-111">[コマンドレット内でスクリプトを呼び出す方法](./how-to-invoke-scripts-within-a-cmdlet.md)この例は、コマンドレットに指定されたスクリプトを呼び出す方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="2197f-111">[How to Invoke Scripts Within a Cmdlet](./how-to-invoke-scripts-within-a-cmdlet.md) This example shows how to invoke a script that is supplied to a cmdlet.</span></span>

<span data-ttu-id="2197f-112">[入力処理メソッドをオーバーライドする方法](./how-to-override-input-processing-methods.md)これらの例は、BeginProcessing メソッド、ProcessRecord メソッド、および EndProcessing メソッドをオーバーライドするために使用される基本構造を示しています。</span><span class="sxs-lookup"><span data-stu-id="2197f-112">[How To Override Input Processing Methods](./how-to-override-input-processing-methods.md) These examples show the basic structure used to override the BeginProcessing, ProcessRecord, and EndProcessing methods.</span></span>

<span data-ttu-id="2197f-113">[呼び出しの処理をサポートする方法](./how-to-request-confirmations.md)この例では、コマンドレット内から、[システムの管理](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)、............................... コマンド[レットを呼び出す](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)方法を示します。</span><span class="sxs-lookup"><span data-stu-id="2197f-113">[How to Support ShouldProcess Calls](./how-to-request-confirmations.md) This example shows how the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) and [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) methods should be called from within a cmdlet.</span></span>

<span data-ttu-id="2197f-114">[トランザクションをサポートする方法](./how-to-support-transactions.md)この例では、コマンドレットがトランザクションをサポートしていることを示し、コマンドレットがトランザクション内で使用されている場合に実行されるアクションを実装する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="2197f-114">[How to Support Transactions](./how-to-support-transactions.md) This example shows how to indicate that the cmdlet supports transactions and how to implement the action that is taken when the cmdlet is used within a transaction.</span></span>

<span data-ttu-id="2197f-115">[ジョブをサポートする方法](./how-to-support-jobs.md)この例では、コマンドレットを記述するときにジョブをサポートする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="2197f-115">[How to Support Jobs](./how-to-support-jobs.md) This example shows how to support jobs when you write cmdlets.</span></span>

<span data-ttu-id="2197f-116">[コマンドレット内からコマンドレットを呼び出す方法](./how-to-invoke-a-cmdlet-from-within-a-cmdlet.md)この例では、別のコマンドレット内からコマンドレットを呼び出す方法を示します。このコマンドレットを使用すると、開発中のコマンドレットに、呼び出されたコマンドレットの機能を追加できます。</span><span class="sxs-lookup"><span data-stu-id="2197f-116">[How to Invoke a Cmdlet From Within a Cmdlet](./how-to-invoke-a-cmdlet-from-within-a-cmdlet.md) This example shows how to invoke a cmdlet from within another cmdlet, which allows you to add the functionality of the invoked cmdlet to the cmdlet you are developing.</span></span>

## <a name="see-also"></a><span data-ttu-id="2197f-117">参照</span><span class="sxs-lookup"><span data-stu-id="2197f-117">See Also</span></span>

[<span data-ttu-id="2197f-118">Writing a Windows PowerShell Cmdlet (Windows PowerShell コマンドレットの記述)</span><span class="sxs-lookup"><span data-stu-id="2197f-118">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
