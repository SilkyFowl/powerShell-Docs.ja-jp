---
ms.date: 06/05/2017
keywords: powershell,コマンドレット
title: サービスの管理
description: PowerShell には、ローカル コンピューター上およびリモート コンピューター上のサービスを管理するのに役立つコマンドレットがいくつか用意されています。
ms.openlocfilehash: 003803cdaa37e51b3788f3f897cbec7d6e243ca8
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2020
ms.locfileid: "92500353"
---
# <a name="managing-services"></a>サービスの管理

サービスに関連したさまざまなタスクを実行するために設計された 8 つの主要な Service コマンドレットがあります。 ここでは、サービスの実行状態の一覧表示と変更についてのみ説明しますが、`Get-Help \*-Service` でサービスに関連したコマンドレットを一覧表示したり、`Get-Help <Cmdlet-Name>` (`Get-Help New-Service` など) でサービスに関連した各種コマンドレットの情報を検索したりできます。

## <a name="getting-services"></a>サービスの取得

`Get-Service` コマンドレットを使用して、ローカル コンピューターまたはリモート コンピューター上のサービスを取得できます。 `Get-Process` と同様、パラメーターを指定せずに `Get-Service` コマンドを実行した場合、すべてのサービスが返されます。 アスタリスクをワイルドカードとして使用し、サービスを名前でフィルター処理するには、次のように入力します。

```powershell
PS> Get-Service -Name se*

Status   Name               DisplayName
------   ----               -----------
Running  seclogon           Secondary Logon
Running  SENS               System Event Notification
Stopped  ServiceLayer       ServiceLayer
```

サービスの実際の名前がわかるとは限らないため、表示名でサービスを検索しなければならない場合もあります。 特定の名前を指定するか、ワイルドカードを使用するか、または表示名の一覧を使用することによって検索できます。

```powershell
PS> Get-Service -DisplayName se*

Status   Name               DisplayName
------   ----               -----------
Running  lanmanserver       Server
Running  SamSs              Security Accounts Manager
Running  seclogon           Secondary Logon
Stopped  ServiceLayer       ServiceLayer
Running  wscsvc             Security Center

PS> Get-Service -DisplayName ServiceLayer,Server

Status   Name               DisplayName
------   ----               -----------
Running  lanmanserver       Server
Stopped  ServiceLayer       ServiceLayer
```

Get-Service コマンドレットの ComputerName パラメーターを使用して、リモート コンピューター上のサービスを取得できます。 ComputerName パラメーターには複数の値およびワイルドカード文字を使用できるため、1 つのコマンドで複数のコンピューター上のサービスを取得できます。 たとえば、次のコマンドでは、Server01 リモート コンピューター上のサービスを取得できます。

```powershell
Get-Service -ComputerName Server01
```

## <a name="getting-required-and-dependent-services"></a>必要なサービスおよび依存するサービスの取得

Get-Service コマンドレットには、サービスの管理に非常に便利な 2 つのパラメーターがあります。 DependentServices パラメーターは、そのサービスに依存するサービスを取得します。 RequiredServices パラメーターは、そのサービスが依存しているサービスを取得します。

これらのパラメーターは、Get-Service が返す System.ServiceProcess.ServiceController オブジェクトの DependentServices プロパティと ServicesDependedOn (エイリアス: RequiredServices) プロパティの値を表示するだけですが、コマンドが単純化され、この情報をずっと簡単に取得できるようになります。

次のコマンドは、LanmanWorkstation サービスが必要とするサービスを取得します。

```powershell
PS> Get-Service -Name LanmanWorkstation -RequiredServices

Status   Name               DisplayName
------   ----               -----------
Running  MRxSmb20           SMB 2.0 MiniRedirector
Running  bowser             Bowser
Running  MRxSmb10           SMB 1.x MiniRedirector
Running  NSI                Network Store Interface Service
```

次のコマンドは、LanmanWorkstation サービスを必要とするサービスを取得します。

```powershell
PS> Get-Service -Name LanmanWorkstation -DependentServices

Status   Name               DisplayName
------   ----               -----------
Running  SessionEnv         Terminal Services Configuration
Running  Netlogon           Netlogon
Stopped  Browser            Computer Browser
Running  BITS               Background Intelligent Transfer Ser...
```

また、依存関係を持つサービスをすべて取得することもできます。 次のコマンドは、それを実行した後、Format-Table コマンドレットを使用して、コンピューター上のサービスの Status、Name、RequiredServices、DependentServices の各プロパティを表示します。

```powershell
Get-Service -Name * | Where-Object {$_.RequiredServices -or $_.DependentServices} |
  Format-Table -Property Status, Name, RequiredServices, DependentServices -auto
```

## <a name="stopping-starting-suspending-and-restarting-services"></a>サービスの停止、開始、一時停止、再開

サービスを扱うすべてのコマンドレットは、同じ形式で指定できます。 サービスを一般的な名前 (表示名) で指定できるほか、表示名の一覧を指定したり、ワイルドカードを値として使用したりすることもできます。 印刷スプーラーを停止するには、次のように入力します。

```powershell
Stop-Service -Name spooler
```

停止した印刷スプーラーを開始するには、次のように入力します。

```powershell
Start-Service -Name spooler
```

印刷スプーラーを一時停止するには、次のように入力します。

```powershell
Suspend-Service -Name spooler
```

`Restart-Service` コマンドレットの動作も、サービスを扱う他のコマンドレットと同じですが、もう少し複雑な例を示します。 最も簡単な使い方は、サービスの名前を指定することです。

```powershell
PS> Restart-Service -Name spooler

WARNING: Waiting for service 'Print Spooler (Spooler)' to finish starting...
WARNING: Waiting for service 'Print Spooler (Spooler)' to finish starting...
PS>
```

印刷スプーラーの起動に関して、警告メッセージが繰り返し出力されていることがわかります。 ある程度時間のかかるサービス操作を実行すると、タスクの実行を試みている最中であることを示すメッセージが表示されます。

複数のサービスを再開する場合は、サービスの一覧を取得してからフィルターを適用し、その上でサービスを再開するようにします。

```powershell
PS> Get-Service | Where-Object -FilterScript {$_.CanStop} | Restart-Service

WARNING: Waiting for service 'Computer Browser (Browser)' to finish stopping...
WARNING: Waiting for service 'Computer Browser (Browser)' to finish stopping...
Restart-Service : Cannot stop service 'Logical Disk Manager (dmserver)' because
 it has dependent services. It can only be stopped if the Force flag is set.
At line:1 char:57
+ Get-Service | Where-Object -FilterScript {$_.CanStop} | Restart-Service <<<<
WARNING: Waiting for service 'Print Spooler (Spooler)' to finish starting...
WARNING: Waiting for service 'Print Spooler (Spooler)' to finish starting...
```

サービスを扱うこれらのコマンドレットには ComputerName パラメーターはありませんが、Invoke-Command コマンドレットを使用すれば、これらのコマンドレットをリモート コンピューター上で実行できます。 たとえば、次のコマンドでは、Server01 リモート コンピューター上のスプーラー サービスを再起動できます。

```powershell
Invoke-Command -ComputerName Server01 {Restart-Service Spooler}
```

## <a name="setting-service-properties"></a>サービスのプロパティの設定

`Set-Service` コマンドレットは、ローカル コンピューターまたはリモート コンピューター上のサービスのプロパティを変更します。 サービスの状態もプロパティの 1 つであるため、このコマンドレットを使用してサービスを開始、停止、一時停止できます。
Set-Service コマンドレットには、サービスのスタートアップの種類を変更できる StartupType パラメーターもあります。

Windows Vista 以降のバージョンの Windows で、`Set-Service` を使用するには、Windows PowerShell を開く際に [管理者として実行] オプションを指定する必要があります。

詳細については、「[Set-Service](/powershell/module/Microsoft.PowerShell.Management/set-service)」をご覧ください

## <a name="see-also"></a>参照

- [Get-Service](/powershell/module/Microsoft.PowerShell.Management/get-service)
- [Set-Service](/powershell/module/Microsoft.PowerShell.Management/set-service)
- [Restart-Service](/powershell/module/Microsoft.PowerShell.Management/restart-service)
- [Suspend-Service](/powershell/module/Microsoft.PowerShell.Management/suspend-service)
