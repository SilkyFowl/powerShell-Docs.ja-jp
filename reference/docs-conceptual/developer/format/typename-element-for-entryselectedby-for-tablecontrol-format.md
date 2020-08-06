---
title: TableControl の EntrySelectedBy の TypeName 要素 (Format) |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: c514d3e6155278ddd3a0565c87e9377dc8419356
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87780204"
---
# <a name="typename-element-for-entryselectedby-for-tablecontrol-format"></a><span data-ttu-id="b8f32-102">TableControl の EntrySelectedBy の TypeName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="b8f32-102">TypeName Element for EntrySelectedBy for TableControl (Format)</span></span>

<span data-ttu-id="b8f32-103">テーブルビューのこのエントリを使用する .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="b8f32-103">Specifies a .NET type that uses this entry of the table view.</span></span> <span data-ttu-id="b8f32-104">テーブルエントリに指定できる型の数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="b8f32-104">There is no limit to the number of types that can be specified for a table entry.</span></span>

<span data-ttu-id="b8f32-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) TableControl Element (format) TableRowEntries Element (format) TableRowEntry Element (format) TableRowEntry の EntrySelectedBy Element (format) TypeName 要素 (format)</span><span class="sxs-lookup"><span data-stu-id="b8f32-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) EntrySelectedBy Element (Format) TypeName Element for EntrySelectedBy for TableRowEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="b8f32-106">構文</span><span class="sxs-lookup"><span data-stu-id="b8f32-106">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="b8f32-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="b8f32-107">Attributes and Elements</span></span>

<span data-ttu-id="b8f32-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `TypeName` ます。</span><span class="sxs-lookup"><span data-stu-id="b8f32-108">The following sections describe attributes, child elements, and the parent element of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="b8f32-109">属性</span><span class="sxs-lookup"><span data-stu-id="b8f32-109">Attributes</span></span>

<span data-ttu-id="b8f32-110">なし。</span><span class="sxs-lookup"><span data-stu-id="b8f32-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="b8f32-111">子要素</span><span class="sxs-lookup"><span data-stu-id="b8f32-111">Child Elements</span></span>

<span data-ttu-id="b8f32-112">なし。</span><span class="sxs-lookup"><span data-stu-id="b8f32-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="b8f32-113">親要素</span><span class="sxs-lookup"><span data-stu-id="b8f32-113">Parent Elements</span></span>

|<span data-ttu-id="b8f32-114">要素</span><span class="sxs-lookup"><span data-stu-id="b8f32-114">Element</span></span>|<span data-ttu-id="b8f32-115">説明</span><span class="sxs-lookup"><span data-stu-id="b8f32-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b8f32-116">EntrySelectedBy 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="b8f32-116">EntrySelectedBy Element (Format)</span></span>](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)|<span data-ttu-id="b8f32-117">このエントリを使用する .NET 型、またはこのエントリが使用されるために存在する必要がある条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="b8f32-117">Defines the .NET types that use this entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="b8f32-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="b8f32-118">Text Value</span></span>

<span data-ttu-id="b8f32-119">.NET 型の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="b8f32-119">Specify the name of the .NET type.</span></span>

## <a name="remarks"></a><span data-ttu-id="b8f32-120">解説</span><span class="sxs-lookup"><span data-stu-id="b8f32-120">Remarks</span></span>

<span data-ttu-id="b8f32-121">各リストエントリには、少なくとも1つの型名、選択セット、または選択条件が定義されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b8f32-121">Each list entry must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="b8f32-122">テーブルビューのコンポーネントの詳細については、「[テーブルビューの作成](./creating-a-table-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b8f32-122">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b8f32-123">参照</span><span class="sxs-lookup"><span data-stu-id="b8f32-123">See Also</span></span>

[<span data-ttu-id="b8f32-124">テーブル ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="b8f32-124">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="b8f32-125">EntrySelectedBy 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="b8f32-125">EntrySelectedBy Element (Format)</span></span>](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)

[<span data-ttu-id="b8f32-126">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="b8f32-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
