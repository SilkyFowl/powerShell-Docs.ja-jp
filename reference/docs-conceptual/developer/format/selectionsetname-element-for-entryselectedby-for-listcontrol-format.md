---
title: ListControl (Format) の EntrySelectedBy の SelectionSetName 要素Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 4315d81da4ceeb7a5b171087434ae15fb09e6592
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785270"
---
# <a name="selectionsetname-element-for-entryselectedby-for-listcontrol-format"></a><span data-ttu-id="e24ff-102">ListControl の EntrySelectedBy の SelectionSetName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="e24ff-102">SelectionSetName Element for EntrySelectedBy for ListControl (Format)</span></span>

<span data-ttu-id="e24ff-103">リストエントリの一連の .NET オブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="e24ff-103">Specifies a set of .NET objects for the list entry.</span></span> <span data-ttu-id="e24ff-104">エントリに指定できる選択セットの数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="e24ff-104">There is no limit to the number of selection sets that can be specified for an entry.</span></span>

<span data-ttu-id="e24ff-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) ListControl Element (format) ListEntries Element (format) ListEntry Element (format) SelectionSetName Element for ListEntry (format) Element for ListEntry (Format) の EntrySelectedBy</span><span class="sxs-lookup"><span data-stu-id="e24ff-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element (Format) EntrySelectedBy Element for ListEntry (Format) SelectionSetName Element for EntrySelectedBy for ListEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="e24ff-106">構文</span><span class="sxs-lookup"><span data-stu-id="e24ff-106">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="e24ff-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="e24ff-107">Attributes and Elements</span></span>

<span data-ttu-id="e24ff-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `SelectionSetName` ます。</span><span class="sxs-lookup"><span data-stu-id="e24ff-108">The following sections describe attributes, child elements, and parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="e24ff-109">属性</span><span class="sxs-lookup"><span data-stu-id="e24ff-109">Attributes</span></span>

<span data-ttu-id="e24ff-110">なし。</span><span class="sxs-lookup"><span data-stu-id="e24ff-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="e24ff-111">子要素</span><span class="sxs-lookup"><span data-stu-id="e24ff-111">Child Elements</span></span>

<span data-ttu-id="e24ff-112">なし。</span><span class="sxs-lookup"><span data-stu-id="e24ff-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="e24ff-113">親要素</span><span class="sxs-lookup"><span data-stu-id="e24ff-113">Parent Elements</span></span>

|<span data-ttu-id="e24ff-114">要素</span><span class="sxs-lookup"><span data-stu-id="e24ff-114">Element</span></span>|<span data-ttu-id="e24ff-115">説明</span><span class="sxs-lookup"><span data-stu-id="e24ff-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e24ff-116">ListEntry の EntrySelectedBy 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="e24ff-116">EntrySelectedBy Element for ListEntry (Format)</span></span>](./entryselectedby-element-for-listentry-for-listcontrol-format.md)|<span data-ttu-id="e24ff-117">このリストエントリを使用する .NET 型、またはこのエントリが使用されるために存在する必要がある条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="e24ff-117">Defines the .NET types that use this list entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="e24ff-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="e24ff-118">Text Value</span></span>

<span data-ttu-id="e24ff-119">選択セットの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="e24ff-119">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="e24ff-120">解説</span><span class="sxs-lookup"><span data-stu-id="e24ff-120">Remarks</span></span>

<span data-ttu-id="e24ff-121">各リストエントリには、少なくとも1つの型名、選択セット、または選択条件が定義されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e24ff-121">Each list entry must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="e24ff-122">選択セットは、通常、複数のビューで使用されるオブジェクトのグループを定義する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="e24ff-122">Selection sets are typically used when you want to define a group of objects that are used in multiple views.</span></span> <span data-ttu-id="e24ff-123">たとえば、同じオブジェクトのセットに対してテーブルビューとリストビューを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="e24ff-123">For example, you might want to create a table view and a list view for the same set of objects.</span></span> <span data-ttu-id="e24ff-124">選択セットの定義の詳細については、「[ビューのオブジェクトセットの定義](./defining-selection-sets.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e24ff-124">For more information about defining selection sets, see [Defining Sets of objects for a View](./defining-selection-sets.md).</span></span>

<span data-ttu-id="e24ff-125">リストビューのコンポーネントの詳細については、「[リストビューの作成](./creating-a-list-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e24ff-125">For more information about the components of a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="e24ff-126">例</span><span class="sxs-lookup"><span data-stu-id="e24ff-126">Example</span></span>

<span data-ttu-id="e24ff-127">次の例では、リストビューのエントリの選択セットを指定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="e24ff-127">The following example shows how to specify a selection set for an entry of a list view.</span></span>

```xml
<ListEntry>
  <EntrySelectedBy>
    <SelectionSetName>NameofSelectionSet</SelectionSetName>
  </EntrySelectedBy>
  <ListItems>...</ListItems>
</ListEntry>
```

## <a name="see-also"></a><span data-ttu-id="e24ff-128">参照</span><span class="sxs-lookup"><span data-stu-id="e24ff-128">See Also</span></span>

[<span data-ttu-id="e24ff-129">リスト ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="e24ff-129">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="e24ff-130">ListEntry の EntrySelectedBy 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="e24ff-130">EntrySelectedBy Element for ListEntry (Format)</span></span>](./entryselectedby-element-for-listentry-for-listcontrol-format.md)

[<span data-ttu-id="e24ff-131">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="e24ff-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
