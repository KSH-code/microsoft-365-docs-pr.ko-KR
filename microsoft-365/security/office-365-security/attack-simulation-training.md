---
title: Microsoft Defender for Office 365를 사용하여 피싱 공격 시뮬레이션
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
description: 관리자는 Microsoft Defender for Office 365의 공격 시뮬레이션 교육을 사용하여 피싱 공격을 시뮬레이트하고 사용자에게 피싱 방지를 교육하는 방법을 배울 수 있습니다.
ms.openlocfilehash: 41a5a503fbc8aa5e41760c1cf420d5e3c6047d86
ms.sourcegitcommit: a76de3d1604d755b29053e7bf557c0008be6ad23
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2021
ms.locfileid: "49788054"
---
# <a name="simulate-a-phishing-attack"></a><span data-ttu-id="4a5ba-103">피싱 공격 시뮬레이션</span><span class="sxs-lookup"><span data-stu-id="4a5ba-103">Simulate a phishing attack</span></span>

<span data-ttu-id="4a5ba-104">Office 365용 Microsoft Defender의 공격 시뮬레이션 교육을 통해 조직에서 양성 사이버 공격 시뮬레이션을 실행하여 보안 정책 및 관행을 테스트하고 직원의 인식을 높이고 공격에 대한 인식을 낮출 수 있도록 교육할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a5ba-104">Attack simulation training in Microsoft Defender for Office 365 lets you run benign cyberattack simulations on your organization to test your security policies and practices, as well as train your employees to increase their awareness and decrease their susceptibility to attacks.</span></span> <span data-ttu-id="4a5ba-105">이 문서에서는 공격 시뮬레이션 교육을 사용하여 시뮬레이트된 피싱 공격을 만드는 방법을 단계적으로 연습합니다.</span><span class="sxs-lookup"><span data-stu-id="4a5ba-105">This article walks you through creating  a simulated phishing attack using attack simulation training.</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="4a5ba-106">시뮬레이션된 피싱 공격을 시작하기 위해 [Microsoft 365](https://security.microsoft.com/)보안  센터를 열고 전자 메일 & 공격 시뮬레이션 교육으로 이동한 다음 시뮬레이션 탭으로 \> 전환합니다. [](https://security.microsoft.com/attacksimulator?viewid=simulations)</span><span class="sxs-lookup"><span data-stu-id="4a5ba-106">To launch a simulated phishing attack, open the [Microsoft 365 security center](https://security.microsoft.com/), go to **Email & collaboration** \> **Attack simulation training**, and switch to the [**Simulations**](https://security.microsoft.com/attacksimulator?viewid=simulations) tab.</span></span>

<span data-ttu-id="4a5ba-107">**시뮬레이션에서**+ **시뮬레이션 실행을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4a5ba-107">Under **Simulations**, select **+ Launch a simulation**.</span></span>

![Microsoft 365 보안 센터에서 시뮬레이션 단추 시작](../../media/attack-sim-preview-launch.png)

> [!NOTE]
> <span data-ttu-id="4a5ba-109">시뮬레이션을 만들 때 어느 시점에서든 저장한 후 닫아서 나중에 시뮬레이션을 계속 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a5ba-109">At any point during simulation creation, you can save and close to continue configuring the simulation at a later time.</span></span>

## <a name="selecting-a-social-engineering-technique"></a><span data-ttu-id="4a5ba-110">소셜 엔지니어링 기술 선택</span><span class="sxs-lookup"><span data-stu-id="4a5ba-110">Selecting a social engineering technique</span></span>

<span data-ttu-id="4a5ba-111">[MITRE ATT 및 CK&](https://attack.mitre.org/techniques/enterprise/)프레임워크에서 ® 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4a5ba-111">Select from 4 different techniques, curated from the [MITRE ATT&CK® framework](https://attack.mitre.org/techniques/enterprise/).</span></span> <span data-ttu-id="4a5ba-112">다양한 기술에 대해 다양한 페이로드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a5ba-112">Different payloads are available for different techniques:</span></span>

- <span data-ttu-id="4a5ba-113">**자격 증명 수집은** 입력란이 있는 잘 알려진 웹 사이트로 사용자를 연결하여 사용자 이름 및 암호를 제출하여 자격 증명을 수집하려고 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="4a5ba-113">**Credential harvest** attempts to collect credentials by taking users to a well-known looking website with input boxes to submit a username and password.</span></span>
- <span data-ttu-id="4a5ba-114">**맬웨어 첨부** 파일은 메시지에 악성 첨부 파일을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="4a5ba-114">**Malware attachment** adds a malicious attachment to a message.</span></span> <span data-ttu-id="4a5ba-115">사용자가 첨부 파일을 열면 공격자가 대상의 장치를 손상시킬 수 있도록 임의의 코드가 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a5ba-115">When the user opens the attachment, arbitrary code is run that will help the attacker compromise the target's device.</span></span>
- <span data-ttu-id="4a5ba-116">**첨부 파일 링크는** 자격 증명 수집 하이브리드의 한 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="4a5ba-116">**Link in attachment** is a type of credential harvest hybrid.</span></span> <span data-ttu-id="4a5ba-117">공격자는 전자 메일 첨부 파일에 URL을 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="4a5ba-117">An attacker inserts a URL into an email attachment.</span></span> <span data-ttu-id="4a5ba-118">첨부 파일 내의 URL은 자격 증명 수집과 동일한 기술을 따르게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a5ba-118">The URL within the attachment follows the same technique as credential harvest.</span></span>
- <span data-ttu-id="4a5ba-119">**맬웨어에 대한** 링크는 잘 알려진 파일 공유 서비스에 호스트된 파일에서 일부 임의 코드를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="4a5ba-119">**Link to malware** will run some arbitrary code from a file hosted on a well-known file sharing service.</span></span> <span data-ttu-id="4a5ba-120">사용자에게 전송된 메시지에는 이 악성 파일에 대한 링크가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a5ba-120">The message sent to the user will contain a link to this malicious file.</span></span> <span data-ttu-id="4a5ba-121">파일을 열고 공격자가 대상의 장치를 손상시킬 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a5ba-121">Opening the file and help the attacker compromise the target's device.</span></span>

> [!TIP]
> <span data-ttu-id="4a5ba-122">각 **기술에** 대한 설명 내에서 세부 정보 보기를 클릭하면 해당 기술에 대한 추가 정보와 시뮬레이션 단계가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a5ba-122">Clicking on **View details** within the description of each technique will display further information and the simulation steps for the technique.</span></span>
>
> ![Microsoft 365 보안 센터의 공격 시뮬레이션 교육 내에서 자격 증명 수집을 위한 시뮬레이션 단계](../../media/attack-sim-preview-sim-steps.png)

<span data-ttu-id="4a5ba-124">기술을 선택한 후 다음을 클릭한 후 **시뮬레이션에** 이름과 설명(옵션)을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4a5ba-124">After you've selected the technique and clicked on **Next**, give your simulation a name and optionally a description.</span></span>

## <a name="selecting-a-payload"></a><span data-ttu-id="4a5ba-125">페이로드 선택</span><span class="sxs-lookup"><span data-stu-id="4a5ba-125">Selecting a payload</span></span>

<span data-ttu-id="4a5ba-126">다음으로 기존 페이로드 카탈로그에서 페이로드를 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a5ba-126">Next, you'll need to either select a payload from the pre-existing payload catalog.</span></span>

<span data-ttu-id="4a5ba-127">페이로드에는 다음을 선택하는 데 도움이 되는 다양한 데이터 포인트가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a5ba-127">Payloads have a number of data points to help you choose:</span></span>

- <span data-ttu-id="4a5ba-128">**클릭 속도는** 이 페이로드를 클릭한 사용자 수를 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="4a5ba-128">**Click rate** counts how many people clicked this payload.</span></span>
- <span data-ttu-id="4a5ba-129">**예측된** 손상율은 Office 365 고객용 Microsoft Defender의 페이로드에 대한 기록 데이터를 기반으로 이 페이로드에 의해 손상되는 사용자 비율을 예측합니다.</span><span class="sxs-lookup"><span data-stu-id="4a5ba-129">**Predicted compromise rate** predicts the percentage of people that will get compromised by this payload based on historical data for the payload across Microsoft Defender for Office 365 customers.</span></span>
- <span data-ttu-id="4a5ba-130">**시작된 시뮬레이션은** 이 페이로드가 다른 시뮬레이션에 사용된 횟수를 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="4a5ba-130">**Simulations launched** counts the number of times this payload was used in other simulations.</span></span>
- <span data-ttu-id="4a5ba-131">**필터를** **통해** 사용할 수 있는 복잡성은 페이로드 내의 지표 수를 기반으로 계산됩니다. 페이로드에서 공격 대상의 단서가 되는 지표 수를 기반으로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a5ba-131">**Complexity**, available through **filters**, is calculated based on the number of indicators within the payload that clue targets in on it being an attack.</span></span> <span data-ttu-id="4a5ba-132">지표가 수록 복잡성이 낮아집니다.</span><span class="sxs-lookup"><span data-stu-id="4a5ba-132">More indicators lead to lower complexity.</span></span>
- <span data-ttu-id="4a5ba-133">**필터를** **통해** 사용할 수 있는 원본은 페이로드가 테넌트에서 만들어지거나 Microsoft의 기존 페이로드 카탈로그(전역)의 일부인지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4a5ba-133">**Source**, available through **filters**, indicates whether the payload was created on your tenant or is a part of Microsoft's pre-existing payload catalog (global).</span></span>

![Microsoft 365 보안 센터의 공격 시뮬레이션 교육 내에서 선택한 페이로드](../../media/attack-sim-preview-select-payload.png)

<span data-ttu-id="4a5ba-135">목록에서 페이로드를 선택하여 해당 페이로드에 대한 추가 정보가 있는 페이로드의 미리 보기를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a5ba-135">Select a payload from the list to see a preview of the payload with additional information about it.</span></span>

<span data-ttu-id="4a5ba-136">자신만의 페이로드를 만들고자 하는 경우 공격 시뮬레이션 교육을 위한 [페이로드를 만드시다.](attack-simulation-training-payloads.md)</span><span class="sxs-lookup"><span data-stu-id="4a5ba-136">If you'd like to create your own payload, read [create a payload for attack simulation training](attack-simulation-training-payloads.md).</span></span>

## <a name="audience-targeting"></a><span data-ttu-id="4a5ba-137">대상 그룹 지정</span><span class="sxs-lookup"><span data-stu-id="4a5ba-137">Audience targeting</span></span>

<span data-ttu-id="4a5ba-138">이제 이 시뮬레이션의 대상을 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a5ba-138">Now it's time to select this simulation's audience.</span></span> <span data-ttu-id="4a5ba-139">조직의 모든  사용자를 포함하거나 특정 사용자 및 **그룹만 포함하도록 선택할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="4a5ba-139">You can choose to **include all users in your organization** or **include only specific users and groups**.</span></span>

<span data-ttu-id="4a5ba-140">특정 사용자 및 그룹만 **포함하도록** 선택하는 경우 다음 중 하나를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a5ba-140">When you choose to **include only specific users and groups** you can either:</span></span>

- <span data-ttu-id="4a5ba-141">**지난** 3개월 동안 시뮬레이션의 대상으로 지정되지 않은 사용자를 대상으로 지정하는 등 고급 검색 및 필터링 기능뿐만 아니라 테넌트에 대한 검색을 활용할 수 있는 사용자를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="4a5ba-141">**Add users**, which allows you to leverage search for your tenant, as well as advanced search and filtering capabilities, like targeting users who haven't been targeted by a simulation in the last 3 months.</span></span>
  <span data-ttu-id="4a5ba-142">![Microsoft 365 보안 센터의 공격 시뮬레이션 교육에서 사용자 필터링](../../media/attack-sim-preview-user-targeting.png)</span><span class="sxs-lookup"><span data-stu-id="4a5ba-142">![User filtering in attack simulation training on Microsoft 365 security center](../../media/attack-sim-preview-user-targeting.png)</span></span>
- <span data-ttu-id="4a5ba-143">**CSV에서 가져오기 기능을 사용하면** 이 시뮬레이션을 위해 미리 정의한 사용자 집합을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a5ba-143">**Import from CSV** allows you to import a predefined set of users for this simulation.</span></span>

## <a name="assigning-training"></a><span data-ttu-id="4a5ba-144">교육 할당</span><span class="sxs-lookup"><span data-stu-id="4a5ba-144">Assigning training</span></span>

<span data-ttu-id="4a5ba-145">교육을 통과하는 직원은 유사한 공격에 덜 공격하기에 각 시뮬레이션에 대한 교육을 할당하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4a5ba-145">We recommend that you assign training for each simulation, as employees who go through training are less susceptible to similar attacks.</span></span>

<span data-ttu-id="4a5ba-146">교육을 할당하거나 직접 교육 과정과 모듈을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a5ba-146">You can either choose to have training assigned for you or select training courses and modules yourself.</span></span>

<span data-ttu-id="4a5ba-147">교육 **기한을 선택하여** 직원들이 제시간에 교육을 완료할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a5ba-147">Select the **training due date** to make sure employees finish their training in a timely manner.</span></span>

> [!NOTE]
> <span data-ttu-id="4a5ba-148">직접 과정과 모듈을 선택하기로 선택한 경우 권장되는 콘텐츠와 사용 가능한 모든 과정 및 모듈을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a5ba-148">If you choose to select courses and modules yourself, you'll still be able to see the recommended content as well as all available courses and modules.</span></span>
>
> ![Microsoft 365 보안 센터의 공격 시뮬레이션 교육 내에서 권장 교육 추가](../../media/attack-sim-preview-add-training.png)

<span data-ttu-id="4a5ba-150">다음 단계에서 직접 교육을  선택하기로 선택한 경우 교육을 추가하고 교육 방문 페이지를 사용자 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a5ba-150">In the next steps you'll need to **Add trainings** if you opted to select it yourself, and customize your training landing page.</span></span> <span data-ttu-id="4a5ba-151">교육 방문 페이지를 미리 볼 수 있을 뿐만 아니라 머리더와 본문도 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a5ba-151">You'll be able to preview the training landing page, as well as change the header and body of it.</span></span>

## <a name="launch-details-and-review"></a><span data-ttu-id="4a5ba-152">시작 세부 정보 및 검토</span><span class="sxs-lookup"><span data-stu-id="4a5ba-152">Launch details and review</span></span>

<span data-ttu-id="4a5ba-153">이제 모든 것이 구성되면 이 시뮬레이션을 즉시 시작하거나 나중에 예약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a5ba-153">Now that everything is configured, you can launch this simulation immediately or schedule it for a later date.</span></span> <span data-ttu-id="4a5ba-154">또한 이 시뮬레이션을 종료할 때를 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a5ba-154">You will also need to choose when to end this simulation.</span></span> <span data-ttu-id="4a5ba-155">선택한 시간을 지난 후 이 시뮬레이션의 조작 캡처를 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="4a5ba-155">We will stop capturing interaction with this simulation past the selected time.</span></span>

<span data-ttu-id="4a5ba-156">**지역 인식 시간제네트론** 배달을 사용하도록 설정하여 해당 지역에 따라 작업 시간 동안 시뮬레이트된 공격 메시지를 직원에게 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="4a5ba-156">**Enable region aware timezone delivery** to deliver simulated attack messages to your employees during their working hours based on their region.</span></span>

<span data-ttu-id="4a5ba-157">완료되면 다음을 클릭하고  시뮬레이션의 세부 정보를 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="4a5ba-157">Once you're done, click on **Next** and review the details of your simulation.</span></span> <span data-ttu-id="4a5ba-158">편집을  클릭하여 돌아가서 변경해야 하는 세부 정보를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="4a5ba-158">Click on **Edit** on any of the parts to go back and change any details that need changing.</span></span> <span data-ttu-id="4a5ba-159">완료되면 제출을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="4a5ba-159">Once done, click **Submit**.</span></span>
