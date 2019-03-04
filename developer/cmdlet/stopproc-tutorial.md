---
title: StopProc チュートリアル |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a142aeb6-9c11-44a0-b34f-1f9470fa347b
caps.latest.revision: 5
ms.openlocfilehash: 6e1c8a4709988adfa59bda14eb3af52b0a79f1df
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56856358"
---
# <a name="stopproc-tutorial"></a><span data-ttu-id="1bc80-102">StopProc チュートリアル</span><span class="sxs-lookup"><span data-stu-id="1bc80-102">StopProc Tutorial</span></span>

<span data-ttu-id="1bc80-103">このセクションによく似ていますが、停止 Proc コマンドレットを作成するためのチュートリアルを提供する、 [Stop-process](/powershell/module/Microsoft.PowerShell.Management/Stop-Process)コマンドレットの Windows PowerShell によって提供されます。</span><span class="sxs-lookup"><span data-stu-id="1bc80-103">This section provides a tutorial for creating the Stop-Proc cmdlet, which is very similar to the [Stop-Process](/powershell/module/Microsoft.PowerShell.Management/Stop-Process) cmdlet provided by Windows PowerShell.</span></span> <span data-ttu-id="1bc80-104">このチュートリアルでは、コマンドレットの実装方法を示すコードのフラグメントとコードの説明を提供します。</span><span class="sxs-lookup"><span data-stu-id="1bc80-104">This tutorial provides fragments of code that illustrate how cmdlets are implemented, and an explanation of the code.</span></span>
<span data-ttu-id="1bc80-105">このセクションによく似ていますが、停止 Proc コマンドレットを作成するためのチュートリアルを提供する、 [Stop-process](/powershell/module/Microsoft.PowerShell.Management/Stop-Process)コマンドレットの Windows PowerShell によって提供されます。</span><span class="sxs-lookup"><span data-stu-id="1bc80-105">This section provides a tutorial for creating the Stop-Proc cmdlet, which is very similar to the [Stop-Process](/powershell/module/Microsoft.PowerShell.Management/Stop-Process) cmdlet provided by Windows PowerShell.</span></span> <span data-ttu-id="1bc80-106">このチュートリアルでは、コマンドレットの実装方法を示すコードのフラグメントとコードの説明を提供します。</span><span class="sxs-lookup"><span data-stu-id="1bc80-106">This tutorial provides fragments of code that illustrate how cmdlets are implemented, and an explanation of the code.</span></span>

## <a name="topics-in-this-tutorial"></a><span data-ttu-id="1bc80-107">このチュートリアルのトピック</span><span class="sxs-lookup"><span data-stu-id="1bc80-107">Topics in this Tutorial</span></span>

<span data-ttu-id="1bc80-108">このチュートリアルのトピックは、前のトピックで説明した内容に基づき、各トピックで、順番に読み取ることが設計されています。</span><span class="sxs-lookup"><span data-stu-id="1bc80-108">The topics in this tutorial are designed to be read sequentially, with each topic building on what was discussed in the previous topic.</span></span>

<span data-ttu-id="1bc80-109">[システムを変更するコマンドレットを作成する](./creating-a-cmdlet-that-modifies-the-system.md)コンピューターで実行されているプロセスを停止するなど、システムの変更をサポートするコマンドレットを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1bc80-109">[Creating a Cmdlet that Modifies the System](./creating-a-cmdlet-that-modifies-the-system.md) This section describes how to create a cmdlet that supports system modifications, such as stopping a process running on the computer.</span></span>

<span data-ttu-id="1bc80-110">[ユーザー メッセージのコマンドレットに追加](./adding-user-messages-to-your-cmdlet.md)コマンドレットに、ユーザー メッセージ、デバッグ メッセージ、警告メッセージ、および進行状況に関する情報を記述する機能を追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1bc80-110">[Adding User Messages to Your Cmdlet](./adding-user-messages-to-your-cmdlet.md) This section describes how to add the ability to write user messages, debug messages, warning messages, and progress information to your cmdlet.</span></span>

<span data-ttu-id="1bc80-111">[ワイルドカードの展開のエイリアスを追加し、コマンドレット パラメーター](./adding-aliases-wildcard-expansion-and-help-to-cmdlet-parameters.md)パラメーターのエイリアス、ヘルプ、およびワイルドカードの展開をサポートするコマンドレットを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1bc80-111">[Adding Aliases, Wildcard Expansion, and Help to Cmdlet Parameters](./adding-aliases-wildcard-expansion-and-help-to-cmdlet-parameters.md) This section describes how to create a cmdlet that supports parameter aliases, Help, and wildcard expansion.</span></span>

<span data-ttu-id="1bc80-112">[コマンドレットにパラメーターの設定を追加する](./adding-parameter-sets-to-a-cmdlet.md)コマンドレットにパラメーターの設定を追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1bc80-112">[Adding Parameter Sets to Cmdlets](./adding-parameter-sets-to-a-cmdlet.md) This section describes how to add parameter sets to a cmdlet.</span></span> <span data-ttu-id="1bc80-113">パラメーター セットは、に応じて異なるパラメーターがユーザーによって指定された動作するコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="1bc80-113">Parameter sets allow the cmdlet to operate differently based on what parameters are specified by the user.</span></span>

## <a name="see-also"></a><span data-ttu-id="1bc80-114">参照</span><span class="sxs-lookup"><span data-stu-id="1bc80-114">See Also</span></span>

[<span data-ttu-id="1bc80-115">システムを変更するコマンドレットを作成します。</span><span class="sxs-lookup"><span data-stu-id="1bc80-115">Creating a Cmdlet that Modifies the System</span></span>](./creating-a-cmdlet-that-modifies-the-system.md)

[<span data-ttu-id="1bc80-116">ユーザー メッセージをコマンドレットに追加します。</span><span class="sxs-lookup"><span data-stu-id="1bc80-116">Adding User Messages to Your Cmdlet</span></span>](./adding-user-messages-to-your-cmdlet.md)

[<span data-ttu-id="1bc80-117">ワイルドカードの展開のエイリアスを追加し、コマンドレットのパラメーター</span><span class="sxs-lookup"><span data-stu-id="1bc80-117">Adding Aliases, Wildcard Expansion, and Help to Cmdlet Parameters</span></span>](./adding-aliases-wildcard-expansion-and-help-to-cmdlet-parameters.md)

[<span data-ttu-id="1bc80-118">コマンドレットにパラメーターを追加すると設定します。</span><span class="sxs-lookup"><span data-stu-id="1bc80-118">Adding Parameter Sets to Cmdlets</span></span>](./adding-parameter-sets-to-a-cmdlet.md)

[<span data-ttu-id="1bc80-119">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="1bc80-119">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)