---
title: 엔터프라이즈 테스트 환경용 Microsoft 365에 대 한 Microsoft 365 보안 강화
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/09/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-security-compliance
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: 이 테스트 랩 가이드를 사용 하 여 추가 Microsoft 365 보안 설정 (엔터프라이즈 테스트 환경에 대해 Microsoft 365)을 사용 하도록 설정 합니다.
ms.openlocfilehash: 06273bda00635a65ed9821b2bac23c3a3ee1366a
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686805"
---
# <a name="increased-microsoft-365-security-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="ae1a7-103">엔터프라이즈 테스트 환경용 Microsoft 365에 대 한 Microsoft 365 보안 강화</span><span class="sxs-lookup"><span data-stu-id="ae1a7-103">Increased Microsoft 365 security for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="ae1a7-104">*이 테스트 랩 가이드는 엔터프라이즈 테스트 환경용 Microsoft 365에만 사용할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="ae1a7-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="ae1a7-105">이 문서의 지침을 사용 하 여 microsoft 365 (엔터프라이즈 테스트 환경)에서 보안을 강화 하도록 Microsoft 365 설정을 추가로 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae1a7-105">With the instructions in this article, you configure additional Microsoft 365 settings to increase security in your Microsoft 365 for enterprise test environment.</span></span>

![Microsoft 클라우드의 테스트 랩 가이드](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="ae1a7-107">[여기](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)를 클릭하여 Microsoft 365 Enterprise 테스트 랩 가이드 스택의 모든 문서에 대한 가상 맵을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae1a7-107">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="ae1a7-108">1 단계: 엔터프라이즈 테스트 환경용 Microsoft 365 구축</span><span class="sxs-lookup"><span data-stu-id="ae1a7-108">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="ae1a7-109">최소 요구 사항에 따라 간단한 방법으로 Microsoft 365 보안 강화를 구성 하려는 경우에는 [간단한 기본 구성](lightweight-base-configuration-microsoft-365-enterprise.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="ae1a7-109">If you just want to configure increased Microsoft 365 security in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="ae1a7-110">시뮬레이트된 엔터프라이즈에서 Microsoft 365 보안 향상을 구성 하려면 [통과 인증](pass-through-auth-m365-ent-test-environment.md)의 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="ae1a7-110">If you want to configure increased Microsoft 365 security in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="ae1a7-111">테스팅 Microsoft 365 security에서는 AD DS (Active Directory 도메인 서비스) 포리스트의 인터넷 및 디렉터리 동기화에 연결 된 시뮬레이트된 인트라넷을 포함 하는 시뮬레이트된 엔터프라이즈 테스트 환경을 필요로 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ae1a7-111">Testing increased Microsoft 365 security does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="ae1a7-112">이 기능은 자동 라이선스 및 그룹 구성원을 테스트 하 고 일반적인 조직을 나타내는 환경에서 테스트할 수 있도록 옵션으로 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae1a7-112">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 

## <a name="phase-2-configure-increased-microsoft-365-security"></a><span data-ttu-id="ae1a7-113">2 단계: 향상 된 Microsoft 365 보안 구성</span><span class="sxs-lookup"><span data-stu-id="ae1a7-113">Phase 2: Configure increased Microsoft 365 security</span></span>

<span data-ttu-id="ae1a7-114">이 단계에서는 엔터프라이즈 테스트 환경용 Microsoft 365에 대 한 Microsoft 365 보안 향상을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae1a7-114">In this phase, you enable increased Microsoft 365 security for your Microsoft 365 for enterprise test environment.</span></span> <span data-ttu-id="ae1a7-115">추가 정보 및 설정에 대 한 자세한 내용은 [보안 강화를 위해 테 넌 트 구성을](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="ae1a7-115">For additional details and settings, see [Configure your tenant for increased security](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security).</span></span>

### <a name="configure-sharepoint-online-to-block-apps-that-dont-support-modern-authentication"></a><span data-ttu-id="ae1a7-116">최신 인증을 지원 하지 않는 앱을 차단 하도록 SharePoint Online 구성</span><span class="sxs-lookup"><span data-stu-id="ae1a7-116">Configure SharePoint Online to block apps that don't support modern authentication</span></span>

<span data-ttu-id="ae1a7-117">최신 인증을 지원 하지 않는 앱에는 [id 및 장치 액세스 구성을](microsoft-365-policies-configurations.md) 적용할 수 없으며,이는 Microsoft 365 구독 및 디지털 자산의 보안을 유지 하는 중요 한 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="ae1a7-117">Apps that do not support modern authentication cannot have [identity and device access configurations](microsoft-365-policies-configurations.md) applied to them, which is an important element of securing your Microsoft 365 subscription and its digital assets.</span></span> 

1. <span data-ttu-id="ae1a7-118">Microsoft 365 관리 센터 ()로 이동 하 [https://portal.microsoft.com](https://portal.microsoft.com) 고 전역 관리자 계정을 사용 하 여 microsoft 365 테스트 랩 구독에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae1a7-118">Go to the Microsoft 365 admin center ([https://portal.microsoft.com](https://portal.microsoft.com)) and sign in to your Microsoft 365 test lab subscription with your global administrator account.</span></span>
    
  - <span data-ttu-id="ae1a7-119">경량 Microsoft 365 테스트 환경을 사용 하는 경우 로컬 컴퓨터에서 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae1a7-119">If you are using the lightweight Microsoft 365 test environment, sign in from your local computer.</span></span>
    
  - <span data-ttu-id="ae1a7-120">시뮬레이트된 엔터프라이즈 Microsoft 365 테스트 환경을 사용 하는 경우 [Azure portal](https://portal.azure.com) 을 사용 하 여 client1 가상 컴퓨터에 연결한 다음 client1에서 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae1a7-120">If you are using the simulated enterprise Microsoft 365 test environment, use the [Azure portal](https://portal.azure.com) to connect to the CLIENT1 virtual machine, and then sign in from CLIENT1.</span></span>
 
2. <span data-ttu-id="ae1a7-121">새 **Microsoft 365 관리 센터** 탭의 왼쪽 탐색 창에 있는 **관리 센터** 에서 **SharePoint**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae1a7-121">On the new **Microsoft 365 admin center** tab, under **Admin centers** in the left navigation pane, click **SharePoint**.</span></span>
3. <span data-ttu-id="ae1a7-122">새 **SharePoint 관리 센터** 탭에서 **정책 > 액세스 제어**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae1a7-122">On the new **SharePoint admin center** tab, click **Policies > Access control**.</span></span>
4. <span data-ttu-id="ae1a7-123">**최신 인증을 지원 하지 않는 앱**을 클릭 하 고 **액세스 차단을**선택한 다음 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae1a7-123">Click **Apps that don't support modern authentication**, select **Block access**, and then click **Save**.</span></span>


### <a name="enable-advanced-threat-protection-for-sharepoint-onedrive-for-business-and-microsoft-teams"></a><span data-ttu-id="ae1a7-124">SharePoint, 비즈니스용 OneDrive 및 Microsoft 팀에 대해 Advanced Threat Protection을 사용 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="ae1a7-124">Enable Advanced Threat Protection for SharePoint, OneDrive for Business, and Microsoft Teams</span></span>

<span data-ttu-id="ae1a7-125">SharePoint, OneDrive 및 Microsoft 팀의 Office 365 Advanced Threat Protection (ATP)은 악의적인 파일을 실수로 공유 하지 않도록 조직을 보호 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae1a7-125">Office 365 Advanced Threat Protection (ATP) for SharePoint, OneDrive, and Microsoft Teams protects your organization from inadvertently sharing malicious files.</span></span>

1. <span data-ttu-id="ae1a7-126">[보안 & 준수 센터로](https://protection.office.com) 이동 하 여 전역 관리자 계정으로 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae1a7-126">Go to the [Security & Compliance Center](https://protection.office.com) and sign in with your global administrator account.</span></span>

2. <span data-ttu-id="ae1a7-127">왼쪽 탐색 창의 **위협 관리**에서 **정책을**클릭 하 고 **ATP 안전한 첨부 파일**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae1a7-127">In the left navigation pane, under **Threat management**, click **Policy**, and then click **ATP safe attachments**.</span></span> 

3. <span data-ttu-id="ae1a7-128">**SharePoint, OneDrive 및 Microsoft 팀의 파일을 보호**합니다.</span><span class="sxs-lookup"><span data-stu-id="ae1a7-128">Under **Protect files in SharePoint, OneDrive, and Microsoft Teams**.</span></span> <span data-ttu-id="ae1a7-129">**SharePoint, OneDrive 및 Microsoft 팀에 대해 ATP 사용**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae1a7-129">select **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams**.</span></span>

4. <span data-ttu-id="ae1a7-130">**저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ae1a7-130">Click **Save**.</span></span>


### <a name="enable-anti-malware"></a><span data-ttu-id="ae1a7-131">맬웨어 방지 사용</span><span class="sxs-lookup"><span data-stu-id="ae1a7-131">Enable anti-malware</span></span>

<span data-ttu-id="ae1a7-132">맬웨어는 바이러스 및 스파이웨어로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae1a7-132">Malware is comprised of viruses and spyware.</span></span> <span data-ttu-id="ae1a7-133">바이러스는 다른 프로그램 및 데이터를 감염시키며 컴퓨터 전체로 전파되어 감염시킬 프로그램을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="ae1a7-133">Viruses infect other programs and data, and they spread throughout your computer looking for programs to infect.</span></span> <span data-ttu-id="ae1a7-134">스파이웨어는 로그인 정보와 개인 데이터 등의 개인 정보를 수집하여 이를 맬웨어 작성자에게 보내는 맬웨어입니다.</span><span class="sxs-lookup"><span data-stu-id="ae1a7-134">Spyware refers to malware that gathers your personal information, such as sign-in information and personal data, and sends it back to the malware author.</span></span> 

<span data-ttu-id="ae1a7-135">Microsoft 365에는 악성 소프트웨어 로부터 인바운드 및 아웃 바운드 메시지를 보호 하 고 스팸을 보호 하는 데 도움이 되는 맬웨어 및 스팸 필터링 기능이 기본적으로 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae1a7-135">Microsoft 365 has built-in malware and spam filtering capabilities that help protect inbound and outbound messages from malicious software and help protect you from spam.</span></span> <span data-ttu-id="ae1a7-136">자세한 내용은 [스팸 방지 & 맬웨어 방지 보호](../security/office-365-security/anti-spam-and-anti-malware-protection.md)기능을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="ae1a7-136">For more information, see [Anti-spam & anti-malware protection](../security/office-365-security/anti-spam-and-anti-malware-protection.md).</span></span>

<span data-ttu-id="ae1a7-137">일반적인 첨부 파일 형식이 포함 된 파일에서 맬웨어 방지 처리가 수행 되 고 있는지 확인 하려면 다음과 같이 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae1a7-137">To ensure that anti-malware processing is being performed on files with common attachment file types:</span></span>

1. <span data-ttu-id="ae1a7-138">브라우저에서 뒤로 단추를 클릭 하 여 **정책** 페이지로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="ae1a7-138">Click the back button on your browser to get back to the **Policy** page.</span></span>
2. <span data-ttu-id="ae1a7-139">**맬웨어 방지**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae1a7-139">Click **Anti-malware**.</span></span>
3. <span data-ttu-id="ae1a7-140">**Default**라는 정책을 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae1a7-140">Double-click the policy named **Default**.</span></span>
4. <span data-ttu-id="ae1a7-141">**맬웨어 방지 정책** 창에서 **설정을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae1a7-141">In the **Anti-malware policy** window, click **Settings**.</span></span>
4. <span data-ttu-id="ae1a7-142">**일반 첨부 파일 형식 필터**에서 **설정**를 선택 하 고 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae1a7-142">Under **Common Attachment Types filter**, select **On**, and then click **Save**.</span></span>


## <a name="phase-3-examine-the-security-dashboard"></a><span data-ttu-id="ae1a7-143">3 단계: 보안 대시보드 검사</span><span class="sxs-lookup"><span data-stu-id="ae1a7-143">Phase 3: Examine the security dashboard</span></span>

<span data-ttu-id="ae1a7-144">Microsoft 365의 위협 관리 기능을 사용 하면 조직의 데이터에 대 한 모바일 장치 액세스를 제어 및 관리 하 고, 데이터 손실 로부터 조직을 보호 하 고, 악성 소프트웨어 및 스팸 으로부터 인바운드 및 아웃 바운드 메시지를 보호 하는 데 도움을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae1a7-144">Threat management in Microsoft 365 can help you control and manage mobile device access to your organization's data, help protect your organization from data loss, and help protect inbound and outbound messages from malicious software and spam.</span></span> <span data-ttu-id="ae1a7-145">또한 위협 관리를 사용 하 여 도메인의 신뢰도를 보호 하 고 보낸 사람이 도메인에서 악의적으로 계정을 위장 하는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae1a7-145">You also use threat management to protect your domain's reputation and to determine whether or not senders are maliciously spoofing accounts from your domain.</span></span> 

<span data-ttu-id="ae1a7-146">보안 대시보드를 보려면:</span><span class="sxs-lookup"><span data-stu-id="ae1a7-146">To see the security dashboard:</span></span>

1. <span data-ttu-id="ae1a7-147">필요한 경우 [보안 & 준수 센터로](https://protection.office.com) 이동 하 여 전역 관리자 계정으로 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae1a7-147">If needed, go to the [Security & Compliance Center](https://protection.office.com) and sign in with your global administrator account.</span></span>

2. <span data-ttu-id="ae1a7-148">왼쪽 탐색 창의 **위협 관리**에서 **대시보드**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae1a7-148">In the left navigation pane, under **Threat management**, click **Dashboard**.</span></span>

<span data-ttu-id="ae1a7-149">대시보드의 모든 카드를 살펴보고 제공 된 정보를 숙지 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae1a7-149">Take a close look at all the cards on the dashboard to familiarize yourself with the information provided.</span></span>

<span data-ttu-id="ae1a7-150">자세한 내용은 [보안 대시보드](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-dashboard)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ae1a7-150">For more information, see [Security Dashboard](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-dashboard).</span></span>


## <a name="phase-4-examine-microsoft-secure-score"></a><span data-ttu-id="ae1a7-151">4 단계: Microsoft 보안 점수 조사</span><span class="sxs-lookup"><span data-stu-id="ae1a7-151">Phase 4: Examine Microsoft Secure Score</span></span>

<span data-ttu-id="ae1a7-152">Microsoft 보안 점수는 구독에서 사용할 수 있는 기능을 기준으로 현재 수준을 나타내는 숫자로, 보안 상황을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae1a7-152">Microsoft Secure Score shows your security posture as a number, which indicates your current level relative to the features that are available in your subscription.</span></span> <span data-ttu-id="ae1a7-153">또한 점수를 높이기 위해 수행할 수 있는 개선 작업 목록을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae1a7-153">It also gives you a list of improvement actions you can take to improve your score.</span></span>

1. <span data-ttu-id="ae1a7-154">브라우저에서 새 탭을 만들고 [Microsoft 365 보안 센터로](https://security.microsoft.com/)이동한 후 **보안 점수**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae1a7-154">Create a new tab in your browser and go to the [Microsoft 365 security center](https://security.microsoft.com/), and then click **Secure score**.</span></span>
2. <span data-ttu-id="ae1a7-155">**개요** 탭에서 현재 보안 점수를 확인 하 고, 유사한 라이선스 수를 포함 하는 전역 평균과 구독과 비교 하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="ae1a7-155">On the **Overview**  tab, note your current Secure Score and how it compares with the global average and subscriptions with a similar number of licenses.</span></span>
3. <span data-ttu-id="ae1a7-156">**향상 작업** 탭에서 점수를 증가 시키기 위해 수행할 수 있는 작업 목록을 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="ae1a7-156">On the **Improvement actions** tab, read through the list of actions you can take to increase your score.</span></span>

<span data-ttu-id="ae1a7-157">자세한 내용은 [Microsoft 보안 점수](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ae1a7-157">For more information, see [Microsoft Secure Score](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score).</span></span>

## <a name="next-steps"></a><span data-ttu-id="ae1a7-158">다음 단계</span><span class="sxs-lookup"><span data-stu-id="ae1a7-158">Next steps</span></span>

<span data-ttu-id="ae1a7-159">테스트 환경에서 추가 [정보 보호](m365-enterprise-test-lab-guides.md#information-protection) 기능에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="ae1a7-159">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="ae1a7-160">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ae1a7-160">See also</span></span>

[<span data-ttu-id="ae1a7-161">엔터프라이증용 Microsoft 365 테스트 랩 가이드</span><span class="sxs-lookup"><span data-stu-id="ae1a7-161">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="ae1a7-162">엔터프라이즈용 Microsoft 365 개요</span><span class="sxs-lookup"><span data-stu-id="ae1a7-162">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="ae1a7-163">엔터프라이즈 설명서에 대 한 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ae1a7-163">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
