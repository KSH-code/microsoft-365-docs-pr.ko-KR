---
title: 끝점 흐름 커넥터용 Microsoft Defender
ms.reviewer: ''
description: Microsoft Defender for Endpoint Flow 커넥터를 사용하여 보안을 자동화하고 테넌트에서 새 경고가 발생할 때 트리거되는 흐름을 만들 수 있습니다.
keywords: flow, 지원되는 api, api, Microsoft 흐름, 쿼리, 자동화
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 33a7c7b1907ac761dfdde43a70bfb8f515235150
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51929302"
---
# <a name="microsoft-power-automate-formerly-microsoft-flow-and-azure-functions"></a><span data-ttu-id="8363f-104">Microsoft Power Automate(이전의 Microsoft Flow) 및 Azure Functions</span><span class="sxs-lookup"><span data-stu-id="8363f-104">Microsoft Power Automate (formerly Microsoft Flow), and Azure Functions</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8363f-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="8363f-105">**Applies to:**</span></span>
- [<span data-ttu-id="8363f-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="8363f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="8363f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8363f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


- <span data-ttu-id="8363f-108">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="8363f-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="8363f-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="8363f-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

<span data-ttu-id="8363f-110">모든 최신 보안 운영 센터의 표준 요구 사항은 보안 절차를 자동화하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8363f-110">Automating security procedures is a standard requirement for every modern Security Operations Center.</span></span> <span data-ttu-id="8363f-111">전문 사이버 방어자 부족으로 SOC가 가장 효율적인 방식으로 작동하고 자동화가 반드시 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8363f-111">The lack of professional cyber defenders forces SOC to work in the most efficient way and automation is a must.</span></span> <span data-ttu-id="8363f-112">Microsoft Power Automate는 정확히 구축된 여러 커넥터를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="8363f-112">Microsoft Power Automate supports different connectors that were built exactly for that.</span></span> <span data-ttu-id="8363f-113">몇 분 내에 종단간 프로시저 자동화를 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8363f-113">You can build an end-to-end procedure automation within a few minutes.</span></span>

<span data-ttu-id="8363f-114">Microsoft Defender API에는 다양한 기능이 있는 공식 Flow Connector가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8363f-114">Microsoft Defender API has an official Flow Connector with many capabilities.</span></span>

![자격 증명 편집 이미지1](images/api-flow-0.png)

> [!NOTE]
> <span data-ttu-id="8363f-116">프리미엄 커넥터 라이선싱 선행 조건에 대한 자세한 내용은 프리미엄 커넥터에 대한 라이선싱을 [참조합니다.](https://docs.microsoft.com/power-automate/triggers-introduction#licensing-for-premium-connectors)</span><span class="sxs-lookup"><span data-stu-id="8363f-116">For more details about premium connectors licensing prerequisites, see [Licensing for premium connectors](https://docs.microsoft.com/power-automate/triggers-introduction#licensing-for-premium-connectors).</span></span>


## <a name="usage-example"></a><span data-ttu-id="8363f-117">사용 예제</span><span class="sxs-lookup"><span data-stu-id="8363f-117">Usage example</span></span>

<span data-ttu-id="8363f-118">다음 예제에서는 테넌트에서 새 Alert가 발생할 때 트리거되는 Flow를 만드는 방법을 보여 주며,</span><span class="sxs-lookup"><span data-stu-id="8363f-118">The following example demonstrates how to create a Flow that is triggered any time a new Alert occurs on your tenant.</span></span>

1. <span data-ttu-id="8363f-119">[Microsoft Power Automate에 로그인합니다.](https://flow.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="8363f-119">Log in to [Microsoft Power Automate](https://flow.microsoft.com).</span></span>

2. <span data-ttu-id="8363f-120">Go to **My flows**  >  **New**  >  **Automated-from blank**.</span><span class="sxs-lookup"><span data-stu-id="8363f-120">Go to **My flows** > **New** > **Automated-from blank**.</span></span>

    ![자격 증명 편집 이미지2](images/api-flow-1.png)

3. <span data-ttu-id="8363f-122">흐름의 이름을 선택하고 트리거로 "Microsoft Defender ATP 트리거"를 검색한 다음 새 경고 트리거를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8363f-122">Choose a name for your Flow, search for "Microsoft Defender ATP Triggers" as the trigger, and then select the new Alerts trigger.</span></span>

    ![자격 증명 편집 이미지3](images/api-flow-2.png)

<span data-ttu-id="8363f-124">이제 새 경고가 발생할 때마다 트리거되는 Flow가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8363f-124">Now you have a Flow that is triggered every time a new Alert occurs.</span></span>

![자격 증명 편집 이미지4](images/api-flow-3.png)

<span data-ttu-id="8363f-126">이제 다음 단계를 선택하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8363f-126">All you need to do now is choose your next steps.</span></span>
<span data-ttu-id="8363f-127">예를 들어 경고의 심각도가 높음인 경우 장치를 격리하고 장치에 대한 전자 메일을 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8363f-127">For example, you can isolate the device if the Severity of the Alert is High and send an email about it.</span></span>
<span data-ttu-id="8363f-128">경고 트리거는 경고 ID와 컴퓨터 ID만 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8363f-128">The Alert trigger provides only the Alert ID and the Machine ID.</span></span> <span data-ttu-id="8363f-129">커넥터를 사용하여 이러한 엔터티를 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8363f-129">You can use the connector to expand these entities.</span></span>

### <a name="get-the-alert-entity-using-the-connector"></a><span data-ttu-id="8363f-130">커넥터를 사용하여 Alert 엔터티 사용</span><span class="sxs-lookup"><span data-stu-id="8363f-130">Get the Alert entity using the connector</span></span>

1. <span data-ttu-id="8363f-131">새 **단계를 위해 Microsoft Defender ATP를** 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8363f-131">Choose **Microsoft Defender ATP** for the new step.</span></span>

2. <span data-ttu-id="8363f-132">경고 **- 단일 경고 API를 를 선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="8363f-132">Choose **Alerts - Get single alert API**.</span></span>

3. <span data-ttu-id="8363f-133">마지막 단계에서 **경고 ID를** 입력으로 **설정**</span><span class="sxs-lookup"><span data-stu-id="8363f-133">Set the **Alert ID** from the last step as **Input**.</span></span>

    ![자격 증명 편집 이미지5](images/api-flow-4.png)

### <a name="isolate-the-device-if-the-alerts-severity-is-high"></a><span data-ttu-id="8363f-135">경고 심각도 높음인 경우 장치 격리</span><span class="sxs-lookup"><span data-stu-id="8363f-135">Isolate the device if the Alert's severity is High</span></span>

1. <span data-ttu-id="8363f-136">조건을 **새** 단계로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8363f-136">Add **Condition** as a new step.</span></span>

2. <span data-ttu-id="8363f-137">경고 심각도가 **높음과 같은지** 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="8363f-137">Check if the Alert severity **is equal to** High.</span></span>

   <span data-ttu-id="8363f-138">그렇다면 **Microsoft Defender ATP - 컴퓨터** ID 및 설명을 사용하여 컴퓨터 격리 작업을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8363f-138">If yes, add the **Microsoft Defender ATP - Isolate machine** action with the Machine ID and a comment.</span></span>

    ![자격 증명 편집 이미지6](images/api-flow-5.png)

3. <span data-ttu-id="8363f-140">경고 및 Isolation에 대한 전자 메일을 보내기 위한 새 단계를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8363f-140">Add a new step for emailing about the Alert and the Isolation.</span></span> <span data-ttu-id="8363f-141">Outlook 또는 Gmail과 같이 사용하기 쉬운 여러 전자 메일 커넥터가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8363f-141">There are multiple email connectors that are very easy to use, such as Outlook or Gmail.</span></span>

4. <span data-ttu-id="8363f-142">흐름을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="8363f-142">Save your flow.</span></span>

<span data-ttu-id="8363f-143">고급 헌팅  쿼리를 실행하여 예약된 흐름을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8363f-143">You can also create a **scheduled** flow that runs Advanced Hunting queries and much more!</span></span>

## <a name="related-topic"></a><span data-ttu-id="8363f-144">관련 항목</span><span class="sxs-lookup"><span data-stu-id="8363f-144">Related topic</span></span>
- [<span data-ttu-id="8363f-145">끝점 API용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="8363f-145">Microsoft Defender for Endpoint APIs</span></span>](apis-intro.md)
