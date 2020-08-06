---
title: TableHeaders 要素 (Format) |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: b3176cbe1316d5b30cb61831d9915a80389709a5
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787429"
---
# <a name="tableheaders-element-format"></a><span data-ttu-id="30d3f-102">TableHeaders 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="30d3f-102">TableHeaders Element (Format)</span></span>

<span data-ttu-id="30d3f-103">テーブルの列のヘッダーを定義します。</span><span class="sxs-lookup"><span data-stu-id="30d3f-103">Defines the headers for the columns of a table.</span></span>

<span data-ttu-id="30d3f-104">ViewDefinitions 要素 (Format) ビュー要素 (Format) TableControl Element (Format) TableHeaders 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="30d3f-104">ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableHeaders Element for TableControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="30d3f-105">構文</span><span class="sxs-lookup"><span data-stu-id="30d3f-105">Syntax</span></span>

```xml
<TableHeaders>
  <TableColumnHeader>...</TableColumnHeader>
</TableHeaders>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="30d3f-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="30d3f-106">Attributes and Elements</span></span>

<span data-ttu-id="30d3f-107">次のセクションでは、要素の属性、子要素、および親要素について説明し `TableHeaders` ます。</span><span class="sxs-lookup"><span data-stu-id="30d3f-107">The following sections describe the attributes, child elements, and parent elements of the `TableHeaders` element.</span></span> <span data-ttu-id="30d3f-108">表示されるオブジェクトの各プロパティには、子要素が必要です。</span><span class="sxs-lookup"><span data-stu-id="30d3f-108">There must be a child element for each property of the object that is to be displayed.</span></span> <span data-ttu-id="30d3f-109">列ヘッダー情報は、子要素が指定されている順序で表示されます。</span><span class="sxs-lookup"><span data-stu-id="30d3f-109">The column header information is displayed in the order that the child elements are specified.</span></span>

### <a name="attributes"></a><span data-ttu-id="30d3f-110">属性</span><span class="sxs-lookup"><span data-stu-id="30d3f-110">Attributes</span></span>

<span data-ttu-id="30d3f-111">なし。</span><span class="sxs-lookup"><span data-stu-id="30d3f-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="30d3f-112">子要素</span><span class="sxs-lookup"><span data-stu-id="30d3f-112">Child Elements</span></span>

|<span data-ttu-id="30d3f-113">要素</span><span class="sxs-lookup"><span data-stu-id="30d3f-113">Element</span></span>|<span data-ttu-id="30d3f-114">説明</span><span class="sxs-lookup"><span data-stu-id="30d3f-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="30d3f-115">TableColumnHeader 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="30d3f-115">TableColumnHeader Element (Format)</span></span>](./tablecolumnheader-element-format.md)|<span data-ttu-id="30d3f-116">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="30d3f-116">Optional element.</span></span><br /><br /> <span data-ttu-id="30d3f-117">テーブルビューの列のデータのラベル、幅、および配置を定義します。</span><span class="sxs-lookup"><span data-stu-id="30d3f-117">Defines the label, the width, and the alignment of the data for a column of a table view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="30d3f-118">親要素</span><span class="sxs-lookup"><span data-stu-id="30d3f-118">Parent Elements</span></span>

|<span data-ttu-id="30d3f-119">要素</span><span class="sxs-lookup"><span data-stu-id="30d3f-119">Element</span></span>|<span data-ttu-id="30d3f-120">説明</span><span class="sxs-lookup"><span data-stu-id="30d3f-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="30d3f-121">TableControl 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="30d3f-121">TableControl Element (Format)</span></span>](./tablecontrol-element-format.md)|<span data-ttu-id="30d3f-122">ビューのテーブル形式を定義します。</span><span class="sxs-lookup"><span data-stu-id="30d3f-122">Defines a table format for a view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="30d3f-123">解説</span><span class="sxs-lookup"><span data-stu-id="30d3f-123">Remarks</span></span>

<span data-ttu-id="30d3f-124">テーブルビューのコンポーネントの詳細については、「[テーブルビューの作成](./creating-a-table-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="30d3f-124">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="30d3f-125">例</span><span class="sxs-lookup"><span data-stu-id="30d3f-125">Example</span></span>

<span data-ttu-id="30d3f-126">次の例は、 `TableHeaders` 2 つの列ヘッダーを定義する要素を示しています。</span><span class="sxs-lookup"><span data-stu-id="30d3f-126">This example shows a `TableHeaders` element that defines two column headers.</span></span>

```xml
<TableHeaders>
  <TableColumnHeader>
    <Label>Column 1</Label)
    <Width>16</Width>
    <Alignment>Left</Alignment>
  </TableColumnHeader>
  <TableColumnHeader>
    <Label>Column 2</Label)
    <Width>10</Width>
    <Alignment>Centered</Alignment>
  </TableColumnHeader>
</TableHeaders>
```

## <a name="see-also"></a><span data-ttu-id="30d3f-127">参照</span><span class="sxs-lookup"><span data-stu-id="30d3f-127">See Also</span></span>

[<span data-ttu-id="30d3f-128">テーブル ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="30d3f-128">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="30d3f-129">TableColumnHeader 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="30d3f-129">TableColumnHeader Element (Format)</span></span>](./tablecolumnheader-element-format.md)

[<span data-ttu-id="30d3f-130">TableControl 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="30d3f-130">TableControl Element (Format)</span></span>](./tablecontrol-element-format.md)

[<span data-ttu-id="30d3f-131">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="30d3f-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
