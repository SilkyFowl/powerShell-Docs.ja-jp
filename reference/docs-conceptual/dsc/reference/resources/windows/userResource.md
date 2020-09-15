---
ms.date: 07/16/2020
keywords: DSC, PowerShell, 構成, セットアップ
title: DSC User リソース
ms.openlocfilehash: 340fce45a2074930ae14ca1aaeef7eff78531916
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/18/2020
ms.locfileid: "86463773"
---
# <a name="dsc-user-resource"></a>DSC User リソース

> 適用先: Windows PowerShell 4.0、Windows PowerShell 5.x

PowerShell Desired State Configuration (DSC) の **User** リソースは、ターゲット ノード上でローカル ユーザー アカウントを管理するためのメカニズムを備えています。

## <a name="syntax"></a>構文

```Syntax
User [string] #ResourceName
{
    UserName = [string]
    [ Description = [string] ]
    [ Disabled = [bool] ]
    [ FullName = [string] ]
    [ Password = [PSCredential] ]
    [ PasswordChangeNotAllowed = [bool] ]
    [ PasswordChangeRequired = [bool] ]
    [ PasswordNeverExpires = [bool] ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Absent | Present }  ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a>Properties

|プロパティ |説明 |
|---|---|
|UserName |特定の状態を保証するアカウント名を示します。 |
|説明 |ユーザー アカウントのために使用する説明を示します。 |
|無効 |アカウントが有効になっているかどうかを示します。 このアカウントを無効にするには、このプロパティを `$true` に設定し、有効にするには `$false` に設定します。 |
|FullName |ユーザー アカウントのために使用する完全名の文字列を表します。 |
|Password |このアカウントに使用するパスワードを示します。 |
|PasswordChangeNotAllowed |ユーザーがパスワードを変更できるかどうかを示します。 ユーザーがパスワードを変更できないようにするには、このプロパティを `$true` に設定し、ユーザーがパスワードを変更できるようにするには、`$false` に設定します。 既定値は `$false` です。 |
|PasswordChangeRequired |ユーザーが次回ログオンしたときにパスワードを変更する必要があるかどうかを示します。 ユーザーがパスワードを変更する必要がある場合は、このプロパティを `$true` に設定します。 既定値は `$true` です。 |
|PasswordNeverExpires |パスワードの有効期限が切れるかどうかを示します。 このアカウントのパスワードが確実に期限切れにならないようにするには、このプロパティを `$true` に設定します。 パスワードの有効期限が切れるようにするには、`$false` に設定します。 既定値は `$false` です。 |

## <a name="common-properties"></a>共通プロパティ

|プロパティ |説明 |
|---|---|
|DependsOn |このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。 たとえば、最初に実行するリソース構成スクリプト ブロックの ID が ResourceName で、そのタイプが ResourceType である場合、このプロパティを使用する構文は `DependsOn = "[ResourceType]ResourceName"` になります。 |
|Ensure |アカウントが存在するかどうかを示します。 このアカウントの存在を保証するには、このプロパティを **Present** に設定し、アカウントが存在しないことを保証するには、**Absent** に設定します。 既定値は **Present** です。 |
|PsDscRunAsCredential |リソース全体を実行するための資格情報を設定します。 |

> [!NOTE]
> **PsDscRunAsCredential** という共通プロパティは、他の資格情報という文脈の中であらゆる DSC リソースを実行するために WMF 5.0 で追加されました。 詳細については、「[DSC リソースに対して資格情報を使用する](../../../configurations/runasuser.md)」を参照してください。

## <a name="example"></a>例

```powershell
User UserExample
{
    Ensure = "Present"  # To ensure the user account does not exist, set Ensure to "Absent"
    UserName = "SomeName"
    Password = $passwordCred # This needs to be a credential object
    DependsOn = "[Group]GroupExample" # Configures GroupExample first
}
```
