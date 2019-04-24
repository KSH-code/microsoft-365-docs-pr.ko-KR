---
title: microsoft 365 Enterprise 테스트 환경에 대 한 microsoft 365 보안이 향상 되었습니다.
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/10/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-security-compliance
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: 이 테스트 랩 가이드를 사용 하 여 microsoft 365 Enterprise Test environment 추가 microsoft 365 보안 설정을 사용 하도록 설정 합니다.
ms.openlocfilehash: 54e05122dcbe5d4e24f092536897f2a8ad449e05
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32283658"
---
# <a name="increased-microsoft-365-security-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="5b430-103">microsoft 365 Enterprise 테스트 환경에 대 한 microsoft 365 보안이 향상 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5b430-103">Increased Microsoft 365 security for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="5b430-104">이 문서의 지침을 사용 하 여 microsoft 365 Enterprise 테스트 환경의 보안을 강화 하도록 microsoft 365 설정을 추가로 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b430-104">With the instructions in this article, you configure additional Microsoft 365 settings to increase security in your Microsoft 365 Enterprise test environment.</span></span>

![Microsoft 클라우드의 테스트 랩 가이드](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="5b430-106">[여기](https://aka.ms/m365etlgstack)를 클릭하여 Microsoft 365 Enterprise 테스트 랩 가이드 스택의 모든 문서에 대한 가상 맵을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b430-106">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="5b430-107">1 단계: Microsoft 365 Enterprise 테스트 환경 구축</span><span class="sxs-lookup"><span data-stu-id="5b430-107">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="5b430-108">최소 요구 사항에 따라 간단한 방법으로 Microsoft 365 보안 강화를 구성 하려는 경우에는 [간단한 기본 구성](lightweight-base-configuration-microsoft-365-enterprise.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="5b430-108">If you just want to configure increased Microsoft 365 security in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="5b430-109">시뮬레이트된 엔터프라이즈에서 Microsoft 365 보안 향상을 구성 하려면 [통과 인증](pass-through-auth-m365-ent-test-environment.md)의 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="5b430-109">If you want to configure increased Microsoft 365 security in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="5b430-110">테스팅 Microsoft 365 security에서는 AD DS (Active directory 도메인 서비스) 포리스트의 인터넷 및 디렉터리 동기화에 연결 된 시뮬레이트된 인트라넷을 포함 하는 시뮬레이트된 엔터프라이즈 테스트 환경을 필요로 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5b430-110">Testing increased Microsoft 365 security does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="5b430-111">이 기능은 자동 라이선스 및 그룹 구성원을 테스트 하 고 일반적인 조직을 나타내는 환경에서 테스트할 수 있도록 옵션으로 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5b430-111">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 


## <a name="phase-2-configure-increased-microsoft-365-security"></a><span data-ttu-id="5b430-112">2 단계: 향상 된 Microsoft 365 보안 구성</span><span class="sxs-lookup"><span data-stu-id="5b430-112">Phase 2: Configure increased Microsoft 365 security</span></span>

<span data-ttu-id="5b430-113">이 단계에서는 microsoft 365 Enterprise 테스트 환경에 대 한 microsoft 365 보안 향상을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b430-113">In this phase, you enable increased Microsoft 365 security for your Microsoft 365 Enterprise test environment.</span></span> <span data-ttu-id="5b430-114">추가 정보 및 설정에 대 한 자세한 내용은 [보안 강화를 위해 Office 365 테 넌 트 구성](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5b430-114">For additional details and settings, see [Configure your Office 365 tenant for increased security](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security).</span></span>

### <a name="configure-sharepoint-online-to-block-apps-that-dont-support-modern-authentication"></a><span data-ttu-id="5b430-115">최신 인증을 지원 하지 않는 앱을 차단 하도록 SharePoint Online 구성</span><span class="sxs-lookup"><span data-stu-id="5b430-115">Configure SharePoint Online to block apps that don’t support modern authentication</span></span>

<span data-ttu-id="5b430-116">최신 인증을 지원 하지 않는 앱에는 [id 및 장치 액세스 구성을](microsoft-365-policies-configurations.md) 적용할 수 없으며,이는 Microsoft 365 구독 및 디지털 자산의 보안을 유지 하는 중요 한 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="5b430-116">Apps that do not support modern authentication cannot have [identity and device access configurations](microsoft-365-policies-configurations.md) applied to them, which is an important element of securing your Microsoft 365 subscription and its digital assets.</span></span> 

1. <span data-ttu-id="5b430-117">office portal ([https://office.com](https://office.com))로 이동 하 고 전역 관리자 계정을 사용 하 여 office 365 평가판 구독에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b430-117">Go to the Office portal ([https://office.com](https://office.com)) and sign in to your Office 365 trial subscription with your global administrator account.</span></span>
    
  - <span data-ttu-id="5b430-118">경량 Microsoft 365 테스트 환경을 사용 하는 경우 로컬 컴퓨터에서 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b430-118">If you are using the lightweight Microsoft 365 test environment, sign in from your local computer.</span></span>
    
  - <span data-ttu-id="5b430-119">시뮬레이트된 엔터프라이즈 Microsoft 365 테스트 환경을 사용 하는 경우 [Azure portal](https://portal.azure.com) 을 사용 하 여 client1 가상 컴퓨터에 연결한 다음 client1에서 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b430-119">If you are using the simulated enterprise Microsoft 365 test environment, use the [Azure portal](https://portal.azure.com) to connect to the CLIENT1 virtual machine, and then sign in from CLIENT1.</span></span>
 
2. <span data-ttu-id="5b430-120">**Microsoft 365 관리 센터** 탭에서 **관리자**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b430-120">From the **Microsoft 365 admin center** tab, click **Admin**.</span></span>
3. <span data-ttu-id="5b430-121">새 **Microsoft 365 관리 센터** 탭에서 **관리 센터 > SharePoint**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b430-121">On the new **Microsoft 365 admin center** tab, click **Admin centers > SharePoint**.</span></span>
4. <span data-ttu-id="5b430-122">새 **SharePoint 관리 센터** 탭에서 **액세스 제어**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b430-122">On the new **SharePoint admin center** tab, click **Access control**.</span></span>
5. <span data-ttu-id="5b430-123">**최신 인증을 지원 하지 않는 앱**에서 **차단을**클릭 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b430-123">Under **Apps that don’t support modern authentication**, click **Block**, and then click **OK**.</span></span>


### <a name="enable-advanced-threat-protection-for-sharepoint-onedrive-for-business-and-microsoft-teams"></a><span data-ttu-id="5b430-124">SharePoint, 비즈니스용 OneDrive 및 Microsoft 팀에 대해 Advanced Threat Protection을 사용 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="5b430-124">Enable Advanced Threat Protection for SharePoint, OneDrive for Business, and Microsoft Teams</span></span>

<span data-ttu-id="5b430-125">SharePoint, OneDrive 및 Microsoft 팀의 Office 365 Advanced Threat Protection (ATP)은 악의적인 파일을 실수로 공유 하지 않도록 조직을 보호 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b430-125">Office 365 Advanced Threat Protection (ATP) for SharePoint, OneDrive, and Microsoft Teams protects your organization from inadvertently sharing malicious files.</span></span>

1. <span data-ttu-id="5b430-126">[Office 365 Security & 준수 센터로](https://protection.office.com) 이동 하 여 전역 관리자 계정으로 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b430-126">Go to the [Office 365 Security & Compliance Center](https://protection.office.com) and sign in with your global administrator account.</span></span>

2. <span data-ttu-id="5b430-127">왼쪽 탐색 창의 **위협 관리**에서 **정책 > 안전한 첨부 파일**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b430-127">In the left navigation pane, under **Threat management**, choose **Policy > Safe Attachments**.</span></span> 

3. <span data-ttu-id="5b430-128">**SharePoint, OneDrive 및 Microsoft 팀에 대해 ATP 사용**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b430-128">Select **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams**.</span></span>

4. <span data-ttu-id="5b430-129">**저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5b430-129">Click **Save**.</span></span>


### <a name="enable-anti-malware"></a><span data-ttu-id="5b430-130">맬웨어 방지 사용</span><span class="sxs-lookup"><span data-stu-id="5b430-130">Enable anti-malware</span></span>

<span data-ttu-id="5b430-131">맬웨어는 바이러스 및 스파이웨어로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="5b430-131">Malware is comprised of viruses and spyware.</span></span> <span data-ttu-id="5b430-132">바이러스는 다른 프로그램 및 데이터를 감염시키며 컴퓨터 전체로 전파되어 감염시킬 프로그램을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="5b430-132">Viruses infect other programs and data, and they spread throughout your computer looking for programs to infect.</span></span> <span data-ttu-id="5b430-133">스파이웨어는 로그인 정보와 개인 데이터 등의 개인 정보를 수집하여 이를 맬웨어 작성자에게 보내는 맬웨어입니다.</span><span class="sxs-lookup"><span data-stu-id="5b430-133">Spyware refers to malware that gathers your personal information, such as sign-in information and personal data, and sends it back to the malware author.</span></span> 

<span data-ttu-id="5b430-134">Office 365에는 악성 소프트웨어 로부터 인바운드 및 아웃 바운드 메시지를 보호 하 고 스팸을 보호 하는 데 도움이 되는 맬웨어 및 스팸 필터링 기능이 기본적으로 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5b430-134">Office 365 has built-in malware and spam filtering capabilities that help protect inbound and outbound messages from malicious software and help protect you from spam.</span></span> <span data-ttu-id="5b430-135">자세한 내용은 [스팸 방지 & 맬웨어 방지 보호 기능 (Office 365의](https://docs.microsoft.com/office365/securitycompliance/anti-spam-and-anti-malware-protection) )을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5b430-135">For more information, see [Anti-spam & anti-malware protection in Office 365](https://docs.microsoft.com/office365/securitycompliance/anti-spam-and-anti-malware-protection)</span></span>

<span data-ttu-id="5b430-136">일반적인 첨부 파일 형식이 포함 된 파일에서 맬웨어 방지 처리가 수행 되 고 있는지 확인 하려면 다음과 같이 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b430-136">To ensure that anti-malware processing is being performed on files with common attachment file types:</span></span>

1. <span data-ttu-id="5b430-137">브라우저에서 뒤로 단추를 클릭 하 여 **정책** 페이지로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="5b430-137">Click the back button on your browser to get back to the **Policy** page.</span></span>
2. <span data-ttu-id="5b430-138">**맬웨어 방지**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b430-138">Click **Anti-malware**.</span></span>
3. <span data-ttu-id="5b430-139">**Default**라는 정책을 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b430-139">Double-click the policy named **Default**.</span></span>
4. <span data-ttu-id="5b430-140">**맬웨어 방지 정책** 창에서 **설정을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b430-140">In the **Anti-malware policy** window, click **Settings**.</span></span>
4. <span data-ttu-id="5b430-141">**일반 첨부 파일 형식 필터**에서 **> 저장을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b430-141">Under **Common Attachment Types filter**, click **On > Save**.</span></span>


## <a name="phase-3-examine-office-365-security-tools-and-logs"></a><span data-ttu-id="5b430-142">3 단계: Office 365 보안 도구 및 로그 검사</span><span class="sxs-lookup"><span data-stu-id="5b430-142">Phase 3: Examine Office 365 security tools and logs</span></span>

<span data-ttu-id="5b430-143">이 단계에서는 보안 이벤트를 알려 주고 전반적인 보안 환경을 측정 하는 기본 제공 서비스를 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="5b430-143">In this phase, you look at built-in services that inform you about security events and measure your overall security posture.</span></span>

### <a name="threat-management-dashboard"></a><span data-ttu-id="5b430-144">위협 관리 대시보드</span><span class="sxs-lookup"><span data-stu-id="5b430-144">Threat management dashboard</span></span>

<span data-ttu-id="5b430-145">Office 365 위협 관리는 조직의 데이터에 대 한 모바일 장치 액세스를 제어 및 관리 하 고, 데이터 손실을 방지 하는 데 도움이 되며, 악성 소프트웨어 및 스팸 으로부터 인바운드 및 아웃 바운드 메시지를 보호 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5b430-145">Office 365 Threat management can help you control and manage mobile device access to your organization's data, help protect your organization from data loss, and help protect inbound and outbound messages from malicious software and spam.</span></span> <span data-ttu-id="5b430-146">또한 위협 관리를 사용 하 여 도메인의 신뢰도를 보호 하 고 보낸 사람이 도메인에서 악의적으로 계정을 위장 하는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b430-146">You also use threat management to protect your domain's reputation and to determine whether or not senders are maliciously spoofing accounts from your domain.</span></span> <span data-ttu-id="5b430-147">자세한 내용은 [Microsoft 365 보안 센터의 위협 관리](https://docs.microsoft.com/office365/securitycompliance/threat-management)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5b430-147">For more information, see [Threat management in the Microsoft 365 security center](https://docs.microsoft.com/office365/securitycompliance/threat-management).</span></span>


### <a name="office-365-cloud-app-security-dashboard"></a><span data-ttu-id="5b430-148">Office 365 Cloud App Security 대시보드</span><span class="sxs-lookup"><span data-stu-id="5b430-148">Office 365 Cloud App Security dashboard</span></span>

<span data-ttu-id="5b430-149">office 365 Cloud App security (이전에는 office 365 Advanced Security Management)를 통해 office 365 구독에서 의심 스러운 활동을 모니터링 하 고 사용자에 게 알리기 위한 정책을 만들 수 있습니다. 수정 작업</span><span class="sxs-lookup"><span data-stu-id="5b430-149">Office 365 Cloud App Security, previously known as Office 365 Advanced Security Management, allows you to create policies that monitor for and inform you of suspicious activities in your Office 365 subscription, so that you can investigate and take possible remediation action.</span></span> <span data-ttu-id="5b430-150">자세한 내용은 [Overview For Office 365 Cloud App Security](https://docs.microsoft.com/office365/securitycompliance/office-365-cas-overview)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5b430-150">For more information, see [Overview of Office 365 Cloud App Security](https://docs.microsoft.com/office365/securitycompliance/office-365-cas-overview).</span></span>

<!--
### Microsoft 365 Secure Score

1. Create a new tab in your browser and go to the [Microsoft 365 security center](https://security.microsoft.com/), and then click **Secure score**.
2. On the **Dashboard tab**, note your current Secure Score and the list of actions in the queue to increase your score.
!-->


## <a name="next-steps"></a><span data-ttu-id="5b430-151">다음 단계</span><span class="sxs-lookup"><span data-stu-id="5b430-151">Next steps</span></span>

<span data-ttu-id="5b430-152">프로덕션 환경에서 이러한 설정을 구성 하는 방법에 대 한 자세한 내용은 **정보 보호** 단계에서 [Microsoft 365에 대 한 향상 된 보안 구성](infoprotect-configure-increased-security-office-365.md) 단계를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5b430-152">See the [Configure increased security for Microsoft 365](infoprotect-configure-increased-security-office-365.md) step in the **Information protection** phase for information and links to configure these settings in production.</span></span>

<span data-ttu-id="5b430-153">테스트 환경에서 추가 [정보 보호](m365-enterprise-test-lab-guides.md#information-protection) 기능에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="5b430-153">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="5b430-154">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5b430-154">See also</span></span>

[<span data-ttu-id="5b430-155">Microsoft 365 Enterprise 테스트 랩 가이드</span><span class="sxs-lookup"><span data-stu-id="5b430-155">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="5b430-156">Microsoft 365 Enterprise 배포</span><span class="sxs-lookup"><span data-stu-id="5b430-156">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="5b430-157">Microsoft 365 Enterprise 설명서</span><span class="sxs-lookup"><span data-stu-id="5b430-157">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)

