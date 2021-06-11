---
title: Microsoft Defender를 사용하여 피싱 공격을 Office 365
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: m365-security
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 관리자는 피싱 공격을 시뮬레이션하고 사용자를 피싱 방지를 위한 Microsoft Defender의 공격 시뮬레이션 교육을 사용하여 피싱 방지를 교육하는 방법을 Office 365.
ms.technology: mdo
ms.openlocfilehash: d82e7544e6795e4514cf1949645107c53fc69c61
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878367"
---
# <a name="simulate-a-phishing-attack"></a><span data-ttu-id="22d8b-103">피싱 공격 시뮬레이션</span><span class="sxs-lookup"><span data-stu-id="22d8b-103">Simulate a phishing attack</span></span>

<span data-ttu-id="22d8b-104">**Microsoft** [Defender for Office 365 요금제 2에 적용](defender-for-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="22d8b-104">**Applies to** [Microsoft Defender for Office 365 plan 2](defender-for-office-365.md)</span></span>

<span data-ttu-id="22d8b-105">Microsoft Defender for Office 365 공격 시뮬레이션 교육을 사용하면 조직에서 양성 사이버 공격 시뮬레이션을 실행하여 보안 정책 및 관행을 테스트할 수 있을 뿐만 아니라 직원의 인식을 높이고 공격에 대한 인식을 낮출 수 있도록 교육할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22d8b-105">Attack simulation training in Microsoft Defender for Office 365 lets you run benign cyberattack simulations on your organization to test your security policies and practices, as well as train your employees to increase their awareness and decrease their susceptibility to attacks.</span></span> <span data-ttu-id="22d8b-106">이 문서에서는 공격 시뮬레이션 교육을 사용하여 시뮬레이션된 피싱 공격을 만드는 방법을 단계적으로 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="22d8b-106">This article walks you through creating  a simulated phishing attack using attack simulation training.</span></span>

<span data-ttu-id="22d8b-107">공격 시뮬레이션 교육에 대한 시작 정보는 공격 시뮬레이션 교육 사용 [시작을 참조하세요.](attack-simulation-training-get-started.md)</span><span class="sxs-lookup"><span data-stu-id="22d8b-107">For getting started information about Attack simulation training, see [Get started using Attack simulation training](attack-simulation-training-get-started.md).</span></span>

<span data-ttu-id="22d8b-108">시뮬레이션된 피싱 공격을 시작하기 위해 Microsoft 365 Defender 포털()을 열고 전자 메일 & 공동 작업 공격 시뮬레이션 교육으로 이동한 후 시뮬레이션 탭으로 <https://security.microsoft.com/>  \> 전환합니다. **[](https://security.microsoft.com/attacksimulator?viewid=simulations)**</span><span class="sxs-lookup"><span data-stu-id="22d8b-108">To launch a simulated phishing attack, open the Microsoft 365 Defender portal (<https://security.microsoft.com/>), go to **Email & collaboration** \> **Attack simulation training**, and switch to the **[Simulations](https://security.microsoft.com/attacksimulator?viewid=simulations)** tab.</span></span>

<span data-ttu-id="22d8b-109">**시뮬레이션에서**+ **시뮬레이션 실행을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="22d8b-109">Under **Simulations**, select **+ Launch a simulation**.</span></span>

![Defender 포털에서 시뮬레이션 Microsoft 365 실행](../../media/attack-sim-preview-launch.png)

> [!NOTE]
> <span data-ttu-id="22d8b-111">시뮬레이션을 만들 때 어느 시점에서든 저장하고 닫아서 나중에 시뮬레이션을 계속 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22d8b-111">At any point during simulation creation, you can save and close to continue configuring the simulation at a later time.</span></span>

## <a name="selecting-a-social-engineering-technique"></a><span data-ttu-id="22d8b-112">소셜 엔지니어링 기술 선택</span><span class="sxs-lookup"><span data-stu-id="22d8b-112">Selecting a social engineering technique</span></span>

<span data-ttu-id="22d8b-113">[MITRE ATT 및 CK&](https://attack.mitre.org/techniques/enterprise/)프레임워크에서 ® 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="22d8b-113">Select from 4 different techniques, curated from the [MITRE ATT&CK® framework](https://attack.mitre.org/techniques/enterprise/).</span></span> <span data-ttu-id="22d8b-114">다양한 기술에 대해 다양한 페이로드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22d8b-114">Different payloads are available for different techniques:</span></span>

- <span data-ttu-id="22d8b-115">**자격 증명 수집은** 입력란이 있는 잘 알려진 웹 사이트로 사용자를 연결하여 사용자 이름 및 암호를 제출하여 자격 증명을 수집하려고 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="22d8b-115">**Credential harvest** attempts to collect credentials by taking users to a well-known looking website with input boxes to submit a username and password.</span></span>
- <span data-ttu-id="22d8b-116">**맬웨어** 첨부 파일은 메시지에 악성 첨부 파일을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="22d8b-116">**Malware attachment** adds a malicious attachment to a message.</span></span> <span data-ttu-id="22d8b-117">사용자가 첨부 파일을 열면 공격자가 대상의 장치를 손상시킬 수 있도록 임의의 코드가 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="22d8b-117">When the user opens the attachment, arbitrary code is run that will help the attacker compromise the target's device.</span></span>
- <span data-ttu-id="22d8b-118">**첨부 파일 링크는** 자격 증명 수집 하이브리드의 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="22d8b-118">**Link in attachment** is a type of credential harvest hybrid.</span></span> <span data-ttu-id="22d8b-119">공격자는 전자 메일 첨부 파일에 URL을 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="22d8b-119">An attacker inserts a URL into an email attachment.</span></span> <span data-ttu-id="22d8b-120">첨부 파일 내의 URL은 자격 증명 수집과 동일한 기술을 따르게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="22d8b-120">The URL within the attachment follows the same technique as credential harvest.</span></span>
- <span data-ttu-id="22d8b-121">**맬웨어에 연결하면** 잘 알려진 파일 공유 서비스에 호스트된 파일에서 임의 코드가 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="22d8b-121">**Link to malware** will run some arbitrary code from a file hosted on a well-known file sharing service.</span></span> <span data-ttu-id="22d8b-122">사용자에게 전송된 메시지에는 이 악성 파일에 대한 링크가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22d8b-122">The message sent to the user will contain a link to this malicious file.</span></span> <span data-ttu-id="22d8b-123">파일을 열고 공격자가 대상의 장치를 손상시킬 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="22d8b-123">Opening the file and help the attacker compromise the target's device.</span></span>
- <span data-ttu-id="22d8b-124">**드라이브-BY URL은** 메시지의 악의적인 URL이 자동으로 실행되거나 사용자 장치에 코드 코드를 설치하는 친숙한 웹 사이트로 이동하는 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="22d8b-124">**Drive-by URL** is where the malicious URL in the message takes the user to a familiar-looking website that silently runs and/or installs code code on the user's device.</span></span>

> [!TIP]
> <span data-ttu-id="22d8b-125">각 기술에 **대한** 설명 내에서 세부 정보 보기를 클릭하면 해당 기술에 대한 추가 정보와 시뮬레이션 단계가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="22d8b-125">Clicking on **View details** within the description of each technique will display further information and the simulation steps for the technique.</span></span>
>
> ![Microsoft 365 Defender 포털의 공격 시뮬레이션 교육 내에서 자격 증명 수집을 위한 시뮬레이션 단계](../../media/attack-sim-preview-sim-steps.png)

<span data-ttu-id="22d8b-127">기술을 선택한 후 다음 을 클릭한 후 **시뮬레이션에** 이름과 설명(옵션)을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="22d8b-127">After you've selected the technique and clicked on **Next**, give your simulation a name and optionally a description.</span></span>

## <a name="selecting-a-payload"></a><span data-ttu-id="22d8b-128">페이로드 선택</span><span class="sxs-lookup"><span data-stu-id="22d8b-128">Selecting a payload</span></span>

<span data-ttu-id="22d8b-129">그런 다음 기존 페이로드 카탈로그에서 페이로드를 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="22d8b-129">Next, you'll need to either select a payload from the pre-existing payload catalog.</span></span>

<span data-ttu-id="22d8b-130">페이로드에는 다음을 선택하는 데 도움이 되는 다양한 데이터 포인트가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22d8b-130">Payloads have a number of data points to help you choose:</span></span>

- <span data-ttu-id="22d8b-131">**클릭 속도는** 이 페이로드를 클릭한 사용자 수를 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="22d8b-131">**Click rate** counts how many people clicked this payload.</span></span>
- <span data-ttu-id="22d8b-132">**예측된** 손상률은 고객용 Microsoft Defender에서 페이로드에 대한 기록 데이터를 기반으로 이 페이로드에 의해 손상될 비율을 Office 365 예측합니다.</span><span class="sxs-lookup"><span data-stu-id="22d8b-132">**Predicted compromise rate** predicts the percentage of people that will get compromised by this payload based on historical data for the payload across Microsoft Defender for Office 365 customers.</span></span>
- <span data-ttu-id="22d8b-133">**실행된 시뮬레이션은** 이 페이로드가 다른 시뮬레이션에 사용된 횟수를 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="22d8b-133">**Simulations launched** counts the number of times this payload was used in other simulations.</span></span>
- <span data-ttu-id="22d8b-134">**필터를** **통해** 사용할 수 있는 복잡성은 페이로드 내에서 공격 대상을 단서하는 지표 수를 기반으로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="22d8b-134">**Complexity**, available through **filters**, is calculated based on the number of indicators within the payload that clue targets in on it being an attack.</span></span> <span data-ttu-id="22d8b-135">지표가 수록 복잡성이 낮아집니다.</span><span class="sxs-lookup"><span data-stu-id="22d8b-135">More indicators lead to lower complexity.</span></span>
- <span data-ttu-id="22d8b-136">**Source** 는 필터를 **통해** 사용할 수 있습니다. 페이로드가 테넌트에서 만들어지거나 Microsoft의 기존 페이로드 카탈로그(전역)의 일부인지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="22d8b-136">**Source**, available through **filters**, indicates whether the payload was created on your tenant or is a part of Microsoft's pre-existing payload catalog (global).</span></span>

![Microsoft 365 Defender 포털에서 공격 시뮬레이션 교육 내에서 선택한 페이로드](../../media/attack-sim-preview-select-payload.png)

<span data-ttu-id="22d8b-138">목록에서 페이로드를 선택하여 페이로드에 대한 추가 정보가 있는 미리 보기를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22d8b-138">Select a payload from the list to see a preview of the payload with additional information about it.</span></span>

<span data-ttu-id="22d8b-139">사용자만의 페이로드를 만들고자 하는 경우 공격 시뮬레이션 교육용 [페이로드 만들기를 읽어 읽습니다.](attack-simulation-training-payloads.md)</span><span class="sxs-lookup"><span data-stu-id="22d8b-139">If you'd like to create your own payload, read [create a payload for attack simulation training](attack-simulation-training-payloads.md).</span></span>

## <a name="audience-targeting"></a><span data-ttu-id="22d8b-140">대상 그룹 지정</span><span class="sxs-lookup"><span data-stu-id="22d8b-140">Audience targeting</span></span>

<span data-ttu-id="22d8b-141">이제 이 시뮬레이션의 대상을 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="22d8b-141">Now it's time to select this simulation's audience.</span></span> <span data-ttu-id="22d8b-142">조직의 모든  사용자를 포함하거나 특정 사용자 및 그룹만 **포함하도록 선택할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="22d8b-142">You can choose to **include all users in your organization** or **include only specific users and groups**.</span></span>

<span data-ttu-id="22d8b-143">특정 사용자 및 그룹만 **포함하도록 선택하는 경우** 다음 중 하나를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22d8b-143">When you choose to **include only specific users and groups** you can either:</span></span>

- <span data-ttu-id="22d8b-144">**사용자를 추가하여** 지난 3개월 동안 시뮬레이션의 대상으로 지정되지 않은 사용자를 대상으로 지정하는 등 테넌트에 대한 검색뿐만 아니라 고급 검색 및 필터링 기능을 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22d8b-144">**Add users**, which allows you to leverage search for your tenant, as well as advanced search and filtering capabilities, like targeting users who haven't been targeted by a simulation in the last 3 months.</span></span>

  ![Microsoft 365 Defender 포털의 공격 시뮬레이션 Microsoft 365 필터링](../../media/attack-sim-preview-user-targeting.png)

- <span data-ttu-id="22d8b-146">**CSV에서 가져오기에서는** 이 시뮬레이션에 대해 미리 정의한 사용자 집합을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22d8b-146">**Import from CSV** allows you to import a predefined set of users for this simulation.</span></span>

## <a name="assigning-training"></a><span data-ttu-id="22d8b-147">교육 할당</span><span class="sxs-lookup"><span data-stu-id="22d8b-147">Assigning training</span></span>

<span data-ttu-id="22d8b-148">교육을 통과하는 직원은 유사한 공격에 덜 덜 공격하기 까다로우며 각 시뮬레이션에 대한 교육을 할당하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="22d8b-148">We recommend that you assign training for each simulation, as employees who go through training are less susceptible to similar attacks.</span></span>

<span data-ttu-id="22d8b-149">교육을 직접 할당하거나 교육 과정과 모듈을 직접 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22d8b-149">You can either choose to have training assigned for you or select training courses and modules yourself.</span></span>

<span data-ttu-id="22d8b-150">교육 **기한을 선택하여** 직원들이 제시간에 교육을 완료할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="22d8b-150">Select the **training due date** to make sure employees finish their training in a timely manner.</span></span>

> [!NOTE]
> <span data-ttu-id="22d8b-151">과정 및 모듈을 직접 선택하기로 선택한 경우 권장되는 콘텐츠와 사용 가능한 모든 과정 및 모듈을 계속 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22d8b-151">If you choose to select courses and modules yourself, you'll still be able to see the recommended content as well as all available courses and modules.</span></span>
>
> ![Microsoft 365 Defender 포털에서 공격 시뮬레이션 Microsoft 365 추가](../../media/attack-sim-preview-add-training.png)

<span data-ttu-id="22d8b-153">다음 단계에서 직접 교육을  선택하기로 선택한 경우 교육을 추가하고 교육 방문 페이지를 사용자 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="22d8b-153">In the next steps you'll need to **Add trainings** if you opted to select it yourself, and customize your training landing page.</span></span> <span data-ttu-id="22d8b-154">교육 방문 페이지를 미리 보고 머리더와 본문을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22d8b-154">You'll be able to preview the training landing page, as well as change the header and body of it.</span></span>

## <a name="launch-details-and-review"></a><span data-ttu-id="22d8b-155">시작 세부 정보 및 검토</span><span class="sxs-lookup"><span data-stu-id="22d8b-155">Launch details and review</span></span>

<span data-ttu-id="22d8b-156">이제 모든 것이 구성되면 이 시뮬레이션을 즉시 시작하거나 나중에 예약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22d8b-156">Now that everything is configured, you can launch this simulation immediately or schedule it for a later date.</span></span> <span data-ttu-id="22d8b-157">또한 이 시뮬레이션을 종료할 때를 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="22d8b-157">You will also need to choose when to end this simulation.</span></span> <span data-ttu-id="22d8b-158">선택한 시간을 지난 이 시뮬레이션의 조작 캡처를 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="22d8b-158">We will stop capturing interaction with this simulation past the selected time.</span></span>

<span data-ttu-id="22d8b-159">**지역 인식 시간제** 배달을 사용하도록 설정하여 해당 지역에 따라 작업 시간 동안 직원에게 시뮬레이트된 공격 메시지를 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="22d8b-159">**Enable region aware timezone delivery** to deliver simulated attack messages to your employees during their working hours based on their region.</span></span>

<span data-ttu-id="22d8b-160">완료되면 다음을 클릭하고  시뮬레이션의 세부 정보를 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="22d8b-160">Once you're done, click on **Next** and review the details of your simulation.</span></span> <span data-ttu-id="22d8b-161">편집을  클릭하여 돌아가서 변경해야 하는 세부 정보를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="22d8b-161">Click on **Edit** on any of the parts to go back and change any details that need changing.</span></span> <span data-ttu-id="22d8b-162">완료되면 제출을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="22d8b-162">Once done, click **Submit**.</span></span>
