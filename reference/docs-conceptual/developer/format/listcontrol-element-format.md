---
title: ListControl 要素 (Format) |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 0173b9797bffcca74f1a32903686f771366ebb1b
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785729"
---
# <a name="listcontrol-element-format"></a><span data-ttu-id="e3517-102">ListControl 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="e3517-102">ListControl Element (Format)</span></span>

<span data-ttu-id="e3517-103">ビューのリスト形式を定義します。</span><span class="sxs-lookup"><span data-stu-id="e3517-103">Defines a list format for the view.</span></span>

<span data-ttu-id="e3517-104">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) ListControl 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="e3517-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="e3517-105">構文</span><span class="sxs-lookup"><span data-stu-id="e3517-105">Syntax</span></span>

```xml
<ListControl>
  <ListEntries>...</ListEntries>
</ListControl>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="e3517-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="e3517-106">Attributes and Elements</span></span>

<span data-ttu-id="e3517-107">次のセクションでは、要素の属性、子要素、および親要素について説明し `ListControl` ます。</span><span class="sxs-lookup"><span data-stu-id="e3517-107">The following sections describe the attributes, child elements, and the parent element of the `ListControl` element.</span></span> <span data-ttu-id="e3517-108">この要素には、1つの子要素のみを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="e3517-108">This element must contain only a single child element.</span></span>

### <a name="attributes"></a><span data-ttu-id="e3517-109">属性</span><span class="sxs-lookup"><span data-stu-id="e3517-109">Attributes</span></span>

<span data-ttu-id="e3517-110">なし。</span><span class="sxs-lookup"><span data-stu-id="e3517-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="e3517-111">子要素</span><span class="sxs-lookup"><span data-stu-id="e3517-111">Child Elements</span></span>

|<span data-ttu-id="e3517-112">要素</span><span class="sxs-lookup"><span data-stu-id="e3517-112">Element</span></span>|<span data-ttu-id="e3517-113">説明</span><span class="sxs-lookup"><span data-stu-id="e3517-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e3517-114">ListEntries 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="e3517-114">ListEntries Element (Format)</span></span>](./listentries-element-for-listcontrol-format.md)|<span data-ttu-id="e3517-115">必須の要素です。</span><span class="sxs-lookup"><span data-stu-id="e3517-115">Required element.</span></span><br /><br /> <span data-ttu-id="e3517-116">リストビューの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="e3517-116">Provides the definitions of the list view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="e3517-117">親要素</span><span class="sxs-lookup"><span data-stu-id="e3517-117">Parent Elements</span></span>

|<span data-ttu-id="e3517-118">要素</span><span class="sxs-lookup"><span data-stu-id="e3517-118">Element</span></span>|<span data-ttu-id="e3517-119">説明</span><span class="sxs-lookup"><span data-stu-id="e3517-119">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e3517-120">View 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="e3517-120">View Element (Format)</span></span>](./view-element-format.md)|<span data-ttu-id="e3517-121">1つ以上のオブジェクトのメンバーを表示するために使用されるビューを定義します。</span><span class="sxs-lookup"><span data-stu-id="e3517-121">Defines a view that is used to display the members of one or more objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="e3517-122">解説</span><span class="sxs-lookup"><span data-stu-id="e3517-122">Remarks</span></span>

<span data-ttu-id="e3517-123">リストビューの作成の詳細については、「[リストビューの作成](./creating-a-list-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e3517-123">For more information about creating a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="e3517-124">例</span><span class="sxs-lookup"><span data-stu-id="e3517-124">Example</span></span>

<span data-ttu-id="e3517-125">この例では、 [Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController)オブジェクトのリストビューを示します。</span><span class="sxs-lookup"><span data-stu-id="e3517-125">This example shows a list view for the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object.</span></span>

```
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <ListControl>
    <ListEntries>
      <ListEntry>...</ListEntry>
    </ListEntries>
  </ListControl>
</View>
```

## <a name="see-also"></a><span data-ttu-id="e3517-126">参照</span><span class="sxs-lookup"><span data-stu-id="e3517-126">See Also</span></span>

[<span data-ttu-id="e3517-127">View 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="e3517-127">View Element (Format)</span></span>](./view-element-format.md)

[<span data-ttu-id="e3517-128">ListEntries 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="e3517-128">ListEntries Element (Format)</span></span>](./listentries-element-for-listcontrol-format.md)

[<span data-ttu-id="e3517-129">リスト ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="e3517-129">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="e3517-130">Windows PowerShell のフォーマットファイルと型ファイルの作成</span><span class="sxs-lookup"><span data-stu-id="e3517-130">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
