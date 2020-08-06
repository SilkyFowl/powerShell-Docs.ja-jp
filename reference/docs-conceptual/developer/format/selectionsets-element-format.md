---
title: SelectionSets 要素 (Format) |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 718b08e02220f285ef215fdca727492fd4407466
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785202"
---
# <a name="selectionsets-element-format"></a><span data-ttu-id="437a7-102">SelectionSets 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="437a7-102">SelectionSets Element (Format)</span></span>

<span data-ttu-id="437a7-103">書式設定ファイルのすべてのビューで使用できる .NET オブジェクトの共通セットを定義します。</span><span class="sxs-lookup"><span data-stu-id="437a7-103">Defines the common sets of .NET objects that can be used by all views of the formatting file.</span></span> <span data-ttu-id="437a7-104">書式設定ファイルのビューおよびコントロールは、選択セットの名前のみを使用して、オブジェクトの完全なセットを参照できます。</span><span class="sxs-lookup"><span data-stu-id="437a7-104">The views and controls of the formatting file can reference the complete set of objects by using only the name of the selection set.</span></span>

<span data-ttu-id="437a7-105">構成要素 SelectionSets 要素の形式</span><span class="sxs-lookup"><span data-stu-id="437a7-105">Configuration Element SelectionSets Element Format</span></span>

## <a name="syntax"></a><span data-ttu-id="437a7-106">構文</span><span class="sxs-lookup"><span data-stu-id="437a7-106">Syntax</span></span>

```xml
<SelectionSets>
  <SelectionSet>...</SelectionSet>
</SelectionSets>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="437a7-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="437a7-107">Attributes and Elements</span></span>

<span data-ttu-id="437a7-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `SelectionSets` ます。</span><span class="sxs-lookup"><span data-stu-id="437a7-108">The following sections describe the attributes, child elements, and parent element of the `SelectionSets` element.</span></span> <span data-ttu-id="437a7-109">各子要素は、セットの名前で参照できるオブジェクトのセットを定義します。</span><span class="sxs-lookup"><span data-stu-id="437a7-109">Each child element defines a set of objects that can be referenced by the name of the set.</span></span> <span data-ttu-id="437a7-110">子要素の順序は重要ではありません。</span><span class="sxs-lookup"><span data-stu-id="437a7-110">The order of the child elements is not significant.</span></span>

### <a name="attributes"></a><span data-ttu-id="437a7-111">属性</span><span class="sxs-lookup"><span data-stu-id="437a7-111">Attributes</span></span>

<span data-ttu-id="437a7-112">なし。</span><span class="sxs-lookup"><span data-stu-id="437a7-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="437a7-113">子要素</span><span class="sxs-lookup"><span data-stu-id="437a7-113">Child Elements</span></span>

|<span data-ttu-id="437a7-114">要素</span><span class="sxs-lookup"><span data-stu-id="437a7-114">Element</span></span>|<span data-ttu-id="437a7-115">説明</span><span class="sxs-lookup"><span data-stu-id="437a7-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="437a7-116">SelectionSet 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="437a7-116">SelectionSet Element (Format)</span></span>](./selectionset-element-format.md)|<span data-ttu-id="437a7-117">必須の要素です。</span><span class="sxs-lookup"><span data-stu-id="437a7-117">Required element.</span></span><br /><br /> <span data-ttu-id="437a7-118">セットの名前で参照できる .NET オブジェクトの1つのセットを定義します。</span><span class="sxs-lookup"><span data-stu-id="437a7-118">Defines a single set of .NET objects that can be referenced by the name of the set.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="437a7-119">親要素</span><span class="sxs-lookup"><span data-stu-id="437a7-119">Parent Elements</span></span>

|<span data-ttu-id="437a7-120">要素</span><span class="sxs-lookup"><span data-stu-id="437a7-120">Element</span></span>|<span data-ttu-id="437a7-121">説明</span><span class="sxs-lookup"><span data-stu-id="437a7-121">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="437a7-122">Configuration 要素</span><span class="sxs-lookup"><span data-stu-id="437a7-122">Configuration Element</span></span>](./configuration-element-format.md)|<span data-ttu-id="437a7-123">書式設定ファイルのトップレベルの要素を表します。</span><span class="sxs-lookup"><span data-stu-id="437a7-123">Represents the top-level element of a formatting file.</span></span>|

## <a name="remarks"></a><span data-ttu-id="437a7-124">解説</span><span class="sxs-lookup"><span data-stu-id="437a7-124">Remarks</span></span>

<span data-ttu-id="437a7-125">継承によって関連付けられたオブジェクトのセットなど、1つの名前を使用して参照する関連オブジェクトのセットがある場合は、選択セットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="437a7-125">You can use selection sets when you have a set of related objects that you want to reference by using a single name, such as a set of objects that are related through inheritance.</span></span> <span data-ttu-id="437a7-126">ビューを定義するときに、各ビュー内のすべてのオブジェクトを一覧表示するのではなく、選択したセットの名前を使用してオブジェクトのセットを指定できます。</span><span class="sxs-lookup"><span data-stu-id="437a7-126">When defining your views, you can specify the set of objects by using the name of the selection set instead of listing all the objects within each view.</span></span>

<span data-ttu-id="437a7-127">共通選択セットは、書式設定ファイルのビューまたはビューの定義を定義するときに、名前によって指定されます。</span><span class="sxs-lookup"><span data-stu-id="437a7-127">Common selection sets are specified by their name when defining the views of the formatting file or the definitions of the views.</span></span> <span data-ttu-id="437a7-128">このような場合、 `SelectionSetName` 要素と要素の子要素は、 `ViewSelectedBy` `EntrySelectedBy` 使用するセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="437a7-128">In these cases, the `SelectionSetName` child element of the `ViewSelectedBy` and `EntrySelectedBy` elements specifies the set to be used.</span></span> <span data-ttu-id="437a7-129">選択セットの詳細については、「[オブジェクトのセットの定義](./defining-selection-sets.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="437a7-129">For more information about selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="437a7-130">参照</span><span class="sxs-lookup"><span data-stu-id="437a7-130">See Also</span></span>

[<span data-ttu-id="437a7-131">Configuration 要素</span><span class="sxs-lookup"><span data-stu-id="437a7-131">Configuration Element</span></span>](./configuration-element-format.md)

[<span data-ttu-id="437a7-132">選択セットを定義する</span><span class="sxs-lookup"><span data-stu-id="437a7-132">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="437a7-133">SelectionSet 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="437a7-133">SelectionSet Element (Format)</span></span>](./selectionset-element-format.md)

[<span data-ttu-id="437a7-134">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="437a7-134">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
