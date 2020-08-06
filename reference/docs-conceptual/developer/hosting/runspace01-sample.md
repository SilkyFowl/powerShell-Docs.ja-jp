---
title: Runspace01 サンプル |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 1ac286512f3cb3b97a6b3179c9dd45f1fefe1ecf
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87772197"
---
# <a name="runspace01-sample"></a><span data-ttu-id="21286-102">Runspace01 サンプル</span><span class="sxs-lookup"><span data-stu-id="21286-102">Runspace01 Sample</span></span>

<span data-ttu-id="21286-103">このサンプルでは、 [system.servicemodel クラスを](/dotnet/api/system.management.automation.powershell)使用して、 [Get Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process)コマンドレットを同期的に実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="21286-103">This sample shows how to use the [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) class to run the [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) cmdlet synchronously.</span></span> <span data-ttu-id="21286-104">[Get process](/powershell/module/Microsoft.PowerShell.Management/Get-Process)コマンドレットは、ローカルコンピューター上で実行されている各プロセスの[system.object オブジェクトを返します。](/dotnet/api/System.Diagnostics.Process)</span><span class="sxs-lookup"><span data-stu-id="21286-104">The [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) cmdlet returns [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) objects for each process running on the local computer.</span></span> <span data-ttu-id="21286-105">次に、返されたオブジェクトから抽出され、コンソールウィンドウに表示される、 [Processname \*](/dotnet/api/System.Diagnostics.Process.ProcessName) [プロパティと \* プロパティ](/dotnet/api/System.Diagnostics.Process.Handlecount)の値を抽出します。</span><span class="sxs-lookup"><span data-stu-id="21286-105">The values of the [System.Diagnostics.Process.Processname\*](/dotnet/api/System.Diagnostics.Process.ProcessName) and [System.Diagnostics.Process.Handlecount\*](/dotnet/api/System.Diagnostics.Process.Handlecount) properties are then extracted from the returned objects and displayed in a console window.</span></span>

## <a name="requirements"></a><span data-ttu-id="21286-106">必要条件</span><span class="sxs-lookup"><span data-stu-id="21286-106">Requirements</span></span>

 <span data-ttu-id="21286-107">このサンプルには、Windows PowerShell 2.0 が必要です。</span><span class="sxs-lookup"><span data-stu-id="21286-107">This sample requires Windows PowerShell 2.0.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="21286-108">対象</span><span class="sxs-lookup"><span data-stu-id="21286-108">Demonstrates</span></span>

- <span data-ttu-id="21286-109">コマンドを実行するための、 [system.servicemodel オブジェクトの作成。](/dotnet/api/system.management.automation.powershell)</span><span class="sxs-lookup"><span data-stu-id="21286-109">Creating a [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object to run a command.</span></span>

- <span data-ttu-id="21286-110">コマンドを、[システムの管理](/dotnet/api/system.management.automation.powershell)オブジェクトのパイプラインに追加します。</span><span class="sxs-lookup"><span data-stu-id="21286-110">Adding a command to the pipeline of the [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object.</span></span>

- <span data-ttu-id="21286-111">コマンドを同期的に実行します。</span><span class="sxs-lookup"><span data-stu-id="21286-111">Running the command synchronously.</span></span>

- <span data-ttu-id="21286-112">コマンドによって返されたオブジェクトからプロパティを抽出するには、[を使用します。](/dotnet/api/System.Management.Automation.PSObject)</span><span class="sxs-lookup"><span data-stu-id="21286-112">Using [System.Management.Automation.PSObject](/dotnet/api/System.Management.Automation.PSObject) objects to extract properties from the objects returned by the command.</span></span>

## <a name="example"></a><span data-ttu-id="21286-113">例</span><span class="sxs-lookup"><span data-stu-id="21286-113">Example</span></span>

 <span data-ttu-id="21286-114">このサンプルでは、Windows PowerShell によって提供される既定の実行空間で、 [Get Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process)コマンドレットを同期的に実行します。</span><span class="sxs-lookup"><span data-stu-id="21286-114">This sample runs the [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) cmdlet synchronously in the default runspace provided by Windows PowerShell.</span></span>

```csharp
namespace Microsoft.Samples.PowerShell.Runspaces
{
  using System;
  using System.Management.Automation;
  using PowerShell = System.Management.Automation.PowerShell;

  /// <summary>
  /// This class contains the Main entry point for this host application.
  /// </summary>
  internal class Runspace01
  {
    /// <summary>
    /// This sample uses the PowerShell class to execute
    /// the get-process cmdlet synchronously. The name and
    /// handlecount are then extracted from the PSObjects
    /// returned and displayed.
    /// </summary>
    /// <param name="args">Parameter not used.</param>
    /// <remarks>
    /// This sample demonstrates the following:
    /// 1. Creating a PowerShell object to run a command.
    /// 2. Adding a command to the pipeline of the PowerShell object.
    /// 3. Running the command synchronously.
    /// 4. Using PSObject objects to extract properties from the objects
    ///    returned by the command.
    /// </remarks>
    private static void Main(string[] args)
    {
      // Create a PowerShell object. Creating this object takes care of
      // building all of the other data structures needed to run the command.
      using (PowerShell powershell = PowerShell.Create().AddCommand("get-process"))
      {
        Console.WriteLine("Process              HandleCount");
        Console.WriteLine("--------------------------------");

        // Invoke the command synchronously and display the
        // ProcessName and HandleCount properties of the
        // objects that are returned.
        foreach (PSObject result in powershell.Invoke())
        {
          Console.WriteLine(
                      "{0,-20} {1}",
                      result.Members["ProcessName"].Value,
                      result.Members["HandleCount"].Value);
        }
      }

      System.Console.WriteLine("Hit any key to exit...");
      System.Console.ReadKey();
    }
  }
}
```

## <a name="see-also"></a><span data-ttu-id="21286-115">参照</span><span class="sxs-lookup"><span data-stu-id="21286-115">See Also</span></span>
