---
title: GetProc04 (C#) サンプルコード |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: dd3965ee504641b1b629ba203090ee14c670da43
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87771891"
---
# <a name="getproc04-c-sample-code"></a>GetProc04 (C#) サンプル コード

次のコードは、 `Get-Process` 終了しないエラーを報告するコマンドレットの実装を示しています。 この実装では、 [WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)メソッドを呼び出して、終了しないエラーを報告します。

> [!NOTE]
> この getprov04.cs コマンドレットの C# ソースファイル () をダウンロードするには、Microsoft Windows Software Development Kit for Windows Vista および .NET Framework 3.0 ランタイムコンポーネントを使用します。 ダウンロードの手順については、「 [Windows powershell をインストールする方法」および「Windows POWERSHELL SDK をダウンロードする方法](/powershell/scripting/developer/installing-the-windows-powershell-sdk)」を参照してください。
> ダウンロードしたソースファイルは、ディレクトリにあり **\<PowerShell Samples>** ます。

## <a name="code-sample"></a>コード サンプル

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/GetProcessSample04/GetProcessSample04.cs" range="11-98":::

## <a name="see-also"></a>参照

[Windows PowerShell プログラマー ガイド](./windows-powershell-programmer-s-guide.md)

[Windows PowerShell SDK](../windows-powershell-reference.md)
