---
title: コマンドレット内でスクリプトを呼び出す方法 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 248ad7e2e35fe53682836d094a391023007fa0b7
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784131"
---
# <a name="how-to-invoke-scripts-within-a-cmdlet"></a>コマンドレット内でスクリプトを呼び出す方法

この例は、コマンドレットに指定されたスクリプトを呼び出す方法を示しています。 スクリプトはコマンドレットによって実行され、その結果は、一連の[システム管理](/dotnet/api/System.Management.Automation.PSObject)オブジェクトのコレクションとしてコマンドレットに返されます。

## <a name="to-invoke-a-script-block"></a>スクリプトブロックを呼び出すには

1. コマンドは、スクリプトブロックがコマンドレットに渡されたことを確認します。 スクリプトブロックが指定されている場合、コマンドは、必要なパラメーターを指定してスクリプトブロックを呼び出します。

    ```csharp
    if (script != null)
    {
      WriteDebug("Executing script block.");

      // Invoke the script block with the required arguments.
      Collection<PSObject> PSObjects =
                     script.Invoke(
                                   line,
                                   simpleMatch,
                                   caseSensitive
                                  );
    ```

2. 次に、返された一連の[システム](/dotnet/api/System.Management.Automation.PSObject)オブジェクトを反復処理し、必要な操作を実行します。

    ```c
    foreach (PSObject psObject in psObjects)
    {
      if (LanguagePrimitives.IsTrue(psObject))
      {
        result = new MatchInfo();
        result.Line = line;
        result.IgnoreCase = !caseSensitive;

        break;
      }
    }

    ```

## <a name="see-also"></a>参照

[Writing a Windows PowerShell Cmdlet (Windows PowerShell コマンドレットの記述)](./writing-a-windows-powershell-cmdlet.md)
