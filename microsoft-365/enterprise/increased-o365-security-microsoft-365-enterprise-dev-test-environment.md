---
title: Microsoft 365 Enterprise 테스트 환경에 대한 Office 365 보안 강화
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/16/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Microsoft 365 Enterprise 테스트 환경을 추가 Office 365 보안 설정을 사용 하도록 설정 하려면이 테스트 랩 가이드를 사용 합니다.
ms.openlocfilehash: 62cf2347d3e003e9368c987912e7748029241501
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/16/2019
ms.locfileid: "26869986"
---
# <a name="increased-office-365-security-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="e55b2-103">Microsoft 365 Enterprise 테스트 환경에 대한 Office 365 보안 강화</span><span class="sxs-lookup"><span data-stu-id="e55b2-103">Increased Office 365 security for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="e55b2-104">이 문서의 지침을 함께 Microsoft 365 기업 테스트 환경에서 보안을 강화 하기 추가 Office 365 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e55b2-104">With the instructions in this article, you configure additional Office 365 settings to increase security in your Microsoft 365 Enterprise test environment.</span></span>

![Microsoft 클라우드의 테스트 랩 가이드](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="e55b2-106">[여기](https://aka.ms/m365etlgstack)를 클릭하여 Microsoft 365 Enterprise 테스트 랩 가이드 스택의 모든 문서에 대한 가상 맵을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e55b2-106">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="e55b2-107">1 단계: Microsoft 365 Enterprise 테스트 환경을 구축합니다</span><span class="sxs-lookup"><span data-stu-id="e55b2-107">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="e55b2-108">최소 요구 사항을 경량 방식으로 Office 365 보안 강화를 구성 하려면 [경량 기본 구성](lightweight-base-configuration-microsoft-365-enterprise.md)의 지시를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="e55b2-108">If you just want to configure increased Office 365 security in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="e55b2-109">시뮬레이션 된 엔터프라이즈에서 Office 365 보안 강화 구성 하려는 경우 [통과 인증](pass-through-auth-m365-ent-test-environment.md)에 대 한 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="e55b2-109">If you want to configure increased Office 365 security in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="e55b2-p101">Office 365 보안 강화를 테스트 하지 않아도 인터넷에 연결 하는 시뮬레이션 된 인트라넷을 포함 하는 시뮬레이션 된 엔터프라이즈 테스트 환경 및 Windows Server AD 포리스트에 대 한 디렉터리 동기화 합니다. 제공는 자동화 된 라이선스 및 그룹 구성원 자격을 테스트 하 고 일반적인 조직을 대표 하는 환경에서 사용해 수 있도록 하는 옵션으로 여기 합니다.</span><span class="sxs-lookup"><span data-stu-id="e55b2-p101">Testing increased Office 365 security does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Windows Server AD forest. It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 


## <a name="phase-2-configure-increased-office-365-security"></a><span data-ttu-id="e55b2-112">2 단계: Office 365 보안 강화 구성</span><span class="sxs-lookup"><span data-stu-id="e55b2-112">Phase 2: Configure increased Office 365 security</span></span>

<span data-ttu-id="e55b2-p102">이 단계에서 Microsoft 365 기업 테스트 환경에 대 한 Office 365 보안 강화를 사용 합니다. 추가 세부 정보 및 설정에 대 한 [구성을 보안 향상된을 위해 Office 365 테 넌 트](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e55b2-p102">In this phase, you enable increased Office 365 security for your Microsoft 365 Enterprise test environment. For additional details and settings, see [Configure your Office 365 tenant for increased security](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security).</span></span>

### <a name="configure-sharepoint-online-to-block-apps-that-dont-support-modern-authentication"></a><span data-ttu-id="e55b2-115">SharePoint Online 현대 인증을 지원 하지 않는 응용 프로그램을 차단 하도록 구성</span><span class="sxs-lookup"><span data-stu-id="e55b2-115">Configure SharePoint Online to block apps that don’t support modern authentication</span></span>

<span data-ttu-id="e55b2-116">현대 인증을 지원 하지 않는 응용 프로그램 [id 및 장치에 대 한 액세스 구성](microsoft-365-policies-configurations.md) , 적용 된 Microsoft 365 구독 및 해당 디지털 자산을 보호의 중요 한 요소가 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e55b2-116">Apps that do not support modern authentication cannot have [identity and device access configurations](microsoft-365-policies-configurations.md) applied to them, which is an important element of securing your Microsoft 365 subscription and its digital assets.</span></span> 

1. <span data-ttu-id="e55b2-117">Office 포털에 이동 ([https://office.com](https://office.com)) 전역 관리자 계정 사용 하 여 Office 365 평가판 구독에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e55b2-117">Go to the Office portal ([https://office.com](https://office.com)) and sign in to your Office 365 trial subscription with your global administrator account.</span></span>
    
  - <span data-ttu-id="e55b2-118">로컬 컴퓨터에서 간단한 Microsoft 365 테스트 환경을 사용 하는 경우에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e55b2-118">If you are using the lightweight Microsoft 365 test environment, sign in from your local computer.</span></span>
    
  - <span data-ttu-id="e55b2-119">시뮬레이션 된 엔터프라이즈 Microsoft 365 테스트 환경을 사용 하는 경우 [Azure 포털](https://portal.azure.com) 을 사용 하 여 CLIENT1 가상 컴퓨터에 연결한 다음 CLIENT1에서 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e55b2-119">If you are using the simulated enterprise Microsoft 365 test environment, use the [Azure portal](https://portal.azure.com) to connect to the CLIENT1 virtual machine, and then sign in from CLIENT1.</span></span>
 
2. <span data-ttu-id="e55b2-120">**Microsoft 365 관리 센터** 탭에서 **관리**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e55b2-120">From the **Microsoft 365 admin center** tab, click **Admin**.</span></span>
3. <span data-ttu-id="e55b2-121">새 **Microsoft 365 관리 센터** 탭을 클릭 **관리 센터 > SharePoint**합니다.</span><span class="sxs-lookup"><span data-stu-id="e55b2-121">On the new **Microsoft 365 admin center** tab, click **Admin centers > SharePoint**.</span></span>
4. <span data-ttu-id="e55b2-122">새 **SharePoint 관리 센터** 탭에서 **액세스 제어**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e55b2-122">On the new **SharePoint admin center** tab, click **Access control**.</span></span>
5. <span data-ttu-id="e55b2-123">**현대 인증을 지원 하지 않는 하는 응용 프로그램** **블록**클릭 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e55b2-123">Under **Apps that don’t support modern authentication**, click **Block**, and then click **OK**.</span></span>


### <a name="enable-advanced-threat-protection-for-sharepoint-onedrive-for-business-and-microsoft-teams"></a><span data-ttu-id="e55b2-124">위협 보호 고급 사용 불가능) 개발자를 위한 SharePoint, 비즈니스 및 Microsoft 팀의 비즈니스용 OneDrive</span><span class="sxs-lookup"><span data-stu-id="e55b2-124">Enable Advanced Threat Protection) for SharePoint, OneDrive for Business, and Microsoft Teams</span></span>

<span data-ttu-id="e55b2-p103">Office 365 고급 위협 보호 (ATP) 기능의 Exchange Online Protection EOP ()는 데 도움이 되는 전자 메일에서 맬웨어를 유지 됩니다. ATP, Exchange 관리 센터 (EAC) 또는 보안 정책을 만들 & 사용자에 게 확인 하는 데 도움이 되는 준수 센터 링크 또는 하지 악의적으로 식별 되는 전자 메일에서 첨부 파일에 액세스 합니다. 자세한 내용은 [안전한 첨부 파일 및 안전 링크에 대 한 고급 위협 보호](https://docs.microsoft.com/office365/securitycompliance/office-365-atp)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e55b2-p103">Office 365 Advanced Threat Protection (ATP) is a feature of Exchange Online Protection (EOP) that helps keep malware out of your email. With ATP, you create policies in the Exchange Admin center (EAC) or the Security & Compliance center that help ensure your users access only links or attachments in emails that are identified as not malicious. For more information, see [Advanced threat protection for safe attachments and safe links](https://docs.microsoft.com/office365/securitycompliance/office-365-atp).</span></span>

1. <span data-ttu-id="e55b2-128">브라우저의 **Microsoft 365 관리 센터** 탭을 클릭 **관리 센터 > 보안 및 규정 준수**합니다.</span><span class="sxs-lookup"><span data-stu-id="e55b2-128">On the **Microsoft 365 admin center** tab of your browser, click **Admin centers > Security & Compliance**.</span></span>
2. <span data-ttu-id="e55b2-129">새 **보안 및 규정 준수** 탭을 클릭 **위협 관리 > 정책**합니다.</span><span class="sxs-lookup"><span data-stu-id="e55b2-129">On the new **Security & Compliance** tab, click **Threat management > Policy**.</span></span>
3. <span data-ttu-id="e55b2-130">**ATP 안전한 첨부 파일**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e55b2-130">Click **ATP safe attachments**.</span></span>
4. <span data-ttu-id="e55b2-131">**안전한 첨부 파일** 창에서 **SharePoint, OneDrive 및 Microsoft 팀의 ATP 설정**, 선택한 다음 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e55b2-131">In the **Safe attachments** pane, select **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams**, and then click **Save**.</span></span>

### <a name="enable-anti-malware"></a><span data-ttu-id="e55b2-132">맬웨어 방지를 사용 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="e55b2-132">Enable anti-malware</span></span>

<span data-ttu-id="e55b2-p104">맬웨어는 바이러스 및 스파이웨어로 구성 됩니다. 다른 프로그램 및 데이터, 바이러스 감염 및 감염 프로그램에 대 한 자세한 내용은 컴퓨터 전체로 확산 되기 합니다. 스파이웨어 로그인 정보 및 개인 데이터와 같은 개인 정보를 수집 하 고 해당 맬웨어 작성자에 게 다시 전송 하는 맬웨어를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="e55b2-p104">Malware is comprised of viruses and spyware. Viruses infect other programs and data, and they spread throughout your computer looking for programs to infect. Spyware refers to malware that gathers your personal information, such as sign-in information and personal data, and sends it back to the malware author.</span></span> 

<span data-ttu-id="e55b2-p105">Office 365에 기본 제공 맬웨어 및 스팸 필터링 악성 소프트웨어에서 인바운드 및 아웃 바운드 메시지를 보호 하 고 스팸에서 사용자를 보호 하는 기능에 있습니다. 자세한 내용은 [Office 365의 스팸 방지 및 맬웨어 방지 보호 기능](https://docs.microsoft.com/office365/securitycompliance/anti-spam-and-anti-malware-protection) 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e55b2-p105">Office 365 has built-in malware and spam filtering capabilities that help protect inbound and outbound messages from malicious software and help protect you from spam. For more information, see [Anti-spam & anti-malware protection in Office 365](https://docs.microsoft.com/office365/securitycompliance/anti-spam-and-anti-malware-protection)</span></span>

<span data-ttu-id="e55b2-138">맬웨어 방지 처리 일반적인 첨부 파일 형식이 포함 된 파일에 대해 수행 되는 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e55b2-138">To ensure that anti-malware processing is being performed on files with common attachment file types:</span></span>

1. <span data-ttu-id="e55b2-139">**정책** 페이지에는을 얻으려는 브라우저에서 뒤로 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e55b2-139">Click the back button on your browser to get back to the **Policy** page.</span></span>
2. <span data-ttu-id="e55b2-140">**맬웨어 방지**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e55b2-140">Click **Anti-malware**.</span></span>
3. <span data-ttu-id="e55b2-141">라는 **기본**정책을 두번클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e55b2-141">Double-click the policy named **Default**.</span></span>
4. <span data-ttu-id="e55b2-142">**맬웨어 방지 정책** 창에서 **설정**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e55b2-142">In the **Anti-malware policy** window, click **Settings**.</span></span>
4. <span data-ttu-id="e55b2-143">**일반 첨부 파일 형식 필터**클릭 **에 > 저장**합니다.</span><span class="sxs-lookup"><span data-stu-id="e55b2-143">Under **Common Attachment Types filter**, click **On > Save**.</span></span>


## <a name="phase-3-examine-office-365-security-tools-and-logs"></a><span data-ttu-id="e55b2-144">3 단계: Office 365 보안 도구 및 로그를 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="e55b2-144">Phase 3: Examine Office 365 security tools and logs</span></span>

<span data-ttu-id="e55b2-145">이 단계는 보안 이벤트에 대 한 알리고 전반적인 보안 환경의 측정 하는 기본 제공 서비스에서 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="e55b2-145">In this phase, you look at built-in services that inform you about security events and measure your overall security posture.</span></span>

### <a name="threat-management-dashboard"></a><span data-ttu-id="e55b2-146">위협 관리 대시보드</span><span class="sxs-lookup"><span data-stu-id="e55b2-146">Threat management dashboard</span></span>

<span data-ttu-id="e55b2-p106">Office 365 위협 관리 제어 및 조직의 데이터에 대 한 모바일 장치 액세스를 관리 하 고, 조직에서 데이터 손실 보호 하 고 악성 소프트웨어와 스팸에서 인바운드 및 아웃 바운드 메시지를 보호할 수 있습니다. 또한 관리 하려면 도메인의 신뢰도 보호 하기 위해 및 보낸사람은 악의적으로 스푸핑 여부를 확인 하려면 도메인에서 계정을 위협을 사용 합니다. 자세한 내용은 [Office 365 보안 및 규정 준수 센터의 위협 관리](https://docs.microsoft.com/office365/securitycompliance/threat-management)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e55b2-p106">Office 365 Threat management can help you control and manage mobile device access to your organization's data, help protect your organization from data loss, and help protect inbound and outbound messages from malicious software and spam. You also use threat management to protect your domain's reputation and to determine whether or not senders are maliciously spoofing accounts from your domain. For more information, see [Threat management in the Office 365 Security & Compliance Center](https://docs.microsoft.com/office365/securitycompliance/threat-management).</span></span>

<span data-ttu-id="e55b2-150">다음이 단계를 사용 하 여 Office 365 위협 관리 대시보드를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e55b2-150">Use these steps to view the Office 365 Threat management dashboard:</span></span>

1. <span data-ttu-id="e55b2-151">브라우저의 **Microsoft 365 관리 센터** 탭을 클릭 **관리 센터 > 보안 및 규정 준수**합니다.</span><span class="sxs-lookup"><span data-stu-id="e55b2-151">On the **Microsoft 365 admin center** tab of your browser, click **Admin centers > Security & Compliance**.</span></span>
2. <span data-ttu-id="e55b2-152">새 **보안 및 규정 준수** 탭을 클릭 **관리 위협 > 대시보드**합니다.</span><span class="sxs-lookup"><span data-stu-id="e55b2-152">On the new **Security & Compliance** tab, click **Threat management > Dashboard**.</span></span>
3. <span data-ttu-id="e55b2-153">브라우저에서 새 **대시보드** 탭에서 맬웨어 추세, 통찰력, 및 대시보드의 다른 섹션을 note 합니다.</span><span class="sxs-lookup"><span data-stu-id="e55b2-153">On the new **Dashboard** tab in your browser, note the malware trends, insights, and other sections of the dashboard.</span></span>

### <a name="office-365-cloud-app-security-dashboard"></a><span data-ttu-id="e55b2-154">Office 365 클라우드 응용 프로그램 보안 대시보드</span><span class="sxs-lookup"><span data-stu-id="e55b2-154">Office 365 Cloud App Security dashboard</span></span>

<span data-ttu-id="e55b2-p107">이전에 Office 365 고급 보안 관리 라고 office 365 클라우드 응용 프로그램 보안에 대 한 모니터링 하 고 알리기 위해 Office 365 구독에 의심 스러운 활동의 조사 하 고 가능한 수행할 수 있도록 하는 정책을 만들 수 있습니다. 업데이트 관리 작업입니다. 자세한 내용은 [개요 (영문)의 Office 365 클라우드 응용 프로그램 보안](https://docs.microsoft.com/office365/securitycompliance/office-365-cas-overview)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e55b2-p107">Office 365 Cloud App Security, previously known as Office 365 Advanced Security Management, allows you to create policies that monitor for and inform you of suspicious activities in your Office 365 subscription, so that you can investigate and take possible remediation action. For more information, see [Overview of Office 365 Cloud App Security](https://docs.microsoft.com/office365/securitycompliance/office-365-cas-overview).</span></span>

1. <span data-ttu-id="e55b2-157">브라우저의 **Microsoft 365 관리 센터** 탭을 클릭 **관리 센터 > 보안 및 규정 준수**합니다.</span><span class="sxs-lookup"><span data-stu-id="e55b2-157">On the **Microsoft 365 admin center** tab of your browser, click **Admin centers > Security & Compliance**.</span></span>
2. <span data-ttu-id="e55b2-158">새 **보안 및 규정 준수** 탭을 클릭 **알림 > 고급 알림 관리 > Office 365 클라우드 응용 프로그램 보안으로 이동**합니다.</span><span class="sxs-lookup"><span data-stu-id="e55b2-158">On the new **Security & Compliance** tab, click **Alerts > Manage advanced alerts > Go to Office 365 Cloud App Security**.</span></span>
3. <span data-ttu-id="e55b2-159">새로운 **클라우드 앱 보안** 탭에서 대시보드 보기 및 Office 365 구독에서 다양 한 활동에 대 한 모니터링 하는 기본 정책 목록 note 합니다.</span><span class="sxs-lookup"><span data-stu-id="e55b2-159">On the new **Cloud App Security** tab, note the dashboard view and the list of default policies that that monitor for various activities in your Office 365 subscription.</span></span>
4. <span data-ttu-id="e55b2-160">추적 하는 클라우드 응용 프로그램 보안 활동의 요약을 보려면 대시보드 아이콘을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e55b2-160">Click the dashboard icon to see a summary of Cloud App Security activities that are being tracked.</span></span>
5. <span data-ttu-id="e55b2-161">**조사** (안경 아이콘) 및 **작업 로그** 최근 로그인의 목록 및 기타 활동을 참조 하려면 다음을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e55b2-161">Click **Investigate** (the eyeglasses icon) and then **Activity log** to see the list of recent sign-ins and other activities.</span></span>

### <a name="secure-score"></a><span data-ttu-id="e55b2-162">보안 점수</span><span class="sxs-lookup"><span data-stu-id="e55b2-162">Secure Score</span></span>

1. <span data-ttu-id="e55b2-163">브라우저에서 새 탭을 만들고 **securescore.office.com**로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="e55b2-163">Create a new tab in your browser and go to **securescore.office.com**.</span></span>
2. <span data-ttu-id="e55b2-164">**대시보드 탭**현재 보안 점수가 및 큐의 작업 목록이 점수 향상 note 합니다.</span><span class="sxs-lookup"><span data-stu-id="e55b2-164">On the **Dashboard tab**, note your current Secure Score and the list of actions in the queue to increase your score.</span></span>

<span data-ttu-id="e55b2-165">정보 및 프로덕션 환경에서 이러한 설정을 구성 하는 링크에 대 한 **정보 보호** 단계에서 [Configure Office 365에 대 한 보안을 향상](increased-o365-security-microsoft-365-enterprise-dev-test-environment.md) 하는 단계를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e55b2-165">See the [Configure increased security for Office 365](increased-o365-security-microsoft-365-enterprise-dev-test-environment.md) step in the **Information protection** phase for information and links to configure these settings in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="e55b2-166">다음 단계</span><span class="sxs-lookup"><span data-stu-id="e55b2-166">Next step</span></span>

<span data-ttu-id="e55b2-167">추가 [정보 보호](m365-enterprise-test-lab-guides.md#information-protection) 기능 및 기능 테스트 환경에서 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="e55b2-167">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="e55b2-168">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e55b2-168">See also</span></span>

[<span data-ttu-id="e55b2-169">Microsoft 365 Enterprise 테스트 랩 가이드</span><span class="sxs-lookup"><span data-stu-id="e55b2-169">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="e55b2-170">Microsoft 365 Enterprise 배포</span><span class="sxs-lookup"><span data-stu-id="e55b2-170">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="e55b2-171">Microsoft 365 Enterprise 설명서</span><span class="sxs-lookup"><span data-stu-id="e55b2-171">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)

