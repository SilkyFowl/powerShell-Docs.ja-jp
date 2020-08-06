---
title: SelectionSet 要素 (Format) |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: cf47229993458492c712d28e04913e75d1bde386
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783400"
---
# <a name="selectionset-element-format"></a><span data-ttu-id="ea368-102">SelectionSet 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="ea368-102">SelectionSet Element (Format)</span></span>

<span data-ttu-id="ea368-103">セットの名前で参照できる .NET オブジェクトのセットを定義します。</span><span class="sxs-lookup"><span data-stu-id="ea368-103">Defines a set of .NET objects that can be referenced by the name of the set.</span></span>

<span data-ttu-id="ea368-104">Configuration 要素 (Format) SelectionSets 要素 (書式) Selectionsets 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="ea368-104">Configuration Element (Format) SelectionSets Element (Format) SelectionSet Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="ea368-105">構文</span><span class="sxs-lookup"><span data-stu-id="ea368-105">Syntax</span></span>

```xml
<SelectionSet>
  <Name>SelectionSetName</Name>
  <Types>...</Types>
</SelectionSet>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="ea368-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="ea368-106">Attributes and Elements</span></span>

<span data-ttu-id="ea368-107">次のセクションでは、要素の属性、子要素、および親要素について説明し `SelectionSet` ます。</span><span class="sxs-lookup"><span data-stu-id="ea368-107">The following sections describe the attributes, child elements, and the parent element of the `SelectionSet` element.</span></span> <span data-ttu-id="ea368-108">各選択セットには名前が必要であり、セットの .NET オブジェクトを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ea368-108">Each selection set must have a name, and it must specify the .NET objects of the set.</span></span>

### <a name="attributes"></a><span data-ttu-id="ea368-109">属性</span><span class="sxs-lookup"><span data-stu-id="ea368-109">Attributes</span></span>

<span data-ttu-id="ea368-110">なし。</span><span class="sxs-lookup"><span data-stu-id="ea368-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="ea368-111">子要素</span><span class="sxs-lookup"><span data-stu-id="ea368-111">Child Elements</span></span>

|<span data-ttu-id="ea368-112">要素</span><span class="sxs-lookup"><span data-stu-id="ea368-112">Element</span></span>|<span data-ttu-id="ea368-113">説明</span><span class="sxs-lookup"><span data-stu-id="ea368-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ea368-114">SelectionSet の Name 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="ea368-114">Name Element for SelectionSet (Format)</span></span>](./name-element-for-selectionset-format.md)|<span data-ttu-id="ea368-115">必須の要素です。</span><span class="sxs-lookup"><span data-stu-id="ea368-115">Required element.</span></span><br /><br /> <span data-ttu-id="ea368-116">選択セットを参照するために使用する名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="ea368-116">Specifies the name used to reference the selection set.</span></span>|
|[<span data-ttu-id="ea368-117">Types 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="ea368-117">Types Element (Format)</span></span>](./types-element-for-selectionset-format.md)|<span data-ttu-id="ea368-118">必須の要素です。</span><span class="sxs-lookup"><span data-stu-id="ea368-118">Required element.</span></span><br /><br /> <span data-ttu-id="ea368-119">選択セット内の .NET オブジェクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="ea368-119">Defines the .NET objects that are in the selection set.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="ea368-120">親要素</span><span class="sxs-lookup"><span data-stu-id="ea368-120">Parent Elements</span></span>

|<span data-ttu-id="ea368-121">要素</span><span class="sxs-lookup"><span data-stu-id="ea368-121">Element</span></span>|<span data-ttu-id="ea368-122">説明</span><span class="sxs-lookup"><span data-stu-id="ea368-122">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ea368-123">SelectionSets 要素の形式</span><span class="sxs-lookup"><span data-stu-id="ea368-123">SelectionSets Element Format</span></span>](./selectionsets-element-format.md)|<span data-ttu-id="ea368-124">書式設定ファイルのすべてのビューで使用できる .NET オブジェクトの共通セットを定義します。</span><span class="sxs-lookup"><span data-stu-id="ea368-124">Defines the common sets of .NET objects that can be used by all views of the formatting file.</span></span>|

## <a name="remarks"></a><span data-ttu-id="ea368-125">解説</span><span class="sxs-lookup"><span data-stu-id="ea368-125">Remarks</span></span>

<span data-ttu-id="ea368-126">継承によって関連付けられたオブジェクトのセットなど、1つの名前を使用して参照する関連オブジェクトのセットがある場合は、選択セットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="ea368-126">You can use selection sets when you have a set of related objects that you want to reference by using a single name, such as a set of objects that are related through inheritance.</span></span> <span data-ttu-id="ea368-127">ビューを定義するときに、各ビュー内のすべてのオブジェクトを一覧表示するのではなく、選択したセットの名前を使用してオブジェクトのセットを指定できます。</span><span class="sxs-lookup"><span data-stu-id="ea368-127">When defining your views, you can specify the set of objects by using the name of the selection set instead of listing all the objects within each view.</span></span>

<span data-ttu-id="ea368-128">共通選択セットは、書式設定ファイルのビューまたはビューの定義を定義するときに、名前によって指定されます。</span><span class="sxs-lookup"><span data-stu-id="ea368-128">Common selection sets are specified by their name when defining the views of the formatting file or the definitions of the views.</span></span> <span data-ttu-id="ea368-129">このような場合、 `SelectionSetName` 要素と要素の子要素は、 `ViewSelectedBy` `EntrySelectedBy` 使用するセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="ea368-129">In these cases, the `SelectionSetName` child element of the `ViewSelectedBy` and `EntrySelectedBy` elements specifies the set to be used.</span></span> <span data-ttu-id="ea368-130">選択セットの詳細については、「[オブジェクトのセットの定義](./defining-selection-sets.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ea368-130">For more information about selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

## <a name="example"></a><span data-ttu-id="ea368-131">例</span><span class="sxs-lookup"><span data-stu-id="ea368-131">Example</span></span>

<span data-ttu-id="ea368-132">次の例は、 `SelectionSet` 4 つの .net 型を定義する要素を示しています。</span><span class="sxs-lookup"><span data-stu-id="ea368-132">The following example shows a `SelectionSet` element that defines four .NET types.</span></span>

```xml
<SelectionSets>
  <SelectionSet>
    <Name>FileSystemTypes</Name>
    <Types>
     <TypeName>System.IO.DirectoryInfo</TypeName>
     <TypeName>System.IO.FileInfo</TypeName>
     <TypeName>Deserialized.System.IO.DirectoryInfo</TypeName>
     <TypeName>Deserialized.System.IO.FileInfo</TypeName>
    </Types>
  </SelectionSet>
</SelectionSets>
```

## <a name="see-also"></a><span data-ttu-id="ea368-133">参照</span><span class="sxs-lookup"><span data-stu-id="ea368-133">See Also</span></span>

[<span data-ttu-id="ea368-134">選択セットを定義する</span><span class="sxs-lookup"><span data-stu-id="ea368-134">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="ea368-135">SelectionSet の Name 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="ea368-135">Name Element of SelectionSet (Format)</span></span>](./name-element-for-selectionset-format.md)

[<span data-ttu-id="ea368-136">SelectionSets 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="ea368-136">SelectionSets Element (Format)</span></span>](./selectionsets-element-format.md)

[<span data-ttu-id="ea368-137">Types 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="ea368-137">Types Element (Format)</span></span>](./types-element-for-selectionset-format.md)

[<span data-ttu-id="ea368-138">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="ea368-138">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
