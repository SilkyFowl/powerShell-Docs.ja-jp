---
title: RunSpace05 コードサンプル |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 31a73f965a6e38dceec740a2f7d4adead3e2a3f9
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784743"
---
# <a name="runspace05-code-sample"></a>RunSpace05 コード サンプル

「 [RunspaceConfiguration を使用した実行空間の構成](https://msdn.microsoft.com/42681d19-2d05-4975-befd-afb1990e79b2)」で説明されている Runspace05 サンプルのソースコードを次に示します。
このサンプルでは、実行空間の構成情報を作成する方法、実行空間を作成する方法、1つのコマンドを使用してパイプラインを作成する方法、パイプラインを実行する方法を示します。 実行されるコマンドは、コマンド `Get-Process` レットです。

> [!NOTE]
> C# ソースファイル (runspace05.cs) をダウンロードするには、Microsoft Windows Software Development Kit for Windows Vista および Microsoft .NET Framework 3.0 ランタイムコンポーネントを使用します。 ダウンロードの手順については、「 [Windows powershell をインストールする方法」および「Windows POWERSHELL SDK をダウンロードする方法](/powershell/scripting/developer/installing-the-windows-powershell-sdk)」を参照してください。
> ダウンロードしたソースファイルは、ディレクトリにあり **\<PowerShell Samples>** ます。

## <a name="code-sample"></a>コード サンプル

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/Runspace05/Runspace05.cs" range="11-86":::

## <a name="see-also"></a>参照

[Windows PowerShell プログラマー ガイド](./windows-powershell-programmer-s-guide.md)

[Windows PowerShell SDK](../windows-powershell-reference.md)
