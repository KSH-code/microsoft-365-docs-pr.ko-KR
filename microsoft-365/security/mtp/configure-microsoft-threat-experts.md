---
title: Microsoft 365 Defender를 통해 Microsoft 위협 전문가 기능 구성 및 관리
description: Microsoft 365 Defender를 통해 Microsoft 위협 전문가를 구독하여 일상적인 보안 작업 및 보안 관리 작업에서 이를 구성, 관리 및 사용할 수 있습니다.
keywords: Microsoft 위협 전문가, 관리되는 위협 헌팅 서비스, MTE, Microsoft 관리 헌팅 서비스
search.product: Windows 10
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-maave
author: martyav
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.topic: article
ms.openlocfilehash: 93e900423fcef1fd357ca50db70e250ef6082dc7
ms.sourcegitcommit: 6e5c00f84b5201422aed094f2697016407df8fc2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51570581"
---
# <a name="configure-and-manage-microsoft-threat-experts-capabilities-through-microsoft-365-defender"></a><span data-ttu-id="c1a4f-104">Microsoft 365 Defender를 통해 Microsoft 위협 전문가 기능 구성 및 관리</span><span class="sxs-lookup"><span data-stu-id="c1a4f-104">Configure and manage Microsoft Threat Experts capabilities through Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="c1a4f-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="c1a4f-105">**Applies to:**</span></span>

- [<span data-ttu-id="c1a4f-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c1a4f-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)
- [<span data-ttu-id="c1a4f-107">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="c1a4f-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

[!INCLUDE [Prerelease](../includes/prerelease.md)]

## <a name="before-you-begin"></a><span data-ttu-id="c1a4f-108">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="c1a4f-108">Before you begin</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c1a4f-109">적용하기 전에 Microsoft 기술 서비스 공급자 및 계정 팀과 함께 Microsoft 위협 전문가 - 대상 공격 알림 관리 위협 헌팅 서비스에 대한 자격 요구 사항을 논의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1a4f-109">Before you apply, make sure to discuss the eligibility requirements for the Microsoft Threat Experts – Targeted Attack Notifications managed threat hunting service with your Microsoft Technical Service provider and account team.</span></span>

<span data-ttu-id="c1a4f-110">대상 공격 알림을 받으하려면 등록된 장치로 Microsoft 365 Defender를 배포해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1a4f-110">To receive targeted attack notifications, you'll need to have Microsoft 365 Defender deployed with devices enrolled.</span></span> <span data-ttu-id="c1a4f-111">그런 다음 Microsoft 위협 전문가를 위한 M365 포털 - 대상 공격 알림을 통해 응용 프로그램을 제출합니다.</span><span class="sxs-lookup"><span data-stu-id="c1a4f-111">Then, submit an application through the M365 portal for Microsoft Threat Experts - Targeted Attack Notifications.</span></span>

<span data-ttu-id="c1a4f-112">계정 팀 또는 Microsoft 담당자에게 문의하여 Microsoft 위협 전문가 - 요구에 대한 전문가를 구독하세요.</span><span class="sxs-lookup"><span data-stu-id="c1a4f-112">Contact your account team or Microsoft representative to subscribe to Microsoft Threat Experts - Experts on Demand.</span></span> <span data-ttu-id="c1a4f-113">요구 전문가를 통해 위협 전문가와 협의하여 조직을 관련 탐지 및 공격자로부터 보호하는 방법에 대해 상담할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1a4f-113">Experts on Demand lets you consult with our threat experts on how to protect your organization from relevant detections and adversaries.</span></span>

## <a name="apply-for-microsoft-threat-experts---targeted-attack-notifications-service"></a><span data-ttu-id="c1a4f-114">Microsoft 위협 전문가 적용 - 대상 공격 알림 서비스</span><span class="sxs-lookup"><span data-stu-id="c1a4f-114">Apply for Microsoft Threat Experts - Targeted Attack Notifications service</span></span>

<span data-ttu-id="c1a4f-115">끝점용 Microsoft Defender 및 Microsoft 365 Defender가 이미 있는 경우 Microsoft 365 Defender 포털을 통해 Microsoft 위협 전문가 – 대상 공격 알림을 신청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1a4f-115">If you already have Microsoft Defender for Endpoint and Microsoft 365 Defender, you can apply for Microsoft Threat Experts – Targeted Attack Notifications through their Microsoft 365 Defender portal.</span></span>  <span data-ttu-id="c1a4f-116">대상 공격 알림은 조직에 가장 중요한 위협을 식별하는 데 도움이 되는 특별한 인사이트 및 분석을 부여하여 신속하게 대응할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1a4f-116">Targeted attack notifications grant you special insight and analysis to help identify the most critical threats to your organization, so you can respond to them quickly.</span></span>

1. <span data-ttu-id="c1a4f-117">탐색 창에서 설정 > 끝점 > Microsoft 위협 전문가 - > 공격 > 고급 기능으로 **이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="c1a4f-117">From the navigation pane, go to **Settings > Endpoints > General > Advanced features > Microsoft Threat Experts - Targeted Attack Notifications**.</span></span>

2. <span data-ttu-id="c1a4f-118">**적용** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c1a4f-118">Select **Apply**.</span></span>

    ![Microsoft 위협 전문가 설정 이미지](../../media/mte/mte-collaboratewithmte.png)

3. <span data-ttu-id="c1a4f-120">Microsoft에서 응용 프로그램에 대해 연락할 수 있도록 이름과 전자 메일 주소를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="c1a4f-120">Enter your name and email address so that Microsoft can contact you about your application.</span></span>

    ![Microsoft 위협 전문가 응용 프로그램의 이미지](../../media/mte/mte-apply.png)

4. <span data-ttu-id="c1a4f-122">개인 정보 [취급 방침 을 읽은](https://privacy.microsoft.com/en-us/privacystatement)다음 완료되면 제출을 선택합니다. </span><span class="sxs-lookup"><span data-stu-id="c1a4f-122">Read the [privacy statement](https://privacy.microsoft.com/en-us/privacystatement), then select **Submit** when you're done.</span></span> <span data-ttu-id="c1a4f-123">응용 프로그램이 승인되면 환영 전자 메일을 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1a4f-123">You'll receive a welcome email once your application is approved.</span></span>

    ![Microsoft Threat Experts 응용 프로그램 확인 이미지](../../media/mte/mte-applicationconfirmation.png)

5. <span data-ttu-id="c1a4f-125">환영 전자 메일을 받은 후 자동으로 대상 공격 알림을 받기 시작하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1a4f-125">After you receive your welcome email, you'll automatically start receiving targeted attack notifications.</span></span>

6. <span data-ttu-id="c1a4f-126">일반 및 고급 기능의 끝점 > 설정을 방문하여 > **> 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="c1a4f-126">You can verify your status by visiting **Settings > Endpoints > General > Advanced features**.</span></span> <span data-ttu-id="c1a4f-127">승인되면 Microsoft **위협** 전문가 - 대상 공격 알림 토글이 표시 및 켜기됩니다. </span><span class="sxs-lookup"><span data-stu-id="c1a4f-127">Once approved, the **Microsoft Threat Experts - Targeted Attack Notification** toggle will be visible and switched **On**.</span></span>

## <a name="where-youll-see-the-targeted-attack-notifications-from-microsoft-threat-experts"></a><span data-ttu-id="c1a4f-128">Microsoft 위협 전문가의 대상 공격 알림을 볼 수 있는 위치</span><span class="sxs-lookup"><span data-stu-id="c1a4f-128">Where you'll see the targeted attack notifications from Microsoft Threat Experts</span></span>

<span data-ttu-id="c1a4f-129">다음 매체를 통해 Microsoft 위협 전문가로부터 대상 공격 알림을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1a4f-129">You can receive targeted attack notification from Microsoft Threat Experts through the following mediums:</span></span>

- <span data-ttu-id="c1a4f-130">Microsoft 365 Defender **포털의** 인시던트 페이지</span><span class="sxs-lookup"><span data-stu-id="c1a4f-130">The Microsoft 365 Defender portal's **Incidents** page</span></span>
- <span data-ttu-id="c1a4f-131">Microsoft 365 Defender 포털의 **경고 대시보드**</span><span class="sxs-lookup"><span data-stu-id="c1a4f-131">The Microsoft 365 Defender portal's **Alerts** dashboard</span></span>
- <span data-ttu-id="c1a4f-132">OData 경고 [API 및](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/get-alerts) REST [API](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/pull-alerts-using-rest-api)</span><span class="sxs-lookup"><span data-stu-id="c1a4f-132">OData alerting [API](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/get-alerts) and [REST API](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/pull-alerts-using-rest-api)</span></span>
- <span data-ttu-id="c1a4f-133">[고급 헌팅의 DeviceAlertEvents](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-devicealertevents-table) 테이블</span><span class="sxs-lookup"><span data-stu-id="c1a4f-133">[DeviceAlertEvents](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-devicealertevents-table) table in Advanced hunting</span></span>
- <span data-ttu-id="c1a4f-134">받은 편지함( 전자 메일을 통해 대상 공격 알림을 전송하기로 선택한 경우).</span><span class="sxs-lookup"><span data-stu-id="c1a4f-134">Your inbox, if you choose to have targeted attack notifications sent to you via email.</span></span> <span data-ttu-id="c1a4f-135">아래 [전자 메일 알림 규칙 만들기를 참조하세요.](#create-an-email-notification-rule)</span><span class="sxs-lookup"><span data-stu-id="c1a4f-135">See [Create an email notification rule](#create-an-email-notification-rule) below.</span></span>

### <a name="create-an-email-notification-rule"></a><span data-ttu-id="c1a4f-136">전자 메일 알림 규칙 만들기</span><span class="sxs-lookup"><span data-stu-id="c1a4f-136">Create an email notification rule</span></span>

<span data-ttu-id="c1a4f-137">알림 받는 사람에 대한 전자 메일 알림을 보내는 규칙을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1a4f-137">You can create rules to send email notifications for notification recipients.</span></span> <span data-ttu-id="c1a4f-138">자세한 내용은  [전자](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-email-notifications) 메일 알림 만들기, 편집, 삭제 또는 문제 해결을 위한 경고 알림 구성을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c1a4f-138">For full details, see  [Configure alert notifications](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-email-notifications) to create, edit, delete, or troubleshoot email notification.</span></span>

## <a name="view-targeted-attack-notifications"></a><span data-ttu-id="c1a4f-139">대상 공격 알림 보기</span><span class="sxs-lookup"><span data-stu-id="c1a4f-139">View targeted attack notifications</span></span>

<span data-ttu-id="c1a4f-140">전자 메일 알림을 받도록 시스템을 구성한 후 전자 메일에서 Microsoft 위협 전문가로부터 대상 공격 알림을 받기 시작할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c1a4f-140">You'll start receiving targeted attack notification from Microsoft Threat Experts in your email after you have configured your system to receive email notification.</span></span>

1. <span data-ttu-id="c1a4f-141">전자 메일의 링크를 선택하여 위협 전문가로 태그가 지정된 대시보드의 해당 경고 컨텍스트로 **이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="c1a4f-141">Select the link in the email to go to the corresponding alert context in the dashboard tagged with **Threat experts**.</span></span>

2. <span data-ttu-id="c1a4f-142">경고 **페이지에서** 추가 세부 정보를 확인하려면 전자 메일에서 받은 경고 항목과 동일한 경고 항목을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c1a4f-142">From the **Alerts** page, select the same alert topic as the one you received in the email, to view further details.</span></span>

## <a name="subscribe-to-microsoft-threat-experts---experts-on-demand"></a><span data-ttu-id="c1a4f-143">Microsoft 위협 전문가 - 전문가를 구독합니다.</span><span class="sxs-lookup"><span data-stu-id="c1a4f-143">Subscribe to Microsoft Threat Experts - Experts on Demand</span></span>

<span data-ttu-id="c1a4f-144">이미 Endpoint용 Microsoft Defender 고객인 경우 Microsoft 담당자에게 문의하여 Microsoft 위협 전문가 - 주문형 전문가를 구독할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1a4f-144">If you're already a Microsoft Defender for Endpoint customer, you can contact your Microsoft representative to subscribe to Microsoft Threat Experts - Experts on Demand.</span></span>

## <a name="consult-a-microsoft-threat-expert-about-suspicious-cybersecurity-activities-in-your-organization"></a><span data-ttu-id="c1a4f-145">조직의 의심스러운 사이버 보안 활동에 대한 Microsoft 위협 전문가에게 문의</span><span class="sxs-lookup"><span data-stu-id="c1a4f-145">Consult a Microsoft threat expert about suspicious cybersecurity activities in your organization</span></span>

<span data-ttu-id="c1a4f-146">Microsoft 365 Defender 포털 내에서 Microsoft 위협 전문가에게 문의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1a4f-146">You can contact Microsoft Threat Experts from inside the Microsoft 365 Defender portal.</span></span> <span data-ttu-id="c1a4f-147">전문가는 복잡한 위협과 대상 공격 알림을 이해하는 데 도움을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1a4f-147">Experts can help you understand complex threats and targeted attack notifications.</span></span> <span data-ttu-id="c1a4f-148">경고 및 인시던트에 대한 자세한 내용이나 손상 처리에 대한 조언을 전문가와 협력합니다.</span><span class="sxs-lookup"><span data-stu-id="c1a4f-148">Partner with experts for further details about alerts and incidents, or advice on handling compromise.</span></span> <span data-ttu-id="c1a4f-149">포털 대시보드에서 설명하는 위협 인텔리전스 컨텍스트에 대한 정보를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="c1a4f-149">Gain insight into the threat intelligence context described by your portal dashboard.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="c1a4f-150">조직의 사용자 지정된 위협 인텔리전스 데이터와 관련된 경고 문의는 현재 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c1a4f-150">Alert inquiries related to your organization's customized threat intelligence data are not currently supported.</span></span> <span data-ttu-id="c1a4f-151">자세한 내용은 보안 운영 또는 인시던트 대응 팀에 문의합니다.</span><span class="sxs-lookup"><span data-stu-id="c1a4f-151">Consult with your security operations or incident response team for details.</span></span>
> - <span data-ttu-id="c1a4f-152">위협 전문가 문의  양식을 통해 문의를 제출하려면 Microsoft 365 Defender 포털의 보안 센터에서 보안 설정 관리 권한이 **필요합니다.**</span><span class="sxs-lookup"><span data-stu-id="c1a4f-152">You need to have the **Manage security settings in Security Center** permission in the Microsoft 365 Defender portal to submit an inquiry through the **Consult a threat expert** form.</span></span>

1. <span data-ttu-id="c1a4f-153">조사할 정보와 관련된 포털 페이지(예: **장치,** 경고 또는 인시던트)로 **이동합니다.** </span><span class="sxs-lookup"><span data-stu-id="c1a4f-153">Navigate to the portal page related to the information that you'd like to investigate: for example, **Device**, **Alert**, or **Incident**.</span></span> <span data-ttu-id="c1a4f-154">조사 요청을 보내기 전에 문의와 관련된 포털 페이지가 보기에 있는지 확인하십시오.</span><span class="sxs-lookup"><span data-stu-id="c1a4f-154">Make sure that the portal page related to your inquiry is in view before you send an investigation request.</span></span>

2. <span data-ttu-id="c1a4f-155">위쪽 메뉴에서 **?를 선택합니다. 위협 전문가에게 문의합니다.**</span><span class="sxs-lookup"><span data-stu-id="c1a4f-155">From the top menu, select **? Consult a threat expert**.</span></span>

    ![메뉴에서 Microsoft 위협 전문가 전문가의 이미지](../../media/mte/incidents-action-mte-highlighted.png)

    <span data-ttu-id="c1a4f-157">플라이아웃 화면이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="c1a4f-157">A flyout screen will open.</span></span>

    <span data-ttu-id="c1a4f-158">헤더는 평가판 구독을 사용 중이거나 전체 Microsoft Threat Experts - Experts on-Demand 구독을 사용 중으로 표시하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c1a4f-158">The header will indicate if you are on a trial subscription, or a full Microsoft Threat Experts - Experts on-Demand subscription.</span></span>

    ![Microsoft Threat Experts On Demand 평가판 구독 화면의 이미지](../../media/mte/mte-trial.png)

    <span data-ttu-id="c1a4f-160">조사 **항목** 필드에는 요청에 대한 관련 페이지에 대한 링크가 이미 채워진 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c1a4f-160">The **Investigation topic** field will already be populated with the link to the relevant page for your request.</span></span>

3. <span data-ttu-id="c1a4f-161">다음 필드에서 Microsoft 위협 전문가에게 조사를 시작할 수 있는 충분한 컨텍스트를 제공할 수 있는 충분한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c1a4f-161">In the next field, provide enough information to give the Microsoft Threat Experts enough context to start the investigation.</span></span>

4. <span data-ttu-id="c1a4f-162">Microsoft 위협 전문가와 대응하는 데 사용할 전자 메일 주소를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="c1a4f-162">Enter the email address that you'd like to use to correspond with Microsoft Threat Experts.</span></span>

> [!NOTE]
> <span data-ttu-id="c1a4f-163">Microsoft 서비스 허브를 통해 전문가 관련 사례의 상태를 추적하려면 기술 계정 관리자에게 문의하세요.</span><span class="sxs-lookup"><span data-stu-id="c1a4f-163">If you would like to track the status of your Experts on Demand cases through Microsoft Services Hub, reach out to your technical account manager.</span></span>

<span data-ttu-id="c1a4f-164">이 비디오를 시청하여 Microsoft 서비스 허브에 대한 간략한 개요를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1a4f-164">Watch this video for a quick overview of the Microsoft Services Hub.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4pk9f]

## <a name="sample-investigation-topics"></a><span data-ttu-id="c1a4f-165">샘플 조사 항목</span><span class="sxs-lookup"><span data-stu-id="c1a4f-165">Sample investigation topics</span></span>

### <a name="alert-information"></a><span data-ttu-id="c1a4f-166">경고 정보</span><span class="sxs-lookup"><span data-stu-id="c1a4f-166">Alert information</span></span>

- <span data-ttu-id="c1a4f-167">이진수 이진에 대한 새로운 유형의 경고를 보했습니다.</span><span class="sxs-lookup"><span data-stu-id="c1a4f-167">We saw a new type of alert for a living-off-the-land binary.</span></span> <span data-ttu-id="c1a4f-168">경고 ID를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1a4f-168">We can provide the alert ID.</span></span> <span data-ttu-id="c1a4f-169">이 경고와 이 경고를 추가로 조사하는 방법에 대해 더 많은 정보를 알려 주시겠습니까?</span><span class="sxs-lookup"><span data-stu-id="c1a4f-169">Can you tell us more about this alert and how we can investigate it further?</span></span>
- <span data-ttu-id="c1a4f-170">두 가지 유사한 공격이 관찰되었습니다. 두 공격 모두 악성 PowerShell 스크립트를 실행하려고 하지만 다른 경고를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="c1a4f-170">We've observed two similar attacks, which both try to execute malicious PowerShell scripts but generate different alerts.</span></span> <span data-ttu-id="c1a4f-171">하나는 "의심스러운 PowerShell 명령줄"이고 다른 하나는 "O365에서 제공한 표시에 따라 악성 파일이 검색되었습니다."입니다.</span><span class="sxs-lookup"><span data-stu-id="c1a4f-171">One is "Suspicious PowerShell command line" and the other is "A malicious file was detected based on indication provided by O365".</span></span> <span data-ttu-id="c1a4f-172">차이점은 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="c1a4f-172">What is the difference?</span></span>
- <span data-ttu-id="c1a4f-173">현재, 프로필이 많은 사용자의 장치에서 비정상적인 로그인 실패 수에 대한 이상한 경고를 수신했습니다.</span><span class="sxs-lookup"><span data-stu-id="c1a4f-173">We received an odd alert today about an abnormal number of failed logins from a high profile user’s device.</span></span> <span data-ttu-id="c1a4f-174">이러한 시도에 대한 추가 증거는 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c1a4f-174">We can't find any further evidence for these attempts.</span></span> <span data-ttu-id="c1a4f-175">Microsoft 365 Defender에서 이러한 시도를 어떻게 볼 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="c1a4f-175">How can Microsoft 365 Defender see these attempts?</span></span> <span data-ttu-id="c1a4f-176">어떤 유형의 로그인이 모니터링되고 있나요?</span><span class="sxs-lookup"><span data-stu-id="c1a4f-176">What type of logins are being monitored?</span></span>
- <span data-ttu-id="c1a4f-177">"시스템 유틸리티의 의심스러운 동작이 관찰되었습니다."라는 경고에 대한 더 많은 컨텍스트나 정보를 얻을 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="c1a4f-177">Can you give more context or insight about the alert, "Suspicious behavior by a system utility was observed"?</span></span>
- <span data-ttu-id="c1a4f-178">"전달/리디렉션 규칙 만들기"라는 경고가 표시되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c1a4f-178">I observed an alert titled "Creation of forwarding/redirect rule".</span></span> <span data-ttu-id="c1a4f-179">활동이 무해한 것으로 생각됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1a4f-179">I believe the activity is benign.</span></span> <span data-ttu-id="c1a4f-180">알림을 받은 이유를 알 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="c1a4f-180">Can you tell me why I received an alert?</span></span>

### <a name="possible-machine-compromise"></a><span data-ttu-id="c1a4f-181">가능한 컴퓨터 손상</span><span class="sxs-lookup"><span data-stu-id="c1a4f-181">Possible machine compromise</span></span>

- <span data-ttu-id="c1a4f-182">조직의 여러 장치에서 "알 수 없는 프로세스가 관찰되었습니다."라는 메시지 또는 경고가 표시되는 이유를 설명하는 데 도움이 될 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="c1a4f-182">Can you help explain why we see a message or alert for "Unknown process observed" on many devices in our organization?</span></span> <span data-ttu-id="c1a4f-183">이 메시지 또는 경고가 악의적인 활동과 관련이 있는지를 명확히 하여 감사드립니다.</span><span class="sxs-lookup"><span data-stu-id="c1a4f-183">We appreciate any input to clarify whether this message or alert is related to malicious activity.</span></span>
- <span data-ttu-id="c1a4f-184">지난 주부터 다음 시스템에서 가능한 손상의 유효성을 검사할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="c1a4f-184">Can you help validate a possible compromise on the following system, dating from last week?</span></span> <span data-ttu-id="c1a4f-185">6개월 전에 동일한 시스템에서 이전 맬웨어 검색과 유사하게 행동하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1a4f-185">It's behaving similarly as a previous malware detection on the same system six months ago.</span></span>

### <a name="threat-intelligence-details"></a><span data-ttu-id="c1a4f-186">위협 인텔리전스 세부 정보</span><span class="sxs-lookup"><span data-stu-id="c1a4f-186">Threat intelligence details</span></span>

- <span data-ttu-id="c1a4f-187">사용자에게 악성 Word 문서를 전달하는 피싱 전자 메일을 검색했습니다.</span><span class="sxs-lookup"><span data-stu-id="c1a4f-187">We detected a phishing email that delivered a malicious Word document to a user.</span></span> <span data-ttu-id="c1a4f-188">이 문서에서는 일련의 의심스러운 이벤트가 발생하여 특정 맬웨어 패밀리에 대한 여러 경고가 트리거되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c1a4f-188">The document caused a series of suspicious events, which triggered multiple alerts for a particular malware family.</span></span> <span data-ttu-id="c1a4f-189">이 맬웨어에 대한 정보가 있나요?</span><span class="sxs-lookup"><span data-stu-id="c1a4f-189">Do you have any information on this malware?</span></span> <span data-ttu-id="c1a4f-190">그렇다면 링크를 보낼 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="c1a4f-190">If yes, can you send us a link?</span></span>
- <span data-ttu-id="c1a4f-191">최근에 업계를 대상으로 하는 위협에 대한 블로그 게시물을 보했습니다.</span><span class="sxs-lookup"><span data-stu-id="c1a4f-191">We recently saw a blog post about a threat that is targeting our industry.</span></span> <span data-ttu-id="c1a4f-192">Microsoft 365 Defender가 이 위협 요소에 대해 제공하는 보호 기능을 이해하는 데 도움이 될 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="c1a4f-192">Can you help us understand what protection Microsoft 365 Defender provides against this threat actor?</span></span>
- <span data-ttu-id="c1a4f-193">최근에 조직에 대해 수행된 피싱 캠페인을 관찰했습니다.</span><span class="sxs-lookup"><span data-stu-id="c1a4f-193">We recently observed a phishing campaign conducted against our organization.</span></span> <span data-ttu-id="c1a4f-194">이 대상이 회사 또는 수직을 대상으로 하는지 알려 주시겠습니까?</span><span class="sxs-lookup"><span data-stu-id="c1a4f-194">Can you tell us if this was targeted specifically to our company or vertical?</span></span>

### <a name="microsoft-threat-experts-alert-communications"></a><span data-ttu-id="c1a4f-195">Microsoft 위협 전문가의 경고 커뮤니케이션</span><span class="sxs-lookup"><span data-stu-id="c1a4f-195">Microsoft Threat Experts’ alert communications</span></span>

- <span data-ttu-id="c1a4f-196">인시던트 대응 팀이 수신한 대상 공격 알림을 해결할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="c1a4f-196">Can your incident response team help us address the targeted attack notification that we got?</span></span>
- <span data-ttu-id="c1a4f-197">Microsoft 위협 전문가로부터 이 대상 공격 알림을 수신했습니다.</span><span class="sxs-lookup"><span data-stu-id="c1a4f-197">We received this targeted attack notification from Microsoft Threat Experts.</span></span> <span data-ttu-id="c1a4f-198">자체 인시던트 대응 팀이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c1a4f-198">We don’t have our own incident response team.</span></span> <span data-ttu-id="c1a4f-199">지금 할 수 있는 일과 인시던트가 어떻게 포함될 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="c1a4f-199">What can we do now, and how can we contain the incident?</span></span>
- <span data-ttu-id="c1a4f-200">Microsoft 위협 전문가로부터 대상 공격 알림을 수신했습니다.</span><span class="sxs-lookup"><span data-stu-id="c1a4f-200">We received a targeted attack notification from Microsoft Threat Experts.</span></span> <span data-ttu-id="c1a4f-201">인시던트 대응 팀에 전달할 수 있는 어떤 데이터를 제공할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="c1a4f-201">What data can you provide to us that we can pass on to our incident response team?</span></span>

> [!NOTE]
> <span data-ttu-id="c1a4f-202">Microsoft 위협 전문가는 인시던트 대응 서비스가 아닌 관리되는 위협 헌팅 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="c1a4f-202">Microsoft Threat Experts is a managed threat hunting service and not an incident response service.</span></span> <span data-ttu-id="c1a4f-203">그러나 전문가는 필요한 경우 조사를 Microsoft CSG(Cybersecurity Solutions Group)의 DART(검색 및 대응 팀) 서비스로 원활하게 전환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1a4f-203">However, the experts can seamlessly transition the investigation to Microsoft Cybersecurity Solutions Group (CSG)'s Detection and Response Team (DART) services, when necessary.</span></span> <span data-ttu-id="c1a4f-204">인시던트 대응이 필요한 문제를 해결하기 위해 자체 인시던트 대응 팀에 참여할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1a4f-204">You can also opt to engage with your own incident response team to address issues that requires an incident response.</span></span>

## <a name="scenario"></a><span data-ttu-id="c1a4f-205">시나리오</span><span class="sxs-lookup"><span data-stu-id="c1a4f-205">Scenario</span></span>

### <a name="receive-a-progress-report-about-your-managed-hunting-inquiry"></a><span data-ttu-id="c1a4f-206">관리되는 헌팅 문의에 대한 진행률 보고서 받기</span><span class="sxs-lookup"><span data-stu-id="c1a4f-206">Receive a progress report about your managed hunting inquiry</span></span>

<span data-ttu-id="c1a4f-207">Microsoft 위협 전문가의 응답은 문의에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="c1a4f-207">The response from Microsoft Threat Experts will vary according to your inquiry.</span></span> <span data-ttu-id="c1a4f-208">일반적으로 다음 응답 중 하나를 받게됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1a4f-208">You'll generally receive one of the following responses:</span></span>

- <span data-ttu-id="c1a4f-209">조사를 계속하려면 추가 정보가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="c1a4f-209">More information is needed to continue with the investigation</span></span>
- <span data-ttu-id="c1a4f-210">기술 컨텍스트를 확인하려면 파일 또는 여러 파일 샘플이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="c1a4f-210">A file or several file samples are needed to determine the technical context</span></span>
- <span data-ttu-id="c1a4f-211">조사에 더 많은 시간이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="c1a4f-211">Investigation requires more time</span></span>
- <span data-ttu-id="c1a4f-212">초기 정보가 조사를 이행하기에 충분했습니다.</span><span class="sxs-lookup"><span data-stu-id="c1a4f-212">Initial information was enough to conclude the investigation</span></span>

<span data-ttu-id="c1a4f-213">전문가가 추가 정보 또는 파일 샘플을 요청하는 경우 조사를 계속 진행하기 위해 신속하게 대응하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="c1a4f-213">If an expert requests more information or file samples, it's crucial to respond quickly to keep the investigation moving.</span></span>

## <a name="see-also"></a><span data-ttu-id="c1a4f-214">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c1a4f-214">See also</span></span>

- [<span data-ttu-id="c1a4f-215">Microsoft 위협 전문가 개요</span><span class="sxs-lookup"><span data-stu-id="c1a4f-215">Microsoft Threat Experts overview</span></span>](microsoft-threat-experts.md)
