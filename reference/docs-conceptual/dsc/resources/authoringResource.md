---
ms.date: 07/08/2020
keywords: DSC, PowerShell, 構成, セットアップ
title: カスタム Windows PowerShell Desired State Configuration のビルド
ms.openlocfilehash: 203a2e3d0e118b86ae1fe959cc3508b6ed2733a8
ms.sourcegitcommit: d26e2237397483c6333abcf4331bd82f2e72b4e3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2020
ms.locfileid: "86217578"
---
# <a name="build-custom-windows-powershell-desired-state-configuration-resources"></a><span data-ttu-id="91673-103">カスタム Windows PowerShell Desired State Configuration のビルド</span><span class="sxs-lookup"><span data-stu-id="91673-103">Build Custom Windows PowerShell Desired State Configuration Resources</span></span>

> <span data-ttu-id="91673-104">適用先: Windows PowerShell 4.0、Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="91673-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

<span data-ttu-id="91673-105">Windows PowerShell Desired State Configuration (DSC) には、環境の構成に使用できる組み込みのリソースがあります</span><span class="sxs-lookup"><span data-stu-id="91673-105">Windows PowerShell Desired State Configuration (DSC) has built-in resources that you can use to configure your environment.</span></span> <span data-ttu-id="91673-106">このトピックでは、開発リソースの概要および特定の情報と例を含むトピックへのリンクを示します。</span><span class="sxs-lookup"><span data-stu-id="91673-106">This topic provides an overview of developing resources and links to topics with specific information and examples.</span></span>

## <a name="dsc-resource-components"></a><span data-ttu-id="91673-107">DSC リソース コンポーネント</span><span class="sxs-lookup"><span data-stu-id="91673-107">DSC resource components</span></span>

<span data-ttu-id="91673-108">DSC リソースは、Windows PowerShell モジュールです。</span><span class="sxs-lookup"><span data-stu-id="91673-108">A DSC resource is a Windows PowerShell module.</span></span> <span data-ttu-id="91673-109">モジュールには、リソースのスキーマ (構成可能なプロパティの定義) と実装 (構成で指定された実際の作業を実行するコード) の両方が含まれています。</span><span class="sxs-lookup"><span data-stu-id="91673-109">The module contains both the schema (the definition of the configurable properties) and the implementation (the code that does the actual work specified by a configuration) for the resource.</span></span> <span data-ttu-id="91673-110">DSC リソースのスキーマは MOF ファイルで定義でき、実装はスクリプト モジュールによって実行されます。</span><span class="sxs-lookup"><span data-stu-id="91673-110">A DSC resource schema can be defined in a MOF file, and the implementation is performed by a script module.</span></span> <span data-ttu-id="91673-111">バージョン 5 で PowerShell クラスがサポートされるようになってから、スキーマと実装は両方ともクラスで定義できます。</span><span class="sxs-lookup"><span data-stu-id="91673-111">Beginning with the support of PowerShell classes in version 5, the schema and implementation can both be defined in a class.</span></span> <span data-ttu-id="91673-112">次のトピックでは、DSC リソースを作成する方法をさらに詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="91673-112">The following topics describe in more detail how to create DSC resources.</span></span>

- [<span data-ttu-id="91673-113">MOF を使用したカスタム DSC リソースの記述</span><span class="sxs-lookup"><span data-stu-id="91673-113">Writing a custom DSC resource with MOF</span></span>](authoringResourceMOF.md)
- [<span data-ttu-id="91673-114">Implementing a DSC resource in C# (C# での DSC リソースの実装)</span><span class="sxs-lookup"><span data-stu-id="91673-114">Implementing a DSC resource in C#</span></span>](authoringResourceMofCS.md)
- [<span data-ttu-id="91673-115">PowerShell クラスを使用したカスタム DSC リソースの記述</span><span class="sxs-lookup"><span data-stu-id="91673-115">Writing a custom DSC resource with PowerShell classes</span></span>](authoringResourceClass.md)
- [<span data-ttu-id="91673-116">複合リソース: リソースとしての DSC 構成の使用</span><span class="sxs-lookup"><span data-stu-id="91673-116">Composite resources: Using a DSC configuration as a resource</span></span>](authoringResourceComposite.md)
- [<span data-ttu-id="91673-117">リソース デザイナー ツールの使用</span><span class="sxs-lookup"><span data-stu-id="91673-117">Using the Resource Designer tool</span></span>](authoringResourceMofDesigner.md)
