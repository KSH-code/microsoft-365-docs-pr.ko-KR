---
title: Microsoft 위협 전문가 기능 구성 및 관리
ms.reviewer: ''
description: Microsoft 위협 전문가에 등록하여 일상적인 보안 작업 및 보안 관리 작업에 이를 구성, 관리 및 사용할 수 있습니다.
keywords: Microsoft 위협 전문가, 관리되는 위협 헌팅 서비스, MTE, Microsoft 관리 헌팅 서비스
search.product: Windows 10
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 226fc389aab24dda2425a17f5fb8d49da93e35d8
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770664"
---
# <a name="configure-and-manage-microsoft-threat-experts-capabilities"></a><span data-ttu-id="3ce8d-104">Microsoft 위협 전문가 기능 구성 및 관리</span><span class="sxs-lookup"><span data-stu-id="3ce8d-104">Configure and manage Microsoft Threat Experts capabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="3ce8d-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="3ce8d-105">**Applies to:**</span></span>
- [<span data-ttu-id="3ce8d-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="3ce8d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="3ce8d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3ce8d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="3ce8d-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="3ce8d-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="3ce8d-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="3ce8d-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="before-you-begin"></a><span data-ttu-id="3ce8d-110">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="3ce8d-110">Before you begin</span></span> 
> [!NOTE]
> <span data-ttu-id="3ce8d-111">Microsoft 위협 전문가 - 대상 공격 알림 관리 위협 헌팅 서비스에 적용하기 전에 Microsoft 기술 서비스 공급자 및 계정 팀과 자격 요구 사항을 논의합니다.</span><span class="sxs-lookup"><span data-stu-id="3ce8d-111">Discuss the eligibility requirements with your Microsoft Technical Service provider and account team before you apply to Microsoft Threat Experts - Targeted Attack Notification managed threat hunting service.</span></span>

<span data-ttu-id="3ce8d-112">실험실 설정이 아니라 장치가 등록된 환경에 Endpoint용 Defender를 배포해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ce8d-112">Ensure that you have Defender for Endpoint deployed in your environment with devices enrolled, and not just on a laboratory set-up.</span></span>

<span data-ttu-id="3ce8d-113">Endpoint 고객용 Defender인 경우 Microsoft 위협 전문가 **-** 대상 지정 공격 알림을 신청하여 가장 중요한 위협을 식별할 수 있도록 특별 인사이트 및 분석을 통해 신속하게 대응할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ce8d-113">If you're a Defender for Endpoint customer, you need to apply for **Microsoft Threat Experts - Targeted Attack Notifications** to get special insights and analysis to help identify the most critical threats, so you can respond to them quickly.</span></span> <span data-ttu-id="3ce8d-114">계정 팀 또는 Microsoft 담당자에게 문의하여 Microsoft 위협 전문가 **-** 요구 시 전문가에게 문의하여 위협 전문가에게 관련 탐지 및 가해자에 대한 자문을 구하세요.</span><span class="sxs-lookup"><span data-stu-id="3ce8d-114">Contact your account team or Microsoft representative to subscribe to **Microsoft Threat Experts - Experts on Demand** to consult with our threat experts on relevant detections and adversaries.</span></span>

## <a name="apply-for-microsoft-threat-experts---targeted-attack-notifications-service"></a><span data-ttu-id="3ce8d-115">대상 Microsoft 위협 전문가 - 대상 공격 알림 서비스</span><span class="sxs-lookup"><span data-stu-id="3ce8d-115">Apply for Microsoft Threat Experts - Targeted Attack Notifications service</span></span> 
<span data-ttu-id="3ce8d-116">이미 Endpoint용 Defender 고객인 경우 다음을 통해 Microsoft Defender 보안 센터.</span><span class="sxs-lookup"><span data-stu-id="3ce8d-116">If you're already a Defender for Endpoint customer, you can apply through the Microsoft Defender Security Center.</span></span> 

1. <span data-ttu-id="3ce8d-117">탐색 창에서 일반 설정 > 고급 > - > Microsoft 위협 전문가 **알림으로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="3ce8d-117">From the navigation pane, go to **Settings > General > Advanced features > Microsoft Threat Experts - Targeted Attack Notifications**.</span></span>

2. <span data-ttu-id="3ce8d-118">**적용** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3ce8d-118">Click **Apply**.</span></span>

    ![Microsoft 위협 전문가 이미지](images/mte-collaboratewithmte.png)

3. <span data-ttu-id="3ce8d-120">Microsoft에서 응용 프로그램에서 다시 연락할 수 있도록 이름과 전자 메일 주소를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="3ce8d-120">Enter your name and email address so that Microsoft can get back to you on your application.</span></span>

    ![응용 Microsoft 위협 전문가 이미지](images/mte-apply.png)

4. <span data-ttu-id="3ce8d-122">개인 정보 [취급 방침을 읽은](https://privacy.microsoft.com/en-us/privacystatement)다음 완료되면 **제출을** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3ce8d-122">Read the [privacy statement](https://privacy.microsoft.com/en-us/privacystatement), then click **Submit** when you're done.</span></span> <span data-ttu-id="3ce8d-123">응용 프로그램이 승인되면 환영 전자 메일을 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3ce8d-123">You will receive a welcome email once your application is approved.</span></span>

    ![응용 Microsoft 위협 전문가 확인 이미지](images/mte-applicationconfirmation.png)

<span data-ttu-id="3ce8d-125">수락하면 환영 전자 메일이 표시되면  적용 단추가 "설정" 토글로 변경되는 것을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ce8d-125">When accepted, you will receive a welcome email and you will see the **Apply** button change to a toggle that is “on”.</span></span> <span data-ttu-id="3ce8d-126">대상 공격 알림 서비스에서 자신을 꺼내려면 토글 "꺼진" 토글을  밀어 페이지 아래쪽의 기본 설정 저장을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3ce8d-126">In case you want to take yourself out of the Targeted Attack Notifications service, slide the toggle “off” and click **Save preferences** at the bottom of the page.</span></span> 

## <a name="where-youll-see-the-targeted-attack-notifications-from-microsoft-threat-experts"></a><span data-ttu-id="3ce8d-127">대상이 지정한 공격 알림을 볼 수 있는 위치는 Microsoft 위협 전문가</span><span class="sxs-lookup"><span data-stu-id="3ce8d-127">Where you'll see the targeted attack notifications from Microsoft Threat Experts</span></span> 
<span data-ttu-id="3ce8d-128">다음 중간을 통해 Microsoft 위협 전문가 대상 공격 알림을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ce8d-128">You can receive targeted attack notification from Microsoft Threat Experts through the following medium:</span></span>  
- <span data-ttu-id="3ce8d-129">Endpoint 포털의 인시던트에 대한 **Defender** 페이지</span><span class="sxs-lookup"><span data-stu-id="3ce8d-129">The Defender for Endpoint portal's **Incidents** page</span></span> 
- <span data-ttu-id="3ce8d-130">Endpoint 포털의 경고 대시보드에 대한 **Defender**</span><span class="sxs-lookup"><span data-stu-id="3ce8d-130">The Defender for Endpoint portal's **Alerts** dashboard</span></span>  
- <span data-ttu-id="3ce8d-131">OData 경고 [API 및](/windows/security/threat-protection/microsoft-defender-atp/get-alerts) REST [API](/windows/security/threat-protection/microsoft-defender-atp/pull-alerts-using-rest-api)</span><span class="sxs-lookup"><span data-stu-id="3ce8d-131">OData alerting [API](/windows/security/threat-protection/microsoft-defender-atp/get-alerts) and [REST API](/windows/security/threat-protection/microsoft-defender-atp/pull-alerts-using-rest-api)</span></span>
- <span data-ttu-id="3ce8d-132">[고급 헌팅의 DeviceAlertEvents](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-devicealertevents-table) 테이블</span><span class="sxs-lookup"><span data-stu-id="3ce8d-132">[DeviceAlertEvents](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-devicealertevents-table) table in Advanced hunting</span></span>
- <span data-ttu-id="3ce8d-133">전자 메일 구성을 선택한 경우</span><span class="sxs-lookup"><span data-stu-id="3ce8d-133">Your email, if you choose to configure it</span></span> 

<span data-ttu-id="3ce8d-134">전자 메일을 통해 대상 공격 알림을 받으면 전자 메일 알림 규칙을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="3ce8d-134">To receive targeted attack notifications through email, create an email notification rule.</span></span>

### <a name="create-an-email-notification-rule"></a><span data-ttu-id="3ce8d-135">전자 메일 알림 규칙 만들기</span><span class="sxs-lookup"><span data-stu-id="3ce8d-135">Create an email notification rule</span></span> 
<span data-ttu-id="3ce8d-136">알림 받는 사람에 대한 전자 메일 알림을 보내는 규칙을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ce8d-136">You can create rules to send email notifications for notification recipients.</span></span> <span data-ttu-id="3ce8d-137">자세한  [내용은 전자](configure-email-notifications.md) 메일 알림을 생성, 편집, 삭제 또는 문제 해결하도록 알림 알림 구성을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3ce8d-137">See  [Configure alert notifications](configure-email-notifications.md) to create, edit, delete, or troubleshoot email notification, for details.</span></span>

## <a name="view-the-targeted-attack-notification"></a><span data-ttu-id="3ce8d-138">대상 공격 알림 보기</span><span class="sxs-lookup"><span data-stu-id="3ce8d-138">View the targeted attack notification</span></span>  
<span data-ttu-id="3ce8d-139">전자 메일 알림을 받도록 시스템을 구성한 후 Microsoft 위협 전문가 대상 공격 알림 수신을 시작할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3ce8d-139">You'll start receiving targeted attack notification from Microsoft Threat Experts in your email after you have configured your system to receive email notification.</span></span>  

1. <span data-ttu-id="3ce8d-140">전자 메일의 링크를 클릭하여 위협 전문가로 태그가 지정된 대시보드의 해당 경고 컨텍스트로 **이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="3ce8d-140">Click the link in the email to go to the corresponding alert context in the dashboard tagged with **Threat experts**.</span></span> 

2. <span data-ttu-id="3ce8d-141">대시보드에서 전자 메일에서 확인한 동일한 경고 항목을 선택하여 세부 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ce8d-141">From the dashboard, select the same alert topic that you got from the email, to view the details.</span></span>  

## <a name="subscribe-to-microsoft-threat-experts---experts-on-demand"></a><span data-ttu-id="3ce8d-142">구독 - Microsoft 위협 전문가 전문가</span><span class="sxs-lookup"><span data-stu-id="3ce8d-142">Subscribe to Microsoft Threat Experts - Experts on Demand</span></span>
<span data-ttu-id="3ce8d-143">이 서비스는 구독 서비스로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ce8d-143">This is available as a subscription service.</span></span> <span data-ttu-id="3ce8d-144">이미 Endpoint용 Defender 고객인 경우 Microsoft 담당자에게 문의하여 Microsoft 위협 전문가 - 전문가에게 문의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ce8d-144">If you're already a Defender for Endpoint customer, you can contact your Microsoft representative to subscribe to Microsoft Threat Experts - Experts on Demand.</span></span> 

## <a name="consult-a-microsoft-threat-expert-about-suspicious-cybersecurity-activities-in-your-organization"></a><span data-ttu-id="3ce8d-145">조직의 의심스러운 사이버 보안 활동에 대한 Microsoft 위협 전문가에게 문의</span><span class="sxs-lookup"><span data-stu-id="3ce8d-145">Consult a Microsoft threat expert about suspicious cybersecurity activities in your organization</span></span> 
<span data-ttu-id="3ce8d-146">적시에 정확한 응답을 Microsoft 위협 전문가 내에서 직접 참여할 수 있는 Microsoft Defender 보안 센터 파트너와 파트너가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ce8d-146">You can partner with Microsoft Threat Experts who can be engaged directly from within the Microsoft Defender Security Center for timely and accurate response.</span></span> <span data-ttu-id="3ce8d-147">전문가는 복잡한 위협, 사용자가 수신하는 대상이 지정되는 공격 알림을 더 잘 이해하거나, 알림, 잠재적으로 손상된 장치 또는 포털 대시보드에 표시될 위협 인텔리전스 컨텍스트에 대한 추가 정보가 필요한 경우를 보다 잘 이해할 수 있는 인사이트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3ce8d-147">Experts provide insights to better understand complex threats, targeted attack notifications that you get, or if you need more information about the alerts, a potentially compromised device, or a threat intelligence context that you see on your portal dashboard.</span></span> 

> [!NOTE]
> - <span data-ttu-id="3ce8d-148">조직의 사용자 지정된 위협 인텔리전스 데이터와 관련된 경고 문의는 현재 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3ce8d-148">Alert inquiries related to your organization's customized threat intelligence data are currently not supported.</span></span> <span data-ttu-id="3ce8d-149">자세한 내용은 보안 운영 또는 인시던트 대응 팀에 문의합니다.</span><span class="sxs-lookup"><span data-stu-id="3ce8d-149">Consult your security operations or incident response team for details.</span></span>
> - <span data-ttu-id="3ce8d-150">보안 센터 포털에서 보안 설정 관리 권한이 있는 경우 "위협 전문가에게 문의" 요청을 제출할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="3ce8d-150">You need to have the **Manage security settings** permission in the Security Center portal to be able to submit a "Consult a threat expert" inquiry.</span></span>

1. <span data-ttu-id="3ce8d-151">조사할 관련 정보(예: 인시던트 페이지)를 사용하여 포털 **페이지로** 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="3ce8d-151">Navigate to the portal page with the relevant information that you'd like to investigate, for example, the **Incident** page.</span></span> <span data-ttu-id="3ce8d-152">조사 요청을 보내기 전에 관련 경고 또는 장치에 대한 페이지가 보기에 표시되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ce8d-152">Ensure that the page for the relevant alert or device is in view before you send an investigation request.</span></span> 

2. <span data-ttu-id="3ce8d-153">오른쪽 위 메뉴에서 **?**</span><span class="sxs-lookup"><span data-stu-id="3ce8d-153">From the upper right-hand menu, click the **?**</span></span> <span data-ttu-id="3ce8d-154">아이콘을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3ce8d-154">icon.</span></span> <span data-ttu-id="3ce8d-155">그런 다음 위협 **전문가에게 문의를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="3ce8d-155">Then, select **Consult a threat expert**.</span></span> 

    ![메뉴의 Microsoft 위협 전문가 전문가 이미지](images/mte-eod-menu.png)

    <span data-ttu-id="3ce8d-157">플라이아웃 화면이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="3ce8d-157">A flyout screen opens.</span></span> <span data-ttu-id="3ce8d-158">다음 화면은 평가판 구독을 사용 중일 때 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3ce8d-158">The following screen shows when you are on a trial subscription.</span></span>

    ![요구 Microsoft 위협 전문가 전문가 화면의 이미지](images/mte-eod.png)

    <span data-ttu-id="3ce8d-160">다음 화면에는 전체 구독 - 전문가 Microsoft 위협 전문가 구독이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3ce8d-160">The following screen shows when you are on a full Microsoft Threat Experts - Experts on-Demand subscription.</span></span>

    ![전문가가 Microsoft 위협 전문가 전체 구독 화면의 이미지](images/mte-eod-fullsubscription.png)

    <span data-ttu-id="3ce8d-162">문의 **항목 필드에는** 조사 요청에 대한 관련 페이지에 대한 링크가 미리 채워진 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3ce8d-162">The **Inquiry topic** field is pre-populated with the link to the relevant page for your investigation request.</span></span> <span data-ttu-id="3ce8d-163">예를 들어 요청을 할 때 확인한 인시던트, 경고 또는 장치 세부 정보 페이지에 대한 링크입니다.</span><span class="sxs-lookup"><span data-stu-id="3ce8d-163">For example, a link to the incident, alert, or device details page that you were at when you made the request.</span></span>

3.  <span data-ttu-id="3ce8d-164">다음 필드에서 조사를 시작할 수 있는 Microsoft 위협 전문가 충분한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3ce8d-164">In the next field, provide enough information to give the Microsoft Threat Experts enough context to start the investigation.</span></span>
  
4. <span data-ttu-id="3ce8d-165">전자 메일 주소와 대응하는 데 사용할 전자 메일 주소를 Microsoft 위협 전문가.</span><span class="sxs-lookup"><span data-stu-id="3ce8d-165">Enter the email address that you'd like to use to correspond with Microsoft Threat Experts.</span></span>

> [!NOTE]
> <span data-ttu-id="3ce8d-166">Microsoft 서비스 허브를 통해 전문가 관련 사례의 상태를 추적하려면 기술 계정 관리자에게 문의하세요.</span><span class="sxs-lookup"><span data-stu-id="3ce8d-166">If you would like to track the status of your Experts on Demand cases through Microsoft Services Hub, reach out to your Technical Account Manager.</span></span> 

<span data-ttu-id="3ce8d-167">이 비디오를 시청하여 Microsoft 서비스 허브에 대한 간략한 개요를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ce8d-167">Watch this video for a quick overview of the Microsoft Services Hub.</span></span>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4pk9f] 


   
## <a name="sample-investigation-topics-that-you-can-consult-with-microsoft-threat-experts---experts-on-demand"></a><span data-ttu-id="3ce8d-168">전문가 - 요구 시 전문가와 Microsoft 위협 전문가 수 있는 샘플 조사 항목</span><span class="sxs-lookup"><span data-stu-id="3ce8d-168">Sample investigation topics that you can consult with Microsoft Threat Experts - Experts on Demand</span></span> 

<span data-ttu-id="3ce8d-169">**경고 정보**</span><span class="sxs-lookup"><span data-stu-id="3ce8d-169">**Alert information**</span></span>
- <span data-ttu-id="3ce8d-170">이진수 이진에 대한 새로운 유형의 경고가 표시됩니다. [AlertID].</span><span class="sxs-lookup"><span data-stu-id="3ce8d-170">We see a new type of alert for a living-off-the-land binary: [AlertID].</span></span> <span data-ttu-id="3ce8d-171">이 경고와 추가 조사 방법과 관련한 자세한 정보를 알려 주시겠습니까?</span><span class="sxs-lookup"><span data-stu-id="3ce8d-171">Can you tell us something more about this alert and how we can investigate further?</span></span>
- <span data-ttu-id="3ce8d-172">악성 PowerShell 스크립트를 실행하려고 하지만 다른 경고를 생성하는 두 가지 유사한 공격을 관찰했습니다.</span><span class="sxs-lookup"><span data-stu-id="3ce8d-172">We’ve observed two similar attacks, which try to execute malicious PowerShell scripts but generate different alerts.</span></span> <span data-ttu-id="3ce8d-173">하나는 "의심스러운 PowerShell 명령줄"이고 다른 하나는 "O365에서 제공한 표시에 따라 악성 파일이 검색되었습니다."입니다.</span><span class="sxs-lookup"><span data-stu-id="3ce8d-173">One is "Suspicious PowerShell command line" and the other is "A malicious file was detected based on indication provided by O365".</span></span> <span data-ttu-id="3ce8d-174">차이점은 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="3ce8d-174">What is the difference?</span></span>
- <span data-ttu-id="3ce8d-175">오늘은 프로필이 높은 사용자의 장치에서 비정상적인 로그인 실패 수에 대한 이상한 경고가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3ce8d-175">I receive an odd alert today for abnormal number of failed logins from a high profile user’s device.</span></span> <span data-ttu-id="3ce8d-176">이러한 로그인 시도에 대한 추가 증거를 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3ce8d-176">I cannot find any further evidence around these sign-in attempts.</span></span> <span data-ttu-id="3ce8d-177">Endpoint용 Defender는 이러한 시도를 어떻게 볼 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="3ce8d-177">How can Defender for Endpoint see these attempts?</span></span> <span data-ttu-id="3ce8d-178">어떤 유형의 로그인을 모니터링하나요?</span><span class="sxs-lookup"><span data-stu-id="3ce8d-178">What type of sign-ins are being monitored?</span></span>
- <span data-ttu-id="3ce8d-179">"시스템 유틸리티의 의심스러운 동작이 관찰되었습니다."라는 경고에 대한 더 많은 컨텍스트 또는 정보를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ce8d-179">Can you give more context or insights about this alert: “Suspicious behavior by a system utility was observed”.</span></span> 

<span data-ttu-id="3ce8d-180">**가능한 컴퓨터 손상**</span><span class="sxs-lookup"><span data-stu-id="3ce8d-180">**Possible machine compromise**</span></span>
- <span data-ttu-id="3ce8d-181">"알 수 없는 프로세스가 관찰되었습니다."가 관찰되는 이유에 대한 답변을 도울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ce8d-181">Can you help answer why we see “Unknown process observed?”</span></span> <span data-ttu-id="3ce8d-182">이 메시지 또는 경고는 많은 장치에서 자주 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3ce8d-182">This message or alert is seen frequently on many devices.</span></span> <span data-ttu-id="3ce8d-183">이 메시지 또는 경고가 악의적인 활동과 관련이 있는지를 명확히 하여 감사드립니다.</span><span class="sxs-lookup"><span data-stu-id="3ce8d-183">We appreciate any input to clarify whether this message or alert is related to malicious activity.</span></span>
- <span data-ttu-id="3ce8d-184">[월]에 동일한 시스템에서 이전 [맬웨어 이름] 맬웨어 검색과 유사한 동작으로 [날짜]에 다음 시스템에서 가능한 손상의 유효성을 검사할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="3ce8d-184">Can you help validate a possible compromise on the following system on [date] with similar behaviors as the previous [malware name] malware detection on the same system in [month]?</span></span>

<span data-ttu-id="3ce8d-185">**위협 인텔리전스 세부 정보**</span><span class="sxs-lookup"><span data-stu-id="3ce8d-185">**Threat intelligence details**</span></span>
- <span data-ttu-id="3ce8d-186">사용자에게 악성 Word 문서를 전달하는 피싱 전자 메일을 검색했습니다.</span><span class="sxs-lookup"><span data-stu-id="3ce8d-186">We detected a phishing email that delivered a malicious Word document to a user.</span></span> <span data-ttu-id="3ce8d-187">악성 Word 문서에서 일련의 의심스러운 이벤트가 발생하여 [맬웨어 이름] 맬웨어에 대한 여러 Microsoft Defender 경고가 트리거되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3ce8d-187">The malicious Word document caused a series of suspicious events, which triggered multiple Microsoft Defender alerts for [malware name] malware.</span></span> <span data-ttu-id="3ce8d-188">이 맬웨어에 대한 정보가 있나요?</span><span class="sxs-lookup"><span data-stu-id="3ce8d-188">Do you have any information on this malware?</span></span> <span data-ttu-id="3ce8d-189">그렇다면 링크를 보낼 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="3ce8d-189">If yes, can you send me a link?</span></span>
- <span data-ttu-id="3ce8d-190">최근에 산업을 대상으로 하는 위협에 대한 [소셜 미디어 참조, 예: Twitter 또는 블로그] 게시물을 보했습니다.</span><span class="sxs-lookup"><span data-stu-id="3ce8d-190">I recently saw a [social media reference, for example, Twitter or blog] post about a threat that is targeting my industry.</span></span> <span data-ttu-id="3ce8d-191">이 위협 요소에 대해 끝점용 보호 Defender가 제공하는 보호 기능을 이해하는 데 도움이 될 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="3ce8d-191">Can you help me understand what protection Defender for Endpoint provides against this threat actor?</span></span> 

<span data-ttu-id="3ce8d-192">**Microsoft 위협 전문가 알림 통신**</span><span class="sxs-lookup"><span data-stu-id="3ce8d-192">**Microsoft Threat Experts’ alert communications**</span></span> 
- <span data-ttu-id="3ce8d-193">인시던트 대응 팀이 수신한 대상 공격 알림을 해결할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="3ce8d-193">Can your incident response team help us address the targeted attack notification that we got?</span></span>
- <span data-ttu-id="3ce8d-194">I received this targeted attack notification from Microsoft 위협 전문가.</span><span class="sxs-lookup"><span data-stu-id="3ce8d-194">I received this targeted attack notification from Microsoft Threat Experts.</span></span> <span data-ttu-id="3ce8d-195">자체 인시던트 대응 팀이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3ce8d-195">We don’t have our own incident response team.</span></span> <span data-ttu-id="3ce8d-196">지금 할 수 있는 일과 인시던트가 어떻게 포함될 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="3ce8d-196">What can we do now, and how can we contain the incident?</span></span>
- <span data-ttu-id="3ce8d-197">I received a targeted attack notification from Microsoft 위협 전문가.</span><span class="sxs-lookup"><span data-stu-id="3ce8d-197">I received a targeted attack notification from Microsoft Threat Experts.</span></span> <span data-ttu-id="3ce8d-198">인시던트 대응 팀에 전달할 수 있는 어떤 데이터를 제공할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="3ce8d-198">What data can you provide to us that we can pass on to our incident response team?</span></span>

  >[!NOTE]
  ><span data-ttu-id="3ce8d-199">Microsoft 위협 전문가 서비스는 인시던트 대응 서비스가 아니라 관리되는 사이버 보안 헌팅 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="3ce8d-199">Microsoft Threat Experts is a managed cybersecurity hunting service and not an incident response service.</span></span> <span data-ttu-id="3ce8d-200">그러나 전문가는 필요한 경우 조사를 Microsoft CSG(Cybersecurity Solutions Group)의 DART(검색 및 대응 팀) 서비스로 원활하게 전환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ce8d-200">However, the experts can seamlessly transition the investigation to Microsoft Cybersecurity Solutions Group (CSG)'s  Detection and Response Team (DART) services, when necessary.</span></span> <span data-ttu-id="3ce8d-201">인시던트 대응이 필요한 문제를 해결하기 위해 자체 인시던트 대응 팀에 참여할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ce8d-201">You can also opt to engage with your own incident response team to address issues that requires an incident response.</span></span> 

## <a name="scenario"></a><span data-ttu-id="3ce8d-202">시나리오</span><span class="sxs-lookup"><span data-stu-id="3ce8d-202">Scenario</span></span>

### <a name="receive-a-progress-report-about-your-managed-hunting-inquiry"></a><span data-ttu-id="3ce8d-203">관리되는 헌팅 문의에 대한 진행률 보고서 받기</span><span class="sxs-lookup"><span data-stu-id="3ce8d-203">Receive a progress report about your managed hunting inquiry</span></span> 
<span data-ttu-id="3ce8d-204">응답은 Microsoft 위협 전문가 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="3ce8d-204">Response from Microsoft Threat Experts varies according to your inquiry.</span></span> <span data-ttu-id="3ce8d-205">2일 이내에 위협 전문가  문의에 대한 진행 상황 보고서를 전자 메일로 보내 다음 범주의 조사 상태를 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="3ce8d-205">They will email a progress report to you about your **Consult a threat expert** inquiry within two days, to communicate the investigation status from the following categories:</span></span> 
- <span data-ttu-id="3ce8d-206">조사를 계속하려면 추가 정보가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="3ce8d-206">More information is needed to continue with the investigation</span></span> 
- <span data-ttu-id="3ce8d-207">기술 컨텍스트를 확인하려면 파일 또는 여러 파일 샘플이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="3ce8d-207">A file or several file samples are needed to determine the technical context</span></span> 
- <span data-ttu-id="3ce8d-208">조사에 더 많은 시간이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="3ce8d-208">Investigation requires more time</span></span>   
- <span data-ttu-id="3ce8d-209">초기 정보가 조사를 이행하기에 충분했습니다.</span><span class="sxs-lookup"><span data-stu-id="3ce8d-209">Initial information was enough to conclude the investigation</span></span> 

<span data-ttu-id="3ce8d-210">조사를 계속 진행하기 위해 신속하게 대응하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="3ce8d-210">It is crucial to respond in quickly to keep the investigation moving.</span></span> 

## <a name="related-topic"></a><span data-ttu-id="3ce8d-211">관련 항목</span><span class="sxs-lookup"><span data-stu-id="3ce8d-211">Related topic</span></span>
- [<span data-ttu-id="3ce8d-212">Microsoft 위협 전문가 개요</span><span class="sxs-lookup"><span data-stu-id="3ce8d-212">Microsoft Threat Experts overview</span></span>](microsoft-threat-experts.md)
- [<span data-ttu-id="3ce8d-213">Microsoft 위협 전문가 개요의 Microsoft 365 참조</span><span class="sxs-lookup"><span data-stu-id="3ce8d-213">Microsoft Threat Experts in Microsoft 365 Overview</span></span>](/microsoft-365/security/mtp/microsoft-threat-experts)
