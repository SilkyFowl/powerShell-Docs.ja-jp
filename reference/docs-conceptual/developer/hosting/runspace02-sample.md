---
title: Runspace02 サンプル |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 7a2dce436aceb1d8744377c37671a66398614851
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784964"
---
# <a name="runspace02-sample"></a><span data-ttu-id="d596d-102">Runspace02 サンプル</span><span class="sxs-lookup"><span data-stu-id="d596d-102">Runspace02 Sample</span></span>

<span data-ttu-id="d596d-103">このサンプル[では、system.servicemodel クラスを](/dotnet/api/system.management.automation.powershell)使用して、 [Get Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process)および[Sort-Object](/powershell/module/Microsoft.PowerShell.Utility/Sort-Object)コマンドレットを同期的に実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="d596d-103">This sample shows how to use the [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) class to run the [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) and [Sort-Object](/powershell/module/Microsoft.PowerShell.Utility/Sort-Object) cmdlets synchronously.</span></span> <span data-ttu-id="d596d-104">[Get process](/powershell/module/Microsoft.PowerShell.Management/Get-Process)コマンドレットは、ローカルコンピューター上で実行[されて](/dotnet/api/System.Diagnostics.Process)いる各プロセスの System.Diagnostics.Process.Id オブジェクトを返し、はそれらのオブジェクトをその `Sort-Object` [\*](/dotnet/api/System.Diagnostics.Process.Id)プロパティに基づいて並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="d596d-104">The [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) cmdlet returns [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) objects for each process running on the local computer, and the `Sort-Object` sorts the objects based on their [System.Diagnostics.Process.Id\*](/dotnet/api/System.Diagnostics.Process.Id) property.</span></span> <span data-ttu-id="d596d-105">これらのコマンドの結果[は、system.string コントロールを](/dotnet/api/System.Windows.Forms.DataGridView)使用して表示されます。</span><span class="sxs-lookup"><span data-stu-id="d596d-105">The results of these commands is displayed by using a [System.Windows.Forms.Datagridview](/dotnet/api/System.Windows.Forms.DataGridView) control.</span></span>

## <a name="requirements"></a><span data-ttu-id="d596d-106">必要条件</span><span class="sxs-lookup"><span data-stu-id="d596d-106">Requirements</span></span>

<span data-ttu-id="d596d-107">このサンプルには、Windows PowerShell 2.0 が必要です。</span><span class="sxs-lookup"><span data-stu-id="d596d-107">This sample requires Windows PowerShell 2.0.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="d596d-108">対象</span><span class="sxs-lookup"><span data-stu-id="d596d-108">Demonstrates</span></span>

<span data-ttu-id="d596d-109">このサンプルでは、次のことを示します。</span><span class="sxs-lookup"><span data-stu-id="d596d-109">This sample demonstrates the following.</span></span>

- <span data-ttu-id="d596d-110">コマンドを実行するため[の、system.servicemodel](/dotnet/api/system.management.automation.powershell)オブジェクトの作成。</span><span class="sxs-lookup"><span data-stu-id="d596d-110">Creating a [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object to run commands.</span></span>

- <span data-ttu-id="d596d-111">System.servicemodel オブジェクトのパイプラインにコマンドを追加してい[ます。](/dotnet/api/system.management.automation.powershell)</span><span class="sxs-lookup"><span data-stu-id="d596d-111">Adding commands to the pipeline of [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object.</span></span>

- <span data-ttu-id="d596d-112">コマンドを同期的に実行します。</span><span class="sxs-lookup"><span data-stu-id="d596d-112">Running the commands synchronously.</span></span>

- <span data-ttu-id="d596d-113">Windows フォームアプリケーションのコマンドの出力を表示する[には、system.string コントロールを](/dotnet/api/System.Windows.Forms.DataGridView)使用します。</span><span class="sxs-lookup"><span data-stu-id="d596d-113">Using a [System.Windows.Forms.Datagridview](/dotnet/api/System.Windows.Forms.DataGridView) control to display the output of the commands in a Windows Forms application.</span></span>

## <a name="example"></a><span data-ttu-id="d596d-114">例</span><span class="sxs-lookup"><span data-stu-id="d596d-114">Example</span></span>

<span data-ttu-id="d596d-115">このサンプルでは、Windows PowerShell によって提供される既定の実行空間で、 [Get Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process)および[Sort オブジェクト](/powershell/module/Microsoft.PowerShell.Utility/Sort-Object)のコマンドレットを同期的に実行します。</span><span class="sxs-lookup"><span data-stu-id="d596d-115">This sample runs the [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) and [Sort-Object](/powershell/module/Microsoft.PowerShell.Utility/Sort-Object) cmdlets synchronously in the default runspace provided by Windows PowerShell.</span></span> <span data-ttu-id="d596d-116">出力は、[システム](/dotnet/api/System.Windows.Forms.DataGridView)のコントロールを使用してフォームに表示されます。</span><span class="sxs-lookup"><span data-stu-id="d596d-116">The output is displayed in a form using a [System.Windows.Forms.Datagridview](/dotnet/api/System.Windows.Forms.DataGridView) control.</span></span>

```csharp
namespace Microsoft.Samples.PowerShell.Runspaces
{
  using System;
  using System.Collections;
  using System.Collections.ObjectModel;
  using System.Management.Automation;
  using System.Management.Automation.Runspaces;
  using System.Windows.Forms;
  using PowerShell = System.Management.Automation.PowerShell;

  /// <summary>
  /// This class contains the Main entry point for this host application.
  /// </summary>
  internal class Runspace02
  {
    /// <summary>
    /// This method creates the form where the output is displayed.
    /// </summary>
    private static void CreateForm()
    {
      Form form = new Form();
      DataGridView grid = new DataGridView();
      form.Controls.Add(grid);
      grid.Dock = DockStyle.Fill;

      // Create a PowerShell object. Creating this object takes care of
      // building all of the other data structures needed to run the command.
      using (PowerShell powershell = PowerShell.Create())
      {
        powershell.AddCommand("get-process").AddCommand("sort-object").AddArgument("ID");
        if (Runspace.DefaultRunspace == null)
        {
          Runspace.DefaultRunspace = powershell.Runspace;
        }

        Collection<PSObject> results = powershell.Invoke();

        // The generic collection needs to be re-wrapped in an ArrayList
        // for data-binding to work.
        ArrayList objects = new ArrayList();
        objects.AddRange(results);

        // The DataGridView will use the PSObjectTypeDescriptor type
        // to retrieve the properties.
        grid.DataSource = objects;
      }

      form.ShowDialog();
    }

    /// <summary>
    /// This sample uses a PowerShell object to run the Get-Process
    /// and Sort-Object cmdlets synchronously. Windows Forms and
    /// data binding are then used to display the results in a
    /// DataGridView control.
    /// </summary>
    /// <param name="args">The parameter is not used.</param>
    /// <remarks>
    /// This sample demonstrates the following:
    /// 1. Creating a PowerShell object.
    /// 2. Adding commands and arguments to the pipeline of
    ///    the PowerShell object.
    /// 3. Running the commands synchronously.
    /// 4. Using a DataGridView control to display the output
    ///    of the commands in a Windows Forms application.
    /// </remarks>
    private static void Main(string[] args)
    {
      Runspace02.CreateForm();
    }
  }
}
```

## <a name="see-also"></a><span data-ttu-id="d596d-117">参照</span><span class="sxs-lookup"><span data-stu-id="d596d-117">See Also</span></span>

[<span data-ttu-id="d596d-118">Windows PowerShell ホスト アプリケーションを記述する</span><span class="sxs-lookup"><span data-stu-id="d596d-118">Writing a Windows PowerShell Host Application</span></span>](./writing-a-windows-powershell-host-application.md)
