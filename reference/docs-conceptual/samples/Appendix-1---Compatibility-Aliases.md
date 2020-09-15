---
ms.date: 08/03/2020
keywords: powershell,コマンドレット
title: 付録 1 - 互換性のあるエイリアス
ms.openlocfilehash: e5bd170fea6b6109d2ef4fd58863d6cc8a0e3ae1
ms.sourcegitcommit: d3f78120bdc9096c72aa0dfdbdd91efaf254c738
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/04/2020
ms.locfileid: "87758501"
---
# <a name="appendix-1---compatibility-aliases"></a><span data-ttu-id="c2baa-103">付録 1 - 互換性のあるエイリアス</span><span class="sxs-lookup"><span data-stu-id="c2baa-103">Appendix 1 - Compatibility Aliases</span></span>

<span data-ttu-id="c2baa-104">PowerShell には、**UNIX** と **cmd.exe** のユーザーが使い慣れたコマンドを使用できるようにするさまざまなエイリアスがあります。</span><span class="sxs-lookup"><span data-stu-id="c2baa-104">PowerShell has several aliases that allow **UNIX** and **cmd.exe** users to use familiar commands.</span></span>
<span data-ttu-id="c2baa-105">そのコマンドと、それに関連する PowerShell コマンドレットおよび PowerShell エイリアスを次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="c2baa-105">The commands and their related PowerShell cmdlet and PowerShell alias are shown in the following table:</span></span>

|            <span data-ttu-id="c2baa-106">cmd.exe コマンド</span><span class="sxs-lookup"><span data-stu-id="c2baa-106">cmd.exe command</span></span>            | <span data-ttu-id="c2baa-107">UNIX コマンド</span><span class="sxs-lookup"><span data-stu-id="c2baa-107">UNIX command</span></span> | <span data-ttu-id="c2baa-108">PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="c2baa-108">PowerShell cmdlet</span></span> | <span data-ttu-id="c2baa-109">PowerShell エイリアス</span><span class="sxs-lookup"><span data-stu-id="c2baa-109">PowerShell alias</span></span> |
| ------------------------------------- | ------------ | ----------------- | ---------------- |
| <span data-ttu-id="c2baa-110">**cd**、**chdir**</span><span class="sxs-lookup"><span data-stu-id="c2baa-110">**cd**, **chdir**</span></span>                     | <span data-ttu-id="c2baa-111">**cd**</span><span class="sxs-lookup"><span data-stu-id="c2baa-111">**cd**</span></span>       | `Set-Location`    | `sl`             |
| <span data-ttu-id="c2baa-112">**cls**</span><span class="sxs-lookup"><span data-stu-id="c2baa-112">**cls**</span></span>                               | <span data-ttu-id="c2baa-113">**オフ**</span><span class="sxs-lookup"><span data-stu-id="c2baa-113">**clear**</span></span>    | `Clear-Host`      | `cls`            |
| <span data-ttu-id="c2baa-114">**copy**</span><span class="sxs-lookup"><span data-stu-id="c2baa-114">**copy**</span></span>                              | <span data-ttu-id="c2baa-115">**cp**</span><span class="sxs-lookup"><span data-stu-id="c2baa-115">**cp**</span></span>       | `Copy-Item`       | `cpi`            |
| <span data-ttu-id="c2baa-116">**del**、**erase**、**rd**、**rmdir**</span><span class="sxs-lookup"><span data-stu-id="c2baa-116">**del**, **erase**, **rd**, **rmdir**</span></span> | <span data-ttu-id="c2baa-117">**rm**</span><span class="sxs-lookup"><span data-stu-id="c2baa-117">**rm**</span></span>       | `Remove-Item`     | `ri`             |
| <span data-ttu-id="c2baa-118">**dir**</span><span class="sxs-lookup"><span data-stu-id="c2baa-118">**dir**</span></span>                               | <span data-ttu-id="c2baa-119">**ls**</span><span class="sxs-lookup"><span data-stu-id="c2baa-119">**ls**</span></span>       | `Get-ChildItem`   | `gci`            |
| <span data-ttu-id="c2baa-120">**echo**</span><span class="sxs-lookup"><span data-stu-id="c2baa-120">**echo**</span></span>                              | <span data-ttu-id="c2baa-121">**echo**</span><span class="sxs-lookup"><span data-stu-id="c2baa-121">**echo**</span></span>     | `Write-Output`    | `write`          |
| <span data-ttu-id="c2baa-122">**md**</span><span class="sxs-lookup"><span data-stu-id="c2baa-122">**md**</span></span>                                | <span data-ttu-id="c2baa-123">**mkdir**</span><span class="sxs-lookup"><span data-stu-id="c2baa-123">**mkdir**</span></span>    | `New-Item`        | `ni`             |
| <span data-ttu-id="c2baa-124">**move**</span><span class="sxs-lookup"><span data-stu-id="c2baa-124">**move**</span></span>                              | <span data-ttu-id="c2baa-125">**mv**</span><span class="sxs-lookup"><span data-stu-id="c2baa-125">**mv**</span></span>       | `Move-Item`       | `mi`             |
| <span data-ttu-id="c2baa-126">**popd**</span><span class="sxs-lookup"><span data-stu-id="c2baa-126">**popd**</span></span>                              | <span data-ttu-id="c2baa-127">**popd**</span><span class="sxs-lookup"><span data-stu-id="c2baa-127">**popd**</span></span>     | `Pop-Location`    | `popd`           |
| <span data-ttu-id="c2baa-128">**pushd**</span><span class="sxs-lookup"><span data-stu-id="c2baa-128">**pushd**</span></span>                             | <span data-ttu-id="c2baa-129">**pushd**</span><span class="sxs-lookup"><span data-stu-id="c2baa-129">**pushd**</span></span>    | `Push-Location`   | `pushd`          |
| <span data-ttu-id="c2baa-130">**ren**</span><span class="sxs-lookup"><span data-stu-id="c2baa-130">**ren**</span></span>                               | <span data-ttu-id="c2baa-131">**mv**</span><span class="sxs-lookup"><span data-stu-id="c2baa-131">**mv**</span></span>       | `Rename-Item`     | `rni`            |
| <span data-ttu-id="c2baa-132">**type**</span><span class="sxs-lookup"><span data-stu-id="c2baa-132">**type**</span></span>                              | <span data-ttu-id="c2baa-133">**cat**</span><span class="sxs-lookup"><span data-stu-id="c2baa-133">**cat**</span></span>      | `Get-Content`     | `gc`             |

<span data-ttu-id="c2baa-134">PowerShell エイリアスを検索するには、[Get-Alias](xref:Microsoft.PowerShell.Utility.Get-Alias) コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="c2baa-134">To find the PowerShell aliases, use the [Get-Alias](xref:Microsoft.PowerShell.Utility.Get-Alias) cmdlet.</span></span> <span data-ttu-id="c2baa-135">コマンドレットのエイリアスを表示するには、**Definition** パラメーターを使用して、コマンドレット名を指定します。</span><span class="sxs-lookup"><span data-stu-id="c2baa-135">To display a cmdlet's aliases, use the **Definition** parameter and specify the cmdlet name.</span></span>
<span data-ttu-id="c2baa-136">または、エイリアスのコマンドレット名を検索するには、**Name** パラメーターを使用して、エイリアスを指定します。</span><span class="sxs-lookup"><span data-stu-id="c2baa-136">Or, to find an alias's cmdlet name, use the **Name** parameter and specify the alias.</span></span>

```powershell
Get-Alias -Definition Get-ChildItem
```

```Output
CommandType     Name
-----------     ----
Alias           dir -> Get-ChildItem
Alias           gci -> Get-ChildItem
Alias           ls -> Get-ChildItem
```

```powershell
Get-Alias -Name gci
```

```Output
CommandType     Name
-----------     ----
Alias           gci -> Get-ChildItem
```
