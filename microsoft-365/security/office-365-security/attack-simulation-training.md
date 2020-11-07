---
title: Microsoft Defender를 사용 하 여 피싱 공격 시뮬레이션
ms.author: daniha
author: danihalfin
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
description: Microsoft Defender for Office 365에서 피싱 공격을 시뮬레이트하고 피싱 방지 교육을 통해 사용자를 교육 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: b9b8a431fc28942f5e11bc7ce2e805ca082cf36b
ms.sourcegitcommit: dab50e1cc5bba920720b80033c93457f5ca1c330
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/07/2020
ms.locfileid: "48944572"
---
# <a name="simulate-a-phishing-attack"></a><span data-ttu-id="f1b4e-103">피싱 공격 시뮬레이션</span><span class="sxs-lookup"><span data-stu-id="f1b4e-103">Simulate a phishing attack</span></span>

<span data-ttu-id="f1b4e-104">Microsoft Defender for Office 365를 통한 Attack 시뮬레이터 교육을 통해 조직의 직원 들에 게 보안 정책 및 사례를 테스트 하 고 조직의 직원이 자신의 공격에 대 한 susceptibility을 절감할 수 있도록 교육을 받을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1b4e-104">Attack simulator training through Microsoft Defender for Office 365 lets you run benign cyber attack simulations on your organization to test your security policies and practices, as well as train the employees of your organization to increase their awareness and decrease their susceptibility to attacks.</span></span> <span data-ttu-id="f1b4e-105">다음은 attack 시뮬레이터 교육을 사용 하 여 피싱 공격을 시뮬레이션 하는 과정입니다.</span><span class="sxs-lookup"><span data-stu-id="f1b4e-105">The following walks you through simulating a phishing attack using attack simulator training.</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="f1b4e-106">시뮬레이트된 피싱 공격을 시작 하려면 [Microsoft 365 보안 센터로](https://security.microsoft.com/)이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1b4e-106">To launch a simulated phishing attack, navigate to the [Microsoft 365 security center](https://security.microsoft.com/).</span></span> <span data-ttu-id="f1b4e-107">**전자 메일 & 공동 작업** 에서 **공격 시뮬레이터** 를 클릭 하 고 [**시뮬레이션**](https://security.microsoft.com/attacksimulator?viewid=simulations) 탭으로 전환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1b4e-107">Under **Email & collaboration** click on **Attack simulator** and switch to the [**Simulations**](https://security.microsoft.com/attacksimulator?viewid=simulations) tab.</span></span>

<span data-ttu-id="f1b4e-108">시뮬레이션 **아래** 에서 **시뮬레이션을** 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1b4e-108">Under **Simulations** select **+ Launch a simulation**.</span></span>

![Microsoft 365 보안 센터에서 시뮬레이션 단추 실행](../../media/attack-sim-preview-launch.png)

> [!NOTE]
> <span data-ttu-id="f1b4e-110">시뮬레이션을 만들 때 언제 든 지 나중에 시뮬레이션을 계속 구성 하기 위해 저장 하 고 닫을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1b4e-110">At any point during simulation creation you can save and close to continue configuring the simulation at a later time.</span></span>

## <a name="selecting-a-social-engineering-technique"></a><span data-ttu-id="f1b4e-111">소셜 엔지니어링 기술 선택</span><span class="sxs-lookup"><span data-stu-id="f1b4e-111">Selecting a social engineering technique</span></span>

<span data-ttu-id="f1b4e-112">[MITRE at&t&접시 헤드® 프레임 워크](https://attack.mitre.org/techniques/enterprise/)의 네 가지 방법, 맞게 조정 된을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1b4e-112">Select from 4 different techniques, curated from the [MITRE ATT&CK® framework](https://attack.mitre.org/techniques/enterprise/).</span></span> <span data-ttu-id="f1b4e-113">다양 한 방법으로 서로 다른 페이로드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1b4e-113">Different payloads are available for different techniques.</span></span>

- <span data-ttu-id="f1b4e-114">**자격 증명** 수집은 사용자 이름 및 암호를 전송 하는 입력란을 사용 하 여 직원 들이 자격 증명을 수집할 수 있도록 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1b4e-114">**Credential harvest** attempts to collect credentials from employees by taking them to a well-known looking website with input boxes to submit a username and password.</span></span>
- <span data-ttu-id="f1b4e-115">**맬웨어 첨부 파일** 에 악의 있는 첨부 파일이 메시지에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1b4e-115">**Malware attachment** adds a malicious attachment to a message.</span></span> <span data-ttu-id="f1b4e-116">이 첨부 파일을 열면 공격자가 대상 장치를 손상 시키는 데 도움이 되는 일부 임의 코드가 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1b4e-116">When opened, this attachment will run some arbitrary code that will help the attacker compromise the target's device.</span></span>
- <span data-ttu-id="f1b4e-117">**첨부 파일의 링크** 는 자격 증명 수집 하이브리드의 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="f1b4e-117">**Link in attachment** is a type of credential harvest hybrid.</span></span> <span data-ttu-id="f1b4e-118">공격자가 URL을 전자 메일 첨부 파일에 삽입 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1b4e-118">An attacker inserts a URL into an email attachment.</span></span> <span data-ttu-id="f1b4e-119">첨부 파일 내의 URL은 자격 증명을 수집 하는 것과 동일한 방법을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="f1b4e-119">The URL within the attachment follows the same technique as credential harvest.</span></span>
- <span data-ttu-id="f1b4e-120">**맬웨어에 연결** 하면 잘 알려진 파일 공유 사이트에서 호스트 되는 파일에서 일부 임의 코드가 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1b4e-120">**Link to malware** will run some arbitrary code from a file hosted on a well-known file-sharing site.</span></span> <span data-ttu-id="f1b4e-121">이 악성 파일에 대 한 링크가 대상으로 전송 된 메시지에 추가 되 고, 클릭 하면 파일을 실행 하 고 공격자가 대상의 장치를 손상 시키는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1b4e-121">A link to this malicious file is added to the message sent to the target and clicking it will run the file and help the attacker compromise the target's device.</span></span>

> [!TIP]
> <span data-ttu-id="f1b4e-122">각 기술 설명 내에서 **세부 정보 보기** 를 클릭 하면 기술에 대 한 추가 정보 및 해당 기법의 시뮬레이션 단계가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1b4e-122">Clicking on **View details** within the description of each technique will display further information about the technique as well as the simulation steps for that technique.</span></span>
>
> ![Microsoft 365 보안 센터의 공격 시뮬레이션 교육 내에서 자격 증명을 수집 하기 위한 시뮬레이션 단계](../../media/attack-sim-preview-sim-steps.png)

<span data-ttu-id="f1b4e-124">이 방법을 선택 하 고 **다음** 을 클릭 한 후에는 시뮬레이션에 이름을 지정 하 고 원하는 경우 설명을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1b4e-124">Once you've selected the technique and clicked on **Next** give your simulation a name and optionally a description.</span></span>

## <a name="selecting-a-payload"></a><span data-ttu-id="f1b4e-125">페이로드 선택</span><span class="sxs-lookup"><span data-stu-id="f1b4e-125">Selecting a payload</span></span>

<span data-ttu-id="f1b4e-126">다음으로 기존 페이로드 카탈로그에서 페이로드를 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1b4e-126">Next, you'll need to either select a payload from the pre-existing payload catalog.</span></span>

<span data-ttu-id="f1b4e-127">페이로드에는 다음과 같은 다양 한 데이터 요소를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1b4e-127">Payloads have a number of data points to help you choose:</span></span>

- <span data-ttu-id="f1b4e-128">**속도를 클릭** 하면이 페이로드를 클릭 한 사용자의 수가 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1b4e-128">**Click rate** counts how many people clicked this payload.</span></span>
- <span data-ttu-id="f1b4e-129">**예측 된 손상 률** 은 Microsoft Defender for Office 365 고객 전반에서이 페이로드의 기록 데이터를 기반으로이 페이로드에 의해 손상 될 사용자 비율을 예측 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1b4e-129">**Predicted compromise rate** predicts the percentage of people that will get compromised by this payload based on historic data for this payload across Microsoft Defender for Office 365 customers.</span></span>
- <span data-ttu-id="f1b4e-130">**시뮬레이션이 시작** 됨이 페이로드가 다른 시뮬레이션에서 사용 된 횟수입니다.</span><span class="sxs-lookup"><span data-stu-id="f1b4e-130">**Simulations launched** counts the number of times this payload was used in other simulations.</span></span>
- <span data-ttu-id="f1b4e-131">**복잡성** ( **필터** 를 통해 사용 가능)은 공격 대상이 되는 것을 알 수 있는 페이로드 내의 지표 수를 기반으로 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1b4e-131">**Complexity** , available through **filters** , is calculated based on the number of indicators within the payload that clue targets in on it being an attack.</span></span> <span data-ttu-id="f1b4e-132">더 많은 지표로 인해 복잡도가 낮아집니다.</span><span class="sxs-lookup"><span data-stu-id="f1b4e-132">More indicators lead to lower complexity.</span></span>
- <span data-ttu-id="f1b4e-133">**원본** ( **필터** 를 통해 사용 가능)은 해당 페이로드가 테 넌 트에서 만들어졌거나 Microsoft의 기존 페이로드 카탈로그 (전역)에 포함 되어 있는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f1b4e-133">**Source** , available through **filters** , indicates whether the payload was created on your tenant or is a part of Microsoft's pre-existing payload catalog (global).</span></span>

![Microsoft 365 보안 센터에서 공격 시뮬레이션 교육 내에서 선택한 페이로드](../../media/attack-sim-preview-select-payload.png)

<span data-ttu-id="f1b4e-135">목록에서 페이로드를 선택 하 여 해당 페이로드에 대 한 추가 정보를 볼 수 있는 페이로드의 미리 보기를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1b4e-135">Select a payload from the list to see a preview of the payload with additional information about it.</span></span>

<span data-ttu-id="f1b4e-136">자체 페이로드를 만들려면 [공격 시뮬레이션 학습을 위한 페이로드 만들기](attack-simulation-training-payloads.md)를 읽어보십시오.</span><span class="sxs-lookup"><span data-stu-id="f1b4e-136">If you'd like to create your own payload, read [create a payload for attack simulation training](attack-simulation-training-payloads.md).</span></span>

## <a name="audience-targeting"></a><span data-ttu-id="f1b4e-137">대상 그룹 지정</span><span class="sxs-lookup"><span data-stu-id="f1b4e-137">Audience targeting</span></span>

<span data-ttu-id="f1b4e-138">이제이 시뮬레이션 대상 그룹을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1b4e-138">Now it's time to select this simulation's audience.</span></span> <span data-ttu-id="f1b4e-139">**조직의 모든 사용자를 포함** 하거나 **특정 사용자 및 그룹만 포함** 하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1b4e-139">You can choose to **include all users in your organization** or **include only specific users and groups**.</span></span> 

<span data-ttu-id="f1b4e-140">**특정 사용자 및 그룹만 포함** 하도록 선택 하는 경우 다음 중 하나를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1b4e-140">When you choose to **include only specific users and groups** you can either:</span></span>

- <span data-ttu-id="f1b4e-141">**사용자를 추가** 하 여 테 넌 트에 대 한 검색을 활용 하 고 지난 3 개월 동안의 시뮬레이션 대상이 아닌 대상 사용자와 같은 고급 검색 및 필터링 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1b4e-141">**Add users** , which allows you to leverage search for your tenant, as well as advanced search and filtering capabilities, like targeting users who haven't been targeted by a simulation in the last 3 months.</span></span>
  <span data-ttu-id="f1b4e-142">![Microsoft 365 보안 센터에 대 한 공격 시뮬레이션 교육의 사용자 필터링](../../media/attack-sim-preview-user-targeting.png)</span><span class="sxs-lookup"><span data-stu-id="f1b4e-142">![User filtering in attack simulation training on Microsoft 365 security center](../../media/attack-sim-preview-user-targeting.png)</span></span>
- <span data-ttu-id="f1b4e-143">**CSV에서 가져오기** 기능을 사용 하면이 시뮬레이션에 대해 미리 정의 된 사용자 집합을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1b4e-143">**Import from CSV** allows you to import a predefined set of users for this simulation.</span></span>

## <a name="assigning-training"></a><span data-ttu-id="f1b4e-144">교육 할당</span><span class="sxs-lookup"><span data-stu-id="f1b4e-144">Assigning training</span></span>

<span data-ttu-id="f1b4e-145">교육을 통과 하는 직원은 유사한 공격에 덜 취약 하므로 각 시뮬레이션에 대 한 교육을 할당 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f1b4e-145">We recommend that you assign training for each simulation, as employees who go through training are less susceptible to similar attacks.</span></span>

<span data-ttu-id="f1b4e-146">교육을 할당 하도록 선택 하거나 직접 교육 코스 및 모듈을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1b4e-146">You can either choose to have training assigned for you or select training courses and modules yourself.</span></span>

<span data-ttu-id="f1b4e-147">직원 들이 적절 한 시간 내에 교육을 완료 했는지 확인 하기 위해 **교육 기한을** 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1b4e-147">Select the **training due date** to make sure employees finish their training in a timely manner.</span></span>

> [!NOTE]
> <span data-ttu-id="f1b4e-148">강의 및 모듈을 직접 선택 하는 경우에도 사용할 수 있는 모든 과정 및 모듈 뿐 아니라 권장 되는 콘텐츠도 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1b4e-148">If you choose to select courses and modules yourself, you'll still be able to see the recommended content as well as all available courses and modules.</span></span>
>
> ![Microsoft 365 보안 센터의 공격 시뮬레이션 교육 내에서 권장 되는 교육 추가](../../media/attack-sim-preview-add-training.png)

<span data-ttu-id="f1b4e-150">다음 단계에서는 trainings를 직접 선택 하 고 교육 랜딩 페이지를 사용자 지정 하는 경우 **추가** 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1b4e-150">In the next steps you'll need to **Add trainings** if you opted to select it yourself, and customize your training landing page.</span></span> <span data-ttu-id="f1b4e-151">학습 랜딩 페이지를 미리 볼 수 있을 뿐만 아니라 머리글 및 본문을 변경할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1b4e-151">You'll be able to preview the training landing page, as well as change the header and body of it.</span></span>

## <a name="launch-details-and-review"></a><span data-ttu-id="f1b4e-152">세부 정보 시작 및 검토</span><span class="sxs-lookup"><span data-stu-id="f1b4e-152">Launch details and review</span></span>

<span data-ttu-id="f1b4e-153">모든 것이 구성 되었으므로이 시뮬레이션을 즉시 시작 하거나 나중에 예약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1b4e-153">Now that everything is configured, you can launch this simulation immediately or schedule it for a later date.</span></span> <span data-ttu-id="f1b4e-154">또한이 시뮬레이션을 종료 하는 경우를 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1b4e-154">You will also need to choose when to end this simulation.</span></span> <span data-ttu-id="f1b4e-155">선택한 시간 이후에이 시뮬레이션을 사용한 상호 작용 캡처를 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1b4e-155">We will stop capturing interaction with this simulation past the selected time.</span></span> 

<span data-ttu-id="f1b4e-156">지역에 따른 작업 시간 동안 직원에 게 시뮬레이트된 공격 메시지를 배달 하도록 **지역별 수신 표준 시간대 배달을 사용 하도록 설정** 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1b4e-156">**Enable region aware timezone delivery** to deliver simulated attack messages to your employees during their working hours based on their region.</span></span>

<span data-ttu-id="f1b4e-157">작업이 완료 되 면 **다음** 을 클릭 하 고 시뮬레이션에 대 한 세부 정보를 검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1b4e-157">Once you're done, click on **Next** and review the details of your simulation.</span></span> <span data-ttu-id="f1b4e-158">변경할 부분에 대 한 **편집** 을 클릭 하 여 되돌아가서 변경 해야 하는 세부 정보를 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1b4e-158">Click on **Edit** on any of the parts to go back and change any details that need changing.</span></span> <span data-ttu-id="f1b4e-159">작업이 완료 되 면 **제출을** 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1b4e-159">Once done, click **Submit**.</span></span>
