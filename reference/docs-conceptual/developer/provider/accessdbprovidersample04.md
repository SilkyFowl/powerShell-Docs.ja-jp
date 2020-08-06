---
title: AccessDBProviderSample04 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 097591528fd12cdf9f134a0fd8a0bd278f216fab
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786868"
---
# <a name="accessdbprovidersample04"></a><span data-ttu-id="108cc-102">AccessDBProviderSample04</span><span class="sxs-lookup"><span data-stu-id="108cc-102">AccessDBProviderSample04</span></span>

<span data-ttu-id="108cc-103">このサンプルでは、、、、およびの各コマンドレットの呼び出しをサポートするために、コンテナーメソッドを上書きする方法を示し `Copy-Item` `Get-ChildItem` `New-Item` `Remove-Item` ます。</span><span class="sxs-lookup"><span data-stu-id="108cc-103">This sample shows how to overwrite container methods to support calls to the `Copy-Item`, `Get-ChildItem`, `New-Item`, and `Remove-Item` cmdlets.</span></span> <span data-ttu-id="108cc-104">これらのメソッドは、データ ストアにコンテナーであるアイテムが含まれる場合に実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="108cc-104">These methods should be implemented when the data store contains items that are containers.</span></span> <span data-ttu-id="108cc-105">コンテナーは、共通の親項目の子項目のグループです。</span><span class="sxs-lookup"><span data-stu-id="108cc-105">A container is a group of child items under a common parent item.</span></span> <span data-ttu-id="108cc-106">このサンプルのプロバイダークラスは、 [Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)クラスから派生しています。</span><span class="sxs-lookup"><span data-stu-id="108cc-106">The provider class in this sample derives from the [System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) class.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="108cc-107">対象</span><span class="sxs-lookup"><span data-stu-id="108cc-107">Demonstrates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="108cc-108">プロバイダークラスは、ほとんどの場合、[システム](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)から派生することがあります。</span><span class="sxs-lookup"><span data-stu-id="108cc-108">Your provider class will most likely derive from the [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)</span></span>

<span data-ttu-id="108cc-109">このサンプルでは、次の方法を示します。</span><span class="sxs-lookup"><span data-stu-id="108cc-109">This sample demonstrates the following:</span></span>

- <span data-ttu-id="108cc-110">属性を宣言 `CmdletProvider` しています。</span><span class="sxs-lookup"><span data-stu-id="108cc-110">Declaring the `CmdletProvider` attribute.</span></span>
- <span data-ttu-id="108cc-111">[Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)クラスから派生したプロバイダークラスを定義しています。</span><span class="sxs-lookup"><span data-stu-id="108cc-111">Defining a provider class that derives from the [System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) class.</span></span>
- <span data-ttu-id="108cc-112">[ContainerCmdletProvider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem)メソッドを上書きして、コマンドレットの動作を変更します `Copy-Item` 。これにより、ユーザーは、ある場所から別の場所に項目をコピーできます。</span><span class="sxs-lookup"><span data-stu-id="108cc-112">Overwriting the [System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem) method to change the behavior of the `Copy-Item` cmdlet which allows the user to copy items from one location to another.</span></span> <span data-ttu-id="108cc-113">(このサンプルでは、コマンドレットに動的パラメーターを追加する方法については説明しません `Copy-Item` )。</span><span class="sxs-lookup"><span data-stu-id="108cc-113">(This sample does not show how to add dynamic parameters to the `Copy-Item` cmdlet.)</span></span>
- <span data-ttu-id="108cc-114">[Getchilditems \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems)メソッドを上書きして、ChildItems コマンドレットの動作を変更します。これにより、ユーザーは親項目の子項目を取得できるようになります。</span><span class="sxs-lookup"><span data-stu-id="108cc-114">Overwriting the [System.Management.Automation.Provider.Containercmdletprovider.Getchilditems\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems) method to change the behavior of the Get-ChildItems cmdlet, which allows the user to retrieve the child items of the parent item.</span></span> <span data-ttu-id="108cc-115">(このサンプルでは、ChildItems コマンドレットに動的パラメーターを追加する方法については説明しません)。</span><span class="sxs-lookup"><span data-stu-id="108cc-115">(This sample does not show how to add dynamic parameters to the Get-ChildItems cmdlet.)</span></span>
- <span data-ttu-id="108cc-116">[Containercmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNames)メソッドを上書きして、 `Name` コマンドレットのパラメーターが指定されている場合に、ChildItems コマンドレットの動作を変更します。</span><span class="sxs-lookup"><span data-stu-id="108cc-116">Overwriting the [System.Management.Automation.Provider.Containercmdletprovider.Getchildnames\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNames) method to change the behavior of the Get-ChildItems cmdlet when the `Name` parameter of the cmdlet is specified.</span></span>
- <span data-ttu-id="108cc-117">[Containercmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem)メソッドを上書きしてコマンドレットの動作を変更し、 `New-Item` ユーザーがデータストアに項目を追加できるようにします。</span><span class="sxs-lookup"><span data-stu-id="108cc-117">Overwriting the [System.Management.Automation.Provider.Containercmdletprovider.Newitem\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem) method to change the behavior of the `New-Item` cmdlet, which allows the user to add items to the data store.</span></span> <span data-ttu-id="108cc-118">(このサンプルでは、コマンドレットに動的パラメーターを追加する方法については説明しません `New-Item` )。</span><span class="sxs-lookup"><span data-stu-id="108cc-118">(This sample does not show how to add dynamic parameters to the `New-Item` cmdlet.)</span></span>
- <span data-ttu-id="108cc-119">[Containercmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItem)メソッドを上書きして、コマンドレットの動作を変更してい `Remove-Item` ます。</span><span class="sxs-lookup"><span data-stu-id="108cc-119">Overwriting the [System.Management.Automation.Provider.Containercmdletprovider.Removeitem\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItem) method to change the behavior of the `Remove-Item` cmdlet.</span></span> <span data-ttu-id="108cc-120">(このサンプルでは、コマンドレットに動的パラメーターを追加する方法については説明しません `Remove-Item` )。</span><span class="sxs-lookup"><span data-stu-id="108cc-120">(This sample does not show how to add dynamic parameters to the `Remove-Item` cmdlet.)</span></span>

## <a name="example"></a><span data-ttu-id="108cc-121">例</span><span class="sxs-lookup"><span data-stu-id="108cc-121">Example</span></span>

<span data-ttu-id="108cc-122">このサンプルでは、項目をコピー、作成、および削除するために必要なメソッドと、親項目の子項目を取得するメソッドを上書きする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="108cc-122">This sample shows how to overwrite the methods needed to copy, create, and remove items, as well as methods for getting the child items of a parent item.</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample04/AccessDBProviderSample04.cs" range="11-1635":::

## <a name="see-also"></a><span data-ttu-id="108cc-123">参照</span><span class="sxs-lookup"><span data-stu-id="108cc-123">See Also</span></span>

[<span data-ttu-id="108cc-124">システムの................</span><span class="sxs-lookup"><span data-stu-id="108cc-124">System.Management.Automation.Provider.Itemcmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)

[<span data-ttu-id="108cc-125">Containercmdletprovider (システム管理)</span><span class="sxs-lookup"><span data-stu-id="108cc-125">System.Management.Automation.Provider.Containercmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)

[<span data-ttu-id="108cc-126">システムの管理...。</span><span class="sxs-lookup"><span data-stu-id="108cc-126">System.Management.Automation.Provider.Navigationcmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)

[<span data-ttu-id="108cc-127">Windows PowerShell プロバイダーを設計する</span><span class="sxs-lookup"><span data-stu-id="108cc-127">Designing Your Windows PowerShell Provider</span></span>](./provider-types.md)
