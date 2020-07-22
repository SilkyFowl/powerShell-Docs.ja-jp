---
title: パラメーター情報を追加する方法
ms.date: 09/12/2016
ms.openlocfilehash: 15d0194a1d5449c65977703faf245e449d75d176
ms.sourcegitcommit: de59ff77c6535fc772c1e327b3c823295eaed6ea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/22/2020
ms.locfileid: "86893392"
---
# <a name="how-to-add-parameter-information"></a><span data-ttu-id="c61a7-102">パラメーター情報を追加する方法</span><span class="sxs-lookup"><span data-stu-id="c61a7-102">How to Add Parameter Information</span></span>

<span data-ttu-id="c61a7-103">このセクションでは、コマンドレットのヘルプトピックの「**パラメーター** 」セクションに表示されるコンテンツを追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c61a7-103">This section describes how to add content that is displayed in the **PARAMETERS** section of the cmdlet Help topic.</span></span> <span data-ttu-id="c61a7-104">ヘルプトピックの「**パラメーター** 」セクションでは、コマンドレットの各パラメーターの一覧を示し、各パラメーターの詳細について説明します。</span><span class="sxs-lookup"><span data-stu-id="c61a7-104">The **PARAMETERS** section of the Help topic lists each of the parameters of the cmdlet and provides a detailed description of each parameter.</span></span>

<span data-ttu-id="c61a7-105">**PARAMETERS**セクションの内容は、ヘルプトピックの「**構文**」セクションの内容と一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="c61a7-105">The content of the **PARAMETERS** section should be consistent with the content of the **SYNTAX** section of the Help topic.</span></span> <span data-ttu-id="c61a7-106">**構文**と**パラメーター**ノードの両方に類似した XML 要素が含まれているかどうかを確認するのは、ヘルプの作成者の責任です。</span><span class="sxs-lookup"><span data-stu-id="c61a7-106">It is the responsibility of the Help author to make sure that both the **Syntax** and **Parameters** node contain similar XML elements.</span></span>

> [!NOTE]
> <span data-ttu-id="c61a7-107">ヘルプファイルの完全なビューを表示するには、 `dll-Help.xml` PowerShell インストールディレクトリにあるいずれかのファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="c61a7-107">For a complete view of a Help file, open one of the `dll-Help.xml` files located in the PowerShell installation directory.</span></span> <span data-ttu-id="c61a7-108">たとえば、ファイルには、 `Microsoft.PowerShell.Commands.Management.dll-Help.xml` いくつかの PowerShell コマンドレットのコンテンツが含まれています。</span><span class="sxs-lookup"><span data-stu-id="c61a7-108">For example, the `Microsoft.PowerShell.Commands.Management.dll-Help.xml` file contains content for several of the PowerShell cmdlets.</span></span>

### <a name="to-add-parameters"></a><span data-ttu-id="c61a7-109">パラメーターを追加するには</span><span class="sxs-lookup"><span data-stu-id="c61a7-109">To Add Parameters</span></span>

1. <span data-ttu-id="c61a7-110">コマンドレットのヘルプファイルを開き、ドキュメント化しているコマンドレットのコマンドノードを見つけます。</span><span class="sxs-lookup"><span data-stu-id="c61a7-110">Open the cmdlet Help file and locate the Command node for the cmdlet you are documenting.</span></span> <span data-ttu-id="c61a7-111">新しいコマンドレットを追加する場合は、新しいコマンドノードを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c61a7-111">If you are adding a new cmdlet you will need to create a new Command node.</span></span> <span data-ttu-id="c61a7-112">ヘルプファイルには、ヘルプコンテンツを提供しているコマンドレットごとにコマンドノードが含まれています。</span><span class="sxs-lookup"><span data-stu-id="c61a7-112">Your Help file will contain a Command node for each cmdlet that you are providing Help content for.</span></span> <span data-ttu-id="c61a7-113">空のコマンドノードの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="c61a7-113">Here is an example of a blank Command node.</span></span>

    ```xml
    <command:command>
    </command:command>
    ```

1. <span data-ttu-id="c61a7-114">次に示すように、[コマンド] ノードで [説明] ノードを見つけて、[パラメーター] ノードを追加します。</span><span class="sxs-lookup"><span data-stu-id="c61a7-114">Within the Command node, locate the Description node and add a Parameters node as shown below.</span></span>
   <span data-ttu-id="c61a7-115">パラメーターノードは1つしか使用できません。構文ノードの直後に指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c61a7-115">Only one Parameters node is allowed, and it should immediately follow the Syntax node.</span></span>

    ```xml
    <command:command>
      <command:details></command:details>
      <maml:description></maml:description>
      <command:syntax></command:syntax>
      <command:parameters>
      </command:Parameters>
    </command:command>
    ```

1. <span data-ttu-id="c61a7-116">次に示すように、[パラメーター] ノード内で、コマンドレットの各パラメーターの**パラメーター**ノードを追加します。</span><span class="sxs-lookup"><span data-stu-id="c61a7-116">Within the Parameters node, add a **Parameter** node for each parameter of the cmdlet as shown below.</span></span>

   <span data-ttu-id="c61a7-117">この例では、3つのパラメーターに**パラメーター**ノードが追加されています。</span><span class="sxs-lookup"><span data-stu-id="c61a7-117">In this example, a **Parameter** node is added for three parameters.</span></span>

    ```xml
    <command:parameters>
      <command:parameter></command:parameter>
      <command:parameter></command:parameter>
      <command:parameter></command:parameter>
    </command:Parameters>
    ```

   <span data-ttu-id="c61a7-118">これらは構文ノードで使用される XML タグと同じであるため、ここで指定するパラメーターは、構文ノードで指定されたパラメーターと一致する必要があるため、[構文] ノードからパラメーターノードをコピーし、[パラメーター] ノードに貼り付けることができます。</span><span class="sxs-lookup"><span data-stu-id="c61a7-118">Because these are the same XML tags that are used in the Syntax node, and because the parameters specified here must match the parameters specified by the Syntax node, you can copy the Parameter nodes from the Syntax node and paste them into the Parameters node.</span></span> <span data-ttu-id="c61a7-119">ただし、構文内の複数のパラメーターセットでパラメーターが指定されている場合でも、パラメーターノードのインスタンスを1つだけコピーしてください。</span><span class="sxs-lookup"><span data-stu-id="c61a7-119">However, be sure to copy only one instance of a Parameter node, even if the parameter is specified in multiple parameter sets in the syntax.</span></span>

1. <span data-ttu-id="c61a7-120">各パラメーターノードについて、各パラメーターの特性を定義する属性値を設定します。</span><span class="sxs-lookup"><span data-stu-id="c61a7-120">For each Parameter node, set the attribute values that define the characteristics of each parameter.</span></span> <span data-ttu-id="c61a7-121">これらの属性には、required、グロビング、pipelineinput、position などがあります。</span><span class="sxs-lookup"><span data-stu-id="c61a7-121">These attributes include the following: required, globbing, pipelineinput, and position.</span></span>

    ```xml
    <command:parameters>
      <command:parameter required="true" globbing="true"
               pipelineInput="false" position="named">
      </command:parameter>
      <command:parameter required="false" globbing="false"
               pipelineInput="false" position="named">
      </command:parameter>
      <command:parameter required="false" globbing="false"
               pipelineInput="false" position="named" ></command:parameter>
    </command:Parameters>
    ```

1. <span data-ttu-id="c61a7-122">パラメーターノードごとに、パラメーターの名前を追加します。</span><span class="sxs-lookup"><span data-stu-id="c61a7-122">For each Parameter node, add the name of the parameter.</span></span> <span data-ttu-id="c61a7-123">パラメーターノードに追加されたパラメーター名の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="c61a7-123">Here is an example of the parameter name added to the Parameter node.</span></span>

    ```xml
    <command:parameters>
      <command:parameter required="true" globbing="true"
               pipelineInput="false" position="named">
        <maml:name> Add parameter name...  </maml:name>
      </command:parameter>
    </command:Parameters>
    ```

1. <span data-ttu-id="c61a7-124">**パラメーター**ノードごとに、パラメーターの説明を追加します。</span><span class="sxs-lookup"><span data-stu-id="c61a7-124">For each **Parameter** node, add the description of the parameter.</span></span> <span data-ttu-id="c61a7-125">**パラメーターノードに**追加されたパラメーターの説明の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="c61a7-125">Here is an example of the parameter description added to the **Parameter** node.</span></span>

    ```xml
    <command:parameters>
      <command:parameter required="true" globbing="true"
               pipelineInput="false" position="named">
        <maml:name> Add parameter name...  </maml:name>
        <maml:description>
          <maml:para> Add parameter description... </maml:para>
        </maml:description>
      </command:parameter>
    </command:parameters>
    ```

1. <span data-ttu-id="c61a7-126">**パラメーター**ノードごとに、パラメーターの .net 型を追加します。</span><span class="sxs-lookup"><span data-stu-id="c61a7-126">For each **Parameter** node, add the .NET type of the parameter.</span></span> <span data-ttu-id="c61a7-127">パラメーターの型がパラメーター名と共に表示されます。</span><span class="sxs-lookup"><span data-stu-id="c61a7-127">The parameter type is displayed along with the parameter name.</span></span>

   <span data-ttu-id="c61a7-128">**パラメーターノードに**追加された .net 型のパラメーターの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="c61a7-128">Here is an example of the parameter .NET type added to the **Parameter** node.</span></span>

    ```xml
    <command:parameters>
      <command:parameter required="true" globbing="true"
               pipelineInput="false" position="named">
        <maml:name> Add parameter name...  </maml:name>
        <maml:description>
          <maml:para> Add parameter description... </maml:para>
        </maml:description>
        <dev:type> Add .NET Framework type... </dev:type>
      </command:parameter>
    </command:parameters>
    ```

1. <span data-ttu-id="c61a7-129">**パラメーター**ノードごとに、パラメーターの既定値を追加します。</span><span class="sxs-lookup"><span data-stu-id="c61a7-129">For each **Parameter** node, add the default value of the parameter.</span></span> <span data-ttu-id="c61a7-130">コンテンツが表示されると、次の文がパラメーターの説明に追加されます。 **DefaultValue**が既定値です。</span><span class="sxs-lookup"><span data-stu-id="c61a7-130">The following sentence is added to the parameter description when the content is displayed: **DefaultValue** is the default.</span></span>

   <span data-ttu-id="c61a7-131">**パラメーターノードに**既定値を追加する例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="c61a7-131">Here is an example of the parameter default value is added to the **Parameter** node.</span></span>

    ```xml
    <command:parameters>
      <command:parameter required="true" globbing="true"
               pipelineInput="false" position="named">
        <maml:name> Add parameter name...  </maml:name>
        <maml:description>
          <maml:para> Add parameter description... </maml:para>
        </maml:description>
        <dev:type> Add .NET Framework type... </dev:type>
        <dev:defaultvalue> Add default value...</dev:defaultvalue>
      </command:parameter>
    </command:parameters>
    ```

1. <span data-ttu-id="c61a7-132">複数の値を持つパラメーターごとに、使用可能な値ノードを追加します。</span><span class="sxs-lookup"><span data-stu-id="c61a7-132">For each Parameter that has multiple values, add a possible values node.</span></span>

   <span data-ttu-id="c61a7-133">パラメーターに使用可能な2つの値を定義する、使用可能な値ノードのの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="c61a7-133">Here is an example of the of a possible values node that defines two possible values for the parameter</span></span>

    ```xml
    <dev:possiblevalues>
      <dev:possiblevalue>
        <dev:value>Unknown</dev:value>
        <maml:description>
          <maml:para></maml:para>
        </maml:description>
      </dev:possiblevalue>
      <dev:possiblevalue>
        <dev:value>String</dev:value>
        <maml:description>
          <maml:para></maml:para>
        </maml:description>
      </dev:possibleValue>
    </dev:possiblevalues>
    ```

<span data-ttu-id="c61a7-134">ここでは、パラメーターを追加する際の注意事項について説明します。</span><span class="sxs-lookup"><span data-stu-id="c61a7-134">Here are some things to remember when adding parameters.</span></span>

- <span data-ttu-id="c61a7-135">パラメーターの属性は、コマンドレットのヘルプトピックのすべてのビューに表示されません。</span><span class="sxs-lookup"><span data-stu-id="c61a7-135">The attributes of the parameter are not displayed in all views of the cmdlet Help topic.</span></span> <span data-ttu-id="c61a7-136">ただし、ユーザーがトピックの**Full** ( `Get-Help <cmdletname> -full` ) または**parameter** () ビューを要求したときに、パラメーターの説明の後の表に表示され `Get-Help <cmdletname> -parameter` ます。</span><span class="sxs-lookup"><span data-stu-id="c61a7-136">However, they are displayed in a table following the parameter description when the user asks for the **Full** (`Get-Help <cmdletname> -full`) or **Parameter** (`Get-Help <cmdletname> -parameter`) view of the topic.</span></span>

- <span data-ttu-id="c61a7-137">パラメーターの説明は、コマンドレットのヘルプトピックの中で最も重要な部分の1つです。</span><span class="sxs-lookup"><span data-stu-id="c61a7-137">The parameter description is one of the most important parts of a cmdlet Help topic.</span></span> <span data-ttu-id="c61a7-138">説明は簡潔で、完全なものである必要があります。</span><span class="sxs-lookup"><span data-stu-id="c61a7-138">The description should be brief, as well as thorough.</span></span> <span data-ttu-id="c61a7-139">また、2つのパラメーターが相互に対話する場合など、パラメーターの説明が長すぎる場合は、コマンドレットのヘルプトピックの「NOTES」セクションでコンテンツを追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="c61a7-139">Also, remember that if the parameter description becomes too long, such as when two parameters interact with each other, you can add more content in the NOTES section of the cmdlet Help topic.</span></span>

  <span data-ttu-id="c61a7-140">パラメーターの説明は、2種類の情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="c61a7-140">The parameter description provides two types of information.</span></span>

- <span data-ttu-id="c61a7-141">パラメーターを使用した場合のコマンドレットの動作</span><span class="sxs-lookup"><span data-stu-id="c61a7-141">What the cmdlet does when the parameter is used.</span></span>

- <span data-ttu-id="c61a7-142">パラメーターの有効な値を指定します。</span><span class="sxs-lookup"><span data-stu-id="c61a7-142">What a legal value is for the parameter.</span></span>

- <span data-ttu-id="c61a7-143">パラメーター値は .NET オブジェクトとして表現されるため、ユーザーは従来のコマンドラインヘルプよりもこれらの値に関する詳細情報を必要とします。</span><span class="sxs-lookup"><span data-stu-id="c61a7-143">Because the parameter values are expressed as .NET objects, users need more information about these values than they would in a traditional command-line Help.</span></span> <span data-ttu-id="c61a7-144">パラメーターによって使用されるデータの種類をユーザーに通知し、例を含めます。</span><span class="sxs-lookup"><span data-stu-id="c61a7-144">Tell the user what type of data the parameter is designed to accept, and include examples.</span></span>

<span data-ttu-id="c61a7-145">パラメーターの既定値は、パラメーターがコマンドラインで指定されていない場合に使用される値です。</span><span class="sxs-lookup"><span data-stu-id="c61a7-145">The default value of the parameter is the value that is used if the parameter is not specified on the command line.</span></span> <span data-ttu-id="c61a7-146">既定値は省略可能であり、必須パラメーターなど、一部のパラメーターには必要ないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="c61a7-146">Note that the default value is optional, and is not needed for some parameters, such as required parameters.</span></span> <span data-ttu-id="c61a7-147">ただし、ほとんどのオプションのパラメーターには既定値を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c61a7-147">However, you should specify a default value for most optional parameters.</span></span>

<span data-ttu-id="c61a7-148">既定値は、ユーザーがパラメーターを使用しない場合の効果を理解するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="c61a7-148">The default value helps the user to understand the effect of not using the parameter.</span></span> <span data-ttu-id="c61a7-149">"現在のディレクトリ" や "PowerShell のインストールディレクトリ ()" など、オプションのパスの既定値を指定し `$PSHOME` ます。</span><span class="sxs-lookup"><span data-stu-id="c61a7-149">Describe the default value very specifically, such as the "Current directory" or the "PowerShell installation directory (`$PSHOME`)" for an optional path.</span></span> <span data-ttu-id="c61a7-150">また、 **passthru**パラメーターに使用される次の文など、既定値を説明する文を記述することもできます。 "passthru が指定されていない場合、コマンドレットはオブジェクトをパイプラインから渡しません。"</span><span class="sxs-lookup"><span data-stu-id="c61a7-150">You can also write a sentence that describes the default, such as the following sentence used for the **PassThru** parameter: "If PassThru is not specified, the cmdlet does not pass objects down the pipeline."</span></span> <span data-ttu-id="c61a7-151">また、値はフィールド名の**既定値**の反対に表示されるため、エントリに "Default value" という用語を含める必要はありません。</span><span class="sxs-lookup"><span data-stu-id="c61a7-151">Also, because the value is displayed opposite the field name **Default value**, you do not need to include the term "default value" in the entry.</span></span>

<span data-ttu-id="c61a7-152">パラメーターの既定値は、コマンドレットのヘルプトピックのすべてのビューに表示されません。</span><span class="sxs-lookup"><span data-stu-id="c61a7-152">The default value of the parameter is not displayed in all views of the cmdlet Help topic.</span></span> <span data-ttu-id="c61a7-153">ただし、ユーザーがトピックの**Full** ( `Get-Help <cmdletname> -full` ) または**parameter** () ビューを要求したときに、パラメーターの説明に続くテーブル (パラメーター属性と共に) に表示され `Get-Help
<cmdletname> -parameter` ます。</span><span class="sxs-lookup"><span data-stu-id="c61a7-153">However, it is displayed in a table (along with the parameter attributes) following the parameter description when the user asks for the **Full** (`Get-Help <cmdletname> -full`) or **Parameter** (`Get-Help
<cmdletname> -parameter`) view of the topic.</span></span>

<span data-ttu-id="c61a7-154">次の XML は、 `<dev:defaultValue>` ノードに追加されたタグのペアを示して `<command:parameter>` います。</span><span class="sxs-lookup"><span data-stu-id="c61a7-154">The following XML shows a pair of `<dev:defaultValue>` tags added to the `<command:parameter>` node.</span></span>
<span data-ttu-id="c61a7-155">既定値は、終了タグの直後 `</command:parameterValue>` (パラメーター値が指定されている場合) または `</maml:description>` パラメーターの説明の終了タグの直後に続くことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="c61a7-155">Notice that the default value follows immediately after the closing `</command:parameterValue>` tag (when the parameter value is specified) or the closing `</maml:description>` tag of the parameter description.</span></span> <span data-ttu-id="c61a7-156">name:</span><span class="sxs-lookup"><span data-stu-id="c61a7-156">name.</span></span>

```xml
<command:parameters>
  <command:parameter required="true" globbing="true"
           pipelineInput="false" position="named">
    <maml:name> Parameter name </maml:name>
    <maml:description>
      <maml:para> Parameter Description </maml:para>
    </maml:description>
    <command:parameterValue required="true">
      Value
    </command:parameterValue>
    <dev:defaultValue> Default parameter value </dev:defaultValue>
  </command:parameter>
</command:parameters>
```

<span data-ttu-id="c61a7-157">列挙型の値の追加</span><span class="sxs-lookup"><span data-stu-id="c61a7-157">Add Values for Enumerated Types</span></span>

<span data-ttu-id="c61a7-158">パラメーターに列挙型の複数の値または値が含まれている場合は、省略可能なノードを使用でき \<dev:possibleValues> ます。</span><span class="sxs-lookup"><span data-stu-id="c61a7-158">If the parameter has multiple values or values of an enumerated type, you can use an optional \<dev:possibleValues> node.</span></span> <span data-ttu-id="c61a7-159">このノードでは、複数の値の名前と説明を指定できます。</span><span class="sxs-lookup"><span data-stu-id="c61a7-159">This node allows you to specify a name and description for multiple values.</span></span>

<span data-ttu-id="c61a7-160">列挙値の説明はコマンドレットによって表示される既定のヘルプビューには表示されません `Get-Help` が、他のヘルプビューアーではビューにこのコンテンツが表示される場合があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="c61a7-160">Be aware that the descriptions of the enumerated values do not appear in any of the default Help views displayed by the `Get-Help` cmdlet, but other Help viewers may display this content in their views.</span></span>

<span data-ttu-id="c61a7-161">次の XML は、 `<dev:possibleValues>` 2 つの値が指定されたノードを示しています。</span><span class="sxs-lookup"><span data-stu-id="c61a7-161">The following XML shows a `<dev:possibleValues>` node with two values specified.</span></span>

```xml
<command:parameters>
  <command:parameter required="true" globbing="true"
           pipelineInput="false" position="named">
    <maml:name> Parameter name </maml:name>
    <maml:description>
      <maml:para> Parameter Description </maml:para>
    </maml:description>
    <command:parameterValue required="true">
      Value
    </command:parameterValue>
    <dev:defaultValue> Default parameter value </dev:defaultValue>
    <dev:possibleValues>
      <dev:possibleValue>
        <dev:value> Value 1 </dev:value>
        <maml:description>
          <maml:para> Description 1 </maml:para>
        </maml:description>
      <dev:possibleValue>
      <dev:possibleValue>
        <dev:value> Value 2 </dev:value>
        <maml:description>
          <maml:para> Description 2 </maml:para>
        </maml:description>
      <dev:possibleValue>
    </dev:possibleValues>
  </command:parameter>
</command:parameters>
```
