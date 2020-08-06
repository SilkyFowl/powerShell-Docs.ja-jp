---
title: リストビュー (GroupBy) |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 7956d13e196454a3f6da185e9be74f9d3cb8ef63
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87773404"
---
# <a name="list-view-groupby"></a><span data-ttu-id="65525-102">リスト ビュー (グループ別)</span><span class="sxs-lookup"><span data-stu-id="65525-102">List View (GroupBy)</span></span>

<span data-ttu-id="65525-103">この例では、リストの行をグループに分割するリストビューを実装する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="65525-103">This example shows how to implement a list view that separates the rows of the list into groups.</span></span> <span data-ttu-id="65525-104">このリストビューには、Servicecontroller のプロパティが表示されます。 [Displayproperty =](/dotnet/api/System.ServiceProcess.ServiceController) [Get Service](/powershell/module/Microsoft.PowerShell.Management/Get-Service)コマンドレットによって返される Fullname オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="65525-104">This list view displays the properties of the [System.Serviceprocess.Servicecontroller?Displayproperty=Fullname](/dotnet/api/System.ServiceProcess.ServiceController) objects returned by the [Get-Service](/powershell/module/Microsoft.PowerShell.Management/Get-Service) cmdlet.</span></span> <span data-ttu-id="65525-105">リストビューのコンポーネントの詳細については、「[リストビューの作成](./creating-a-list-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="65525-105">For more information about the components of a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

### <a name="to-load-this-formatting-file"></a><span data-ttu-id="65525-106">この書式設定ファイルを読み込むには</span><span class="sxs-lookup"><span data-stu-id="65525-106">To load this formatting file</span></span>

1. <span data-ttu-id="65525-107">このトピックの「例」のセクションにある XML をテキストファイルにコピーします。</span><span class="sxs-lookup"><span data-stu-id="65525-107">Copy the XML from the Example section of this topic into a text file.</span></span>

2. <span data-ttu-id="65525-108">テキスト ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="65525-108">Save the text file.</span></span> <span data-ttu-id="65525-109">ファイルに拡張子を追加して、 `format.ps1xml` 書式設定ファイルとして識別するようにしてください。</span><span class="sxs-lookup"><span data-stu-id="65525-109">Be sure to add the `format.ps1xml` extension to the file to identify it as a formatting file.</span></span>

3. <span data-ttu-id="65525-110">Windows PowerShell を開き、次のコマンドを実行して、書式設定ファイルを現在のセッションに読み込み `Update-formatdata -prependpath PathToFormattingFile` ます。</span><span class="sxs-lookup"><span data-stu-id="65525-110">Open Windows PowerShell, and run the following command to load the formatting file into the current session: `Update-formatdata -prependpath PathToFormattingFile`.</span></span>

   > [!WARNING]
   > <span data-ttu-id="65525-111">この書式設定ファイルは、Windows PowerShell の書式設定ファイルによって既に定義されているオブジェクトの表示を定義します。</span><span class="sxs-lookup"><span data-stu-id="65525-111">This formatting file defines the display of an object that is already defined by a Windows PowerShell formatting file.</span></span> <span data-ttu-id="65525-112">`prependPath`コマンドレットを実行するときにパラメーターを使用する必要があります。このフォーマットファイルをモジュールとして読み込むことはできません。</span><span class="sxs-lookup"><span data-stu-id="65525-112">You must use the `prependPath` parameter when you run the cmdlet, and you cannot load this formatting file as a module.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="65525-113">対象</span><span class="sxs-lookup"><span data-stu-id="65525-113">Demonstrates</span></span>

<span data-ttu-id="65525-114">この書式設定ファイルは、次の XML 要素を示しています。</span><span class="sxs-lookup"><span data-stu-id="65525-114">This formatting file demonstrates the following XML elements:</span></span>

- <span data-ttu-id="65525-115">ビューの[Name](./name-element-for-view-format.md)要素。</span><span class="sxs-lookup"><span data-stu-id="65525-115">The [Name](./name-element-for-view-format.md) element for the view.</span></span>

- <span data-ttu-id="65525-116">ビューによって表示されるオブジェクトを定義する[Viewselectedby](./viewselectedby-element-format.md)要素。</span><span class="sxs-lookup"><span data-stu-id="65525-116">The [ViewSelectedBy](./viewselectedby-element-format.md) element that defines what objects are displayed by the view.</span></span>

- <span data-ttu-id="65525-117">オブジェクトの新しいグループをどのように表示するかを定義する[GroupBy](./viewselectedby-element-format.md)要素。</span><span class="sxs-lookup"><span data-stu-id="65525-117">The [GroupBy](./viewselectedby-element-format.md) element that defines how a new group of objects is displayed.</span></span>

- <span data-ttu-id="65525-118">ビューによって表示されるプロパティを定義する[ListControl](./listcontrol-element-format.md)要素。</span><span class="sxs-lookup"><span data-stu-id="65525-118">The [ListControl](./listcontrol-element-format.md) element that defines what property is displayed by the view.</span></span>

- <span data-ttu-id="65525-119">リストビューの行に表示される内容を定義する[ListItem](./listitem-element-for-listitems-for-listcontrol-format.md)要素。</span><span class="sxs-lookup"><span data-stu-id="65525-119">The [ListItem](./listitem-element-for-listitems-for-listcontrol-format.md) element that defines what is displayed in a row of the list view.</span></span>

- <span data-ttu-id="65525-120">表示されるプロパティを定義する[PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md)要素。</span><span class="sxs-lookup"><span data-stu-id="65525-120">The [PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md) element that defines which property is displayed.</span></span>

## <a name="example"></a><span data-ttu-id="65525-121">例</span><span class="sxs-lookup"><span data-stu-id="65525-121">Example</span></span>

<span data-ttu-id="65525-122">次の XML は、 [Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController.Status)プロパティの値が変更されるたびに新しいグループを開始するリストビューを定義します。</span><span class="sxs-lookup"><span data-stu-id="65525-122">The following XML defines a list view that starts a new group whenever the value of the [System.Serviceprocess.Servicecontroller.Status](/dotnet/api/System.ServiceProcess.ServiceController.Status) property changes.</span></span> <span data-ttu-id="65525-123">各グループが開始されると、プロパティの新しい値を含むカスタムラベルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="65525-123">When each group is started, a custom label is displayed that includes the new value of the property.</span></span>

```xml
<Configuration>
  <ViewDefinitions>
    <View>
      <Name>System.ServiceProcess.ServiceController</Name>
      <ViewSelectedBy>
        <TypeName>System.ServiceProcess.ServiceController</TypeName>
      </ViewSelectedBy>
      <GroupBy>
        <PropertyName>Status</PropertyName>
        <Label>New Service Status</Label>
      </GroupBy>
      <ListControl>
        <ListEntries>
          <ListEntry>
            <ListItems>
              <ListItem>
                <PropertyName>Name</PropertyName>
              </ListItem>
              <ListItem>
                <PropertyName>DisplayName</PropertyName>
              </ListItem>
              <ListItem>
                <PropertyName>ServiceType</PropertyName>
              </ListItem>
            </ListItems>
          </ListEntry>
        </ListEntries>
      </ListControl>
    </View>
  </ViewDefinitions>
</Configuration>
```

<span data-ttu-id="65525-124">次の例は、Windows PowerShell で Servicecontroller を表示する方法を示しています。 [Displayproperty = Fullname](/dotnet/api/System.ServiceProcess.ServiceController)オブジェクトこのフォーマットファイルが読み込まれた後。</span><span class="sxs-lookup"><span data-stu-id="65525-124">The following example shows how Windows PowerShell displays the [System.Serviceprocess.Servicecontroller?Displayproperty=Fullname](/dotnet/api/System.ServiceProcess.ServiceController) objects after this format file is loaded.</span></span> <span data-ttu-id="65525-125">グループラベルの前後に追加された空白行は、Windows PowerShell によって自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="65525-125">The blank lines added before and after the group label are automatically added by Windows PowerShell.</span></span>

```powershell
Get-Service f*
```

```output
   New Service Status: Stopped

Name        : Fax
DisplayName : Fax
ServiceType : Win32OwnProcess

   New Service Status: Running

Name        : FCSAM
DisplayName : Microsoft Antimalware Service
ServiceType : Win32OwnProcess

   New Service Status: Stopped

Name        : fdPHost
DisplayName : Function Discovery Provider Host
ServiceType : Win32ShareProcess

   New Service Status: Running

Name        : FDResPub
DisplayName : Function Discovery Resource Publication
ServiceType : Win32ShareProcess

Name        : FontCache
DisplayName : Windows Font Cache Service
ServiceType : Win32ShareProcess

   New Service Status: Stopped

Name        : FontCache3.0.0.0
DisplayName : Windows Presentation Foundation Font Cache 3.0.0.0
ServiceType : Win32OwnProcess

   New Service Status: Running

Name        : FSysAgent
DisplayName : Microsoft Forefront System Agent
ServiceType : Win32OwnProcess

Name        : FwcAgent
DisplayName : Firewall Client Agent
ServiceType : Win32OwnProcess
```

## <a name="see-also"></a><span data-ttu-id="65525-126">参照</span><span class="sxs-lookup"><span data-stu-id="65525-126">See Also</span></span>

[<span data-ttu-id="65525-127">書式設定ファイルの例</span><span class="sxs-lookup"><span data-stu-id="65525-127">Examples of Formatting Files</span></span>](./examples-of-formatting-files.md)

[<span data-ttu-id="65525-128">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="65525-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
