---
ms.date: 09/20/2019
keywords: DSC, PowerShell, 構成, セットアップ
description: ターゲット ノード上のローカル グループを管理するためのメカニズムを備えています。
title: DSC GroupSet リソース
ms.openlocfilehash: 90e0c3f0e09c6a300988869265dfdb432ed5d217
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/18/2020
ms.locfileid: "86464197"
---
# <a name="dsc-groupset-resource"></a><span data-ttu-id="1efb0-104">DSC GroupSet リソース</span><span class="sxs-lookup"><span data-stu-id="1efb0-104">DSC GroupSet Resource</span></span>

> <span data-ttu-id="1efb0-105">適用先:Windows PowerShell 5.x</span><span class="sxs-lookup"><span data-stu-id="1efb0-105">Applies To: Windows PowerShell 5.x</span></span>

<span data-ttu-id="1efb0-106">PowerShell Desired State Configuration (DSC) の **GroupSet** リソースは、ターゲット ノード上でローカル グループを管理するためのメカニズムを備えています。</span><span class="sxs-lookup"><span data-stu-id="1efb0-106">The **GroupSet** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to manage local groups on the target node.</span></span> <span data-ttu-id="1efb0-107">このリソースは[複合リソース](../../../resources/authoringResourceComposite.md)であり、`GroupName` パラメーターに指定されているグループごとに [Group リソース](groupResource.md)を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="1efb0-107">This resource is a [composite resource](../../../resources/authoringResourceComposite.md) that calls the [Group resource](groupResource.md) for each group specified in the `GroupName` parameter.</span></span>

<span data-ttu-id="1efb0-108">このリソースは、複数のグループに対して同じメンバー一覧の追加/削除を行うとき、複数のグループを削除するとき、同じメンバー一覧の複数のグループを追加するときに使用します。</span><span class="sxs-lookup"><span data-stu-id="1efb0-108">Use this resource when you want to add and/or remove the same list of members to more than one group, remove more than one group, or add more than one group with the same list of members.</span></span>

## <a name="syntax"></a><span data-ttu-id="1efb0-109">構文</span><span class="sxs-lookup"><span data-stu-id="1efb0-109">Syntax</span></span>

```Syntax
Group [string] #ResourceName
{
    GroupName = [string[]]
    [ MembersToInclude = [string[]] ]
    [ MembersToExclude = [string[]] ]
    [ Credential = [PSCredential] ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Absent | Present }  ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a><span data-ttu-id="1efb0-110">Properties</span><span class="sxs-lookup"><span data-stu-id="1efb0-110">Properties</span></span>

|<span data-ttu-id="1efb0-111">プロパティ</span><span class="sxs-lookup"><span data-stu-id="1efb0-111">Property</span></span> |<span data-ttu-id="1efb0-112">説明</span><span class="sxs-lookup"><span data-stu-id="1efb0-112">Description</span></span> |
|---|---|
|<span data-ttu-id="1efb0-113">GroupName</span><span class="sxs-lookup"><span data-stu-id="1efb0-113">GroupName</span></span> |<span data-ttu-id="1efb0-114">特定の状態を保証するグループの名前です。</span><span class="sxs-lookup"><span data-stu-id="1efb0-114">The names of the groups for which you want to ensure a specific state.</span></span> |
|<span data-ttu-id="1efb0-115">メンバー</span><span class="sxs-lookup"><span data-stu-id="1efb0-115">Members</span></span> |<span data-ttu-id="1efb0-116">このプロパティは、現在のグループ メンバーシップを指定したメンバーで置き換えるために使用します。</span><span class="sxs-lookup"><span data-stu-id="1efb0-116">Use this property to replace the current group membership with the specified members.</span></span> <span data-ttu-id="1efb0-117">このプロパティの値は、`Domain\UserName` 形式の文字列の配列です。</span><span class="sxs-lookup"><span data-stu-id="1efb0-117">The value of this property is an array of strings of the form `Domain\UserName`.</span></span> <span data-ttu-id="1efb0-118">構成でこのプロパティを設定する場合、**MembersToExclude** プロパティおよび **MembersToInclude** プロパティは併用しないでください。</span><span class="sxs-lookup"><span data-stu-id="1efb0-118">If you set this property in a configuration, do not use either the **MembersToExclude** or **MembersToInclude** property.</span></span> <span data-ttu-id="1efb0-119">併用した場合、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="1efb0-119">Doing so will generate an error.</span></span> |
|<span data-ttu-id="1efb0-120">MembersToInclude</span><span class="sxs-lookup"><span data-stu-id="1efb0-120">MembersToInclude</span></span> |<span data-ttu-id="1efb0-121">このプロパティは、グループの既存のメンバーシップにメンバーを追加するために使用します。</span><span class="sxs-lookup"><span data-stu-id="1efb0-121">Use this property to add members to the existing membership of the group.</span></span> <span data-ttu-id="1efb0-122">このプロパティの値は、`Domain\UserName` 形式の文字列の配列です。</span><span class="sxs-lookup"><span data-stu-id="1efb0-122">The value of this property is an array of strings of the form `Domain\UserName`.</span></span> <span data-ttu-id="1efb0-123">構成でこのプロパティを設定する場合、**Members** プロパティは使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="1efb0-123">If you set this property in a configuration, do not use the **Members** property.</span></span> <span data-ttu-id="1efb0-124">併用した場合、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="1efb0-124">Doing so will generate an error.</span></span> |
|<span data-ttu-id="1efb0-125">MembersToExclude</span><span class="sxs-lookup"><span data-stu-id="1efb0-125">MembersToExclude</span></span> |<span data-ttu-id="1efb0-126">このプロパティは、グループの既存のメンバーシップからメンバーを削除するために使用します。</span><span class="sxs-lookup"><span data-stu-id="1efb0-126">Use this property to remove members from the existing membership of the groups.</span></span> <span data-ttu-id="1efb0-127">このプロパティの値は、`Domain\UserName` 形式の文字列の配列です。</span><span class="sxs-lookup"><span data-stu-id="1efb0-127">The value of this property is an array of strings of the form `Domain\UserName`.</span></span> <span data-ttu-id="1efb0-128">構成でこのプロパティを設定する場合、**Members** プロパティは使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="1efb0-128">If you set this property in a configuration, do not use the **Members** property.</span></span> <span data-ttu-id="1efb0-129">併用した場合、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="1efb0-129">Doing so will generate an error.</span></span> |
|<span data-ttu-id="1efb0-130">資格情報</span><span class="sxs-lookup"><span data-stu-id="1efb0-130">Credential</span></span> |<span data-ttu-id="1efb0-131">リモート リソースにアクセスするために必要な資格情報です</span><span class="sxs-lookup"><span data-stu-id="1efb0-131">The credentials required to access remote resources.</span></span> <span data-ttu-id="1efb0-132">このアカウントには、ローカルではないすべてのアカウントをグループに追加できる、Active Directory への適切なアクセス許可が必要です。このアクセス許可がない場合、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="1efb0-132">This account must have the appropriate Active Directory permissions to add all non-local accounts to the group; otherwise, an error will occur.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="1efb0-133">共通プロパティ</span><span class="sxs-lookup"><span data-stu-id="1efb0-133">Common properties</span></span>

|<span data-ttu-id="1efb0-134">プロパティ</span><span class="sxs-lookup"><span data-stu-id="1efb0-134">Property</span></span> |<span data-ttu-id="1efb0-135">説明</span><span class="sxs-lookup"><span data-stu-id="1efb0-135">Description</span></span> |
|---|---|
|<span data-ttu-id="1efb0-136">DependsOn</span><span class="sxs-lookup"><span data-stu-id="1efb0-136">DependsOn</span></span> |<span data-ttu-id="1efb0-137">このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="1efb0-137">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="1efb0-138">たとえば、最初に実行するリソース構成スクリプト ブロックの ID が ResourceName で、そのタイプが ResourceType である場合、このプロパティを使用する構文は `DependsOn = "[ResourceType]ResourceName"` になります。</span><span class="sxs-lookup"><span data-stu-id="1efb0-138">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="1efb0-139">Ensure</span><span class="sxs-lookup"><span data-stu-id="1efb0-139">Ensure</span></span> |<span data-ttu-id="1efb0-140">グループが存在するかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="1efb0-140">Indicates whether the groups exist.</span></span> <span data-ttu-id="1efb0-141">グループが存在していないことを保証するには、このプロパティを **Absent** に設定します。</span><span class="sxs-lookup"><span data-stu-id="1efb0-141">Set this property to **Absent** to ensure that the groups do not exist.</span></span> <span data-ttu-id="1efb0-142">グループが存在することを保証するには、このプロパティを **Present** に設定します。</span><span class="sxs-lookup"><span data-stu-id="1efb0-142">Setting it to **Present** ensures that the groups exist.</span></span> <span data-ttu-id="1efb0-143">既定値は **Present** です。</span><span class="sxs-lookup"><span data-stu-id="1efb0-143">The default value is **Present**.</span></span> |
|<span data-ttu-id="1efb0-144">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="1efb0-144">PsDscRunAsCredential</span></span> |<span data-ttu-id="1efb0-145">リソース全体を実行するための資格情報を設定します。</span><span class="sxs-lookup"><span data-stu-id="1efb0-145">Sets the credential for running the entire resource as.</span></span> |

> [!NOTE]
> <span data-ttu-id="1efb0-146">**PsDscRunAsCredential** という共通プロパティは、他の資格情報という文脈の中であらゆる DSC リソースを実行するために WMF 5.0 で追加されました。</span><span class="sxs-lookup"><span data-stu-id="1efb0-146">The **PsDscRunAsCredential** common property was added in WMF 5.0 to allow running any DSC resource in the context of other credentials.</span></span> <span data-ttu-id="1efb0-147">詳細については、「[DSC リソースに対して資格情報を使用する](../../../configurations/runasuser.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1efb0-147">For more information, see [Use Credentials with DSC Resources](../../../configurations/runasuser.md).</span></span>

## <a name="example-1-ensuring-groups-are-present"></a><span data-ttu-id="1efb0-148">例 1: グループが存在することを確認する</span><span class="sxs-lookup"><span data-stu-id="1efb0-148">Example 1: Ensuring Groups are present</span></span>

<span data-ttu-id="1efb0-149">次に、"myGroup" と "myOtherGroup" という 2 つのグループが存在することを保証する例を示します。</span><span class="sxs-lookup"><span data-stu-id="1efb0-149">The following example shows how to ensure that two groups called "myGroup" and "myOtherGroup" are present.</span></span>

```powershell
configuration GroupSetTest
{
    Import-DscResource -ModuleName PSDesiredStateConfiguration
    Node localhost
    {
        GroupSet GroupSetTest
        {
            GroupName        = @("myGroup", "myOtherGroup")
            Ensure           = "Present"
            MembersToInclude = @("contoso\alice", "contoso\bob")
            MembersToExclude = $("contoso\john")
            Credential       = Get-Credential
        }
    }
}
$cd = @{
    AllNodes = @(
        @{
            NodeName                    = 'localhost'
            PSDscAllowPlainTextPassword = $true
            PSDscAllowDomainUser        = $true
        }
    )
}

GroupSetTest -ConfigurationData $cd
```

> [!NOTE]
> <span data-ttu-id="1efb0-150">この例では、わかりやすくするためにプレーンテキストの資格情報を使用しています。</span><span class="sxs-lookup"><span data-stu-id="1efb0-150">This example uses plaintext credentials for simplicity.</span></span> <span data-ttu-id="1efb0-151">構成 MOF ファイル内の資格情報を暗号化する方法の詳細については、「[MOF ファイルのセキュリティ保護](../../../pull-server/secureMOF.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1efb0-151">For information about how to encrypt credentials in the configuration MOF file, see [Securing the MOF File](../../../pull-server/secureMOF.md).</span></span>
