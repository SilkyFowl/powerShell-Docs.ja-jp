---
ms.date: 07/16/2020
keywords: DSC, PowerShell, 構成, セットアップ
title: DSC WindowsFeature リソース
ms.openlocfilehash: b15b267c6898697816b386a381e5a6d59acd492a
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/18/2020
ms.locfileid: "86464113"
---
# <a name="dsc-windowsfeature-resource"></a>DSC WindowsFeature リソース

> 適用先: Windows PowerShell 4.0、Windows PowerShell 5.x

Windows PowerShell Desired State Configuration (DSC) の **WindowsFeature** リソースは、役割と機能がターゲット ノードで追加または削除されることを保証するためのメカニズムを備えています。

## <a name="syntax"></a>構文

```Syntax
WindowsFeature [string] #ResourceName
{
    Name = [string]
    [ Credential = [PSCredential] ]
    [ IncludeAllSubFeature = [bool] ]
    [ LogPath = [string] ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Absent | Present }  ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a>Properties

|プロパティ |説明 |
|---|---|
|名前 |追加または削除されることを保証する役割または機能の名前を示します。 これは、[Get-WindowsFeature](/powershell/module/servermanager/Get-WindowsFeature) コマンドレットからの **Name** プロパティと同じものであり、役割または機能の表示名ではありません。 |
|資格情報 |役割または機能の追加や削除に使用する資格情報を示します。 |
|IncludeAllSubFeature |**Name** プロパティで指定した機能の状態を使用して必要なすべてのサブ機能の状態を保証するには、このプロパティを `$true` に設定します。 |
|LogPath |リソース プロバイダーの操作を記録するログ ファイルへのパスを示します。 |

## <a name="common-properties"></a>共通プロパティ

|プロパティ |説明 |
|---|---|
|DependsOn |このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。 たとえば、最初に実行するリソース構成スクリプト ブロックの ID が ResourceName で、そのタイプが ResourceType である場合、このプロパティを使用する構文は `DependsOn = "[ResourceType]ResourceName"` になります。 |
|Ensure |役割または機能が追加されるかどうかを示します。 役割または機能を確実に追加するには、このプロパティを **Present** に設定します。 役割または機能を確実に削除するには、このプロパティを **Absent** に設定します。 既定値は **Present** です。 |
|PsDscRunAsCredential |リソース全体を実行するための資格情報を設定します。 |

> [!NOTE]
> **PsDscRunAsCredential** という共通プロパティは、他の資格情報という文脈の中であらゆる DSC リソースを実行するために WMF 5.0 で追加されました。 詳細については、「[DSC リソースに対して資格情報を使用する](../../../configurations/runasuser.md)」を参照してください。

## <a name="example"></a>例

```powershell
WindowsFeature RoleExample
{
    Ensure = "Present"
    # Alternatively, to ensure the role is uninstalled, set Ensure to "Absent"
    Name = "Web-Server" # Use the Name property from Get-WindowsFeature
}
```
