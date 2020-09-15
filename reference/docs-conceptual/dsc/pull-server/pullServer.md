---
ms.date: 01/08/2020
keywords: DSC, PowerShell, 構成, セットアップ
title: DSC プル サービス
ms.openlocfilehash: c4e725569db776fe0dbd5395b2f0f8b8e70cbbeb
ms.sourcegitcommit: 105c69ecedfe5180d8c12e8015d667c5f1a71579
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2020
ms.locfileid: "85837479"
---
# <a name="desired-state-configuration-pull-service"></a><span data-ttu-id="23945-103">Desired State Configuration プル サービス</span><span class="sxs-lookup"><span data-stu-id="23945-103">Desired State Configuration Pull Service</span></span>

> [!IMPORTANT]
> <span data-ttu-id="23945-104">プル サーバー (Windows Feature *DSC-Service*) は、Windows Server のサポート対象のコンポーネントですが、新機能がオファーされる予定はありません。</span><span class="sxs-lookup"><span data-stu-id="23945-104">The Pull Server (Windows Feature *DSC-Service*) is a supported component of Windows Server however there are no plans to offer new features or capabilities.</span></span> <span data-ttu-id="23945-105">管理対象のクライアントは、(Windows Server のプル サーバー以降の機能が含まれる) [Azure Automation DSC](/azure/automation/automation-dsc-getting-started) または、[こちら](pullserver.md#community-solutions-for-pull-service)に列挙されているコミュニティ ソリューションのいずれかに切り替えを開始することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="23945-105">It is recommended to begin transitioning managed clients to [Azure Automation DSC](/azure/automation/automation-dsc-getting-started) (includes features beyond Pull Server on Windows Server) or one of the community solutions listed [here](pullserver.md#community-solutions-for-pull-service).</span></span>

<span data-ttu-id="23945-106">Local Configuration Manager (LCM) は、プル サービス ソリューションで一元管理できます。</span><span class="sxs-lookup"><span data-stu-id="23945-106">Local Configuration Manager (LCM) can be centrally managed by a Pull Service solution.</span></span> <span data-ttu-id="23945-107">この方法を使用する場合、管理対象のノードはサービスに登録され、LCM 設定で構成が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="23945-107">When using this approach, the node that is being managed is registered with a service and assigned a configuration in LCM settings.</span></span> <span data-ttu-id="23945-108">構成の依存関係として必要な構成とすべての DSC リソースは、マシンにダウンロードされ、構成を管理するために LCM によって使用されます。</span><span class="sxs-lookup"><span data-stu-id="23945-108">The configuration and all DSC resources needed as dependencies for the configuration are downloaded to the machine and used by LCM to manage the configuration.</span></span> <span data-ttu-id="23945-109">管理対象のマシンの状態に関する情報は、レポートのためにサービスにアップロードされます。</span><span class="sxs-lookup"><span data-stu-id="23945-109">Information about the state of the machine being managed is uploaded to the service for reporting.</span></span> <span data-ttu-id="23945-110">この概念は "プル サービス" と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="23945-110">This concept is referred to as "pull service".</span></span>

<span data-ttu-id="23945-111">現在選択できるプル サービスは以下のとおりです。</span><span class="sxs-lookup"><span data-stu-id="23945-111">The current options for pull service include:</span></span>

- <span data-ttu-id="23945-112">Azure Automation Desired State Configuration サービス</span><span class="sxs-lookup"><span data-stu-id="23945-112">Azure Automation Desired State Configuration service</span></span>
- <span data-ttu-id="23945-113">Windows Server で実行されるプル サービス</span><span class="sxs-lookup"><span data-stu-id="23945-113">A pull service running on Windows Server</span></span>
- <span data-ttu-id="23945-114">コミュニティが維持するオープン ソースのソリューション</span><span class="sxs-lookup"><span data-stu-id="23945-114">Community maintained open-source solutions</span></span>
- <span data-ttu-id="23945-115">SMB 共有</span><span class="sxs-lookup"><span data-stu-id="23945-115">An SMB share</span></span>

<span data-ttu-id="23945-116">各ソリューションの推奨スケールは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="23945-116">The recommended scale for each solution is as follows:</span></span>

|                   <span data-ttu-id="23945-117">解決策</span><span class="sxs-lookup"><span data-stu-id="23945-117">Solution</span></span>                   |              <span data-ttu-id="23945-118">クライアント ノード</span><span class="sxs-lookup"><span data-stu-id="23945-118">Client nodes</span></span>              |
| -------------------------------------------- | -------------------------------------- |
| <span data-ttu-id="23945-119">MDB/ESENT データベースを使用する Windows プル サーバー</span><span class="sxs-lookup"><span data-stu-id="23945-119">Windows Pull Server using MDB/ESENT database</span></span> | <span data-ttu-id="23945-120">最大 500 ノード</span><span class="sxs-lookup"><span data-stu-id="23945-120">Up to 500 nodes</span></span>                        |
| <span data-ttu-id="23945-121">SQL データベースを使用する Windows プル サーバー</span><span class="sxs-lookup"><span data-stu-id="23945-121">Windows Pull Server using SQL database</span></span>       | <span data-ttu-id="23945-122">最大 3500 ノード</span><span class="sxs-lookup"><span data-stu-id="23945-122">Up to 3500 nodes</span></span>                       |
| <span data-ttu-id="23945-123">Azure Automation DSC</span><span class="sxs-lookup"><span data-stu-id="23945-123">Azure Automation DSC</span></span>                         | <span data-ttu-id="23945-124">小規模環境と大規模環境の両方</span><span class="sxs-lookup"><span data-stu-id="23945-124">Both small and large environments</span></span>      |

<span data-ttu-id="23945-125">**推奨されるソリューション**であり、最も多くの機能を使用できる選択肢は [Azure Automation DSC](/azure/automation/automation-dsc-getting-started) です。</span><span class="sxs-lookup"><span data-stu-id="23945-125">**The recommended solution**, and the option with the most features available, is [Azure Automation DSC](/azure/automation/automation-dsc-getting-started).</span></span> <span data-ttu-id="23945-126">Automation アカウントあたりのノード数の上限は指定されていません。</span><span class="sxs-lookup"><span data-stu-id="23945-126">An upper limit for number of nodes per Automation Account has not been identified.</span></span>

<span data-ttu-id="23945-127">Azure サービスでは、プライベート データセンター内にあるオンプレミス ノードと、パブリック クラウド （Azure や AWS など) 内にあるノードのどちらも管理できます。</span><span class="sxs-lookup"><span data-stu-id="23945-127">The Azure service can manage nodes on-premises in private datacenters, or in public clouds such as Azure and AWS.</span></span> <span data-ttu-id="23945-128">インターネットへのサーバーの直接接続が許可されないプライベート環境の場合は、公開されている Azure の IP 範囲 ([Azure データセンターの IP 範囲](https://www.microsoft.com/download/details.aspx?id=41653)に関するページを参照) のみに送信トラフィックを制限することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="23945-128">For private environments where servers cannot directly connect to the Internet, consider limiting outbound traffic to only the published Azure IP range (see [Azure Datacenter IP Ranges](https://www.microsoft.com/download/details.aspx?id=41653)).</span></span>

<span data-ttu-id="23945-129">現時点で Windows Server 上のプル サービスでは利用できないオンライン サービスの機能は以下のとおりです。</span><span class="sxs-lookup"><span data-stu-id="23945-129">Features of the online service that are not currently available in the pull service on Windows Server include:</span></span>

- <span data-ttu-id="23945-130">転送中および保存中のすべてのデータの暗号化</span><span class="sxs-lookup"><span data-stu-id="23945-130">All data is encrypted in transit and at rest</span></span>
- <span data-ttu-id="23945-131">クライアント証明書の自動作成および管理</span><span class="sxs-lookup"><span data-stu-id="23945-131">Client certificates are created and managed automatically</span></span>
- <span data-ttu-id="23945-132">[パスワード/資格情報](/azure/automation/automation-credentials) または[変数](/azure/automation/automation-variables) (サーバー名や接続文字列など) を一元管理するためのシークレット ストア</span><span class="sxs-lookup"><span data-stu-id="23945-132">Secrets store for centrally managing [passwords/credentials](/azure/automation/automation-credentials), or [variables](/azure/automation/automation-variables) such as server names or connection strings</span></span>
- <span data-ttu-id="23945-133">[LCM 構成](../managing-nodes/metaConfig.md#basic-settings)ノードの一元管理</span><span class="sxs-lookup"><span data-stu-id="23945-133">Centrally manage node [LCM configuration](../managing-nodes/metaConfig.md#basic-settings)</span></span>
- <span data-ttu-id="23945-134">クライアント ノードへ構成を一元的に割り当てる</span><span class="sxs-lookup"><span data-stu-id="23945-134">Centrally assign configurations to client nodes</span></span>
- <span data-ttu-id="23945-135">運用環境への適用前に "カナリア グループ" へ構成の変更をリリースしてテストする</span><span class="sxs-lookup"><span data-stu-id="23945-135">Release configuration changes to "canary groups" for testing before reaching production</span></span>
- <span data-ttu-id="23945-136">グラフィカル レポート</span><span class="sxs-lookup"><span data-stu-id="23945-136">Graphical reporting</span></span>
  - <span data-ttu-id="23945-137">きめ細かな DSC リソース レベルでの状態の詳細</span><span class="sxs-lookup"><span data-stu-id="23945-137">Status detail at the DSC resource level of granularity</span></span>
  - <span data-ttu-id="23945-138">クライアント マシンからの詳細なエラー メッセージによるトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="23945-138">Verbose error messages from client machines for troubleshooting</span></span>
- <span data-ttu-id="23945-139">[Azure Log Analytics との統合](/azure/automation/automation-dsc-diagnostics)によるアラートとタスクの自動化、およびレポートとアラート用の Android/iOS アプリ</span><span class="sxs-lookup"><span data-stu-id="23945-139">[Integration with Azure Log Analytics](/azure/automation/automation-dsc-diagnostics) for alerting, automated tasks, Android/iOS app for reporting and alerting</span></span>

## <a name="dsc-pull-service-in-windows-server"></a><span data-ttu-id="23945-140">Windows Server の DSC プル サービス</span><span class="sxs-lookup"><span data-stu-id="23945-140">DSC pull service in Windows Server</span></span>

<span data-ttu-id="23945-141">Windows Server 上で実行するようにプル サービスを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="23945-141">It is possible to configure a pull service to run on Windows Server.</span></span> <span data-ttu-id="23945-142">Windows Server に含まれるプル サービス ソリューションには、ダウンロード用の構成/モジュールを格納する機能と、レポート データをデータベースにキャプチャする機能のみが含まれている点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="23945-142">Be advised that the pull service solution included in Windows Server includes only capabilities of storing configurations/modules for download and capturing report data into a database.</span></span> <span data-ttu-id="23945-143">Azure のサービスで提供される機能の多くは含まれていないため、サービスの使用方法を評価する場合に適したツールではありません。</span><span class="sxs-lookup"><span data-stu-id="23945-143">It does not include many of the capabilities offered by the service in Azure and so, is not a good tool for evaluating how the service would be used.</span></span>

<span data-ttu-id="23945-144">Windows Server で提供されるプル サービスは、OData インターフェイスを使用してターゲット ノードからの要求に応じて DSC 構成ファイルをそのターゲット ノードで使用できるようにする、IIS 内の Web サービスです。</span><span class="sxs-lookup"><span data-stu-id="23945-144">The pull service offered in Windows Server is a web service in IIS that uses an OData interface to make DSC configuration files available to target nodes when those nodes ask for them.</span></span>

<span data-ttu-id="23945-145">プル サーバーを使用するための要件:</span><span class="sxs-lookup"><span data-stu-id="23945-145">Requirements for using a pull server:</span></span>

- <span data-ttu-id="23945-146">次のものを実行するサーバー。</span><span class="sxs-lookup"><span data-stu-id="23945-146">A server running:</span></span>
  - <span data-ttu-id="23945-147">WMF/PowerShell 4.0 以降</span><span class="sxs-lookup"><span data-stu-id="23945-147">WMF/PowerShell 4.0 or greater</span></span>
  - <span data-ttu-id="23945-148">IIS サーバー ロール</span><span class="sxs-lookup"><span data-stu-id="23945-148">IIS server role</span></span>
  - <span data-ttu-id="23945-149">DSC サービス</span><span class="sxs-lookup"><span data-stu-id="23945-149">DSC Service</span></span>
- <span data-ttu-id="23945-150">理想としては、証明書を生成する何らかの手段。これは、ターゲット ノードのローカル構成マネージャー (LCM) に渡された資格情報をセキュリティ保護するためのものです。</span><span class="sxs-lookup"><span data-stu-id="23945-150">Ideally, some means of generating a certificate, to secure credentials passed to the Local Configuration Manager (LCM) on target nodes</span></span>

<span data-ttu-id="23945-151">プル サービスをホストするように Windows Server を構成するには、DSC 構成を使用する方法が最適です。</span><span class="sxs-lookup"><span data-stu-id="23945-151">The best way to configure Windows Server to host pull service is to use a DSC configuration.</span></span> <span data-ttu-id="23945-152">スクリプトの例を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="23945-152">An example script is provided below.</span></span>

### <a name="supported-database-systems"></a><span data-ttu-id="23945-153">サポートされているデータベース システム</span><span class="sxs-lookup"><span data-stu-id="23945-153">Supported database systems</span></span>

| <span data-ttu-id="23945-154">WMF 4.0</span><span class="sxs-lookup"><span data-stu-id="23945-154">WMF 4.0</span></span> |       <span data-ttu-id="23945-155">WMF 5.0</span><span class="sxs-lookup"><span data-stu-id="23945-155">WMF 5.0</span></span>        |       <span data-ttu-id="23945-156">WMF 5.1</span><span class="sxs-lookup"><span data-stu-id="23945-156">WMF 5.1</span></span>        | <span data-ttu-id="23945-157">WMF 5.1 (Windows Server Insider プレビュー 17090)</span><span class="sxs-lookup"><span data-stu-id="23945-157">WMF 5.1 (Windows Server Insider Preview 17090)</span></span> |
| ------- | -------------------- | -------------------- | ---------------------------------------------- |
| <span data-ttu-id="23945-158">MDB</span><span class="sxs-lookup"><span data-stu-id="23945-158">MDB</span></span>     | <span data-ttu-id="23945-159">ESENT (既定)、MDB</span><span class="sxs-lookup"><span data-stu-id="23945-159">ESENT (Default), MDB</span></span> | <span data-ttu-id="23945-160">ESENT (既定)、MDB</span><span class="sxs-lookup"><span data-stu-id="23945-160">ESENT (Default), MDB</span></span> | <span data-ttu-id="23945-161">ESENT (既定)、SQL Server、MDB</span><span class="sxs-lookup"><span data-stu-id="23945-161">ESENT (Default), SQL Server, MDB</span></span>               |

<span data-ttu-id="23945-162">Windows Server のリリース 17090 以降では、SQL Server は、プル サービス (Windows Feature *DSC-Service*) でサポートされるオプションです。</span><span class="sxs-lookup"><span data-stu-id="23945-162">Starting in release 17090 of Windows Server, SQL Server is a supported option for the Pull Service (Windows Feature *DSC-Service*).</span></span> <span data-ttu-id="23945-163">これは、[Azure Automation DSC](/azure/automation/automation-dsc-getting-started) に移行されていない大規模な DSC 環境をスケーリングする新しいオプションです。</span><span class="sxs-lookup"><span data-stu-id="23945-163">This provides a new option for scaling large DSC environments that have not migrated to [Azure Automation DSC](/azure/automation/automation-dsc-getting-started).</span></span>

> [!NOTE]
> <span data-ttu-id="23945-164">SQL Server は WMF 5.1 以前のバージョンには追加されず、17090 以降の Windows Server バージョンでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="23945-164">SQL Server support will not be added to previous versions of WMF 5.1 (or earlier) and will only be available on Windows Server versions greater than or equal to 17090.</span></span>

<span data-ttu-id="23945-165">プル サーバーで SQL Server を使用するよう構成するには、**SqlProvider** を `$true` に、そして **SqlConnectionString** を有効な SQL Server 接続文字列に設定します。</span><span class="sxs-lookup"><span data-stu-id="23945-165">To configure the pull server to use SQL Server, set **SqlProvider** to `$true` and **SqlConnectionString** to a valid SQL Server Connection String.</span></span> <span data-ttu-id="23945-166">詳細については、「[SqlClient 接続文字列](/dotnet/framework/data/adonet/connection-string-syntax#sqlclient-connection-strings)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="23945-166">For more information, see [SqlClient Connection Strings](/dotnet/framework/data/adonet/connection-string-syntax#sqlclient-connection-strings).</span></span>
<span data-ttu-id="23945-167">**xDscWebService** を使用した SQL Server の構成例については、まず「[xDscWebService リソースの使用](#using-the-xdscwebservice-resource)」に目を通してから、GitHub の「[Sample_xDscWebServiceRegistration_UseSQLProvider.ps1](https://github.com/dsccommunity/xPSDesiredStateConfiguration/blob/master/source/Examples/Sample_xDscWebServiceRegistration_UseSQLProvider.ps1)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="23945-167">For an example of SQL Server configuration with **xDscWebService**, first read [Using the xDscWebService resource](#using-the-xdscwebservice-resource) and then review [Sample_xDscWebServiceRegistration_UseSQLProvider.ps1 on GitHub](https://github.com/dsccommunity/xPSDesiredStateConfiguration/blob/master/source/Examples/Sample_xDscWebServiceRegistration_UseSQLProvider.ps1).</span></span>

### <a name="using-the-xdscwebservice-resource"></a><span data-ttu-id="23945-168">xDscWebService リソースの使用</span><span class="sxs-lookup"><span data-stu-id="23945-168">Using the xDscWebService resource</span></span>

<span data-ttu-id="23945-169">Web プル サーバーをセットアップする最も簡単な方法は、**xPSDesiredStateConfiguration** モジュールに含まれる **xDscWebService** リソースを使用することです。</span><span class="sxs-lookup"><span data-stu-id="23945-169">The easiest way to set up a web pull server is to use the **xDscWebService** resource, included in the **xPSDesiredStateConfiguration** module.</span></span> <span data-ttu-id="23945-170">次の手順では、Web サービスを設定する `Configuration` 内でリソースを使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="23945-170">The following steps explain how to use the resource in a `Configuration` that sets up the web service.</span></span>

1. <span data-ttu-id="23945-171">[Install-Module](/powershell/module/PowerShellGet/Install-Module) コマンドレットを呼び出して、**xPSDesiredStateConfiguration** モジュールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="23945-171">Call the [Install-Module](/powershell/module/PowerShellGet/Install-Module) cmdlet to install the **xPSDesiredStateConfiguration** module.</span></span>

   > [!NOTE]
   > <span data-ttu-id="23945-172">`Install-Module` は、**PowerShellGet** モジュールに含まれています。これは PowerShell 5.0 以降に含まれています。</span><span class="sxs-lookup"><span data-stu-id="23945-172">`Install-Module` is included in the **PowerShellGet** module, which is included in PowerShell 5.0 and higher.</span></span>

1. <span data-ttu-id="23945-173">DSC プル サーバーの SSL 証明書を、自社組織内またはパブリック証明機関のいずれかの信頼された証明機関から取得します。</span><span class="sxs-lookup"><span data-stu-id="23945-173">Get an SSL certificate for the DSC Pull server from a trusted Certificate Authority, either within your organization or a public authority.</span></span> <span data-ttu-id="23945-174">証明機関から受け取る証明書は、通常、PFX 形式です。</span><span class="sxs-lookup"><span data-stu-id="23945-174">The certificate received from the authority is usually in the PFX format.</span></span>
1. <span data-ttu-id="23945-175">証明書は、DSC プル サーバーになるノードの既定の場所 (`CERT:\LocalMachine\My` である必要があります) にインストールします。</span><span class="sxs-lookup"><span data-stu-id="23945-175">Install the certificate on the node that will become the DSC Pull server in the default location, which should be `CERT:\LocalMachine\My`.</span></span>
   - <span data-ttu-id="23945-176">証明書の拇印をメモしておきます。</span><span class="sxs-lookup"><span data-stu-id="23945-176">Make a note of the certificate thumbprint.</span></span>
1. <span data-ttu-id="23945-177">登録キーとして使う GUID を選択します。</span><span class="sxs-lookup"><span data-stu-id="23945-177">Select a GUID to be used as the Registration Key.</span></span> <span data-ttu-id="23945-178">PowerShell を使って GUID を生成するには、PS プロンプトに「`[guid]::newGuid()`」または「`New-Guid`」と入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="23945-178">To generate one using PowerShell enter the following at the PS prompt and press enter: `[guid]::newGuid()` or `New-Guid`.</span></span> <span data-ttu-id="23945-179">このキーは、登録時にクライアント ノードによって認証のために共有キーとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="23945-179">This key will be used by client nodes as a shared key to authenticate during registration.</span></span> <span data-ttu-id="23945-180">詳細については、この後の「登録キー」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="23945-180">For more information, see the Registration Key section below.</span></span>
1. <span data-ttu-id="23945-181">PowerShell ISE で、次の構成スクリプトを起動 (<kbd>F5</kbd>) します (**xPSDesiredStateConfiguration** モジュールのフォルダーに `Sample_xDscWebServiceRegistration.ps1` として含まれています)。</span><span class="sxs-lookup"><span data-stu-id="23945-181">In the PowerShell ISE, start (<kbd>F5</kbd>) the following configuration script (included in the folder of the **xPSDesiredStateConfiguration** module as `Sample_xDscWebServiceRegistration.ps1`) .</span></span> <span data-ttu-id="23945-182">このスクリプトは、プル サーバーをセットアップします。</span><span class="sxs-lookup"><span data-stu-id="23945-182">This script sets up the pull server.</span></span>

    ```powershell
    configuration Sample_xDscWebServiceRegistration
    {
        param
        (
            [string[]]$NodeName = 'localhost',

            [ValidateNotNullOrEmpty()]
            [string] $certificateThumbPrint,

            [Parameter(HelpMessage='This should be a string with enough entropy (randomness) to protect the registration of clients to the pull server.  We will use new GUID by default.')]
            [ValidateNotNullOrEmpty()]
            [string] $RegistrationKey   # A guid that clients use to initiate conversation with pull server
        )

        Import-DSCResource -ModuleName PSDesiredStateConfiguration
        Import-DSCResource -ModuleName xPSDesiredStateConfiguration

        Node $NodeName
        {
            WindowsFeature DSCServiceFeature
            {
                Ensure = "Present"
                Name   = "DSC-Service"
            }

            xDscWebService PSDSCPullServer
            {
                Ensure                  = "Present"
                EndpointName            = "PSDSCPullServer"
                Port                    = 8080
                PhysicalPath            = "$env:SystemDrive\inetpub\PSDSCPullServer"
                CertificateThumbPrint   = $certificateThumbPrint
                ModulePath              = "$env:PROGRAMFILES\WindowsPowerShell\DscService\Modules"
                ConfigurationPath       = "$env:PROGRAMFILES\WindowsPowerShell\DscService\Configuration"
                State                   = "Started"
                DependsOn               = "[WindowsFeature]DSCServiceFeature"
                RegistrationKeyPath     = "$env:PROGRAMFILES\WindowsPowerShell\DscService"
                AcceptSelfSignedCertificates = $true
                UseSecurityBestPractices     = $true
                Enable32BitAppOnWin64   = $false
            }

            File RegistrationKeyFile
            {
                Ensure          = 'Present'
                Type            = 'File'
                DestinationPath = "$env:ProgramFiles\WindowsPowerShell\DscService\RegistrationKeys.txt"
                Contents        = $RegistrationKey
            }
        }
    }
    ```

1. <span data-ttu-id="23945-183">構成を実行します。このとき、SSL 証明書の拇印を **certificateThumbPrint** パラメーターとして渡し、GUID 登録キーを **RegistrationKey** パラメーターとして渡します。</span><span class="sxs-lookup"><span data-stu-id="23945-183">Run the configuration, passing the thumbprint of the SSL certificate as the **certificateThumbPrint** parameter and a GUID registration key as the **RegistrationKey** parameter:</span></span>

    ```powershell
    # To find the Thumbprint for an installed SSL certificate for use with the pull server list all certificates in your local store
    # and then copy the thumbprint for the appropriate certificate by reviewing the certificate subjects
    dir Cert:\LocalMachine\my

    # Then include this thumbprint when running the configuration
    Sample_xDscWebServiceRegistration -certificateThumbprint 'A7000024B753FA6FFF88E966FD6E19301FAE9CCC' -RegistrationKey '140a952b-b9d6-406b-b416-e0f759c9c0e4' -OutputPath c:\Configs\PullServer

    # Run the compiled configuration to make the target node a DSC Pull Server
    Start-DscConfiguration -Path c:\Configs\PullServer -Wait -Verbose
    ```

#### <a name="registration-key"></a><span data-ttu-id="23945-184">登録キー</span><span class="sxs-lookup"><span data-stu-id="23945-184">Registration Key</span></span>

<span data-ttu-id="23945-185">サーバーにクライアント ノードを登録して、構成 ID の代わりに構成名を使用できるように、上の構成で作成された登録キーは、`C:\Program Files\WindowsPowerShell\DscService` にある `RegistrationKeys.txt` という名前のファイルに保存されます。</span><span class="sxs-lookup"><span data-stu-id="23945-185">To allow client nodes to register with the server so that they can use configuration names instead of a configuration ID, a registration key that was created by the above configuration is saved in a file named `RegistrationKeys.txt` in `C:\Program Files\WindowsPowerShell\DscService`.</span></span> <span data-ttu-id="23945-186">登録キーは、クライアントがプル サーバーに初期登録を行うときに共有シークレットとして機能します。</span><span class="sxs-lookup"><span data-stu-id="23945-186">The registration key functions as a shared secret used during the initial registration by the client with the pull server.</span></span> <span data-ttu-id="23945-187">登録が正常に完了すると、クライアントは、プル サーバーに一意に認証されるために使う自己署名証明書を生成します。</span><span class="sxs-lookup"><span data-stu-id="23945-187">The client will generate a self-signed certificate that is used to uniquely authenticate to the pull server once registration is successfully completed.</span></span> <span data-ttu-id="23945-188">この証明書の拇印がローカルに保存され、プル サーバーの URL に関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="23945-188">The thumbprint of this certificate is stored locally and associated with the URL of the pull server.</span></span>

> [!NOTE]
> <span data-ttu-id="23945-189">登録キーは、PowerShell 4.0 ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="23945-189">Registration keys are not supported in PowerShell 4.0.</span></span>

<span data-ttu-id="23945-190">プル サーバーで認証するようにノードを構成するには、登録キーが、このプル サーバーに登録されるすべてのターゲット ノードのメタ構成に含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="23945-190">In order to configure a node to authenticate with the pull server, the registration key needs to be in the metaconfiguration for any target node that will be registering with this pull server.</span></span> <span data-ttu-id="23945-191">なお、次のメタ構成にある **RegistrationKey** は、ターゲット コンピューターが正常に登録された後に削除され、値はプル サーバーの `RegistrationKeys.txt` ファイルに格納されている値と一致する必要があります (この例では '140a952b-b9d6-406b-b416-e0f759c9c0e4')。</span><span class="sxs-lookup"><span data-stu-id="23945-191">Note that the **RegistrationKey** in the metaconfiguration below is removed after the target machine has successfully registered, and that the value must match the value stored in the `RegistrationKeys.txt` file on the pull server ('140a952b-b9d6-406b-b416-e0f759c9c0e4' for this example).</span></span> <span data-ttu-id="23945-192">登録キー値を知ると、任意のターゲット コンピューターをプル サーバーに登録できるようになるので、登録キー値は常にセキュリティで保護してください。</span><span class="sxs-lookup"><span data-stu-id="23945-192">Always treat the registration key value securely, because knowing it allows any target machine to register with the pull server.</span></span>

```powershell
[DSCLocalConfigurationManager()]
configuration Sample_MetaConfigurationToRegisterWithLessSecurePullServer
{
    param
    (
        [ValidateNotNullOrEmpty()]
        [string] $NodeName = 'localhost',

        [ValidateNotNullOrEmpty()]
        [string] $RegistrationKey, #same as the one used to set up pull server in previous configuration

        [ValidateNotNullOrEmpty()]
        [string] $ServerName = 'localhost' #node name of the pull server, same as $NodeName used in previous configuration
    )

    Node $NodeName
    {
        Settings
        {
            RefreshMode        = 'Pull'
        }

        ConfigurationRepositoryWeb CONTOSO-PullSrv
        {
            ServerURL          = "https://$ServerName`:8080/PSDSCPullServer.svc" # notice it is https
            RegistrationKey    = $RegistrationKey
            ConfigurationNames = @('ClientConfig')
        }

        ReportServerWeb CONTOSO-PullSrv
        {
            ServerURL       = "https://$ServerName`:8080/PSDSCPullServer.svc" # notice it is https
            RegistrationKey = $RegistrationKey
        }
    }
}

Sample_MetaConfigurationToRegisterWithLessSecurePullServer -RegistrationKey $RegistrationKey -OutputPath c:\Configs\TargetNodes
```

> [!NOTE]
> <span data-ttu-id="23945-193">**ReportServerWeb** セクションでは、レポートするデータをプル サーバーに送信できるようにしています。</span><span class="sxs-lookup"><span data-stu-id="23945-193">The **ReportServerWeb** section allows reporting data to be sent to the pull server.</span></span>

<span data-ttu-id="23945-194">メタ構成ファイルに **ConfigurationID** プロパティがないことは、暗黙的に、そのプル サーバーが V2 バージョンのプル サーバー プロトコルをサポートしていることを示すので、初期登録が必要になります。</span><span class="sxs-lookup"><span data-stu-id="23945-194">The lack of the **ConfigurationID** property in the metaconfiguration file implicitly means that pull server is supporting the V2 version of the pull server protocol so an initial registration is required.</span></span> <span data-ttu-id="23945-195">逆に、**ConfigurationID** が存在することは、V1 バージョンのプル サーバー プロトコルが使用され、登録処理がないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="23945-195">Conversely, the presence of a **ConfigurationID** means that the V1 version of the pull server protocol is used and there is no registration processing.</span></span>

> [!NOTE]
> <span data-ttu-id="23945-196">プッシュのシナリオでは、現在のリリースにバグが存在するため、プル サーバーに登録されていないノードにも、メタ構成ファイルに ConfigurationID プロパティを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="23945-196">In a PUSH scenario, a bug exists in the current release that makes it necessary to define a ConfigurationID property in the metaconfiguration file for nodes that have never registered with a pull server.</span></span> <span data-ttu-id="23945-197">こうすると、V1 プル サーバー プロトコルが強制されるので、登録エラーのメッセージが表示されません。</span><span class="sxs-lookup"><span data-stu-id="23945-197">This will force the V1 Pull Server protocol and avoid registration failure messages.</span></span>

## <a name="placing-configurations-and-resources"></a><span data-ttu-id="23945-198">構成とリソースの配置</span><span class="sxs-lookup"><span data-stu-id="23945-198">Placing configurations and resources</span></span>

<span data-ttu-id="23945-199">プル サーバーのセットアップが完了すると、プル サーバーの構成で **ConfigurationPath** プロパティと **ModulePath** プロパティによって定義されているフォルダーは、プルするためにターゲット ノードで使用可能にするモジュールと構成を配置する場所になります。</span><span class="sxs-lookup"><span data-stu-id="23945-199">After the pull server setup completes, the folders defined by the **ConfigurationPath** and **ModulePath** properties in the pull server configuration are where you will place modules and configurations that will be available for target nodes to pull.</span></span> <span data-ttu-id="23945-200">これらのファイルをプル サーバーが正しく処理するためには、特定の形式である必要があります。</span><span class="sxs-lookup"><span data-stu-id="23945-200">These files need to be in a specific format in order for the pull server to correctly process them.</span></span>

### <a name="dsc-resource-module-package-format"></a><span data-ttu-id="23945-201">DSC リソース モジュールのパッケージの形式</span><span class="sxs-lookup"><span data-stu-id="23945-201">DSC resource module package format</span></span>

<span data-ttu-id="23945-202">各リソース モジュールは、圧縮し、`{Module Name}_{Module Version}.zip` というパターンで名前を付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="23945-202">Each resource module needs to be zipped and named according to the following pattern `{Module Name}_{Module Version}.zip`.</span></span>

<span data-ttu-id="23945-203">たとえば、モジュール名が **xWebAdminstration** で、バージョンが 3.1.2.0 のモジュールでは、`xWebAdministration_3.1.2.0.zip` という名前になります。</span><span class="sxs-lookup"><span data-stu-id="23945-203">For example, a module named **xWebAdminstration** with a module version of 3.1.2.0 would be named `xWebAdministration_3.1.2.0.zip`.</span></span> <span data-ttu-id="23945-204">各バージョンのモジュールを 1 つの zip ファイルに含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="23945-204">Each version of a module must be contained in a single zip file.</span></span>
<span data-ttu-id="23945-205">各 zip ファイルには 1 つのバージョンのリソースのみが含まれるので、WMF 5.0 で追加された、単一のディレクトリに複数のモジュール バージョンを入れるモジュール形式はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="23945-205">Since there is only a single version of a resource in each zip file, the module format added in WMF 5.0 with support for multiple module versions in a single directory is not supported.</span></span> <span data-ttu-id="23945-206">このため、プル サーバーで使うための DSC リソース モジュールをパッケージ化する前に、ディレクトリ構造に少しの変更が必要です。</span><span class="sxs-lookup"><span data-stu-id="23945-206">This means that before packaging up DSC resource modules for use with pull server you will need to make a small change to the directory structure.</span></span> <span data-ttu-id="23945-207">WMF 5.0 の DSC リソースを含むモジュールの既定の形式は、`{Module Folder}\{Module Version}\DscResources\{DSC Resource Folder}\` です。</span><span class="sxs-lookup"><span data-stu-id="23945-207">The default format of modules containing DSC resource in WMF 5.0 is `{Module Folder}\{Module Version}\DscResources\{DSC Resource Folder}\`.</span></span> <span data-ttu-id="23945-208">プル サーバー用にパッケージ化する前に、パスが `{Module Folder}\DscResources\{DSC Resource Folder}\` になるように **{Module version}** フォルダーを削除します。</span><span class="sxs-lookup"><span data-stu-id="23945-208">Before packaging up for the pull server, remove the **{Module version}** folder so the path becomes `{Module Folder}\DscResources\{DSC Resource Folder}\`.</span></span> <span data-ttu-id="23945-209">この変更を加えた後、上で説明したようにフォルダーを zip 圧縮し、これらの zip ファイルを **ModulePath** フォルダーに置きます。</span><span class="sxs-lookup"><span data-stu-id="23945-209">With this change, zip the folder as described above and place these zip files in the **ModulePath** folder.</span></span>

<span data-ttu-id="23945-210">新しく追加したモジュールのチェックサム ファイルを作成するには、`New-DscChecksum {module zip file}` を使用します。</span><span class="sxs-lookup"><span data-stu-id="23945-210">Use `New-DscChecksum {module zip file}` to create a checksum file for the newly added module.</span></span>

### <a name="configuration-mof-format"></a><span data-ttu-id="23945-211">構成 MOF の形式</span><span class="sxs-lookup"><span data-stu-id="23945-211">Configuration MOF format</span></span>

<span data-ttu-id="23945-212">ターゲット ノード上の LCM が構成を検証できるように、構成 MOF ファイルはチェックサム ファイルと組み合わせて使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="23945-212">A configuration MOF file needs to be paired with a checksum file so that an LCM on a target node can validate the configuration.</span></span> <span data-ttu-id="23945-213">チェックサムを作成するには、[New-DscChecksum](/powershell/module/PSDesiredStateConfiguration/New-DSCCheckSum) コマンドレットを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="23945-213">To create a checksum, call the [New-DscChecksum](/powershell/module/PSDesiredStateConfiguration/New-DSCCheckSum) cmdlet.</span></span> <span data-ttu-id="23945-214">このコマンドレットは、構成 MOF が存在するフォルダーが指定された **Path** パラメーターを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="23945-214">The cmdlet takes a **Path** parameter that specifies the folder where the configuration MOF is located.</span></span> <span data-ttu-id="23945-215">このコマンドレットは、`ConfigurationMOFName.mof.checksum` という名前でチェックサム ファイルを作成します。ここで、`ConfigurationMOFName` は構成 MOF ファイルの名前です。</span><span class="sxs-lookup"><span data-stu-id="23945-215">The cmdlet creates a checksum file named `ConfigurationMOFName.mof.checksum`, where `ConfigurationMOFName` is the name of the configuration mof file.</span></span> <span data-ttu-id="23945-216">指定のフォルダーに複数の構成 MOF ファイルがある場合は、そのフォルダー内の構成ごとにチェックサムが作成されます。</span><span class="sxs-lookup"><span data-stu-id="23945-216">If there are more than one configuration MOF files in the specified folder, a checksum is created for each configuration in the folder.</span></span> <span data-ttu-id="23945-217">MOF ファイルと、それに関連するチェックサム ファイルは、**ConfigurationPath** フォルダーに配置します。</span><span class="sxs-lookup"><span data-stu-id="23945-217">Place the MOF files and their associated checksum files in the **ConfigurationPath** folder.</span></span>

> [!NOTE]
> <span data-ttu-id="23945-218">何らかの方法で構成 MOF ファイルを変更した場合は、チェックサム ファイルも作成し直す必要があります。</span><span class="sxs-lookup"><span data-stu-id="23945-218">If you change the configuration MOF file in any way, you must also recreate the checksum file.</span></span>

### <a name="tooling"></a><span data-ttu-id="23945-219">ツール</span><span class="sxs-lookup"><span data-stu-id="23945-219">Tooling</span></span>

<span data-ttu-id="23945-220">プル サーバーのセットアップ、検証、管理を簡素化するために、次のツールが、xPSDesiredStateConfiguration モジュールの最新バージョンに例として含まれています。</span><span class="sxs-lookup"><span data-stu-id="23945-220">In order to make setting up, validating and managing the pull server easier, the following tools are included as examples in the latest version of the xPSDesiredStateConfiguration module:</span></span>

1. <span data-ttu-id="23945-221">プル サーバーに使用する DSC リソース モジュールおよび構成ファイルをパッケージ化するために役立つモジュール。</span><span class="sxs-lookup"><span data-stu-id="23945-221">A module that will help with packaging DSC resource modules and configuration files for use on the pull server.</span></span>
   <span data-ttu-id="23945-222">[PublishModulesAndMofsToPullServer.psm1](https://github.com/dsccommunity/xPSDesiredStateConfiguration/blob/master/source/Modules/DscPullServerSetup/DscPullServerSetup.psm1)。</span><span class="sxs-lookup"><span data-stu-id="23945-222">[PublishModulesAndMofsToPullServer.psm1](https://github.com/dsccommunity/xPSDesiredStateConfiguration/blob/master/source/Modules/DscPullServerSetup/DscPullServerSetup.psm1).</span></span>
   <span data-ttu-id="23945-223">次の例です。</span><span class="sxs-lookup"><span data-stu-id="23945-223">Examples below:</span></span>

    ```powershell
        # Example 1 - Package all versions of given modules installed locally and MOF files are in c:\LocalDepot
         $moduleList = @('xWebAdministration', 'xPhp')
         Publish-DSCModuleAndMof -Source C:\LocalDepot -ModuleNameList $moduleList

         # Example 2 - Package modules and mof documents from c:\LocalDepot
         Publish-DSCModuleAndMof -Source C:\LocalDepot -Force
    ```

1. <span data-ttu-id="23945-224">プル サーバーが正しく構成されていることを検証するスクリプト。</span><span class="sxs-lookup"><span data-stu-id="23945-224">A script that validates the pull server is configured correctly.</span></span> <span data-ttu-id="23945-225">[PullServerSetupTests.ps1](https://github.com/dsccommunity/xPSDesiredStateConfiguration/blob/master/source/Modules/DscPullServerSetup/DscPullServerSetupTest/DscPullServerSetupTest.ps1)。</span><span class="sxs-lookup"><span data-stu-id="23945-225">[PullServerSetupTests.ps1](https://github.com/dsccommunity/xPSDesiredStateConfiguration/blob/master/source/Modules/DscPullServerSetup/DscPullServerSetupTest/DscPullServerSetupTest.ps1).</span></span>

## <a name="community-solutions-for-pull-service"></a><span data-ttu-id="23945-226">プル サービスのコミュニティ ソリューション</span><span class="sxs-lookup"><span data-stu-id="23945-226">Community Solutions for Pull Service</span></span>

<span data-ttu-id="23945-227">DSC コミュニティは、プル サービス プロトコルを実装するための複数のソリューションを作成しています。</span><span class="sxs-lookup"><span data-stu-id="23945-227">The DSC community has authored multiple solutions to implement the pull service protocol.</span></span> <span data-ttu-id="23945-228">これらはオンプレミス環境向けに、プル サービス機能と、段階的な機能強化でコミュニティに貢献する機会を提供します。</span><span class="sxs-lookup"><span data-stu-id="23945-228">For on-premises environments, these offer pull service capabilities and an opportunity to contribute back to the community with incremental enhancements.</span></span>

- [<span data-ttu-id="23945-229">Tug</span><span class="sxs-lookup"><span data-stu-id="23945-229">Tug</span></span>](https://github.com/powershellorg/tug)
- [<span data-ttu-id="23945-230">DSC-TRÆK</span><span class="sxs-lookup"><span data-stu-id="23945-230">DSC-TRÆK</span></span>](https://github.com/powershellorg/dsc-traek)

## <a name="pull-client-configuration"></a><span data-ttu-id="23945-231">プル クライアントの構成</span><span class="sxs-lookup"><span data-stu-id="23945-231">Pull client configuration</span></span>

<span data-ttu-id="23945-232">次のトピックでは、プル クライアントのセットアップについて詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="23945-232">The following topics describe setting up pull clients in detail:</span></span>

- [<span data-ttu-id="23945-233">構成 ID を使用したプル クライアントのセットアップ</span><span class="sxs-lookup"><span data-stu-id="23945-233">Set up a DSC pull client using a configuration ID</span></span>](pullClientConfigID.md)
- [<span data-ttu-id="23945-234">構成名を使用したプル クライアントのセットアップ</span><span class="sxs-lookup"><span data-stu-id="23945-234">Set up a DSC pull client using configuration names</span></span>](pullClientConfigNames.md)
- [<span data-ttu-id="23945-235">部分構成</span><span class="sxs-lookup"><span data-stu-id="23945-235">Partial configurations</span></span>](partialConfigs.md)

## <a name="see-also"></a><span data-ttu-id="23945-236">参照</span><span class="sxs-lookup"><span data-stu-id="23945-236">See also</span></span>

- [<span data-ttu-id="23945-237">Windows PowerShell Desired State Configuration の概要</span><span class="sxs-lookup"><span data-stu-id="23945-237">Windows PowerShell Desired State Configuration Overview</span></span>](../overview/overview.md)
- [<span data-ttu-id="23945-238">構成の適用</span><span class="sxs-lookup"><span data-stu-id="23945-238">Enacting configurations</span></span>](enactingConfigurations.md)
- [<span data-ttu-id="23945-239">DSC レポート サーバーの使用</span><span class="sxs-lookup"><span data-stu-id="23945-239">Using a DSC report server</span></span>](reportServer.md)
- <span data-ttu-id="23945-240">[[MS-DSCPM]: Desired State Configuration Pull Model プロトコル](/openspecs/windows_protocols/ms-dscpm/ea744c01-51a2-4000-9ef2-312711dcc8c9)</span><span class="sxs-lookup"><span data-stu-id="23945-240">[[MS-DSCPM]: Desired State Configuration Pull Model Protocol](/openspecs/windows_protocols/ms-dscpm/ea744c01-51a2-4000-9ef2-312711dcc8c9)</span></span>
- <span data-ttu-id="23945-241">[[MS-DSCPM]: Desired State Configuration Pull Model プロトコルの正誤表](/openspecs/windows_protocols/ms-winerrata/f5fc7ae3-9172-41e8-ac6a-2a5a5b7bfaf5)</span><span class="sxs-lookup"><span data-stu-id="23945-241">[[MS-DSCPM]: Desired State Configuration Pull Model Protocol Errata](/openspecs/windows_protocols/ms-winerrata/f5fc7ae3-9172-41e8-ac6a-2a5a5b7bfaf5)</span></span>
