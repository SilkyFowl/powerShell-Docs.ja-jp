---
title: TableControl (形式) の TableRowEntry TableColumnItems 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d43684ce-7c3d-4d14-8dbd-061c111ee805
caps.latest.revision: 12
ms.openlocfilehash: faa9ba78397e713400f6072df9915f20d966bb37
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56859448"
---
# <a name="tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format"></a><span data-ttu-id="67007-102">TableControl の TableRowEntry の TableColumnItems 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="67007-102">TableColumnItems Element for TableRowEntry for TableControl (Format)</span></span>

<span data-ttu-id="67007-103">プロパティまたは行の表示が値を持つスクリプトを定義します。</span><span class="sxs-lookup"><span data-stu-id="67007-103">Defines the properties or scripts whose values are displayed in a row.</span></span>

<span data-ttu-id="67007-104">構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) TableControl 要素 (形式) TableRowEntries 要素の要素に TableControl (形式) TableRowEntry TableRowEntries TableControl (形式) 用のTableControl (形式) の TableControlEntry TableColumnItems 要素</span><span class="sxs-lookup"><span data-stu-id="67007-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element for TableControl (Format) TableRowEntry Element for TableRowEntries for TableControl (Format) TableColumnItems Element for TableControlEntry for TableControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="67007-105">構文</span><span class="sxs-lookup"><span data-stu-id="67007-105">Syntax</span></span>

```xml
TableColumnItems>
  <TableColumnItem>...</TableColumnItem>
</TableColumnItems>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="67007-106">属性と要素</span><span class="sxs-lookup"><span data-stu-id="67007-106">Attributes and Elements</span></span>

<span data-ttu-id="67007-107">次のセクションでは、属性、子要素、およびの親要素について説明します、`TableColumnItems`要素。</span><span class="sxs-lookup"><span data-stu-id="67007-107">The following sections describe the attributes, child elements, and parent element of the `TableColumnItems` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="67007-108">属性</span><span class="sxs-lookup"><span data-stu-id="67007-108">Attributes</span></span>

<span data-ttu-id="67007-109">なし。</span><span class="sxs-lookup"><span data-stu-id="67007-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="67007-110">子要素</span><span class="sxs-lookup"><span data-stu-id="67007-110">Child Elements</span></span>

|<span data-ttu-id="67007-111">要素</span><span class="sxs-lookup"><span data-stu-id="67007-111">Element</span></span>|<span data-ttu-id="67007-112">説明</span><span class="sxs-lookup"><span data-stu-id="67007-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="67007-113">TableControl (形式) の TableColumnItems TableColumnItem 要素</span><span class="sxs-lookup"><span data-stu-id="67007-113">TableColumnItem Element for TableColumnItems for TableControl (Format)</span></span>](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)|<span data-ttu-id="67007-114">必須の要素。</span><span class="sxs-lookup"><span data-stu-id="67007-114">Required element.</span></span><br /><br /> <span data-ttu-id="67007-115">プロパティまたは値を持つが、行の列に表示されているスクリプトを定義します。</span><span class="sxs-lookup"><span data-stu-id="67007-115">Defines the property or script whose value is displayed in a column of the row.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="67007-116">親要素</span><span class="sxs-lookup"><span data-stu-id="67007-116">Parent Elements</span></span>

|<span data-ttu-id="67007-117">要素</span><span class="sxs-lookup"><span data-stu-id="67007-117">Element</span></span>|<span data-ttu-id="67007-118">説明</span><span class="sxs-lookup"><span data-stu-id="67007-118">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="67007-119">TableControl (形式) の TableRowEntries TableRowEntry 要素</span><span class="sxs-lookup"><span data-stu-id="67007-119">TableRowEntry Element for TableRowEntries for TableControl (Format)</span></span>](./tablerowentry-element-for-tablerowentroes-for-tablecontrol-format.md)|<span data-ttu-id="67007-120">テーブルの行に表示されるデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="67007-120">Defines the data that is displayed in a row of the table.</span></span>|

## <a name="remarks"></a><span data-ttu-id="67007-121">コメント</span><span class="sxs-lookup"><span data-stu-id="67007-121">Remarks</span></span>

<span data-ttu-id="67007-122">A`TableColumnItem`要素は、行の各列は必須です。</span><span class="sxs-lookup"><span data-stu-id="67007-122">A `TableColumnItem` element is required for each column of the row.</span></span> <span data-ttu-id="67007-123">最初のエントリには、最初の列、列と 2 番目の上から 2 番目のエントリが表示されます。</span><span class="sxs-lookup"><span data-stu-id="67007-123">The first entry is displayed in first column, the second entry in the second column, and so on.</span></span>

<span data-ttu-id="67007-124">テーブル ビューのコンポーネントに関する詳細については、次を参照してください。[テーブル ビューを作成する](./creating-a-table-view.md)します。</span><span class="sxs-lookup"><span data-stu-id="67007-124">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="67007-125">例</span><span class="sxs-lookup"><span data-stu-id="67007-125">Example</span></span>

<span data-ttu-id="67007-126">次の例は、`TableColumnItems`の 3 つのプロパティを定義する要素、 [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process)オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="67007-126">The following example shows a `TableColumnItems` element that defines three properties of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

```xml
<TableColumnItems>
  <TableColumnItem>
    <PropertyName>Status</PropertyName>
  </TableColumnItem>
  <TableColumnItem>
    <PropertyName>Name</PropertyName>
  </TableColumnItem>
  <TableColumnItem>
    <PropertyName>DisplayName</PropertyName>
  </TableColumnItem>
</TableColumnItems>

```

## <a name="see-also"></a><span data-ttu-id="67007-127">参照</span><span class="sxs-lookup"><span data-stu-id="67007-127">See Also</span></span>

[<span data-ttu-id="67007-128">テーブル ビューを作成します。</span><span class="sxs-lookup"><span data-stu-id="67007-128">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="67007-129">TableColumnItem 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="67007-129">TableColumnItem Element (Format)</span></span>](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)

[<span data-ttu-id="67007-130">TableRowEntry 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="67007-130">TableRowEntry Element (Format)</span></span>](./tablerowentry-element-for-tablerowentroes-for-tablecontrol-format.md)

[<span data-ttu-id="67007-131">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="67007-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)