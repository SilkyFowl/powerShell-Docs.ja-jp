---
title: GetProcessSample03 サンプル |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 09df93792ab611e167279bc35755d8d6c28e7cf3
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784216"
---
# <a name="getprocesssample03-sample"></a>GetProcessSample03 サンプル

このサンプルでは、ローカルコンピューター上のプロセスを取得するコマンドレットを実装する方法を示します。 このメソッドは、 `Name` パイプラインからのオブジェクト、またはプロパティ名がパラメーター名と同じであるオブジェクトのプロパティの値を受け取ることができるパラメーターを提供します。 このコマンドレットは、 `Get-Process` Windows PowerShell 2.0 によって提供されるコマンドレットの簡略化されたバージョンです。

## <a name="how-to-build-the-sample-using-visual-studio"></a>Visual Studio を使用してサンプルをビルドする方法。

1. Windows PowerShell 2.0 SDK がインストールされている状態で、GetProcessSample03 フォルダーに移動します。 既定の場所は C:\Program Files (x86) \Microsoft SDKs\Windows\v7.0\Samples\sysmgmt\WindowsPowerShell\csharp\GetProcessSample03. です。

2. ソリューション (.sln) ファイルのアイコンをダブルクリックします。 これにより、Visual Studio でサンプルプロジェクトが開きます。

3. **[ビルド]** メニューで、 **[ソリューションのビルド]** を選択します。

    サンプルのライブラリは、既定の \bin フォルダーまたは \bin\debug フォルダーに構築されます。

### <a name="how-to-run-the-sample"></a>サンプルを実行する方法

1. 次のモジュールフォルダーを作成します。

    `[user]/documents/windowspowershell/modules/GetProcessSample03`

2. サンプルアセンブリをモジュールフォルダーにコピーします。

3. Windows PowerShell を起動します。

4. 次のコマンドを実行して、Windows PowerShell にアセンブリを読み込みます。

    `Import-module getprossessample03`

5. 次のコマンドを実行して、コマンドレットを実行します。

    `get-proc`

## <a name="requirements"></a>必要条件

このサンプルには、Windows PowerShell 2.0 が必要です。

## <a name="demonstrates"></a>対象

このサンプルでは、次のことを示します。

- コマンドレットの属性を使用して、コマンドレットクラスを宣言します。

- Parameter 属性を使用してコマンドレットパラメーターを宣言しています。

- パラメーターの位置を指定します。

- パラメーターがパイプラインからの入力を受け取ることを指定します。 入力は、オブジェクトまたはプロパティ名がパラメーター名と同じであるオブジェクトのプロパティの値から取得できます。

- パラメーター入力の検証属性を宣言しています。

## <a name="example"></a>例

このサンプルでは、パイプラインからの入力を受け入れるパラメーターを含む、Get Proc コマンドレットの実装を示し `Name` ます。

```csharp
namespace Microsoft.Samples.PowerShell.Commands
{
  using System;
  using System.Diagnostics;
  using System.Management.Automation;           // Windows PowerShell namespace
  #region GetProcCommand

  /// <summary>
  /// This class implements the get-proc cmdlet.
  /// </summary>
  [Cmdlet(VerbsCommon.Get, "Proc")]
  public class GetProcCommand : Cmdlet
  {
    #region Parameters

    /// <summary>
    /// The names of the processes retrieved by the cmdlet.
    /// </summary>
    private string[] processNames;

    /// <summary>
    /// Gets or sets the names of the
    /// process that the cmdlet will retrieve.
    /// </summary>
    [Parameter(
               Position = 0,
               ValueFromPipeline = true,
               ValueFromPipelineByPropertyName = true)]
    [ValidateNotNullOrEmpty]
    public string[] Name
    {
      get { return this.processNames; }
      set { this.processNames = value; }
    }

    #endregion Parameters

    #region Cmdlet Overrides

    /// <summary>
    /// The ProcessRecord method calls the Process.GetProcesses
    /// method to retrieve the processes specified by the Name
    /// parameter. Then, the WriteObject method writes the
    /// associated processes to the pipeline.
    /// </summary>
    protected override void ProcessRecord()
    {
      // If no process names are passed to the cmdlet, get all
      // processes.
      if (this.processNames == null)
      {
        WriteObject(Process.GetProcesses(), true);
      }
      else
      {
        // If process names are passed to the cmdlet, get and write
        // the associated processes.
        foreach (string name in this.processNames)
        {
          WriteObject(Process.GetProcessesByName(name), true);
        }
      } // End if (processNames ...)
    } // End ProcessRecord.

    #endregion Overrides
  } // End GetProcCommand.
  #endregion GetProcCommand
}
```

## <a name="see-also"></a>参照

[Writing a Windows PowerShell Cmdlet (Windows PowerShell コマンドレットの記述)](./writing-a-windows-powershell-cmdlet.md)
