---
title: RunSpace04 コード サンプル |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cb6fcc47-cf89-43e7-b686-3d60934ce3e7
caps.latest.revision: 6
ms.openlocfilehash: 10f236b201920d2d456af41328c7a62a9e14b571
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56861098"
---
# <a name="runspace04-code-samples"></a><span data-ttu-id="bb0b7-102">RunSpace04 コード サンプル</span><span class="sxs-lookup"><span data-stu-id="bb0b7-102">RunSpace04 Code Samples</span></span>

<span data-ttu-id="bb0b7-103">使用する実行空間用のコード サンプルを次に示します、 [System.Management.Automation.Runspaceinvoke](/dotnet/api/System.Management.Automation.RunspaceInvoke)終了エラーを生成するスクリプトを実行するクラス。</span><span class="sxs-lookup"><span data-stu-id="bb0b7-103">Here is a code sample for a runspace that uses the [System.Management.Automation.Runspaceinvoke](/dotnet/api/System.Management.Automation.RunspaceInvoke) class to execute a script that generates a terminating error.</span></span> <span data-ttu-id="bb0b7-104">ホスト アプリケーションは、エラーをキャッチし、エラー レコードを解釈する責任を負います。</span><span class="sxs-lookup"><span data-stu-id="bb0b7-104">The host application is responsible for catching the error and interpreting the error record.</span></span>

> [!NOTE]
> <span data-ttu-id="bb0b7-105">Windows ソフトウェア開発キットの Windows Vista と Microsoft .NET Framework 3.0 ランタイム コンポーネントを使用して、この実行空間には、VB.NET のソース ファイル (Runspace04.vb) をダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="bb0b7-105">You can download the VB.NET source file (Runspace04.vb) for this runspace using the Windows Software Development Kit for Windows Vista and Microsoft .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="bb0b7-106">ダウンロードの手順については、次を参照してください。 [Windows PowerShell のインストールと、Windows PowerShell SDK をダウンロードする方法](/powershell/developer/installing-the-windows-powershell-sdk)します。</span><span class="sxs-lookup"><span data-stu-id="bb0b7-106">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/developer/installing-the-windows-powershell-sdk).</span></span>
> <span data-ttu-id="bb0b7-107">Windows ソフトウェア開発キットの Windows Vista と Microsoft .NET Framework 3.0 ランタイム コンポーネントを使用して、この実行空間には、VB.NET のソース ファイル (Runspace04.vb) をダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="bb0b7-107">You can download the VB.NET source file (Runspace04.vb) for this runspace using the Windows Software Development Kit for Windows Vista and Microsoft .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="bb0b7-108">ダウンロードの手順については、次を参照してください。 [Windows PowerShell のインストールと、Windows PowerShell SDK をダウンロードする方法](/powershell/developer/installing-the-windows-powershell-sdk)します。</span><span class="sxs-lookup"><span data-stu-id="bb0b7-108">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/developer/installing-the-windows-powershell-sdk).</span></span>
>
> <span data-ttu-id="bb0b7-109">ダウンロードしたソース ファイルは、  **\<PowerShell のサンプル >** ディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="bb0b7-109">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

<span data-ttu-id="bb0b7-110">完全なサンプル コードでは、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="bb0b7-110">For complete sample code, see the following topics.</span></span>

|<span data-ttu-id="bb0b7-111">Language</span><span class="sxs-lookup"><span data-stu-id="bb0b7-111">Language</span></span>|<span data-ttu-id="bb0b7-112">トピック</span><span class="sxs-lookup"><span data-stu-id="bb0b7-112">Topic</span></span>|
|--------------|-----------|
|<span data-ttu-id="bb0b7-113">VB.NET</span><span class="sxs-lookup"><span data-stu-id="bb0b7-113">VB.NET</span></span>|[<span data-ttu-id="bb0b7-114">Runspace01 (VB.NET) コード サンプル</span><span class="sxs-lookup"><span data-stu-id="bb0b7-114">Runspace01 (VB.NET) Code Sample</span></span>](./runspace01-vb-net-code-sample.md)|

## <a name="see-also"></a><span data-ttu-id="bb0b7-115">参照</span><span class="sxs-lookup"><span data-stu-id="bb0b7-115">See Also</span></span>

[<span data-ttu-id="bb0b7-116">Windows PowerShell プログラマー ガイド</span><span class="sxs-lookup"><span data-stu-id="bb0b7-116">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="bb0b7-117">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="bb0b7-117">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)