---
ms.date: 12/23/2019
keywords: powershell,コマンドレット
title: プリンターの操作
description: この記事では、WMI オブジェクトと COM インターフェイスを使用して Windows でプリンターを管理する方法を示します。
ms.openlocfilehash: 2606753783043eeae8e9d461e56f0901149cb8e3
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2020
ms.locfileid: "92501084"
---
# <a name="working-with-printers-in-windows"></a>Windows でのプリンターの操作

PowerShell を使用してプリンターを管理するには、WMI を使用する方法と WSH から **WScript.Network** COM オブジェクトを使用する方法があります。 ここでは、両方のツールを組み合わせて使用して、特定のタスクの実行方法を紹介します。

## <a name="listing-printer-connections"></a>プリンター接続の一覧表示

コンピューターにインストールされているプリンターを一覧表示する最も簡単な方法は、WMI の **Win32_Printer** クラスを使用することです。

```powershell
Get-CimInstance -Class Win32_Printer
```

**WScript.Network** という COM オブジェクト (通常、WSH スクリプトで使用されます) を使用してプリンターを一覧表示することもできます。

```powershell
(New-Object -ComObject WScript.Network).EnumPrinterConnections()
```

このコマンドは、ポート名とプリンター デバイス名の単純な文字列コレクションを返し、識別に役立つラベルがないため、分かりにくい場合があります。

## <a name="adding-a-network-printer"></a>ネットワーク プリンターの追加

新しいネットワーク プリンターを追加するには、 **WScript.Network** を使用します。

```powershell
(New-Object -ComObject WScript.Network).AddWindowsPrinterConnection("\\Printserver01\Xerox5")
```

## <a name="setting-a-default-printer"></a>通常使うプリンターの設定

通常使うプリンターを WMI を使用して設定するには、 **Win32_Printer** コレクションでプリンターを検索し、 **SetDefaultPrinter** メソッドを呼び出します。

```powershell
$printer = Get-CimInstance -Class Win32_Printer -Filter "Name='HP LaserJet 5Si'"
Invoke-CimMethod -InputObject $printer -MethodName SetDefaultPrinter
```

**WScript.Network** の方が多少簡単に使用できます。これは、プリンター名のみを引数として取る **SetDefaultPrinter** メソッドを備えているためです。

```powershell
(New-Object -ComObject WScript.Network).SetDefaultPrinter('HP LaserJet 5Si')
```

## <a name="removing-a-printer-connection"></a>プリンター接続の削除

プリンター接続を削除するには、 **WScript.Network RemovePrinterConnection** メソッドを使用します。

```powershell
(New-Object -ComObject WScript.Network).RemovePrinterConnection("\\Printserver01\Xerox5")
```
