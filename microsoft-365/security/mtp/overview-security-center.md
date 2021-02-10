---
title: Microsoft 365 보안 센터 개요
description: MDO(Microsoft Defender for Office 365) 및 MDE(Microsoft Defender for Endpoint)를 MDI(Microsoft Defender for Identity) 및 MCAS(Microsoft Cloud App Security)와 결합하여 Microsoft 365 보안 센터의 이점 이 문서에서는 관리자를 위한 Microsoft 365 보안 센터에 대해 간략하게 설명했습니다.
keywords: 보안, 맬웨어, Microsoft 365, M365, 보안 센터, 모니터링, 보고서, ID, 데이터, 장치, 앱
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.date: 02/02/2021
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
search.appverid: met150
ms.custom: seo-marvel-jun2020
ms.technology: m365d
ms.openlocfilehash: 89e72d703bd70647d6c2b00732315b8e5f015cc7
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/09/2021
ms.locfileid: "50167221"
---
# <a name="the-unified-microsoft-365-security-center-overview"></a><span data-ttu-id="2a490-105">통합 Microsoft 365 보안 센터 개요</span><span class="sxs-lookup"><span data-stu-id="2a490-105">The unified Microsoft 365 security center overview</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[!INCLUDE [Prerelease](../includes/prerelease.md)]

<span data-ttu-id="2a490-106">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="2a490-106">**Applies to:**</span></span>

- [<span data-ttu-id="2a490-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2a490-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)
- [<span data-ttu-id="2a490-108">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="2a490-108">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="2a490-109">Office 365용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="2a490-109">Microsoft Defender for Office 365</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)

> <span data-ttu-id="2a490-110">Microsoft 365 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="2a490-110">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="2a490-111">랩 [환경에서 평가하거나](https://aka.ms/mtp-trial-lab) 프로덕션 환경에서 파일럿 프로젝트를 [실행할 수 있습니다.](https://aka.ms/m365d-pilotplaybook)</span><span class="sxs-lookup"><span data-stu-id="2a490-111">You can [evaluate it in a lab environment](https://aka.ms/mtp-trial-lab) or [run your pilot project in production](https://aka.ms/m365d-pilotplaybook).</span></span>

<span data-ttu-id="2a490-112">향상된 **Microsoft 365** 보안 센터()는 중앙 포털에서 전자 메일, 공동 작업, ID 및 장치 위협에 대한 보호, 검색, 조사 및 응답을 [https://security.microsoft.com](https://security.microsoft.com) 결합합니다.    </span><span class="sxs-lookup"><span data-stu-id="2a490-112">The improved **Microsoft 365 security center** ([https://security.microsoft.com](https://security.microsoft.com)) combines protection, detection, investigation, and response to *email*, *collaboration*, *identity*, and *device* threats, in a central portal.</span></span>

<span data-ttu-id="2a490-113">Microsoft 365 보안 센터는 Microsoft Defender 보안 센터 및 Office 365 보안 및 규정 준수 센터와 같은 기존 Microsoft 보안 포털의 & 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2a490-113">Microsoft 365 security center brings together functionality from existing Microsoft security portals, like Microsoft Defender Security Center and the Office 365 Security & Compliance center.</span></span> <span data-ttu-id="2a490-114">보안 센터에서는 정보에 빠르게 액세스하고, 더 간단한 레이아웃을 사용하며, 관련 정보를 함께 사용하여 보다 쉽게 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a490-114">The security center emphasizes quick access to information, simpler layouts, and bringing related information together for easier use.</span></span> <span data-ttu-id="2a490-115">이 센터에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a490-115">This center includes:</span></span>

- <span data-ttu-id="2a490-116">**[Office 365용 Microsoft Defender](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)** Office 365용 Microsoft Defender는 조직이 전자 메일 및 Office 365 리소스를 보호하기 위해 방지, 검색, 조사 및 헌팅 기능 집합을 통해 엔터프라이즈를 보호하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a490-116">**[Microsoft Defender for Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)** Microsoft Defender for Office 365 helps organizations secure their enterprise with a set of prevention, detection, investigation and hunting features to protect email, and Office 365 resources.</span></span>
- <span data-ttu-id="2a490-117">**[끝점용 Microsoft Defender는](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)** 조직의 장치에 대한 예방 보호, 위반 후 감지, 자동화된 조사 및 대응을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2a490-117">**[Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)** delivers preventative protection, post-breach detection, automated investigation, and response for devices in your organization.</span></span>
- <span data-ttu-id="2a490-118">**[Microsoft 365 Defender는](microsoft-threat-protection.md)** Microsoft 365 보안 포트폴리오를 활용하여 도메인 전체의 위협 데이터를 자동으로 분석하고 단일 대시보드에 대한 공격의 그림을 작성하는 Microsoft의 XDR(Extended *Detection and Response)* 솔루션의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="2a490-118">**[Microsoft 365 Defender](microsoft-threat-protection.md)** is part of Microsoft’s *Extended Detection and Response* (XDR) solution that leverages the Microsoft 365 security portfolio to automatically analyze threat data across domains, and build a picture of an attack on a single dashboard.</span></span>

<span data-ttu-id="2a490-119">Office 365 보안 및 준수 센터 또는 Microsoft Defender 보안 센터에서 변경된 & 필요한 경우 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2a490-119">If you need information about what's changed from the Office 365 Security & Compliance center or the Microsoft Defender Security Center, see:</span></span>

- [<span data-ttu-id="2a490-120">Microsoft 365 보안 센터의 Office 365용 Defender</span><span class="sxs-lookup"><span data-stu-id="2a490-120">Defender for Office 365 in the Microsoft 365 security center</span></span>](microsoft-365-security-center-mdo.md)
- [<span data-ttu-id="2a490-121">Microsoft 365 보안 센터의 끝점용 Defender</span><span class="sxs-lookup"><span data-stu-id="2a490-121">Defender for Endpoint in the Microsoft 365 security center</span></span>](microsoft-365-security-center-mde.md)

## <a name="what-to-expect"></a><span data-ttu-id="2a490-122">예상할 일</span><span class="sxs-lookup"><span data-stu-id="2a490-122">What to expect</span></span>

<span data-ttu-id="2a490-123">Office 365 보안 및 준수 센터(protection.office.com) 및 Microsoft Defender 보안 센터(securitycenter.microsoft.com)에서 사용하는 모든 보안 콘텐츠는 *이제 Microsoft 365* 보안 센터에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a490-123">All the security content that you use in the Office 365 Security and Compliance Center (protection.office.com) and the Microsoft Defender security center (securitycenter.microsoft.com) can now be found in the *Microsoft 365 security center*.</span></span>

<span data-ttu-id="2a490-124">Microsoft 365 보안 센터는 보안 팀이 서로 다른 워크로드의 신호를 통합된 단일 환경으로 통합하여 공격을 조사하고 대응할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a490-124">Microsoft 365 security center helps security teams investigate and respond to attacks by brining in signals from different workloads into a single, unified experiences:</span></span>

- <span data-ttu-id="2a490-125">인시던트 & 경고</span><span class="sxs-lookup"><span data-stu-id="2a490-125">Incidents & alerts</span></span>
- <span data-ttu-id="2a490-126">헌팅</span><span class="sxs-lookup"><span data-stu-id="2a490-126">Hunting</span></span>
- <span data-ttu-id="2a490-127">알림 센터 </span><span class="sxs-lookup"><span data-stu-id="2a490-127">Action Center</span></span>
- <span data-ttu-id="2a490-128">위협 분석</span><span class="sxs-lookup"><span data-stu-id="2a490-128">Threat analytics</span></span>

<span data-ttu-id="2a490-129">Microsoft 365 보안 센터는 Office 365용 Microsoft Defender와 끝점용 Microsoft Defender를 병합할 때 단합, 명확성 및 공통 목표를 강조합니다. </span><span class="sxs-lookup"><span data-stu-id="2a490-129">The Microsoft 365 security center emphasizes *unity, clarity, and common goals* as it merges Microsoft Defender for Office 365 and Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="2a490-130">병합은 아래에 나열된 우선 순위를 기반으로 하여 각 보안 제품군이 조합에 가져온 기능을 만족하지 않고 만들어 졌다.</span><span class="sxs-lookup"><span data-stu-id="2a490-130">The merge was based on the priorities listed below, and made without sacrificing the capabilities that each security suite brought to the combination:</span></span>

- <span data-ttu-id="2a490-131">일반적인 구성 요소</span><span class="sxs-lookup"><span data-stu-id="2a490-131">common building blocks</span></span>
- <span data-ttu-id="2a490-132">일반적인 용어</span><span class="sxs-lookup"><span data-stu-id="2a490-132">common terminology</span></span>
- <span data-ttu-id="2a490-133">일반 엔터티</span><span class="sxs-lookup"><span data-stu-id="2a490-133">common entities</span></span>
- <span data-ttu-id="2a490-134">다른 워크로드와의 기능 패리티</span><span class="sxs-lookup"><span data-stu-id="2a490-134">feature parity with other workloads</span></span>

## <a name="unified-investigations"></a><span data-ttu-id="2a490-135">통합 조사</span><span class="sxs-lookup"><span data-stu-id="2a490-135">Unified investigations</span></span>

<span data-ttu-id="2a490-136">보안 센터를 간소화하면 Microsoft 365 조직 전체의 인시던트 조사를 위한 단일 창이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a490-136">Streamlining security centers creates a single pane for investigating any incidents across a Microsoft 365 organization.</span></span> <span data-ttu-id="2a490-137">기본 예로는  Microsoft 365 보안 센터를 빠르게 실행하기 위한 인시던트 노드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a490-137">A primary example is the **Incidents** node on the quick launch of the Microsoft 365 security center.</span></span>

:::image type="content" source="../../media/converged-incidents-2.png.png" alt-text="MDO의 인시던트 페이지입니다.":::

<span data-ttu-id="2a490-139">예를 들어 심각도 높은 인시던트  이름을 두 번 클릭하면 수렴 센터의 이점을 보여줄 수 있는 페이지로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a490-139">As an example, double-clicking on an incident name with **High** severity brings you to a page that demonstrates the advantage of converging centers.</span></span>

![여러 끝점에서 권한 에스컬레이터가 관련된 다단계 인시던트. 영향을 16개 디바이스와 9명에게 영향을 미치는 사용자를 보여 줄 수 있습니다.](../../media/converged-incident-info-3.png)

> [!TIP]
> <span data-ttu-id="2a490-141">수렴형 사용자  탭은 문의를 시작하는 데 좋은 장소입니다.</span><span class="sxs-lookup"><span data-stu-id="2a490-141">The converged **Users** tab is a good place to begin your inquiries.</span></span> <span data-ttu-id="2a490-142">이 단일 페이지는 수렴된 워크로드(이를 활용하는 경우 끝점용 Microsoft Defender, ID용 Microsoft Defender 및 MCAS)의 사용자 및 다양한 원본(예: On-premises Active Directory, Azure Active Directory, 동기화된, 로컬 및 타사 사용자)의 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2a490-142">This single page surfaces information for users from converged workloads (Microsoft Defender for Endpoint, Microsoft Defender for Identity, and MCAS, if you leverage it) and a range of sources such as on-premises Active Directory, Azure Active Directory, synced, local, and third-party users.</span></span> <span data-ttu-id="2a490-143">새 사용자 [경험에 대해 자세히 알아보는 것이 있습니다.](investigate-users.md)</span><span class="sxs-lookup"><span data-stu-id="2a490-143">Learn more about [the new Users experience](investigate-users.md).</span></span>

<span data-ttu-id="2a490-144">인시던트 정보에는 영향을 받는 사서함 외에 사용자/ID 관련 및 위험에 노출된 장치가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a490-144">Incident information shows user/identity specifics and at-risk devices, beside affected mailboxes.</span></span> <span data-ttu-id="2a490-145">또한 모든 조사 **정보** 및 수집된 증거와 **관련이 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="2a490-145">It also relates any **Investigation information** and gathered **Evidence**.</span></span> <span data-ttu-id="2a490-146">이렇게 하면 관리자와 보안 운영 팀이 위험에 노출된 사용자 및 사서함으로 한 번의 고위험 경고에서 더 쉽게 피벗할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a490-146">This makes it easier for admins and security operation teams to pivot from one high-risk alert to the affected users and mailboxes.</span></span> <span data-ttu-id="2a490-147">이 페이지의 **맨** 위에 있는 인시던트 탭에는 이 단일 위치에서 사용할 수 있는 다른 주요 보안 피벗이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a490-147">Looking at the **Incident** tabs at the top of this page, there are other key security pivots available from this single location.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2a490-148">특정 인시던트에 대한 페이지 위쪽에는 **요약,** **경고,** 장치, **사용자,** **사서함,** 조사 및  증거 탭이 표시됩니다.  </span><span class="sxs-lookup"><span data-stu-id="2a490-148">Along the top of any page for a specific Incident, you'll see the **Summary**, **Alerts**, **Devices**, **Users**, **Mailboxes**, **Investigations**, and **Evidence** tabs.</span></span>

<span data-ttu-id="2a490-149">조사를 **선택하면** 진행 중인 분석 그래픽이 있는 페이지가 열리며 수정을 위한 상태(예: 승인 보류 **중)가** 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a490-149">Selecting **Investigations** opens  a page that features a graphic of the analysis taking place and lists a status (such as **pending approval**) for remediation.</span></span> <span data-ttu-id="2a490-150">작업 환경에서 특정 인시던트 선택, 이러한 탭으로 드릴다운 및 다양한 종류의 위협에 대한 프로필을 작성하는 방법을 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="2a490-150">Take time to select specific incidents in your environment, drill down into these tabs, and practice building a profile for different kinds of threats.</span></span> <span data-ttu-id="2a490-151">익숙은 이후의 모든 압박 조사에 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a490-151">Familiarity will benefit any later pressing investigations.</span></span>

## <a name="improved-processes"></a><span data-ttu-id="2a490-152">향상된 프로세스</span><span class="sxs-lookup"><span data-stu-id="2a490-152">Improved processes</span></span>

<span data-ttu-id="2a490-153">공용 컨트롤과 콘텐츠가 같은 장소에 표시되거나 한 데이터 피드로 압축되어 쉽게 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a490-153">Common controls and content either appear in the same place, or are condensed into one feed of data making it easier to find.</span></span> <span data-ttu-id="2a490-154">예를 들어 통합 설정이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a490-154">For example, unified settings.</span></span>

### <a name="unified-settings"></a><span data-ttu-id="2a490-155">통합 설정</span><span class="sxs-lookup"><span data-stu-id="2a490-155">Unified settings</span></span>

!['역할'을 클릭하고 일반 설정, 사용 권한, API 및 규칙이 포함된 설정 페이지를 열했습니다.](../../media/converged-add-role-9.png)

### <a name="permissions--roles"></a><span data-ttu-id="2a490-159">역할에 & 사용 권한</span><span class="sxs-lookup"><span data-stu-id="2a490-159">Permissions & roles</span></span>

![사용 &, 역할 및 장치 그룹에서 끝점 역할을 & 역할 페이지를 참조하세요.](../../media/converged-roles-5.png)

 <span data-ttu-id="2a490-161">Microsoft 365 보안 센터에 액세스하는 것은 Azure Active Directory 전역 역할 또는 사용자 지정 역할을 사용하여 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a490-161">Access the Microsoft 365 security center is configured with Azure Active Directory global roles or by using custom roles.</span></span> <span data-ttu-id="2a490-162">끝점용 Defender에 대한 자세한 내용은 Microsoft Defender 보안 센터에 대한 사용자 액세스 [할당을 참조합니다.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/assign-portal-access)</span><span class="sxs-lookup"><span data-stu-id="2a490-162">For Defender for Endpoint, see [Assign user access to Microsoft Defender Security Center](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/assign-portal-access).</span></span> <span data-ttu-id="2a490-163">Office 365용 Defender의 경우 Microsoft 365 규정 준수 센터 및 [Microsoft 365](../office-365-security/permissions-microsoft-365-compliance-security.md)보안 센터의 사용 권한을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="2a490-163">For Defender for Office 365, see [Permissions in the Microsoft 365 compliance center and Microsoft 365 security center](../office-365-security/permissions-microsoft-365-compliance-security.md).</span></span>

- <span data-ttu-id="2a490-164">[Microsoft 365 Defender에](mtp-permissions.md) 대한 액세스를 관리하는 방법에 대해 자세히 알아보시고</span><span class="sxs-lookup"><span data-stu-id="2a490-164">Learn more about how to [manage access to Microsoft 365 Defender](mtp-permissions.md)</span></span>
- <span data-ttu-id="2a490-165">Microsoft 365 보안 센터에서 사용자 지정 역할을 만드는 방법에 대한 자세한 정보 [](custom-roles.md)</span><span class="sxs-lookup"><span data-stu-id="2a490-165">Learn more about how to [create custom roles](custom-roles.md) in Microsoft 365 security center</span></span>

### <a name="integrated-reports"></a><span data-ttu-id="2a490-166">통합 보고서</span><span class="sxs-lookup"><span data-stu-id="2a490-166">Integrated reports</span></span>

<span data-ttu-id="2a490-167">보고서는 Microsoft 365 보안 센터에서도 통합됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a490-167">Reports are also unified in the Microsoft 365 security center.</span></span> <span data-ttu-id="2a490-168">관리자는 일반 보안 보고서로 시작하여 끝점, 전자 메일 및 공동 작업과 관련한 특정 & 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a490-168">Admins can start with a general security report, and branch into specific reports about endpoints, email & collaboration.</span></span> <span data-ttu-id="2a490-169">여기에 있는 링크는 작업 구성에 따라 동적으로 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a490-169">The links here are dynamically generated based upon workload configuration.</span></span>

### <a name="quickly-view-your-microsoft-365-environment"></a><span data-ttu-id="2a490-170">Microsoft 365 환경 빠르게 보기</span><span class="sxs-lookup"><span data-stu-id="2a490-170">Quickly view your Microsoft 365 environment</span></span>

<span data-ttu-id="2a490-171">홈 **페이지에는** 보안 팀이 필요로 하는 많은 공통 카드가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a490-171">The **Home** page shows many of the common cards that security teams need.</span></span> <span data-ttu-id="2a490-172">카드와 데이터의 구성은 사용자 역할에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="2a490-172">The composition of cards and data is dependent on the user role.</span></span> <span data-ttu-id="2a490-173">Microsoft 365 보안 센터는 역할 기반 액세스 제어를 사용하기 때문에 다양한 역할은 매일의 작업에서 더 의미 있는 카드를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a490-173">Because the Microsoft 365 security center uses role-based access control, different roles will see cards that are more meaningful to their day to day jobs.</span></span>  

<span data-ttu-id="2a490-174">이 정보를 한눈에 확인하면 조직의 최신 활동을 유지하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a490-174">This at-a-glance information helps you keep up with the latest activities in your organization.</span></span> <span data-ttu-id="2a490-175">Microsoft 365 보안 센터는 다양한 소스의 신호를 모아 Microsoft 365 환경의 전체적인 보기를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2a490-175">The Microsoft 365 security center brings together signals from different sources to present a holistic view of your Microsoft 365 environment.</span></span>

<span data-ttu-id="2a490-176">카드는 다음 범주로 분류됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a490-176">The cards fall into these categories:</span></span>

- <span data-ttu-id="2a490-177">**ID**- 조직의 ID를 모니터링하고 의심스거나 위험한 동작을 추적합니다.</span><span class="sxs-lookup"><span data-stu-id="2a490-177">**Identities**- Monitor the identities in your organization and keep track of suspicious or risky behaviors.</span></span> <span data-ttu-id="2a490-178">[ID 보호에 대해 자세히 알아보습니다.](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection)</span><span class="sxs-lookup"><span data-stu-id="2a490-178">[Learn more about identity protection](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection).</span></span>
- <span data-ttu-id="2a490-179">**데이터** - 무단 데이터 공개로 이어질 수 있는 사용자 활동을 추적하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a490-179">**Data** - Help track user activity that could lead to unauthorized data disclosure.</span></span>
- <span data-ttu-id="2a490-180">**장치** - 장치에서 경고, 위반 활동 및 기타 위협에 대한 최신 정보를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="2a490-180">**Devices** - Get up-to-date information on alerts, breach activity, and other threats on your devices.</span></span>
- <span data-ttu-id="2a490-181">**앱** - 조직에서 클라우드 앱이 어떻게 사용되는지 파악합니다.</span><span class="sxs-lookup"><span data-stu-id="2a490-181">**Apps** - Gain insight into how cloud apps are being used in your organization.</span></span> <span data-ttu-id="2a490-182">[Cloud App Security 검색된 앱에 대해 자세히 알아보습니다.](https://docs.microsoft.com/cloud-app-security/discovered-apps)</span><span class="sxs-lookup"><span data-stu-id="2a490-182">[Learn more about Cloud App Security discovered apps](https://docs.microsoft.com/cloud-app-security/discovered-apps).</span></span>

## <a name="threat-analytics-with-better-data-coverage"></a><span data-ttu-id="2a490-183">더 나은 데이터 범위를 제공하는 위협 분석</span><span class="sxs-lookup"><span data-stu-id="2a490-183">Threat analytics with better data coverage</span></span>
<span data-ttu-id="2a490-184">다음 Microsoft 365 Defender 위협 분석 통합 환경을 사용하여 새로운 위협을 추적하고 대응합니다.</span><span class="sxs-lookup"><span data-stu-id="2a490-184">Track and respond to emerging threats with the following Microsoft 365 Defender threat analytics integrated experience:</span></span>

- <span data-ttu-id="2a490-185">엔드포인트용 Microsoft Defender와 Office 365용 Microsoft Defender 사이의 데이터 범위가 향상되어 인시던트 관리, 자동 조사, 수정 및 사전 대응 또는 사후 위협 헌팅이 가능해지며,</span><span class="sxs-lookup"><span data-stu-id="2a490-185">Better data coverage between Microsoft Defender for Endpoint and Microsoft Defender for Office 365, making combined incident management, automatic investigation, remediation, and proactive or reactive threat hunting across-domain possible.</span></span> 
- <span data-ttu-id="2a490-186">끝점용 Microsoft Defender에서 이미 사용할 수 있는 끝점 데이터 외에도 Office 365용 Microsoft Defender의 전자 메일 관련 검색 및 완화 기능</span><span class="sxs-lookup"><span data-stu-id="2a490-186">Email-related detections and mitigations from Microsoft Defender for Office 365, in addition to the endpoint data already available from Microsoft Defender for Endpoint.</span></span>
- <span data-ttu-id="2a490-187">경고를 엔드포인트용 Microsoft Defender 및 Office 365용 Microsoft Defender에서 종합적인 공격 사례로 집계하여 작업 큐를 줄이고 조사를 단순화하고 속도를 향상하는 위협 관련 인시던트 보기입니다.</span><span class="sxs-lookup"><span data-stu-id="2a490-187">A view of threat-related incidents which aggregate alerts into end-to-end attack stories across Microsoft Defender for Endpoint and Microsoft Defender for Office 365 to reduce the work queue, as well as simplify and speed up your investigation.</span></span>
- <span data-ttu-id="2a490-188">Microsoft 365 Defender 솔루션에서 공격을 감지하고 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="2a490-188">Attack attempts detected and blocked by Microsoft 365 Defender solutions.</span></span> <span data-ttu-id="2a490-189">추가 노출 위험을 완화하고 탄력을 높이는 예방 조치를 구동하는 데 사용할 수 있는 데이터도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a490-189">There's also data that you can use to drive preventive actions that mitigate the risk of further exposure and increase resilience.</span></span> 
- <span data-ttu-id="2a490-190">보고서에 집중하고 조사하고 보고서에서 활용하기 위해 데이터를 빠르게 식별할 수 있도록 스포트라이트에 실행 가능한 정보를 저장하는 향상된 디자인입니다.</span><span class="sxs-lookup"><span data-stu-id="2a490-190">Enhanced design that puts actionable information in the spotlight to help you  quickly identify data to urgently focus on, investigate, and leverage from the reports.</span></span>

## <a name="a-centralized-learning-hub"></a><span data-ttu-id="2a490-191">중앙 집중식 학습 허브</span><span class="sxs-lookup"><span data-stu-id="2a490-191">A centralized Learning Hub</span></span>

<span data-ttu-id="2a490-192">Microsoft 365 보안 센터에는 Microsoft 보안 블로그, YouTube의 Microsoft 보안 커뮤니티 및 공식 문서와 같은 리소스의 공식 지침을 버블업하는 학습 허브가 docs.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="2a490-192">The Microsoft 365 security center includes a learning hub that bubbles up official guidance from resources such as the Microsoft security blog, the Microsoft security community on YouTube, and the official documentation at docs.microsoft.com.</span></span>

<span data-ttu-id="2a490-193">학습 허브 내에서 전자 메일 & 공동 작업(Office 365 또는 MDO용 Microsoft Defender) 지침은 Endpoint(Endpoint 또는 MDE용 Microsoft Defender) 및 Microsoft 365 Defender 학습 리소스와 함께 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a490-193">Inside the learning hub, Email & Collaboration (Microsoft Defender for Office 365 or MDO) guidance is side-by-side with Endpoint (Microsoft Defender for Endpoint or MDE), and Microsoft 365 Defender learning resources.</span></span>

<span data-ttu-id="2a490-194">학습 허브는 "Microsoft 365 Defender를 사용하여 조사하는 방법"과 같은 주제에 대해 구성한 학습 경로로 열립니다.</span><span class="sxs-lookup"><span data-stu-id="2a490-194">The learning hub opens with Learning paths organized around topics such as “How to Investigate Using Microsoft 365 Defender?”</span></span> <span data-ttu-id="2a490-195">"Microsoft Defender for Office 365 모범 사례".</span><span class="sxs-lookup"><span data-stu-id="2a490-195">and “Microsoft Defender for Office 365 Best Practices”.</span></span> <span data-ttu-id="2a490-196">이 섹션은 현재 Microsoft 내부의 보안 제품 그룹에서 큐레이터합니다.</span><span class="sxs-lookup"><span data-stu-id="2a490-196">This section is currently curated by the security Product Group inside Microsoft.</span></span> <span data-ttu-id="2a490-197">각 학습 경로는 개념을 통과하는 데 소요되는 시간을 반영합니다.</span><span class="sxs-lookup"><span data-stu-id="2a490-197">Each Learning path reflects a projected time it takes to get through the concepts.</span></span> <span data-ttu-id="2a490-198">예를 들어 'Office 365용 Microsoft Defender 사용자 계정이 손상된 경우 취할 단계'는 8분 정도 걸릴 것으로 예정된 것이고 중요한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2a490-198">For example 'Steps to take when a Microsoft Defender for Office 365 user account is compromised' is projected to take 8 minutes, and is valuable learning on the fly.</span></span>

<span data-ttu-id="2a490-199">콘텐츠를 클릭한 후 이 사이트를 책갈피로 지정하고 책갈피를 '보안' 또는 '중요' 폴더로 구성하는 것이 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a490-199">After clicking through to the content, it may be useful to bookmark this site and organize bookmarks into a 'Security' or 'Critical' folder.</span></span> <span data-ttu-id="2a490-200">모든 학습 경로를 보려면 주 패널에서 모든 링크 표시를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2a490-200">To see all Learning paths, click the Show all link in the main panel.</span></span>

> [!NOTE]
> <span data-ttu-id="2a490-201">제품(현재  Microsoft 365 Defender, 끝점용 Microsoft Defender 및 Office 365용 Microsoft Defender) 중 선택할 수 있는 Microsoft 365 보안 센터 학습 허브 위쪽에 유용한 필터가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a490-201">There are helpful **filters** along the top of the Microsoft 365 security center learning hub that will let you choose between products (currently Microsoft 365 Defender, Microsoft Defender for Endpoint, and Microsoft Defender for Office 365).</span></span> <span data-ttu-id="2a490-202">각 섹션에 대한 학습 리소스의 수가 나열되어 있으며, 학습자는 교육 및 학습을 위해 준비된 리소스의 수를 추적하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a490-202">Notice that the number of learning resources for each section is listed, which can help learners keep track of how many resources they have at hand for training and learning.</span></span>
>
> <span data-ttu-id="2a490-203">제품 필터, 현재 항목, 리소스 유형(비디오에서 웨비나로), 보안 영역, 보안 역할 및 제품 기능에 대한 익숙하거나 경험 수준이 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a490-203">Along with the Product filter, current topics, types of resources (from videos to webinars), levels of familiarity or experience with security areas, security roles, and product features are listed.</span></span>

## <a name="send-us-your-feedback"></a><span data-ttu-id="2a490-204">피드백 보내기</span><span class="sxs-lookup"><span data-stu-id="2a490-204">Send us your feedback</span></span>

<span data-ttu-id="2a490-205">사용자 의견이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="2a490-205">We need your feedback.</span></span> <span data-ttu-id="2a490-206">We're always looking to improve, so if there's something you're like to see, [send us your Microsoft 365 Defender feedback.](https://www.microsoft.com/videoplayer/embed/RE4K5Ci)</span><span class="sxs-lookup"><span data-stu-id="2a490-206">We're always looking to improve, so if there's something you'd like to see, [send us your Microsoft 365 Defender feedback](https://www.microsoft.com/videoplayer/embed/RE4K5Ci).</span></span>

<span data-ttu-id="2a490-207">이 문서에서 피드백을 남길 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a490-207">You can also leave feedback from this article.</span></span> <span data-ttu-id="2a490-208">'제출 및 피드백 보기'의 끝에 있는 '피드백' 섹션에서 옵션은 이 제품 *또는* *이 페이지입니다.*</span><span class="sxs-lookup"><span data-stu-id="2a490-208">In the 'Feedback' section at the end under 'Submit and view feedback for', the options are *This product*, or *This page*.</span></span>

<span data-ttu-id="2a490-209">제품 **피드백에 이 제품** *단추를* 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="2a490-209">Use the **This product** button for *product* feedback:</span></span>

1. <span data-ttu-id="2a490-210">문서 *아래쪽에서* 이 제품을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2a490-210">Select *This product* at the bottom of the article.</span></span>
    1. <span data-ttu-id="2a490-211">단추를 마우스 오른쪽 단추로 클릭하고 이러한 길안을 계속 읽으려면 '새 탭에서 열기'를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2a490-211">Right-click the button and 'Open in a new tab' if you want to keep reading these directions.</span></span>
2. <span data-ttu-id="2a490-212">그러면 **UserVoice** 포럼으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="2a490-212">This will navigate to the **UserVoice forum**.</span></span>
3. <span data-ttu-id="2a490-213">다음 두 가지 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a490-213">You have 2 options:</span></span>
    1. <span data-ttu-id="2a490-214">텍스트 상자까지 아래로 스크롤하여 *Office 365에서* 규정 준수를 개선하거나 사용자를 더 잘 보호할 수 있나요? *Microsoft 365* 보안 센터에서 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="2a490-214">Scroll down to the text box *How can we improve compliance or protect your users better in Office 365?* and paste in *Microsoft 365 security center*.</span></span> <span data-ttu-id="2a490-215">결과에서 사용자와 같은 아이디어를 검색하여 투표하거나 새 아이디어 게시 **단추를 사용할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="2a490-215">You can search the results for an idea like yours and up-vote it, or use the button for **Post a new idea**.</span></span>
    1. <span data-ttu-id="2a490-216">이 문제가 이미 보고된 것으로 생각되고 해당 프로필을 투표(또는 투표)로  올리고 싶은 경우 UserVoice 오른쪽의 피드백 보내기 상자를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="2a490-216">If you feel certain this issue is already reported, and want to raise its profile with a vote (or votes), use the *Give Feedback* box on the right side of UserVoice.</span></span> <span data-ttu-id="2a490-217">Microsoft *365* 보안 센터를 검색하고, 문제를 **찾고,** 투표 단추를 사용하여 상태를 올렸다.</span><span class="sxs-lookup"><span data-stu-id="2a490-217">Search for *Microsoft 365 security center*, **find the issue, and use the vote button** to raise its status.</span></span>

<span data-ttu-id="2a490-218">이 *페이지를 사용하여* 문서 자체에 대한 피드백을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2a490-218">Use *This page* for feedback on the article itself.</span></span> <span data-ttu-id="2a490-219">사용자 의견을 보내 주셔서 감사합니다.</span><span class="sxs-lookup"><span data-stu-id="2a490-219">Thanks for your feedback.</span></span> <span data-ttu-id="2a490-220">음성은 제품을 개선하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a490-220">Your voice helps us improve products.</span></span>

### <a name="explore-what-the-security-center-has-to-offer"></a><span data-ttu-id="2a490-221">보안 센터에서 제공하는 것을 살펴보기</span><span class="sxs-lookup"><span data-stu-id="2a490-221">Explore what the security center has to offer</span></span>

<span data-ttu-id="2a490-222">Microsoft 365 보안 센터에서 기능을 계속 탐색합니다.</span><span class="sxs-lookup"><span data-stu-id="2a490-222">Keep exploring the features and capabilities in the Microsoft 365 security center:</span></span>

- [<span data-ttu-id="2a490-223">인시던트 및 경고 관리</span><span class="sxs-lookup"><span data-stu-id="2a490-223">Manage incidents and alerts</span></span>](manage-incidents.md)
- [<span data-ttu-id="2a490-224">위협 분석을 사용하여 새로운 위협 추적 및 대응</span><span class="sxs-lookup"><span data-stu-id="2a490-224">Track and respond to emerging threats with threat analytics</span></span>](threat-analytics.md)
- [<span data-ttu-id="2a490-225">알림 센터</span><span class="sxs-lookup"><span data-stu-id="2a490-225">The Action center</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
- [<span data-ttu-id="2a490-226">장치, 전자 메일, 앱 및 ID 전반의 위협 헌트</span><span class="sxs-lookup"><span data-stu-id="2a490-226">Hunt for threats across devices, emails, apps, and identities</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/advanced-hunting-query-emails-devices)
- [<span data-ttu-id="2a490-227">사용자 지정 검색 규칙</span><span class="sxs-lookup"><span data-stu-id="2a490-227">Custom detection rules</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/custom-detection-rules)
- [<span data-ttu-id="2a490-228">전자 & 공동 작업 알림</span><span class="sxs-lookup"><span data-stu-id="2a490-228">Email & collaboration alerts</span></span>](https://docs.microsoft.com/microsoft-365/compliance/alert-policies#default-alert-policies)
- <span data-ttu-id="2a490-229">[피싱 공격 시뮬레이션을 만들고](https://docs.microsoft.com/microsoft-365/security/office-365-security/attack-simulation-training) 팀 교육을 위한 [페이로드 만들기](https://docs.microsoft.com/microsoft-365/security/office-365-security/attack-simulation-training-payloads)</span><span class="sxs-lookup"><span data-stu-id="2a490-229">[Create a phishing attack simulation](https://docs.microsoft.com/microsoft-365/security/office-365-security/attack-simulation-training) and [create a payload for training your teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/attack-simulation-training-payloads)</span></span>
 
### <a name="related-information"></a><span data-ttu-id="2a490-230">관련 정보</span><span class="sxs-lookup"><span data-stu-id="2a490-230">Related information</span></span>
- [<span data-ttu-id="2a490-231">Microsoft 365 보안 센터</span><span class="sxs-lookup"><span data-stu-id="2a490-231">Microsoft 365 security center</span></span>](overview-security-center.md)
- [<span data-ttu-id="2a490-232">Microsoft 365 보안 센터의 Office 365용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="2a490-232">Microsoft Defender for Office 365 in the Microsoft 365 security center</span></span>](microsoft-365-security-center-mdo.md)
- [<span data-ttu-id="2a490-233">Microsoft 365 보안 센터의 끝점용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="2a490-233">Microsoft Defender for Endpoint in the Microsoft 365 security center</span></span>](microsoft-365-security-center-mde.md)
- [<span data-ttu-id="2a490-234">끝점용 Microsoft Defender에서 Microsoft 365 보안 센터로 계정 리디렉션</span><span class="sxs-lookup"><span data-stu-id="2a490-234">Redirecting accounts from Microsoft Defender for Endpoint to the Microsoft 365 security center</span></span>](microsoft-365-security-mde-redirection.md)
