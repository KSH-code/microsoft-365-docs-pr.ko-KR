---
title: 법적 보존 알림 만들기
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 고급 eDiscovery 사례의 통신 도구를 사용 하 여 법적 보존 알림을 보내고, 수집 하 고, 추적 합니다.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 0bcbdef1c1393ff3e7f3baf30279909ed3a663f5
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035790"
---
# <a name="create-a-legal-hold-notice"></a><span data-ttu-id="55fb7-103">법적 보존 알림 만들기</span><span class="sxs-lookup"><span data-stu-id="55fb7-103">Create a legal hold notice</span></span>

<span data-ttu-id="55fb7-104">조직에서는 고급 eDiscovery custodian 통신을 사용 하 여 custodians와 통신 하는 방법에 대 한 워크플로를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55fb7-104">Using Advanced eDiscovery custodian communications, organizations can manage their workflow around communicating with custodians.</span></span> <span data-ttu-id="55fb7-105">합법적인 팀은 통신 도구를 통해 법적 보존 알림을 체계적으로 전송, 수집 및 추적할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55fb7-105">Through the Communications tool, legal teams can systematically send, collect, and track legal hold notifications.</span></span> <span data-ttu-id="55fb7-106">또한 유연한 만들기 프로세스를 사용 하면 팀에서 custodians로 전송 되는 알림의 콘텐츠 및 보존 알림 워크플로를 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55fb7-106">The flexible creation process also allows teams to customize the hold notification workflow and the content in the notices sent to custodians.</span></span> 

![통신 페이지](../media/CommunicationPage.PNG)

<span data-ttu-id="55fb7-108">이 문서에서는 보류 알림 워크플로의 단계를 간략하게 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="55fb7-108">The article outlines the steps in the hold notification workflow.</span></span>

## <a name="step-1-specify-communication-details"></a><span data-ttu-id="55fb7-109">1 단계: 통신 정보 지정</span><span class="sxs-lookup"><span data-stu-id="55fb7-109">Step 1: Specify communication details</span></span>

<span data-ttu-id="55fb7-110">첫 번째 단계는 법적 보존 공지와 기타 custodian 통신에 대 한 적절 한 세부 정보를 지정 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="55fb7-110">The first step is to specify the appropriate details for legal hold notices or other custodian communications.</span></span>

![이름 통신 페이지](../media/NameCommunication.PNG)

1. <span data-ttu-id="55fb7-112">보안 & 준수 센터에서 **eDiscovery > Advanced eDiscovery** 로 이동 하 여 조직의 사례 목록을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="55fb7-112">In the Security & Compliance Center, go to **eDiscovery > Advanced eDiscovery** to display the list of cases in your organization.</span></span>

2. <span data-ttu-id="55fb7-113">사례를 선택 하 고 **통신** 탭을 클릭 한 다음 **새 통신**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="55fb7-113">Select a case, click the **Communications** tab, and then click **New communication**.</span></span>

3. <span data-ttu-id="55fb7-114">**이름 통신** 페이지에서 다음 (필수) 통신 정보를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="55fb7-114">On the **Name communication** page, specify the following (required) communication details.</span></span>

    - <span data-ttu-id="55fb7-115">**Name**: 통신의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="55fb7-115">**Name**: This is the name for the communication.</span></span>

    - <span data-ttu-id="55fb7-116">**발급**관리자: 드롭다운 목록에 사례 구성원 목록이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="55fb7-116">**Issuing officer**: The dropdown list displays a list of case members.</span></span> <span data-ttu-id="55fb7-117">Custodians로 전송 되는 각 알림은 지정 된 발급 관리자를 대신 하 여 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="55fb7-117">Each notice sent to custodians will be sent on behalf of the specified issuing officer.</span></span>

4. <span data-ttu-id="55fb7-118">**다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="55fb7-118">Click **Next**.</span></span>

## <a name="step-2-define-the-portal-content"></a><span data-ttu-id="55fb7-119">2 단계: 포털 콘텐츠 정의</span><span class="sxs-lookup"><span data-stu-id="55fb7-119">Step 2: Define the portal content</span></span>

<span data-ttu-id="55fb7-120">다음으로 보류 공지의 내용을 만들고 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55fb7-120">Next, you can create and add the content of the hold notice.</span></span> <span data-ttu-id="55fb7-121">**통신 만들기** 마법사의 **포털 콘텐츠 정의** 페이지에서 보류 주의 내용을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="55fb7-121">On the **Define portal content** page in the **Create communication** wizard, specify the contents of the hold notice.</span></span> <span data-ttu-id="55fb7-122">이 콘텐츠는 발급, 다시 발급, 미리 알림 및 에스컬레이션 공지에 자동으로 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="55fb7-122">This content will be automatically appended to the Issuance, Re-Issue, Reminder, and Escalation notices.</span></span> <span data-ttu-id="55fb7-123">또한이 콘텐츠는 custodian의 준수 포털에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="55fb7-123">Additionally, this content will appear in the custodian's Compliance Portal.</span></span> 

![포털 콘텐츠 페이지](../media/PortalContent.PNG)

<span data-ttu-id="55fb7-125">포털 콘텐츠를 만들려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="55fb7-125">To create the portal content:</span></span>

1. <span data-ttu-id="55fb7-126">포털 콘텐츠의 텍스트 상자에 입력 하거나 다른 문서에서 잘라내어 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="55fb7-126">Type (or cut and paste from another document) your hold notice in the textbox for the portal content.</span></span> 

2. <span data-ttu-id="55fb7-127">공지 사항에 merge 변수를 삽입 하 여 공지를 사용자 지정 하 고 Custodian 준수 포털을 공유 합니다.</span><span class="sxs-lookup"><span data-stu-id="55fb7-127">Insert merge variables into your notice to customize the notice and share the Custodian Compliance Portal.</span></span>

3. <span data-ttu-id="55fb7-128">**다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="55fb7-128">Click **Next**.</span></span>

  >[!Tip]
  ><span data-ttu-id="55fb7-129">포털 콘텐츠의 콘텐츠 및 형식을 사용자 지정 하는 방법에 대 한 자세한 내용은 [통신 편집기 사용](using-communications-editor.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="55fb7-129">To learn more about how to can customize the content and format of the portal content, see [Use the Communications Editor](using-communications-editor.md).</span></span>

## <a name="step-3-set-the-required-notifications"></a><span data-ttu-id="55fb7-130">3 단계: 필요한 알림 설정</span><span class="sxs-lookup"><span data-stu-id="55fb7-130">Step 3: Set the required notifications</span></span>

<span data-ttu-id="55fb7-131">보존 공지의 내용을 정의한 후에는 알림 프로세스를 보내고 관리 하는 방법에 대 한 워크플로를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55fb7-131">After you've defined the contents of the hold notice, you can set up the workflows around sending and managing the notification process.</span></span> <span data-ttu-id="55fb7-132">알림은 custodians를 사용 하 여 알림 및 팔 로우를 위해 전송 되는 전자 메일 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="55fb7-132">Notifications are email messages that are sent to notify and follow up with custodians.</span></span> <span data-ttu-id="55fb7-133">통신에 추가 되는 모든 custodian에는 동일한 알림이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="55fb7-133">Every custodian added to the communication will receive the same notification.</span></span> 

<span data-ttu-id="55fb7-134">보류 알림을 설정 하 고 보내려면 발급, 다시 발급, 릴리스 알림 등을 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="55fb7-134">To set up and send a hold notice, you must include Issuance, Re-Issuance, and Release notifications.</span></span>

### <a name="issuance-notification"></a><span data-ttu-id="55fb7-135">발급 알림</span><span class="sxs-lookup"><span data-stu-id="55fb7-135">Issuance notification</span></span> 

<span data-ttu-id="55fb7-136">통신을 만든 후에는 지정 된 발급 담당자가 **발급 알림을** 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="55fb7-136">After the communication is created, the **Issuance Notification** is initiated by the specified Issuing Officer.</span></span> <span data-ttu-id="55fb7-137">이 발급 알림은 사용자에 게 보존 의무를 알리기 위해 custodian로 전송 되는 첫 번째 통신입니다.</span><span class="sxs-lookup"><span data-stu-id="55fb7-137">The Issuance notification is the first communication sent to the custodian to inform them about their preservation obligations.</span></span> 

<span data-ttu-id="55fb7-138">발급 알림을 만들려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="55fb7-138">To create an issuance notification:</span></span>

1. <span data-ttu-id="55fb7-139">**발급** 타일에서 **편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="55fb7-139">In the **Issuance** tile, click **Edit**.</span></span>

2. <span data-ttu-id="55fb7-140">필요한 경우 **참조** 및 **숨은** 참조 필드에 추가 사례 구성원 또는 직원을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="55fb7-140">If necessary, add additional case members or staff to the **Cc** and **Bcc** fields.</span></span> <span data-ttu-id="55fb7-141">이러한 필드에 여러 사용자를 추가 하려면 전자 메일 주소를 세미콜론으로 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="55fb7-141">To add multiple users to these fields, separate email addresses with a semi-colon.</span></span>

3. <span data-ttu-id="55fb7-142">알림의 **제목을** 지정 합니다 (필수).</span><span class="sxs-lookup"><span data-stu-id="55fb7-142">Specify the **Subject** for the notice (required).</span></span>

4. <span data-ttu-id="55fb7-143">Custodian에 제공할 콘텐츠 또는 추가 지침을 지정 합니다 (필수).</span><span class="sxs-lookup"><span data-stu-id="55fb7-143">Specify the contents or additional instructions that you would like to provide to the custodian (required).</span></span> <span data-ttu-id="55fb7-144">2 단계에서 정의한 포털 콘텐츠가 발급 알림의 끝에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="55fb7-144">The portal content you defined in Step 2 is added to the end of the issuance notice.</span></span> 

5. <span data-ttu-id="55fb7-145">**저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="55fb7-145">Click **Save**.</span></span>

### <a name="re-issuance-notification"></a><span data-ttu-id="55fb7-146">재발급 알림</span><span class="sxs-lookup"><span data-stu-id="55fb7-146">Re-Issuance notification</span></span>

<span data-ttu-id="55fb7-147">사례가 진행 됨에 따라 custodians는 이전에 지시 된 것 보다 더 많은 데이터를 보존 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55fb7-147">As the case progresses, custodians may be required to preserve additional or less data than was previously instructed.</span></span> <span data-ttu-id="55fb7-148">포털 콘텐츠를 업데이트 한 후에는 재 발급 알림이 전송 되 고 custodians에 게 해당 보존 의무의 변경 내용에 대 한 알림이 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="55fb7-148">After you update the portal content, the re-issuance notification is sent and alerts custodians about any changes to their preservation obligations.</span></span>

<span data-ttu-id="55fb7-149">재 발급 알림을 만들려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="55fb7-149">To create a re-issuance notification:</span></span>

1. <span data-ttu-id="55fb7-150">**재발급** 타일에서 **편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="55fb7-150">In the **Reissue** tile, click **Edit**.</span></span>

2. <span data-ttu-id="55fb7-151">필요한 경우 **참조** 및 **숨은** 참조 필드에 추가 사례 구성원 또는 직원을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="55fb7-151">If necessary, add additional case members or staff to the **Cc** and **Bcc** fields.</span></span> <span data-ttu-id="55fb7-152">이러한 필드에 여러 사용자를 추가 하려면 전자 메일 주소를 세미콜론으로 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="55fb7-152">To add multiple users to these fields, separate email addresses with a semi-colon.</span></span>

3. <span data-ttu-id="55fb7-153">알림의 **제목을** 지정 합니다 (필수).</span><span class="sxs-lookup"><span data-stu-id="55fb7-153">Specify the **Subject** for the notice (required).</span></span>

4. <span data-ttu-id="55fb7-154">Custodian에 제공할 콘텐츠 또는 추가 지침을 지정 합니다 (필수).</span><span class="sxs-lookup"><span data-stu-id="55fb7-154">Specify the contents or additional instructions that you would like to provide to the custodian (required).</span></span> <span data-ttu-id="55fb7-155">2 단계에서 정의한 포털 콘텐츠가 재발급 공지의 끝에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="55fb7-155">The portal content you defined in Step 2 is added to the end of the re-issuance notice.</span></span>

5. <span data-ttu-id="55fb7-156">**저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="55fb7-156">Click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="55fb7-157">포털 콘텐츠가 수정 된 경우 ( **통신 편집** 마법사의 **포털 콘텐츠 정의** 페이지에서) 재발급 알림은 해당 공지에 할당 된 모든 custodians 자동으로 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="55fb7-157">If the portal content is modified (on the **Define Portal Content** page in the **Edit communication** wizard), the re-issuance notification will be automatically sent to all custodians assigned to the notice.</span></span> <span data-ttu-id="55fb7-158">알림을 보낸 후에는 custodians에 게 해당 보존 알림을 다시 승인할 것인지 묻는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="55fb7-158">After the notification is sent, custodians will be asked to re-acknowledge their hold notice.</span></span> <span data-ttu-id="55fb7-159">미리 알림 또는 단계적 워크플로를 설정한 경우에도 다시 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="55fb7-159">If you have set up any reminder or escalation workflows, these will also re-start.</span></span> <span data-ttu-id="55fb7-160">통신을 트리거하는 다른 사례 관리 이벤트에 대 한 자세한 내용은 [알림을 트리거하는 이벤트](#events-that-trigger-notifications)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="55fb7-160">For more information about what other case management events trigger communications, see [Events that trigger notifications](#events-that-trigger-notifications).</span></span>

### <a name="release-notification"></a><span data-ttu-id="55fb7-161">릴리스 알림</span><span class="sxs-lookup"><span data-stu-id="55fb7-161">Release notification</span></span>

<span data-ttu-id="55fb7-162">문제가 해결 된 후 또는 custodian이 더 이상 콘텐츠를 보존 하지 않는 경우 사례에서 custodian를 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55fb7-162">After a matter is resolved or if a custodian is no longer subject to preserve content, you can release the custodian from a case.</span></span> <span data-ttu-id="55fb7-163">이전에 custodian에서 보류 알림을 발급 한 경우 릴리스 알림을 사용 하 여 custodians에 게 해당 의무에서 출시 되었음을 알릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55fb7-163">If the custodian was previously issued a hold notice, the release notification can be used to alert custodians that they have been released from their obligation.</span></span>

<span data-ttu-id="55fb7-164">릴리스 알림을 만들려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="55fb7-164">To create a release notification:</span></span> 

1. <span data-ttu-id="55fb7-165">**릴리스** 타일에서 **편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="55fb7-165">In the **Release** tile, click **Edit**.</span></span>

2. <span data-ttu-id="55fb7-166">필요한 경우 **참조** 및 **숨은** 참조 필드에 추가 사례 구성원 또는 직원을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="55fb7-166">If necessary, add additional case members or staff to the **Cc** and **Bcc** fields.</span></span> <span data-ttu-id="55fb7-167">이러한 필드에 여러 사용자를 추가 하려면 전자 메일 주소를 세미콜론으로 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="55fb7-167">To add multiple users to these fields, separate email addresses with a semi-colon.</span></span>

3. <span data-ttu-id="55fb7-168">알림의 **제목을** 지정 합니다 (필수).</span><span class="sxs-lookup"><span data-stu-id="55fb7-168">Specify the **Subject** for the notice (required).</span></span>

4. <span data-ttu-id="55fb7-169">Custodian에 제공할 콘텐츠 또는 추가 지침을 지정 합니다 (필수).</span><span class="sxs-lookup"><span data-stu-id="55fb7-169">Specify the contents or additional instructions that you would like to provide to the custodian (required).</span></span>

5. <span data-ttu-id="55fb7-170">**저장** 을 클릭 하 고 다음 단계로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="55fb7-170">Click **Save** and go to the next step.</span></span>

## <a name="optional-step-4-set-the-optional-notifications"></a><span data-ttu-id="55fb7-171">반드시 4 단계: 선택적 알림 설정</span><span class="sxs-lookup"><span data-stu-id="55fb7-171">(Optional) Step 4: Set the optional notifications</span></span>

<span data-ttu-id="55fb7-172">선택적으로 자동화 된 미리 알림 및 에스컬레이션 알림을 만들고 예약 하 여 응답 하지 않는 custodians를 포함 하도록 워크플로를 단순화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55fb7-172">Optionally, you can simplify the workflow for following up with unresponsive custodians by creating and scheduling automated reminder and escalation notifications.</span></span>

![미리 알림/에스컬레이션 페이지](../media/ReminderEscalations.PNG)

### <a name="reminders"></a><span data-ttu-id="55fb7-174">기한이</span><span class="sxs-lookup"><span data-stu-id="55fb7-174">Reminders</span></span>

<span data-ttu-id="55fb7-175">보류 알림을 보낸 후에는 미리 알림 워크플로를 정의 하 여 응답 하지 않는 custodians 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55fb7-175">After you have sent a hold notification, you can follow up with unresponsive custodians by defining a reminder workflow.</span></span>

<span data-ttu-id="55fb7-176">미리 알림을 예약 하려면:</span><span class="sxs-lookup"><span data-stu-id="55fb7-176">To schedule reminders:</span></span>

1. <span data-ttu-id="55fb7-177">**미리 알림** 타일에서 **편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="55fb7-177">In the **Reminder** tile, click **Edit**.</span></span>

2. <span data-ttu-id="55fb7-178">**상태** 전환 (필수)을 설정 하 여 **미리 알림** 워크플로를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="55fb7-178">Enable the **Reminder** workflow by turning on the **Status** toggle (required).</span></span>

3. <span data-ttu-id="55fb7-179">**미리 알림 간격 (일)** 을 지정 합니다 (필수).</span><span class="sxs-lookup"><span data-stu-id="55fb7-179">Specify the **Reminder interval (in days)** (required).</span></span> <span data-ttu-id="55fb7-180">다음은 첫 번째 및 후속 미리 알림 알림을 보내기 전까지 기다릴 일 수입니다.</span><span class="sxs-lookup"><span data-stu-id="55fb7-180">This is the number of days to wait before sending the first and follow-up reminder notifications.</span></span> <span data-ttu-id="55fb7-181">예를 들어 미리 알림 간격을 7 일로 설정한 경우 처음 알림을 처음에 발급 한 후 7 일 후에 첫 번째 미리 알림이 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="55fb7-181">For example, if you set the reminder interval to seven days, then the first reminder would be sent seven days after the hold notification was initially issued.</span></span> <span data-ttu-id="55fb7-182">이후의 모든 미리 알림도 7 일 마다 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="55fb7-182">All subsequent reminders would also be sent every seven days.</span></span>

4. <span data-ttu-id="55fb7-183">**미리 알림 개수** 를 지정 합니다 (필수).</span><span class="sxs-lookup"><span data-stu-id="55fb7-183">Specify the **Number of reminders** (required).</span></span> <span data-ttu-id="55fb7-184">이 필드는 응답 하지 않는 custodians 보낼 미리 알림 개수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="55fb7-184">This field specifies how many reminders to send to unresponsive custodians.</span></span> <span data-ttu-id="55fb7-185">예를 들어 미리 알림 수를 3으로 설정 하는 경우 custodian에 최대 3 개의 미리 알림이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="55fb7-185">For example, if you set the number of reminders to 3, then a custodian would receive a maximum of three reminders.</span></span> <span data-ttu-id="55fb7-186">Custodian가 보존 알림을 승인 하면 미리 알림이 해당 사용자에 게 더 이상 전송 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="55fb7-186">After a custodian acknowledges the hold notification, reminders will no longer be sent to that user.</span></span>

5. <span data-ttu-id="55fb7-187">알림의 **제목을** 지정 합니다 (필수).</span><span class="sxs-lookup"><span data-stu-id="55fb7-187">Specify the **Subject** for the notice (required).</span></span> 

6. <span data-ttu-id="55fb7-188">Custodian에 제공할 콘텐츠 또는 추가 지침을 지정 합니다 (필수).</span><span class="sxs-lookup"><span data-stu-id="55fb7-188">Specify the contents or additional instructions that you would like to provide to the custodian (required).</span></span> <span data-ttu-id="55fb7-189">2 단계에서 정의한 포털 콘텐츠가 미리 알림 알림의 끝에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="55fb7-189">The portal content you defined in Step 2 is added to the end of the reminder notice.</span></span>

7. <span data-ttu-id="55fb7-190">**저장** 을 클릭 하 고 다음 단계를 진행 합니다.</span><span class="sxs-lookup"><span data-stu-id="55fb7-190">Click **Save** and go the next step.</span></span>

### <a name="escalations"></a><span data-ttu-id="55fb7-191">에스컬레이션이</span><span class="sxs-lookup"><span data-stu-id="55fb7-191">Escalations</span></span>

<span data-ttu-id="55fb7-192">경우에 따라 응답 하지 않는 custodians 추가 작업을 수행 해야 하는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55fb7-192">In some situations, you may need additional ways to follow up with unresponsive custodians.</span></span> <span data-ttu-id="55fb7-193">Custodian에서 지정 된 미리 알림 개수를 받은 후 보류 알림을 승인 하지 않으면 법적 팀이 워크플로를 지정 하 여 custodian 및 해당 관리자에 게 단계적으로 공지 알림을 보내도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55fb7-193">If a custodian doesn't acknowledge a hold notification after receiving the specified number of reminders, the legal team can specify a workflow to automatically send an escalation notice to the custodian and their manager.</span></span>

<span data-ttu-id="55fb7-194">에스컬레이션을 예약 하려면</span><span class="sxs-lookup"><span data-stu-id="55fb7-194">To schedule escalations:</span></span>

1. <span data-ttu-id="55fb7-195">**에스컬레이션** 타일에서 **편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="55fb7-195">In the **Escalation** tile, click **Edit**.</span></span>

2. <span data-ttu-id="55fb7-196">**상태** 전환 기능을 설정 하 여 **에스컬레이션** 워크플로를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="55fb7-196">Enable the **Escalation** workflow by turning on the **Status** toggle.</span></span>

3. <span data-ttu-id="55fb7-197">**에스컬레이션 간격 (일)** 을 지정 합니다 (필수).</span><span class="sxs-lookup"><span data-stu-id="55fb7-197">Specify the **Escalation interval (in days)** (required).</span></span>

4. <span data-ttu-id="55fb7-198">**에스컬레이션 수** (필수)를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="55fb7-198">Specify the **Number of escalations** (required).</span></span> <span data-ttu-id="55fb7-199">이 필드는 응답 하지 않는 custodians 보낼 에스컬레이션 수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="55fb7-199">This field specifies how many escalations to send to unresponsive custodians.</span></span> <span data-ttu-id="55fb7-200">예를 들어 에스컬레이션 수를 3으로 설정 하는 경우 에스컬레이션 알림이 custodian 및 해당 관리자에 게 최대 3 회 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="55fb7-200">For example, if you set the number of escalations to 3, then an escalation notice would be sent to the custodian and their manager a maximum of three times.</span></span> <span data-ttu-id="55fb7-201">Custodian가 보존 알림을 승인 하면 에스컬레이션이 더 이상 전송 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="55fb7-201">After a custodian acknowledges the hold notification, escalations will no longer be sent.</span></span>

5. <span data-ttu-id="55fb7-202">알림의 **제목을** 지정 합니다 (필수).</span><span class="sxs-lookup"><span data-stu-id="55fb7-202">Specify the **Subject** for the notice (required).</span></span> 

6. <span data-ttu-id="55fb7-203">Custodian에 제공할 콘텐츠 또는 추가 지침을 지정 합니다 (필수).</span><span class="sxs-lookup"><span data-stu-id="55fb7-203">Specify the contents or additional instructions that you would like to provide to the custodian (required).</span></span> <span data-ttu-id="55fb7-204">2 단계에서 정의한 포털 콘텐츠가 에스컬레이션 알림의 끝에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="55fb7-204">The portal content you defined in Step 2 is added to the end of the escalation notice.</span></span>

7. <span data-ttu-id="55fb7-205">**저장** 을 클릭 하 고 다음 단계를 진행 합니다.</span><span class="sxs-lookup"><span data-stu-id="55fb7-205">Click **Save** and go the next step.</span></span>

## <a name="step-5-assign-custodians-to-receive-notifications"></a><span data-ttu-id="55fb7-206">5 단계: 알림을 받을 custodians 할당</span><span class="sxs-lookup"><span data-stu-id="55fb7-206">Step 5: Assign custodians to receive notifications</span></span>

<span data-ttu-id="55fb7-207">알림의 콘텐츠를 완성 한 후 알림을 보낼 custodians을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="55fb7-207">After you have finalized the content for notifications, select the custodians that you would like to send notifications to.</span></span> 

![Custodians 선택 페이지](../media/SelectCustodians.PNG)

<span data-ttu-id="55fb7-209">Custodians를 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="55fb7-209">To add custodians:</span></span>

1. <span data-ttu-id="55fb7-210">이름 옆에 있는 확인란을 클릭 하 여 통신에 custodians를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="55fb7-210">Assign custodians to the communication by clicking the checkbox next to their name.</span></span>

    <span data-ttu-id="55fb7-211">통신을 만든 후에는 알림 워크플로가 선택한 custodians에 자동으로 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="55fb7-211">After the communication is created, the notification workflow will automatically apply to the selected custodians.</span></span>

2. <span data-ttu-id="55fb7-212">**다음** 을 클릭 하 여 통신 설정 및 세부 정보를 검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="55fb7-212">Click **Next** to review the communication settings and details.</span></span>

>[!NOTE]
><span data-ttu-id="55fb7-213">사례에 추가 된 custodians 및 사례 내에서 다른 알림을 보내지 않은 사용자만 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55fb7-213">You can only add custodians who have been added to the case and haven't been sent another notification within the case.</span></span>

## <a name="step-6-review-settings"></a><span data-ttu-id="55fb7-214">6 단계: 설정 검토</span><span class="sxs-lookup"><span data-stu-id="55fb7-214">Step 6: Review settings</span></span>

<span data-ttu-id="55fb7-215">설정을 검토 하 고 **보내기를** 클릭 하 여 통신을 완료 하면 시스템에서 발급 알림을 보내 통신 워크플로를 자동으로 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="55fb7-215">After you review the settings and click **Send** to complete the communication, the system will automatically start the communication workflow by sending the issuance notice.</span></span>

## <a name="events-that-trigger-notifications"></a><span data-ttu-id="55fb7-216">알림을 트리거하는 이벤트</span><span class="sxs-lookup"><span data-stu-id="55fb7-216">Events that trigger notifications</span></span>

<span data-ttu-id="55fb7-217">다음 표에서는 서로 다른 유형의 알림이 custodians로 전송 될 때 트리거되는 사례 관리 프로세스의 이벤트에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="55fb7-217">The following table describes events in the case management process that trigger when the different types of notifications are sent to custodians.</span></span>

|<span data-ttu-id="55fb7-218">통신 유형</span><span class="sxs-lookup"><span data-stu-id="55fb7-218">Type of communication</span></span>|<span data-ttu-id="55fb7-219">트리거해야</span><span class="sxs-lookup"><span data-stu-id="55fb7-219">Trigger</span></span> |
|:---------|:---------|
|<span data-ttu-id="55fb7-220">발급 알림</span><span class="sxs-lookup"><span data-stu-id="55fb7-220">Issuance notices</span></span>|<span data-ttu-id="55fb7-221">처음 알림을 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="55fb7-221">The initial creation of the notification.</span></span> <span data-ttu-id="55fb7-222">보류 알림을 수동으로 다시 보낼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55fb7-222">You can also manually resend a hold notification.</span></span> |
|<span data-ttu-id="55fb7-223">재발급 통지</span><span class="sxs-lookup"><span data-stu-id="55fb7-223">Re-issuance notices</span></span>|<span data-ttu-id="55fb7-224">**통신 편집** 마법사의 **포털 콘텐츠 정의** 페이지에서 포털 콘텐츠를 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="55fb7-224">Updating the portal content on the **Define Portal Content** page in the **Edit communication** wizard.</span></span>|
|<span data-ttu-id="55fb7-225">릴리스 알림</span><span class="sxs-lookup"><span data-stu-id="55fb7-225">Release notices</span></span>|<span data-ttu-id="55fb7-226">Custodian가 사례에서 릴리스됩니다.</span><span class="sxs-lookup"><span data-stu-id="55fb7-226">The custodian is released from the case.</span></span>|
|<span data-ttu-id="55fb7-227">기한이</span><span class="sxs-lookup"><span data-stu-id="55fb7-227">Reminders</span></span>|<span data-ttu-id="55fb7-228">미리 알림에 대해 구성 된 미리 알림 간격과 개수입니다.</span><span class="sxs-lookup"><span data-stu-id="55fb7-228">The interval and number of reminders configured for the reminder.</span></span>|
|<span data-ttu-id="55fb7-229">에스컬레이션이</span><span class="sxs-lookup"><span data-stu-id="55fb7-229">Escalations</span></span>|<span data-ttu-id="55fb7-230">에스컬레이션에 대해 구성 된 미리 알림 간격 및 수</span><span class="sxs-lookup"><span data-stu-id="55fb7-230">The interval and number of reminders configured for the escalation.</span></span>|
|||
