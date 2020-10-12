---
ms.date: 08/21/2020
keywords: powershell,コマンドレット
title: リモート コマンドの実行
ms.openlocfilehash: f12d08b03757b24d1de50402b301faff193f27be
ms.sourcegitcommit: 9d95532afe81c235c8094eae28ab84b2f77f8c48
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/07/2020
ms.locfileid: "91814737"
---
# <a name="running-remote-commands"></a><span data-ttu-id="22850-103">リモート コマンドの実行</span><span class="sxs-lookup"><span data-stu-id="22850-103">Running Remote Commands</span></span>

<span data-ttu-id="22850-104">1 つの PowerShell コマンドを使用し、1 台から数百台のコンピューターでコマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="22850-104">You can run commands on one or hundreds of computers with a single PowerShell command.</span></span> <span data-ttu-id="22850-105">Windows PowerShell は、WMI、RPC、WS-Management など、さまざまなテクノロジを使用してリモート コンピューティングをサポートします。</span><span class="sxs-lookup"><span data-stu-id="22850-105">Windows PowerShell supports remote computing by using various technologies, including WMI, RPC, and WS-Management.</span></span>

<span data-ttu-id="22850-106">PowerShell Core では、WMI、WS-Management、および SSH リモート処理をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="22850-106">PowerShell Core supports WMI, WS-Management, and SSH remoting.</span></span> <span data-ttu-id="22850-107">PowerShell 6 では、RPC はサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="22850-107">In PowerShell 6, RPC is no longer supported.</span></span> <span data-ttu-id="22850-108">PowerShell 7 以降では、RPC は Windows でのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="22850-108">In PowerShell 7 and above, RPC is supported only in Windows.</span></span>

<span data-ttu-id="22850-109">PowerShell Core でのリモート処理の詳細については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="22850-109">For more information about remoting in PowerShell Core, see the following articles:</span></span>

- <span data-ttu-id="22850-110">[PowerShell Core での SSH リモート処理][ssh-remoting]</span><span class="sxs-lookup"><span data-stu-id="22850-110">[SSH Remoting in PowerShell Core][ssh-remoting]</span></span>
- <span data-ttu-id="22850-111">[PowerShell Core での WSMan リモート処理][wsman-remoting]</span><span class="sxs-lookup"><span data-stu-id="22850-111">[WSMan Remoting in PowerShell Core][wsman-remoting]</span></span>

## <a name="windows-powershell-remoting-without-configuration"></a><span data-ttu-id="22850-112">構成なしでの Windows PowerShell リモート処理</span><span class="sxs-lookup"><span data-stu-id="22850-112">Windows PowerShell Remoting Without Configuration</span></span>

<span data-ttu-id="22850-113">多くの Windows PowerShell コマンドレットは、1 台以上のリモート コンピューターのデータの収集や設定の変更が可能な ComputerName パラメーターを持っています。</span><span class="sxs-lookup"><span data-stu-id="22850-113">Many Windows PowerShell cmdlets have the ComputerName parameter that enables you to collect data and change settings on one or more remote computers.</span></span> <span data-ttu-id="22850-114">これらのコマンドレットは、さまざまな通信プロトコルを使用して、特別な構成を行わなくてもすべての Windows オペレーティング システム上で動作します。</span><span class="sxs-lookup"><span data-stu-id="22850-114">These cmdlets use varying communication protocols and work on all Windows operating systems without any special configuration.</span></span>

<span data-ttu-id="22850-115">これらのコマンドレットには、次のものがあります。</span><span class="sxs-lookup"><span data-stu-id="22850-115">These cmdlets include:</span></span>

- [<span data-ttu-id="22850-116">Restart-Computer</span><span class="sxs-lookup"><span data-stu-id="22850-116">Restart-Computer</span></span>](/powershell/module/microsoft.powershell.management/restart-computer)
- [<span data-ttu-id="22850-117">Test-Connection</span><span class="sxs-lookup"><span data-stu-id="22850-117">Test-Connection</span></span>](/powershell/module/microsoft.powershell.management/test-connection)
- [<span data-ttu-id="22850-118">Clear-EventLog</span><span class="sxs-lookup"><span data-stu-id="22850-118">Clear-EventLog</span></span>](/powershell/module/microsoft.powershell.management/clear-eventlog)
- [<span data-ttu-id="22850-119">Get-EventLog</span><span class="sxs-lookup"><span data-stu-id="22850-119">Get-EventLog</span></span>](/powershell/module/microsoft.powershell.management/get-eventlog)
- [<span data-ttu-id="22850-120">Get-HotFix</span><span class="sxs-lookup"><span data-stu-id="22850-120">Get-HotFix</span></span>](/powershell/module/microsoft.powershell.management/get-hotfix)
- [<span data-ttu-id="22850-121">Get-Process</span><span class="sxs-lookup"><span data-stu-id="22850-121">Get-Process</span></span>](/powershell/module/microsoft.powershell.management/get-process)
- [<span data-ttu-id="22850-122">Get-Service</span><span class="sxs-lookup"><span data-stu-id="22850-122">Get-Service</span></span>](/powershell/module/microsoft.powershell.management/get-service)
- [<span data-ttu-id="22850-123">Set-Service</span><span class="sxs-lookup"><span data-stu-id="22850-123">Set-Service</span></span>](/powershell/module/microsoft.powershell.management/set-service)
- [<span data-ttu-id="22850-124">Get-WinEvent</span><span class="sxs-lookup"><span data-stu-id="22850-124">Get-WinEvent</span></span>](/powershell/module/microsoft.powershell.diagnostics/get-winevent)
- [<span data-ttu-id="22850-125">Get-WmiObject</span><span class="sxs-lookup"><span data-stu-id="22850-125">Get-WmiObject</span></span>](/powershell/module/microsoft.powershell.management/get-wmiobject)

<span data-ttu-id="22850-126">通常、特別な構成なしでリモート処理をサポートするコマンドレットは、ComputerName パラメーターを指定し、Session パラメーターは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="22850-126">Typically, cmdlets that support remoting without special configuration have the ComputerName parameter and don't have the Session parameter.</span></span> <span data-ttu-id="22850-127">セッションでこれらのコマンドレットを見つけるには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="22850-127">To find these cmdlets in your session, type:</span></span>

```powershell
Get-Command | where { $_.parameters.keys -contains "ComputerName" -and $_.parameters.keys -notcontains "Session"}
```

## <a name="windows-powershell-remoting"></a><span data-ttu-id="22850-128">Windows PowerShell のリモート処理</span><span class="sxs-lookup"><span data-stu-id="22850-128">Windows PowerShell Remoting</span></span>

<span data-ttu-id="22850-129">Windows PowerShell リモート処理では、WS-Management プロトコルを使用して、1 台以上のリモート コンピューターで Windows PowerShell コマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="22850-129">Using the WS-Management protocol, Windows PowerShell remoting lets you run any Windows PowerShell command on one or more remote computers.</span></span> <span data-ttu-id="22850-130">永続的な接続の確立、対話型のセッションの開始、およびリモート コンピューターでのスクリプトの実行が可能です。</span><span class="sxs-lookup"><span data-stu-id="22850-130">You can establish persistent connections, start interactive sessions, and run scripts on remote computers.</span></span>

<span data-ttu-id="22850-131">Windows PowerShell のリモート処理を使用するには、リモート管理のためにリモート コンピューターを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="22850-131">To use Windows PowerShell remoting, the remote computer must be configured for remote management.</span></span>
<span data-ttu-id="22850-132">手順を含む詳細については、「[about_Remote_Requirements](/powershell/module/microsoft.powershell.core/about/about_remote_requirements)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="22850-132">For more information, including instructions, see [About Remote Requirements](/powershell/module/microsoft.powershell.core/about/about_remote_requirements).</span></span>

<span data-ttu-id="22850-133">Windows PowerShell のリモート処理を構成すると、それ以降は、多くのリモート処理の戦略が使用可能になります。</span><span class="sxs-lookup"><span data-stu-id="22850-133">Once you have configured Windows PowerShell remoting, many remoting strategies are available to you.</span></span>
<span data-ttu-id="22850-134">この記事では、その一部のみを示します。</span><span class="sxs-lookup"><span data-stu-id="22850-134">This article lists just a few of them.</span></span> <span data-ttu-id="22850-135">詳細については、「[About Remote](/powershell/module/microsoft.powershell.core/about/about_remote)」(リモート処理について) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="22850-135">For more information, see [About Remote](/powershell/module/microsoft.powershell.core/about/about_remote).</span></span>

### <a name="start-an-interactive-session"></a><span data-ttu-id="22850-136">対話型セッションの開始</span><span class="sxs-lookup"><span data-stu-id="22850-136">Start an Interactive Session</span></span>

<span data-ttu-id="22850-137">1 台のリモート コンピューターとの対話型セッションを開始するには、[Enter-PSSession](/powershell/module/microsoft.powershell.core/enter-pssession) コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="22850-137">To start an interactive session with a single remote computer, use the [Enter-PSSession](/powershell/module/microsoft.powershell.core/enter-pssession) cmdlet.</span></span> <span data-ttu-id="22850-138">たとえば、Server01 リモート コンピューターと対話型セッションを開始するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="22850-138">For example, to start an interactive session with the Server01 remote computer, type:</span></span>

```powershell
Enter-PSSession Server01
```

<span data-ttu-id="22850-139">コマンド プロンプトの画面が更新され、リモート コンピューターの名前が表示されます。</span><span class="sxs-lookup"><span data-stu-id="22850-139">The command prompt changes to display the name of the remote computer.</span></span> <span data-ttu-id="22850-140">プロンプトに入力されたコマンドはリモート コンピューターで実行され、結果はローカル コンピューターに表示されます。</span><span class="sxs-lookup"><span data-stu-id="22850-140">Any commands that you type at the prompt run on the remote computer and the results are displayed on the local computer.</span></span>

<span data-ttu-id="22850-141">対話型セッションを終了するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="22850-141">To end the interactive session, type:</span></span>

```powershell
Exit-PSSession
```

<span data-ttu-id="22850-142">Enter-PSSession コマンドレットおよび Exit-PSSession コマンドレットの詳細については、次を参照してください。</span><span class="sxs-lookup"><span data-stu-id="22850-142">For more information about the Enter-PSSession and Exit-PSSession cmdlets, see:</span></span>

- [<span data-ttu-id="22850-143">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="22850-143">Enter-PSSession</span></span>](/powershell/module/microsoft.powershell.core/enter-pssession)
- [<span data-ttu-id="22850-144">Exit-PSSession</span><span class="sxs-lookup"><span data-stu-id="22850-144">Exit-PSSession</span></span>](/powershell/module/microsoft.powershell.core/exit-pssession)

### <a name="run-a-remote-command"></a><span data-ttu-id="22850-145">リモート コマンドの実行</span><span class="sxs-lookup"><span data-stu-id="22850-145">Run a Remote Command</span></span>

<span data-ttu-id="22850-146">1 台または複数のコンピューターでコマンドを実行するには、[Invoke-Command](/powershell/module/microsoft.powershell.core/invoke-command) コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="22850-146">To run a command on one or more computers, use the [Invoke-Command](/powershell/module/microsoft.powershell.core/invoke-command) cmdlet.</span></span> <span data-ttu-id="22850-147">たとえば、[Get-UICulture](/powershell/module/microsoft.powershell.utility/get-uiculture) コマンドをリモート コンピューター Server01 と Server02 で実行するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="22850-147">For example, to run a [Get-UICulture](/powershell/module/microsoft.powershell.utility/get-uiculture) command on the Server01 and Server02 remote computers, type:</span></span>

```powershell
Invoke-Command -ComputerName Server01, Server02 -ScriptBlock {Get-UICulture}
```

<span data-ttu-id="22850-148">コンピューターに出力が返されます。</span><span class="sxs-lookup"><span data-stu-id="22850-148">The output is returned to your computer.</span></span>

```output
LCID    Name     DisplayName               PSComputerName
----    ----     -----------               --------------
1033    en-US    English (United States)   server01.corp.fabrikam.com
1033    en-US    English (United States)   server02.corp.fabrikam.com
```

### <a name="run-a-script"></a><span data-ttu-id="22850-149">スクリプトの実行</span><span class="sxs-lookup"><span data-stu-id="22850-149">Run a Script</span></span>

<span data-ttu-id="22850-150">1 台または多数のリモート コンピューターでスクリプトを実行するには、`Invoke-Command` コマンドレットの FilePath パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="22850-150">To run a script on one or many remote computers, use the FilePath parameter of the `Invoke-Command` cmdlet.</span></span> <span data-ttu-id="22850-151">スクリプトがローカル コンピューターでアクセス可能でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="22850-151">The script must be on or accessible to your local computer.</span></span> <span data-ttu-id="22850-152">結果はローカル コンピューターに返されます。</span><span class="sxs-lookup"><span data-stu-id="22850-152">The results are returned to your local computer.</span></span>

<span data-ttu-id="22850-153">たとえば、次のコマンドは、リモート コンピューター Server01 と Server02 で DiskCollect.ps1 スクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="22850-153">For example, the following command runs the DiskCollect.ps1 script on the remote computers, Server01 and Server02.</span></span>

```powershell
Invoke-Command -ComputerName Server01, Server02 -FilePath c:\Scripts\DiskCollect.ps1
```

### <a name="establish-a-persistent-connection"></a><span data-ttu-id="22850-154">永続的な接続の確立</span><span class="sxs-lookup"><span data-stu-id="22850-154">Establish a Persistent Connection</span></span>

<span data-ttu-id="22850-155">`New-PSSession` コマンドレットを使用して、リモート コンピューター上に永続的なセッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="22850-155">Use the `New-PSSession` cmdlet to create a persistent session on a remote computer.</span></span> <span data-ttu-id="22850-156">次の例では、Server01 および Server02 上にリモート セッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="22850-156">The following example creates remote sessions on Server01 and Server02.</span></span> <span data-ttu-id="22850-157">セッション オブジェクトは、`$s` 変数に格納されます。</span><span class="sxs-lookup"><span data-stu-id="22850-157">The session objects are stored in the `$s` variable.</span></span>

```powershell
$s = New-PSSession -ComputerName Server01, Server02
```

<span data-ttu-id="22850-158">セッションが確立されたので、それらで任意のコマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="22850-158">Now that the sessions are established, you can run any command in them.</span></span> <span data-ttu-id="22850-159">また、セッションは永続的であるため、1 つのコマンドからデータを収集して、別のコマンドでそのデータを利用できます。</span><span class="sxs-lookup"><span data-stu-id="22850-159">And because the sessions are persistent, you can collect data from one command and use it in another command.</span></span>

<span data-ttu-id="22850-160">たとえば、次のコマンドは $s 変数のセッションで Get-HotFix コマンドを実行し、結果を $h 変数に保存します。</span><span class="sxs-lookup"><span data-stu-id="22850-160">For example, the following command runs a Get-HotFix command in the sessions in the $s variable and it saves the results in the $h variable.</span></span> <span data-ttu-id="22850-161">$h 変数は $s のそれぞれのセッションで作成されますが、ローカル セッションには存在しません。</span><span class="sxs-lookup"><span data-stu-id="22850-161">The $h variable is created in each of the sessions in $s, but it doesn't exist in the local session.</span></span>

```powershell
Invoke-Command -Session $s {$h = Get-HotFix}
```

<span data-ttu-id="22850-162">これで、同じセッション内の他のコマンドで、`$h` 変数のデータを使用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="22850-162">Now you can use the data in the `$h` variable with other commands in the same session.</span></span> <span data-ttu-id="22850-163">結果はローカル コンピューターに表示されます。</span><span class="sxs-lookup"><span data-stu-id="22850-163">The results are displayed on the local computer.</span></span> <span data-ttu-id="22850-164">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="22850-164">For example:</span></span>

```powershell
Invoke-Command -Session $s {$h | where {$_.InstalledBy -ne "NTAUTHORITY\SYSTEM"}}
```

### <a name="advanced-remoting"></a><span data-ttu-id="22850-165">高度なリモート処理</span><span class="sxs-lookup"><span data-stu-id="22850-165">Advanced Remoting</span></span>

<span data-ttu-id="22850-166">Windows PowerShell のリモート管理はこれだけではありません。</span><span class="sxs-lookup"><span data-stu-id="22850-166">Windows PowerShell remote management just begins here.</span></span> <span data-ttu-id="22850-167">Windows PowerShell と共にインストールされるコマンドレットを使用して、ローカルとリモートの両側からのリモート セッションの確立と構成、カスタマイズおよび制限されたセッションの作成、リモート セッションで実際に暗黙的に実行されるコマンドのリモート セッションからのユーザーによるインポート、リモート セッションのセキュリティの構成など、さまざまな処理を実行できます。</span><span class="sxs-lookup"><span data-stu-id="22850-167">By using the cmdlets installed with Windows PowerShell, you can establish and configure remote sessions both from the local and remote ends, create customized and restricted sessions, allow users to import commands from a remote session that actually run implicitly on the remote session, configure the security of a remote session, and much more.</span></span>

<span data-ttu-id="22850-168">Windows PowerShell には、WSMan プロバイダーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="22850-168">Windows PowerShell includes a WSMan provider.</span></span> <span data-ttu-id="22850-169">プロバイダーは、ローカル コンピューターとリモート コンピューターの構成設定の階層内を移動できる `WSMAN:` ドライブを作成します。</span><span class="sxs-lookup"><span data-stu-id="22850-169">The provider creates a `WSMAN:` drive that lets you navigate through a hierarchy of configuration settings on the local computer and remote computers.</span></span>

<span data-ttu-id="22850-170">WSMan プロバイダーの詳細については、[WSMan Provider](https://technet.microsoft.com/library/dd819476.aspx) (WSMan プロバイダー) および [WS-Management コマンドレット関するページ](/powershell/module/microsoft.wsman.management/about/about_ws-management_cmdlets)を参照するか、Windows PowerShell コンソールで `Get-Help wsman` と入力してください。</span><span class="sxs-lookup"><span data-stu-id="22850-170">For more information about the WSMan provider, see [WSMan Provider](https://technet.microsoft.com/library/dd819476.aspx) and [About WS-Management Cmdlets](/powershell/module/microsoft.wsman.management/about/about_ws-management_cmdlets), or in the Windows PowerShell console, type `Get-Help wsman`.</span></span>

<span data-ttu-id="22850-171">詳細については、次を参照してください。</span><span class="sxs-lookup"><span data-stu-id="22850-171">For more information, see:</span></span>

- [<span data-ttu-id="22850-172">about_Remote のよく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="22850-172">About Remote FAQ</span></span>](https://technet.microsoft.com/library/dd315359.aspx)
- [<span data-ttu-id="22850-173">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="22850-173">Register-PSSessionConfiguration</span></span>](https://go.microsoft.com/fwlink/?LinkId=821508)
- [<span data-ttu-id="22850-174">Import-PSSession</span><span class="sxs-lookup"><span data-stu-id="22850-174">Import-PSSession</span></span>](https://go.microsoft.com/fwlink/?LinkId=821821)

<span data-ttu-id="22850-175">リモート処理のエラーに関するヘルプは、「[about_Remote_Troubleshooting](https://technet.microsoft.com/library/dd347642.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="22850-175">For help with remoting errors, see [about_Remote_Troubleshooting](https://technet.microsoft.com/library/dd347642.aspx).</span></span>

## <a name="see-also"></a><span data-ttu-id="22850-176">参照</span><span class="sxs-lookup"><span data-stu-id="22850-176">See Also</span></span>

- [<span data-ttu-id="22850-177">about_Remote</span><span class="sxs-lookup"><span data-stu-id="22850-177">about_Remote</span></span>](https://technet.microsoft.com/library/9b4a5c87-9162-4adf-bdfe-fbc80b9b8970)
- [<span data-ttu-id="22850-178">about_Remote_FAQ</span><span class="sxs-lookup"><span data-stu-id="22850-178">about_Remote_FAQ</span></span>](https://technet.microsoft.com/library/e23702fd-9415-4a98-9975-390a4d3adc42)
- [<span data-ttu-id="22850-179">about_Remote_Requirements</span><span class="sxs-lookup"><span data-stu-id="22850-179">about_Remote_Requirements</span></span>](https://technet.microsoft.com/library/da213949-134c-4741-b307-81f4492ba1bd)
- [<span data-ttu-id="22850-180">about_Remote_Troubleshooting</span><span class="sxs-lookup"><span data-stu-id="22850-180">about_Remote_Troubleshooting</span></span>](https://technet.microsoft.com/library/2f890148-8578-49ed-85ea-79a489dd6317)
- [<span data-ttu-id="22850-181">about_PSSessions</span><span class="sxs-lookup"><span data-stu-id="22850-181">about_PSSessions</span></span>](https://technet.microsoft.com/library/7a9b4e0e-fa1b-47b0-92f6-6e2995d70acb)
- [<span data-ttu-id="22850-182">about_WS-Management_Cmdlets</span><span class="sxs-lookup"><span data-stu-id="22850-182">about_WS-Management_Cmdlets</span></span>](https://technet.microsoft.com/library/6ed3370a-ea10-45a5-9493-696aeace27ed)
- [<span data-ttu-id="22850-183">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="22850-183">Invoke-Command</span></span>](/powershell/module/microsoft.powershell.core/invoke-command)
- [<span data-ttu-id="22850-184">Import-PSSession</span><span class="sxs-lookup"><span data-stu-id="22850-184">Import-PSSession</span></span>](https://go.microsoft.com/fwlink/?LinkId=821821)
- [<span data-ttu-id="22850-185">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="22850-185">New-PSSession</span></span>](https://go.microsoft.com/fwlink/?LinkId=821498)
- [<span data-ttu-id="22850-186">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="22850-186">Register-PSSessionConfiguration</span></span>](https://go.microsoft.com/fwlink/?LinkId=821508)
- [<span data-ttu-id="22850-187">WSMan プロバイダー</span><span class="sxs-lookup"><span data-stu-id="22850-187">WSMan Provider</span></span>](https://technet.microsoft.com/library/66fe1241-e08f-49ca-832f-a84c33ca8735)

[wsman-remoting]: WSMan-Remoting-in-PowerShell-Core.md
[ssh-remoting]: SSH-Remoting-in-PowerShell-Core.md
