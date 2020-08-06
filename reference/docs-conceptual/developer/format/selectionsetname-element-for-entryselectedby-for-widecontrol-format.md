---
title: WideControl (Format) の EntrySelectedBy の SelectionSetName 要素Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 546225b0619ebec83d04a7e27bbc298ffef0a14d
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785253"
---
# <a name="selectionsetname-element-for-entryselectedby-for-widecontrol-format"></a><span data-ttu-id="e4ed0-102">WideControl の EntrySelectedBy の SelectionSetName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="e4ed0-102">SelectionSetName Element for EntrySelectedBy for WideControl (Format)</span></span>

<span data-ttu-id="e4ed0-103">定義の .NET オブジェクトのセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="e4ed0-103">Specifies a set of .NET objects for the definition.</span></span> <span data-ttu-id="e4ed0-104">これらのオブジェクトのいずれかが表示されるたびに、定義が使用されます。</span><span class="sxs-lookup"><span data-stu-id="e4ed0-104">The definition is used whenever one of these objects is displayed.</span></span>

<span data-ttu-id="e4ed0-105">Configuration 要素 (Format) ViewDefinitions 要素 (形式) ビュー要素 (Format) WideControl Element (format) WideEntries Element (format) WideEntry Element (format) WideEntry (Format) SelectionSetName Element for WideEntry (format) の EntrySelectedBy 要素</span><span class="sxs-lookup"><span data-stu-id="e4ed0-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) EntrySelectedBy Element for WideEntry (Format) SelectionSetName Element for EntrySelectedBy for WideEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="e4ed0-106">構文</span><span class="sxs-lookup"><span data-stu-id="e4ed0-106">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="e4ed0-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="e4ed0-107">Attributes and Elements</span></span>

<span data-ttu-id="e4ed0-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `SelectionSetName` ます。</span><span class="sxs-lookup"><span data-stu-id="e4ed0-108">The following sections describe the attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="e4ed0-109">属性</span><span class="sxs-lookup"><span data-stu-id="e4ed0-109">Attributes</span></span>

<span data-ttu-id="e4ed0-110">なし。</span><span class="sxs-lookup"><span data-stu-id="e4ed0-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="e4ed0-111">子要素</span><span class="sxs-lookup"><span data-stu-id="e4ed0-111">Child Elements</span></span>

<span data-ttu-id="e4ed0-112">なし。</span><span class="sxs-lookup"><span data-stu-id="e4ed0-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="e4ed0-113">親要素</span><span class="sxs-lookup"><span data-stu-id="e4ed0-113">Parent Elements</span></span>

|<span data-ttu-id="e4ed0-114">要素</span><span class="sxs-lookup"><span data-stu-id="e4ed0-114">Element</span></span>|<span data-ttu-id="e4ed0-115">説明</span><span class="sxs-lookup"><span data-stu-id="e4ed0-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e4ed0-116">WideEntry の EntrySelectedBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="e4ed0-116">EntrySelectedBy Element for WideEntry (Format)</span></span>](./entryselectedby-element-for-wideentry-format.md)|<span data-ttu-id="e4ed0-117">このワイドエントリを使用する .NET 型、またはこのエントリが使用されるために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="e4ed0-117">Defines the .NET types that use this wide entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="e4ed0-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="e4ed0-118">Text Value</span></span>

<span data-ttu-id="e4ed0-119">選択セットの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="e4ed0-119">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="e4ed0-120">解説</span><span class="sxs-lookup"><span data-stu-id="e4ed0-120">Remarks</span></span>

<span data-ttu-id="e4ed0-121">各定義には、1つの型名、選択セット、または選択条件を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e4ed0-121">Each definition must specify one type name, selection set, or selection condition.</span></span>

<span data-ttu-id="e4ed0-122">選択セットは、通常、複数のビューで使用されるオブジェクトのグループを定義する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="e4ed0-122">Selection sets are typically used when you want to define a group of objects that are used in multiple views.</span></span> <span data-ttu-id="e4ed0-123">たとえば、同じオブジェクトのセットに対してテーブルビューとリストビューを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="e4ed0-123">For example, you might want to create a table view and a list view for the same set of objects.</span></span> <span data-ttu-id="e4ed0-124">選択セットの定義の詳細については、「[ビューのオブジェクトセットの定義](./defining-selection-sets.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e4ed0-124">For more information about defining selection sets, see [Defining Sets of Objects for a View](./defining-selection-sets.md).</span></span>

<span data-ttu-id="e4ed0-125">ワイドビューのその他のコンポーネントの詳細については、「[ワイドビューの作成](./creating-a-wide-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e4ed0-125">For more information about other components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e4ed0-126">参照</span><span class="sxs-lookup"><span data-stu-id="e4ed0-126">See Also</span></span>

[<span data-ttu-id="e4ed0-127">ワイド ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="e4ed0-127">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="e4ed0-128">選択セットを定義する</span><span class="sxs-lookup"><span data-stu-id="e4ed0-128">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="e4ed0-129">WideEntry の EntrySelectedBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="e4ed0-129">EntrySelectedBy Element for WideEntry (Format)</span></span>](./entryselectedby-element-for-wideentry-format.md)

[<span data-ttu-id="e4ed0-130">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="e4ed0-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
