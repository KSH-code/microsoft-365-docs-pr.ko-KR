---
title: 엔터프라이즈 Microsoft 365 환경의 Microsoft 365 보안 강화
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
description: 이 테스트 랩 가이드를 사용하여 엔터프라이즈 테스트 환경에 Microsoft 365 추가 보안 Microsoft 365 사용하도록 설정할 수 있습니다.
ms.openlocfilehash: d1bff8b736e5074f621a173d206f7c5f77841b25
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/25/2021
ms.locfileid: "51198354"
---
# <a name="increased-microsoft-365-security-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="84972-103">엔터프라이즈 Microsoft 365 환경의 Microsoft 365 보안 강화</span><span class="sxs-lookup"><span data-stu-id="84972-103">Increased Microsoft 365 security for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="84972-104">*이 테스트 랩 가이드는 엔터프라이즈 테스트 환경에 Microsoft 365 사용할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="84972-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="84972-105">이 문서의 지침에 따라 엔터프라이즈 테스트 환경의 보안 Microsoft 365 추가 Microsoft 365 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="84972-105">With the instructions in this article, you configure additional Microsoft 365 settings to increase security in your Microsoft 365 for enterprise test environment.</span></span>

![Microsoft 클라우드의 테스트 랩 가이드](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="84972-107">[여기](../downloads/Microsoft365EnterpriseTLGStack.pdf)를 클릭하여 Microsoft 365 Enterprise 테스트 랩 가이드 스택의 모든 문서에 대한 가상 맵을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84972-107">Click [here](../downloads/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="84972-108">1단계: 엔터프라이즈 테스트 Microsoft 365 사용자 환경 구축</span><span class="sxs-lookup"><span data-stu-id="84972-108">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="84972-109">최소 요구 사항과 Microsoft 365 경량 방식으로 강화된 보안만 구성하려면 [Lightweight base configuration의 지침을 따릅니다.](lightweight-base-configuration-microsoft-365-enterprise.md)</span><span class="sxs-lookup"><span data-stu-id="84972-109">If you just want to configure increased Microsoft 365 security in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="84972-110">시뮬레이트된 엔터프라이즈에서 Microsoft 365 보안 강화를 구성하려는 경우 통과 인증의 [지침을 따릅니다.](pass-through-auth-m365-ent-test-environment.md)</span><span class="sxs-lookup"><span data-stu-id="84972-110">If you want to configure increased Microsoft 365 security in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="84972-111">보안이 강화된 Microsoft 365 테스트 환경에는 시뮬레이트된 엔터프라이즈 테스트 환경이 필요하지 않습니다. 여기에는 인터넷에 연결된 시뮬레이트된 인트라넷과 AD DS(Active Directory 도메인 서비스) 포리스트에 대한 디렉터리 동기화가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="84972-111">Testing increased Microsoft 365 security does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="84972-112">여기서는 옵션으로 제공되어 자동화된 라이선싱 및 그룹 멤버 자격을 테스트하고 일반적인 조직을 나타내는 환경에서 실험해 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84972-112">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 

## <a name="phase-2-configure-increased-microsoft-365-security"></a><span data-ttu-id="84972-113">2단계: 보안 강화 Microsoft 365 구성</span><span class="sxs-lookup"><span data-stu-id="84972-113">Phase 2: Configure increased Microsoft 365 security</span></span>

<span data-ttu-id="84972-114">이 단계에서는 엔터프라이즈 테스트 환경에 Microsoft 365 보안 강화를 Microsoft 365 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84972-114">In this phase, you enable increased Microsoft 365 security for your Microsoft 365 for enterprise test environment.</span></span> <span data-ttu-id="84972-115">자세한 내용 및 설정은 보안 강화를 [위해 테넌트 구성을 참조하세요.](/office365/securitycompliance/tenant-wide-setup-for-increased-security)</span><span class="sxs-lookup"><span data-stu-id="84972-115">For additional details and settings, see [Configure your tenant for increased security](/office365/securitycompliance/tenant-wide-setup-for-increased-security).</span></span>

### <a name="configure-sharepoint-online-to-block-apps-that-dont-support-modern-authentication"></a><span data-ttu-id="84972-116">최신 SharePoint 지원하지 않는 앱을 차단하도록 SharePoint Online 구성</span><span class="sxs-lookup"><span data-stu-id="84972-116">Configure SharePoint Online to block apps that don't support modern authentication</span></span>

<span data-ttu-id="84972-117">최신 인증을 지원하지 않는 [](../security/office-365-security/microsoft-365-policies-configurations.md) 앱에는 ID 및 장치 액세스 구성을 적용할 수 없습니다. 이는 Microsoft 365 디지털 자산을 보호하는 데 중요한 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="84972-117">Apps that do not support modern authentication cannot have [identity and device access configurations](../security/office-365-security/microsoft-365-policies-configurations.md) applied to them, which is an important element of securing your Microsoft 365 subscription and its digital assets.</span></span> 

1. <span data-ttu-id="84972-118">Microsoft 365 관리 센터( )로 이동하고 전역 관리자 계정을 Microsoft 365 테스트 랩 구독에 [https://portal.microsoft.com](https://portal.microsoft.com) 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="84972-118">Go to the Microsoft 365 admin center ([https://portal.microsoft.com](https://portal.microsoft.com)) and sign in to your Microsoft 365 test lab subscription with your global administrator account.</span></span>
    
  - <span data-ttu-id="84972-119">간단한 테스트 환경을 사용하는 Microsoft 365 로컬 컴퓨터에서 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="84972-119">If you are using the lightweight Microsoft 365 test environment, sign in from your local computer.</span></span>
    
  - <span data-ttu-id="84972-120">시뮬레이트된 엔터프라이즈 Microsoft 365 환경을 사용하는 경우 Azure [Portal을](https://portal.azure.com) 사용하여 CLIENT1 가상 컴퓨터에 연결한 다음 CLIENT1에서 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="84972-120">If you are using the simulated enterprise Microsoft 365 test environment, use the [Azure portal](https://portal.azure.com) to connect to the CLIENT1 virtual machine, and then sign in from CLIENT1.</span></span>
 
2. <span data-ttu-id="84972-121">새 Microsoft 365 관리 센터 **탭의** 왼쪽  탐색 창에 있는 관리 센터에서 를 **SharePoint.**</span><span class="sxs-lookup"><span data-stu-id="84972-121">On the new **Microsoft 365 admin center** tab, under **Admin centers** in the left navigation pane, click **SharePoint**.</span></span>
3. <span data-ttu-id="84972-122">새 SharePoint **관리** 센터 탭에서 액세스 제어 **> 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="84972-122">On the new **SharePoint admin center** tab, click **Policies > Access control**.</span></span>
4. <span data-ttu-id="84972-123">최신 **인증을** 지원하지 않는 앱을 클릭하고 액세스 차단을 선택한 **다음** 저장을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="84972-123">Click **Apps that don't support modern authentication**, select **Block access**, and then click **Save**.</span></span>


### <a name="enable-defender-for-office-365-for-sharepoint-onedrive-for-business-and-microsoft-teams"></a><span data-ttu-id="84972-124">사용자, Office 365 및 SharePoint 및 비즈니스용 OneDrive Defender를 사용하도록 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="84972-124">Enable Defender for Office 365 for SharePoint, OneDrive for Business, and Microsoft Teams</span></span>

<span data-ttu-id="84972-125">조직에서 Office 365, SharePoint OneDrive Microsoft Teams 파일을 공유하지 못하게 조직을 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="84972-125">Defender for Office 365 for SharePoint, OneDrive, and Microsoft Teams protects your organization from inadvertently sharing malicious files.</span></span>

1. <span data-ttu-id="84972-126">보안 및 준수 [& 이동하고](https://protection.office.com) 전역 관리자 계정으로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="84972-126">Go to the [Security & Compliance Center](https://protection.office.com) and sign in with your global administrator account.</span></span>

2. <span data-ttu-id="84972-127">왼쪽 탐색 창의 **위협** 관리에서 정책 **을** 클릭한 다음 안전한 첨부 **파일을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="84972-127">In the left navigation pane, under **Threat management**, click **Policy**, and then click **Safe Attachments**.</span></span> 

3. <span data-ttu-id="84972-128">의 **파일 보호에서 SharePoint,** OneDrive 및 Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="84972-128">Under **Protect files in SharePoint, OneDrive, and Microsoft Teams**.</span></span> <span data-ttu-id="84972-129">에 **대해 ATP 켜기, SharePoint,** OneDrive 및 Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="84972-129">select **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams**.</span></span>

4. <span data-ttu-id="84972-130">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="84972-130">Click **Save**.</span></span>


### <a name="enable-anti-malware"></a><span data-ttu-id="84972-131">맬웨어 방지 사용</span><span class="sxs-lookup"><span data-stu-id="84972-131">Enable anti-malware</span></span>

<span data-ttu-id="84972-132">맬웨어는 바이러스 및 스파이웨어로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="84972-132">Malware is comprised of viruses and spyware.</span></span> <span data-ttu-id="84972-133">바이러스는 다른 프로그램 및 데이터를 감염시키며 컴퓨터 전체로 전파되어 감염시킬 프로그램을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="84972-133">Viruses infect other programs and data, and they spread throughout your computer looking for programs to infect.</span></span> <span data-ttu-id="84972-134">스파이웨어는 로그인 정보와 개인 데이터 등의 개인 정보를 수집하여 이를 맬웨어 작성자에게 보내는 맬웨어입니다.</span><span class="sxs-lookup"><span data-stu-id="84972-134">Spyware refers to malware that gathers your personal information, such as sign-in information and personal data, and sends it back to the malware author.</span></span> 

<span data-ttu-id="84972-135">Microsoft 365 맬웨어 및 스팸 필터링 기능이 내장되어 있으며 인바운드 및 아웃바운드 메시지를 악성 소프트웨어로부터 보호하고 스팸으로부터 보호하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="84972-135">Microsoft 365 has built-in malware and spam filtering capabilities that help protect inbound and outbound messages from malicious software and help protect you from spam.</span></span> <span data-ttu-id="84972-136">자세한 내용은 맬웨어 방지 [보호 & 스팸 방지를 참조하세요.](../security/office-365-security/anti-spam-and-anti-malware-protection.md)</span><span class="sxs-lookup"><span data-stu-id="84972-136">For more information, see [Anti-spam & anti-malware protection](../security/office-365-security/anti-spam-and-anti-malware-protection.md).</span></span>

<span data-ttu-id="84972-137">일반적인 첨부 파일 형식의 파일에 대해 맬웨어 방지 처리가 수행되도록 보장하려면</span><span class="sxs-lookup"><span data-stu-id="84972-137">To ensure that anti-malware processing is being performed on files with common attachment file types:</span></span>

1. <span data-ttu-id="84972-138">브라우저에서 뒤로 단추를 클릭하여 정책  페이지로 돌아오십시오.</span><span class="sxs-lookup"><span data-stu-id="84972-138">Click the back button on your browser to get back to the **Policy** page.</span></span>
2. <span data-ttu-id="84972-139">**맬웨어 방지 를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="84972-139">Click **Anti-malware**.</span></span>
3. <span data-ttu-id="84972-140">Default라는 정책을 두 번 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="84972-140">Double-click the policy named **Default**.</span></span>
4. <span data-ttu-id="84972-141">**맬웨어 방지 정책** 창에서 를 **설정.**</span><span class="sxs-lookup"><span data-stu-id="84972-141">In the **Anti-malware policy** window, click **Settings**.</span></span>
4. <span data-ttu-id="84972-142">일반 첨부 파일 형식  **필터에서** 을 선택하고 저장을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="84972-142">Under **Common Attachment Types filter**, select **On**, and then click **Save**.</span></span>


## <a name="phase-3-examine-the-security-dashboard"></a><span data-ttu-id="84972-143">3단계: 보안 대시보드 검사</span><span class="sxs-lookup"><span data-stu-id="84972-143">Phase 3: Examine the security dashboard</span></span>

<span data-ttu-id="84972-144">조직의 위협 Microsoft 365 관리하면 조직의 데이터에 대한 모바일 장치 액세스를 제어 및 관리하고, 데이터 손실로부터 조직을 보호하고, 악성 소프트웨어 및 스팸으로부터 인바운드 및 아웃바운드 메시지를 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84972-144">Threat management in Microsoft 365 can help you control and manage mobile device access to your organization's data, help protect your organization from data loss, and help protect inbound and outbound messages from malicious software and spam.</span></span> <span data-ttu-id="84972-145">또한 위협 관리를 사용하여 도메인의 평판을 보호하고 보낸 사람이 도메인의 계정을 악의적으로 스푸핑하는지 여부를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84972-145">You also use threat management to protect your domain's reputation and to determine whether or not senders are maliciously spoofing accounts from your domain.</span></span> 

<span data-ttu-id="84972-146">보안 대시보드를 표시하는 데 사용할 수 있는 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="84972-146">To see the security dashboard:</span></span>

1. <span data-ttu-id="84972-147">필요한 경우 보안 및 준수 [&](https://protection.office.com) 이동하여 전역 관리자 계정으로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="84972-147">If needed, go to the [Security & Compliance Center](https://protection.office.com) and sign in with your global administrator account.</span></span>

2. <span data-ttu-id="84972-148">왼쪽 탐색 창의 **위협** 관리에서 대시보드 를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="84972-148">In the left navigation pane, under **Threat management**, click **Dashboard**.</span></span>

<span data-ttu-id="84972-149">대시보드의 모든 카드를 살펴보고 제공된 정보를 익히세요.</span><span class="sxs-lookup"><span data-stu-id="84972-149">Take a close look at all the cards on the dashboard to familiarize yourself with the information provided.</span></span>

<span data-ttu-id="84972-150">자세한 내용은 보안 [대시보드를 참조하세요.](../security/office-365-security/security-dashboard.md)</span><span class="sxs-lookup"><span data-stu-id="84972-150">For more information, see [Security Dashboard](../security/office-365-security/security-dashboard.md).</span></span>


## <a name="phase-4-examine-microsoft-secure-score"></a><span data-ttu-id="84972-151">4단계: Microsoft 보안 점수 검사</span><span class="sxs-lookup"><span data-stu-id="84972-151">Phase 4: Examine Microsoft Secure Score</span></span>

<span data-ttu-id="84972-152">Microsoft 보안 점수는 구독에서 사용할 수 있는 기능을 상대로 현재 수준을 나타내는 숫자로 보안 상태 표시</span><span class="sxs-lookup"><span data-stu-id="84972-152">Microsoft Secure Score shows your security posture as a number, which indicates your current level relative to the features that are available in your subscription.</span></span> <span data-ttu-id="84972-153">또한 점수를 개선하기 위해 수행할 수 있는 개선 작업 목록도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84972-153">It also gives you a list of improvement actions you can take to improve your score.</span></span>

1. <span data-ttu-id="84972-154">브라우저에서 새 탭을 만들고 Microsoft 365 센터로 이동한 다음 보안 점수 [를](https://security.microsoft.com/) **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="84972-154">Create a new tab in your browser and go to the [Microsoft 365 security center](https://security.microsoft.com/), and then click **Secure score**.</span></span>
2. <span data-ttu-id="84972-155">개요 **탭에서**  현재 보안 점수와 전역 평균 및 라이선스 수가 비슷한 구독과 비교하는 방법을 기록해 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="84972-155">On the **Overview**  tab, note your current Secure Score and how it compares with the global average and subscriptions with a similar number of licenses.</span></span>
3. <span data-ttu-id="84972-156">개선 **작업 탭에서** 점수를 높이기 위해 수행할 수 있는 작업 목록을 읽어 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="84972-156">On the **Improvement actions** tab, read through the list of actions you can take to increase your score.</span></span>

<span data-ttu-id="84972-157">자세한 내용은 Microsoft 보안 점수를 [참조하세요.](../security/defender/microsoft-secure-score.md)</span><span class="sxs-lookup"><span data-stu-id="84972-157">For more information, see [Microsoft Secure Score](../security/defender/microsoft-secure-score.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="84972-158">다음 단계</span><span class="sxs-lookup"><span data-stu-id="84972-158">Next steps</span></span>

<span data-ttu-id="84972-159">테스트 환경의 추가 [정보](m365-enterprise-test-lab-guides.md#information-protection) 보호 기능을 살펴보아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="84972-159">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="84972-160">참고 항목</span><span class="sxs-lookup"><span data-stu-id="84972-160">See also</span></span>

[<span data-ttu-id="84972-161">엔터프라이증용 Microsoft 365 테스트 랩 가이드</span><span class="sxs-lookup"><span data-stu-id="84972-161">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="84972-162">엔터프라이즈용 Microsoft 365 개요</span><span class="sxs-lookup"><span data-stu-id="84972-162">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="84972-163">기업용 Microsoft 365 설명서</span><span class="sxs-lookup"><span data-stu-id="84972-163">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)