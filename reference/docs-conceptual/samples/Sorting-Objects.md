---
ms.date: 06/05/2017
keywords: powershell,コマンドレット
title: オブジェクトの並べ替え
description: Sort-Object コマンドレットを使用すると、オブジェクトのコレクションを 1 つまたは複数のプロパティで並べ替えることができます。
ms.openlocfilehash: 836207adfc566003e9714e45920d9b4e24a677e9
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2020
ms.locfileid: "92501016"
---
# <a name="sorting-objects"></a><span data-ttu-id="7834a-104">オブジェクトの並べ替え</span><span class="sxs-lookup"><span data-stu-id="7834a-104">Sorting Objects</span></span>

<span data-ttu-id="7834a-105">`Sort-Object` コマンドレットを使用すると、表示データを見やすく整理できます。</span><span class="sxs-lookup"><span data-stu-id="7834a-105">We can organize displayed data to make it easier to scan by using the `Sort-Object` cmdlet.</span></span>
<span data-ttu-id="7834a-106">`Sort-Object` では、並べ替え条件としてプロパティ名 (複数可) を指定すると、そのプロパティ値で並べ替えられたデータが返されます。</span><span class="sxs-lookup"><span data-stu-id="7834a-106">`Sort-Object` takes the name of one or more properties to sort on, and returns data sorted by the values of those properties.</span></span>

## <a name="basic-sorting"></a><span data-ttu-id="7834a-107">基本的な並べ替え</span><span class="sxs-lookup"><span data-stu-id="7834a-107">Basic sorting</span></span>

<span data-ttu-id="7834a-108">現在のディレクトリ内のサブディレクトリとファイルを一覧表示する問題について考えます。</span><span class="sxs-lookup"><span data-stu-id="7834a-108">Consider the problem of listing subdirectories and files in the current directory.</span></span>
<span data-ttu-id="7834a-109">**LastWriteTime** で並べ替えた後、 **Name** で並べ替えるには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="7834a-109">If we want to sort by **LastWriteTime** and then by **Name** , we can do it by typing:</span></span>

```powershell
Get-ChildItem |
  Sort-Object -Property LastWriteTime, Name |
  Format-Table -Property LastWriteTime, Name
```

```output
LastWriteTime          Name
-------------          ----
11/6/2017 10:10:11 AM  .localization-config
11/6/2017 10:10:11 AM  .openpublishing.build.ps1
11/6/2017 10:10:11 AM  appveyor.yml
11/6/2017 10:10:11 AM  LICENSE
11/6/2017 10:10:11 AM  LICENSE-CODE
11/6/2017 10:10:11 AM  ThirdPartyNotices
11/6/2017 10:10:15 AM  tests
6/6/2018 7:58:59 PM    CONTRIBUTING.md
6/6/2018 7:58:59 PM    README.md
...
```

<span data-ttu-id="7834a-110">**Descending** スイッチ パラメーターを指定して、オブジェクトを降順に並べ替えることもできます。</span><span class="sxs-lookup"><span data-stu-id="7834a-110">You can also sort the objects in reverse order by specifying the **Descending** switch parameter.</span></span>

```powershell
Get-ChildItem |
  Sort-Object -Property LastWriteTime, Name -Descending |
  Format-Table -Property LastWriteTime, Name
```

```output
LastWriteTime          Name
-------------          ----
12/1/2018 10:13:50 PM  reference
12/1/2018 10:13:50 PM  dsc
...
6/6/2018 7:58:59 PM    README.md
6/6/2018 7:58:59 PM    CONTRIBUTING.md
11/6/2017 10:10:15 AM  tests
11/6/2017 10:10:11 AM  ThirdPartyNotices
11/6/2017 10:10:11 AM  LICENSE-CODE
11/6/2017 10:10:11 AM  LICENSE
11/6/2017 10:10:11 AM  appveyor.yml
11/6/2017 10:10:11 AM  .openpublishing.build.ps1
11/6/2017 10:10:11 AM  .localization-config
```

## <a name="using-hash-tables"></a><span data-ttu-id="7834a-111">ハッシュ テーブルを使用する</span><span class="sxs-lookup"><span data-stu-id="7834a-111">Using hash tables</span></span>

<span data-ttu-id="7834a-112">配列でハッシュ テーブルを使用することにより、異なるプロパティを異なる順序で並べ替えることができます。</span><span class="sxs-lookup"><span data-stu-id="7834a-112">You can sort different properties in different orders by using hash tables in an array.</span></span>
<span data-ttu-id="7834a-113">各ハッシュ テーブルでは、 **Expression** キーを使用してプロパティ名を文字列として指定し、 **Ascending** または **Descending** キーを使用して `$true` または `$false` で並べ替え順序を指定します。</span><span class="sxs-lookup"><span data-stu-id="7834a-113">Each hash table uses an **Expression** key to specify the property name as string and an **Ascending** or **Descending** key to specify the sort order by `$true` or `$false`.</span></span>
<span data-ttu-id="7834a-114">**Expression** キーは必須です。</span><span class="sxs-lookup"><span data-stu-id="7834a-114">The **Expression** key is mandatory.</span></span>
<span data-ttu-id="7834a-115">**Ascending** キーまたは **Descending** キーは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="7834a-115">The **Ascending** or **Descending** key is optional.</span></span>

<span data-ttu-id="7834a-116">次の例では、オブジェクトを **LastWriteTime** については降順に、 **Name** については昇順に並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="7834a-116">The following example sorts objects in descending **LastWriteTime** order and ascending **Name** order.</span></span>

```powershell
Get-ChildItem |
  Sort-Object -Property @{ Expression = 'LastWriteTime'; Descending = $true }, @{ Expression = 'Name'; Ascending = $true } |
  Format-Table -Property LastWriteTime, Name
```

```output
LastWriteTime          Name
-------------          ----
12/1/2018 10:13:50 PM  dsc
12/1/2018 10:13:50 PM  reference
11/29/2018 6:56:01 PM  .openpublishing.redirection.json
11/29/2018 6:56:01 PM  gallery
11/24/2018 10:33:22 AM developer
11/20/2018 7:22:19 PM  .markdownlint.json
...
```

<span data-ttu-id="7834a-117">**Expression** キーに対してスクリプトブロックを設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="7834a-117">You can also set a scriptblock to the **Expression** key.</span></span>
<span data-ttu-id="7834a-118">`Sort-Object` コマンドレットを実行すると、スクリプトブロックが実行されて、結果が並べ替えに使用されます。</span><span class="sxs-lookup"><span data-stu-id="7834a-118">When running the `Sort-Object` cmdlet, the scriptblock is executed and the result is used for sorting.</span></span>

<span data-ttu-id="7834a-119">次の例では、 **CreationTime** から **LastWriteTime** までの期間について、オブジェクトを降順に並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="7834a-119">The following example sorts objects in descending order by the time span between **CreationTime** and **LastWriteTime** .</span></span>

```powershell
Get-ChildItem |
  Sort-Object -Property @{ Expression = { $_.LastWriteTime - $_.CreationTime }; Descending = $true } |
  Format-Table -Property LastWriteTime, CreationTime
```

```output
LastWriteTime          CreationTime
-------------          ------------
12/1/2018 10:13:50 PM  11/6/2017 10:10:11 AM
12/1/2018 10:13:50 PM  11/6/2017 10:10:11 AM
11/7/2018 6:52:24 PM   11/6/2017 10:10:11 AM
11/7/2018 6:52:24 PM   11/6/2017 10:10:15 AM
11/3/2018 9:58:17 AM   11/6/2017 10:10:11 AM
10/26/2018 4:50:21 PM  11/6/2017 10:10:11 AM
11/17/2018 1:10:57 PM  11/29/2017 5:48:30 PM
11/12/2018 6:29:53 PM  12/7/2017 7:57:07 PM
...
```

## <a name="tips"></a><span data-ttu-id="7834a-120">ヒント</span><span class="sxs-lookup"><span data-stu-id="7834a-120">Tips</span></span>

<span data-ttu-id="7834a-121">次のように、 **Property** パラメーター名は省略できます。</span><span class="sxs-lookup"><span data-stu-id="7834a-121">You can omit the **Property** parameter name as following:</span></span>

```powershell
Sort-Object LastWriteTime, Name
```

<span data-ttu-id="7834a-122">さらに、組み込みの別名 `sort` で `Sort-Object` を参照できます。</span><span class="sxs-lookup"><span data-stu-id="7834a-122">Besides, you can refer to `Sort-Object` by its built-in alias, `sort`:</span></span>

```powershell
sort LastWriteTime, Name
```

<span data-ttu-id="7834a-123">並べ替え用のハッシュ テーブル内のキーは、次のように省略できます。</span><span class="sxs-lookup"><span data-stu-id="7834a-123">The keys in the hash tables for sorting can be abbreviated as following:</span></span>

```powershell
Sort-Object @{ e = 'LastWriteTime'; d = $true }, @{ e = 'Name'; a = $true }
```

<span data-ttu-id="7834a-124">この例では、 **e** は **Expression** を表し、 **d** は **Descending** を表し、 **a** は **Ascending** を表します。</span><span class="sxs-lookup"><span data-stu-id="7834a-124">In this example, the **e** stands for **Expression** , the **d** stands for **Descending** , and the **a** stands for **Ascending** .</span></span>

<span data-ttu-id="7834a-125">読みやすさを向上させるため、ハッシュ テーブルを別の変数に配置できます。</span><span class="sxs-lookup"><span data-stu-id="7834a-125">To improve readability, you can place the hash tables into a separate variable:</span></span>

```powershell
$order = @(
  @{ Expression = 'LastWriteTime'; Descending = $true }
  @{ Expression = 'Name'; Ascending = $true }
)

Get-ChildItem |
  Sort-Object $order |
  Format-Table LastWriteTime, Name
```
