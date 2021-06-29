---
title: Microsoft 365 Defender, MDO, MDE, MDI 및 MCAS 결합 개요
description: MDO Microsoft 365 Defender용 Microsoft Defender for Office 365(MDO) 및 MDE(Microsoft Defender for Endpoint)를 MDI(Microsoft Defender for Identity) 및 MCAS(Microsoft Defender)Microsoft Cloud App Security 결합하는 이점입니다. 이 문서에서는 관리자의 Microsoft 365 Defender 대한 간략한 설명을 제공합니다.
keywords: 보안, 맬웨어, Microsoft 365, M365, 보안 센터, 모니터링, 보고서, ID, 데이터, 장치, 앱
ms.prod: m365-security
ms.mktglfcycl: deploy
localization_priority: Normal
f1.keywords:
- NOCSH
ms.date: 04/21/2021
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid: met150
ms.custom: seo-marvel-jun2020
ms.technology: m365d
ms.openlocfilehash: 8e37572b07c6d81abc531e204a8cb060f1f6402c
ms.sourcegitcommit: 6749455c52b0f98a92f6fffbc2bb86caf3538bd8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/29/2021
ms.locfileid: "53195000"
---
# <a name="microsoft-365-defender-overview"></a><span data-ttu-id="88795-105">Microsoft 365 Defender 개요</span><span class="sxs-lookup"><span data-stu-id="88795-105">Microsoft 365 Defender overview</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="88795-106">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="88795-106">**Applies to:**</span></span>

- [<span data-ttu-id="88795-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="88795-107">Microsoft 365 Defender</span></span>](microsoft-365-defender.md)
- [<span data-ttu-id="88795-108">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="88795-108">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="88795-109">Office 365용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="88795-109">Microsoft Defender for Office 365</span></span>](/microsoft-365/security/office-365-security/defender-for-office-365)

> <span data-ttu-id="88795-110">Microsoft 365 Defender를 경험해 보고 싶으신가요?</span><span class="sxs-lookup"><span data-stu-id="88795-110">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="88795-111">[랩 환경에서 평가](m365d-evaluation.md?ocid=cx-docs-MTPtriallab)하거나 [프로덕션에서 파일럿 프로젝트를 실행](m365d-pilot.md?ocid=cx-evalpilot)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88795-111">You can [evaluate it in a lab environment](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) or [run your pilot project in production](m365d-pilot.md?ocid=cx-evalpilot).</span></span>

<span data-ttu-id="88795-112">**Microsoft 365 Defender** ( )는 중앙 포털에서 전자 메일, 공동 작업, ID 및 장치 위협에 대한 보호, 검색, 조사 및 [https://security.microsoft.com](https://security.microsoft.com) 응답을 결합합니다.   </span><span class="sxs-lookup"><span data-stu-id="88795-112">**Microsoft 365 Defender** ([https://security.microsoft.com](https://security.microsoft.com)) combines protection, detection, investigation, and response to *email*, *collaboration*, *identity*, and *device* threats, in a central portal.</span></span>

<span data-ttu-id="88795-113">Microsoft 365 Defender Microsoft 보안 포털 및 Microsoft Defender 보안 센터 보안 및 준수 센터와 같은 Office 365 기능을 & 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="88795-113">Microsoft 365 Defender brings together functionality from existing Microsoft security portals, like Microsoft Defender Security Center and the Office 365 Security & Compliance center.</span></span> <span data-ttu-id="88795-114">보안 센터에서는 정보에 빠르게 액세스하고, 더 간단한 레이아웃을 사용하며, 관련 정보를 함께 모아 보다 쉽게 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="88795-114">The security center emphasizes quick access to information, simpler layouts, and bringing related information together for easier use.</span></span> <span data-ttu-id="88795-115">이 센터에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="88795-115">This center includes:</span></span>

- <span data-ttu-id="88795-116">**[Microsoft Defender for Office 365](/microsoft-365/security/office-365-security/defender-for-office-365)** Microsoft Defender for Office 365 보호, 검색, 조사 및 헌팅 기능 집합을 통해 조직의 엔터프라이즈 보안을 유지하여 전자 메일 및 전자 메일 리소스를 Office 365 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88795-116">**[Microsoft Defender for Office 365](/microsoft-365/security/office-365-security/defender-for-office-365)** Microsoft Defender for Office 365 helps organizations secure their enterprise with a set of prevention, detection, investigation and hunting features to protect email, and Office 365 resources.</span></span>
- <span data-ttu-id="88795-117">**[끝점용 Microsoft Defender는](/microsoft-365/security/defender-endpoint/microsoft-defender-advanced-threat-protection)** 조직의 장치에 대한 예방 보호, 위반 후 감지, 자동화된 조사 및 응답을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="88795-117">**[Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/microsoft-defender-advanced-threat-protection)** delivers preventative protection, post-breach detection, automated investigation, and response for devices in your organization.</span></span>
- <span data-ttu-id="88795-118">**[Microsoft 365 Defender](microsoft-365-defender.md)** 보안 포트폴리오를 활용하여 도메인 전체의 위협 데이터를 자동으로 분석하고 단일 대시보드에 대한 공격 그림을 작성하는 Microsoft의 XDR(Extended *Detection and Response* Microsoft 365) 솔루션에 속합니다.</span><span class="sxs-lookup"><span data-stu-id="88795-118">**[Microsoft 365 Defender](microsoft-365-defender.md)** is part of Microsoft’s *Extended Detection and Response* (XDR) solution that leverages the Microsoft 365 security portfolio to automatically analyze threat data across domains, and build a picture of an attack on a single dashboard.</span></span>

<span data-ttu-id="88795-119">Office 365 Security & Compliance Center 또는 Microsoft Defender 보안 센터 변경된 내용은 다음을 Microsoft Defender 보안 센터 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="88795-119">If you need information about what's changed from the Office 365 Security & Compliance center or the Microsoft Defender Security Center, see:</span></span>

- [<span data-ttu-id="88795-120">Microsoft 365 Defender의 Office 365용 Defender</span><span class="sxs-lookup"><span data-stu-id="88795-120">Defender for Office 365 in Microsoft 365 Defender</span></span>](microsoft-365-security-center-mdo.md)
- [<span data-ttu-id="88795-121">Microsoft 365 Defender의 엔드포인트용 Defender</span><span class="sxs-lookup"><span data-stu-id="88795-121">Defender for Endpoint in Microsoft 365 Defender</span></span>](microsoft-365-security-center-mde.md)

> [!NOTE]
> <span data-ttu-id="88795-122">보안 Microsoft 365 기존 역할 기반 액세스를 사용 및 적용하며 각 보안 모델을 통합 포털로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="88795-122">The Microsoft 365 security portal uses and enforces existing roles-based access, and will move each security model into the unified portal.</span></span> <span data-ttu-id="88795-123">수렴형 워크로드마다 자체 역할 기반 액세스 권한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88795-123">Each converged workload has its own roles-based access.</span></span> <span data-ttu-id="88795-124">제품에 이미 있는 역할은 자동으로 Microsoft 365 포털로 수렴됩니다.</span><span class="sxs-lookup"><span data-stu-id="88795-124">The roles already in the products will be converged into the Microsoft 365 security portal, automatically.</span></span> <span data-ttu-id="88795-125">그러나 MCAS에 대한 역할 및 사용 권한은 MCAS에서 계속 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="88795-125">However, roles and permissions for MCAS will still handled over in MCAS.</span></span>

## <a name="what-to-expect"></a><span data-ttu-id="88795-126">예상할 일</span><span class="sxs-lookup"><span data-stu-id="88795-126">What to expect</span></span>

<span data-ttu-id="88795-127">Office 365 보안 및 준수 센터(protection.office.com) 및 Microsoft Defender 보안 센터(securitycenter.microsoft.com)에서 사용하는 모든 보안 콘텐츠는 이제 *Microsoft 365 Defender.*</span><span class="sxs-lookup"><span data-stu-id="88795-127">All the security content that you use in the Office 365 Security and Compliance Center (protection.office.com) and the Microsoft Defender security center (securitycenter.microsoft.com) can now be found in the *Microsoft 365 Defender*.</span></span>

<span data-ttu-id="88795-128">Microsoft 365 Defender 보안 팀이 다음에 대한 통합 환경 집합으로 여러 워크로드의 신호를 가져와 공격을 조사하고 대응하는 데 도움을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88795-128">Microsoft 365 Defender helps security teams investigate and respond to attacks by bringing in signals from different workloads into a set of unified experiences for:</span></span>

- <span data-ttu-id="88795-129">인시던트 & 경고</span><span class="sxs-lookup"><span data-stu-id="88795-129">Incidents & alerts</span></span>
- <span data-ttu-id="88795-130">헌팅</span><span class="sxs-lookup"><span data-stu-id="88795-130">Hunting</span></span>
- <span data-ttu-id="88795-131">작업 센터</span><span class="sxs-lookup"><span data-stu-id="88795-131">Action center</span></span>
- <span data-ttu-id="88795-132">위협 분석</span><span class="sxs-lookup"><span data-stu-id="88795-132">Threat analytics</span></span>

<span data-ttu-id="88795-133">Microsoft 365 Defender Microsoft Defender  for Office 365 끝점용 Microsoft Defender를 병합할 때 단합, 명확성 및 공통 목표를 강조합니다.</span><span class="sxs-lookup"><span data-stu-id="88795-133">Microsoft 365 Defender emphasizes *unity, clarity, and common goals* as it merges Microsoft Defender for Office 365 and Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="88795-134">병합은 아래에 나열된 우선 순위를 기반으로 하여 각 보안 제품군이 다음과 같은 조합으로 가져온 기능을 만족하지 않고도 이행됩니다.</span><span class="sxs-lookup"><span data-stu-id="88795-134">The merge was based on the priorities listed below, and made without sacrificing the capabilities that each security suite brought to the combination of:</span></span>

- <span data-ttu-id="88795-135">일반적인 구성 요소</span><span class="sxs-lookup"><span data-stu-id="88795-135">Common building blocks</span></span>
- <span data-ttu-id="88795-136">일반적인 용어</span><span class="sxs-lookup"><span data-stu-id="88795-136">Common terminology</span></span>
- <span data-ttu-id="88795-137">일반 엔터티</span><span class="sxs-lookup"><span data-stu-id="88795-137">Common entities</span></span>
- <span data-ttu-id="88795-138">다른 워크로드와의 기능 패리티</span><span class="sxs-lookup"><span data-stu-id="88795-138">Feature parity with other workloads</span></span>

> [!NOTE]
> <span data-ttu-id="88795-139">Microsoft 365 Defender 마이그레이션 단계를 수행하거나 새 라이선스를 구매할 필요 없이 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88795-139">Microsoft 365 Defender will be accessible without any need for customers to take migration steps or purchase a new license.</span></span> <span data-ttu-id="88795-140">예를 들어 E3 구독이 있는 관리자는 이 새 포털에 액세스할 수 있습니다. 이 포털은 Office 365 계획 1 및 계획 2에 대한 Microsoft Defender를 Office 365 있습니다. 그러나 Exchange Online Protection 또는 Office 365 요금제 1 고객에게는 구독 라이선스가 지원하는 보안 기능만 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88795-140">For example, this new portal will be accessible to administrators with an E3 subscription, just as it is to those with Microsoft Defender for Office 365 Plan 1 and Plan 2; however, Exchange Online Protection, or Defender for Office 365 Plan 1 customers will see only the security features their subscription license supports.</span></span> <span data-ttu-id="88795-141">새 센터의 목표는 보안을 중앙 집중화하는 데 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88795-141">The goal of the new center is to centralize security.</span></span>

## <a name="unified-investigations"></a><span data-ttu-id="88795-142">통합 조사</span><span class="sxs-lookup"><span data-stu-id="88795-142">Unified investigations</span></span>

<span data-ttu-id="88795-143">보안 센터를 수렴하면 보안 센터 전체에서 보안 인시던트 조사를 위한 단일 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="88795-143">Converging security centers creates a single place for investigating security incidents across Microsoft 365.</span></span> <span data-ttu-id="88795-144">기본 예로  인시던트 및 인시던트 & 빠른 실행에 대한 알림이 Microsoft 365 Defender. </span><span class="sxs-lookup"><span data-stu-id="88795-144">A primary example is **Incidents** under **Incidents & alerts** on the quick launch of Microsoft 365 Defender.</span></span>

:::image type="content" source="../../media/converged-incidents-2.png.png" alt-text="2016의 인시던트 Microsoft 365 Defender.":::

<span data-ttu-id="88795-146">인시던트 이름을 선택하면 보안 센터 수렴의 가치를 보여주는 페이지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="88795-146">Selecting an incident name displays a page that demonstrates the value of converging security centers.</span></span>

:::image type="content" source="../../media/converged-incident-info-3.png" alt-text="문서의 인시던트에 대한 요약 Microsoft 365 Defender":::

<!--
![Example of the Summary page for an incident in Microsoft 365 Defender](../../media/converged-incident-info-3.png)
--> 

<span data-ttu-id="88795-148">인시던트 페이지 위쪽에는 요약, **경고,** 장치,  **사용자,** 사서함, 조사 및 증거  탭이 표시됩니다.  </span><span class="sxs-lookup"><span data-stu-id="88795-148">Along the top of an incident page, you'll see the **Summary**, **Alerts**, **Devices**, **Users**, **Mailboxes**, **Investigations**, and **Evidence** tabs.</span></span> <span data-ttu-id="88795-149">자세한 내용을 확인하려면 이 탭을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="88795-149">Select these tabs for more detailed information.</span></span> <span data-ttu-id="88795-150">예를 들어  사용자 탭에는 수렴형 워크로드(끝점용 Microsoft Defender, ID용 Microsoft Defender 및 Microsoft Cloud App Security) 및 다양한 원본(예: Ad DS(Active Directory 도메인 서비스), Azure Active Directory(Azure AD) 및 타사 ID 공급자)의 사용자에 대한 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="88795-150">For example, the **Users** tab displays information for users from converged workloads (Microsoft Defender for Endpoint, Microsoft Defender for Identity, and Microsoft Cloud App Security) and a range of sources such as on-premises Active Directory Domain Services (AD DS), Azure Active Directory (Azure AD), and third-party identity providers.</span></span> <span data-ttu-id="88795-151">자세한 내용은 사용자 [조사를 참조하세요.](investigate-users.md)</span><span class="sxs-lookup"><span data-stu-id="88795-151">For more information, see [investigate users](investigate-users.md).</span></span>

<span data-ttu-id="88795-152">시간을 내어 환경의 인시던트 검토, 이러한 탭으로 드릴다운, 다양한 종류의 위협에 대해 인시던트에 제공된 정보에 액세스하는 방법을 파악하는 방법을 연습하세요.</span><span class="sxs-lookup"><span data-stu-id="88795-152">Take the time to review the incidents in your environment, drill down into these tabs, and practice building an understanding of how to access the information provided for incidents for different kinds of threats.</span></span>

<span data-ttu-id="88795-153">자세한 내용은 에서 [인시던트 Microsoft 365 Defender.](incidents-overview.md)</span><span class="sxs-lookup"><span data-stu-id="88795-153">For more information, see [incidents in Microsoft 365 Defender](incidents-overview.md).</span></span>

## <a name="improved-processes"></a><span data-ttu-id="88795-154">향상된 프로세스</span><span class="sxs-lookup"><span data-stu-id="88795-154">Improved processes</span></span>

<span data-ttu-id="88795-155">공용 컨트롤과 콘텐츠는 같은 장소에 표시되거나 한 데이터 피드로 압축되어 찾기가 더 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="88795-155">Common controls and content either appear in the same place, or are condensed into one feed of data making it easier to find.</span></span> <span data-ttu-id="88795-156">예를 들어 통합 설정이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88795-156">For example, unified settings.</span></span>

### <a name="unified-settings"></a><span data-ttu-id="88795-157">통합 설정</span><span class="sxs-lookup"><span data-stu-id="88795-157">Unified settings</span></span>

!['역할'을 클릭하고 일반 설정, 사용 권한, API 및 규칙이 포함된 페이지가 열립니다.](../../media/converged-add-role-9.png)

### <a name="permissions--roles"></a><span data-ttu-id="88795-161">역할에 & 사용 권한</span><span class="sxs-lookup"><span data-stu-id="88795-161">Permissions & roles</span></span>

![사용 권한 & 그룹, 역할 및 장치 & 끝점 역할을 보여 주는 역할 페이지입니다.](../../media/converged-roles-5.png)

 <span data-ttu-id="88795-163">전역 Microsoft 365 Defender 액세스는 전역 Azure Active Directory 또는 사용자 지정 역할을 사용하여 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="88795-163">Access to Microsoft 365 Defender is configured with Azure Active Directory global roles or by using custom roles.</span></span> <span data-ttu-id="88795-164">끝점용 Defender에 대한 자세한 내용은 에 [대한 사용자 액세스 할당을 Microsoft Defender 보안 센터.](/microsoft-365/security/defender-endpoint/assign-portal-access)</span><span class="sxs-lookup"><span data-stu-id="88795-164">For Defender for Endpoint, see [Assign user access to Microsoft Defender Security Center](/microsoft-365/security/defender-endpoint/assign-portal-access).</span></span> <span data-ttu-id="88795-165">For Defender for Office 365, see [Permissions in the Microsoft 365 규정 준수 센터 and Microsoft 365 Defender.](../office-365-security/permissions-microsoft-365-compliance-security.md)</span><span class="sxs-lookup"><span data-stu-id="88795-165">For Defender for Office 365, see [Permissions in the Microsoft 365 compliance center and Microsoft 365 Defender](../office-365-security/permissions-microsoft-365-compliance-security.md).</span></span>

- <span data-ttu-id="88795-166">액세스 권한을 관리하는 방법에 대해 자세히 [Microsoft 365 Defender](m365d-permissions.md)</span><span class="sxs-lookup"><span data-stu-id="88795-166">Learn more about how to [manage access to Microsoft 365 Defender](m365d-permissions.md)</span></span>
- <span data-ttu-id="88795-167">자세한 내용은 2013에서 사용자 지정 역할을 만드는 [방법을](custom-roles.md) Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="88795-167">Learn more about how to [create custom roles](custom-roles.md) in Microsoft 365 Defender</span></span>

> [!NOTE]
> <span data-ttu-id="88795-168">Microsoft Defender for Endpoint Microsoft 365 Defender Microsoft Defender 보안 센터에서 액세스 권한을 부여하는 방법과 동일한 방식으로 관리되는 보안 서비스 [공급자(MSSP)에](/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access) 대한 액세스 권한을 [부여할 수 있습니다.](./mssp-access.md)</span><span class="sxs-lookup"><span data-stu-id="88795-168">Microsoft Defender for Endpoint in Microsoft 365 Defender supports [granting access to managed security service providers (MSSPs)](/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access) in the same that way access is [granted in the Microsoft Defender security center](./mssp-access.md).</span></span>

### <a name="integrated-reports"></a><span data-ttu-id="88795-169">통합 보고서</span><span class="sxs-lookup"><span data-stu-id="88795-169">Integrated reports</span></span>

<span data-ttu-id="88795-170">보고서도 통합되어 Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="88795-170">Reports are also unified in Microsoft 365 Defender.</span></span> <span data-ttu-id="88795-171">관리자는 일반 보안 보고서로 시작하여 끝점, 전자 메일 및 공동 작업과 관련한 특정 보고서로 & 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88795-171">Admins can start with a general security report, and branch into specific reports about endpoints, email & collaboration.</span></span> <span data-ttu-id="88795-172">여기에 있는 링크는 작업 구성에 따라 동적으로 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="88795-172">The links here are dynamically generated based upon workload configuration.</span></span>

### <a name="quickly-view-your-microsoft-365-environment"></a><span data-ttu-id="88795-173">사용자 환경의 Microsoft 365 빠르게 보기</span><span class="sxs-lookup"><span data-stu-id="88795-173">Quickly view your Microsoft 365 environment</span></span>

<span data-ttu-id="88795-174">홈 **페이지에는** 보안 팀에 필요한 많은 공통 카드가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="88795-174">The **Home** page shows many of the common cards that security teams need.</span></span> <span data-ttu-id="88795-175">카드와 데이터의 구성은 사용자 역할에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="88795-175">The composition of cards and data is dependent on the user role.</span></span> <span data-ttu-id="88795-176">보안 Microsoft 365 센터에서는 역할 기반 액세스 제어를 사용하기 때문에 각 역할에 따라 매일 작업하는 데 더 의미 있는 카드가 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88795-176">Because Microsoft 365 security center uses role-based access control, different roles will see cards that are more meaningful to their day to day jobs.</span></span>  

<span data-ttu-id="88795-177">이 정보를 한눈에 확인하면 조직의 최신 활동을 유지하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="88795-177">This at-a-glance information helps you keep up with the latest activities in your organization.</span></span> <span data-ttu-id="88795-178">Microsoft 365 Defender 소스의 신호를 함께 모아 사용자 환경의 전체적인 Microsoft 365 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="88795-178">Microsoft 365 Defender brings together signals from different sources to present a holistic view of your Microsoft 365 environment.</span></span>

<span data-ttu-id="88795-179">카드는 다음 범주로 분류됩니다.</span><span class="sxs-lookup"><span data-stu-id="88795-179">The cards fall into these categories:</span></span>

- <span data-ttu-id="88795-180">**ID**- 조직의 ID를 모니터링하고 의심스거나 위험한 동작을 추적합니다.</span><span class="sxs-lookup"><span data-stu-id="88795-180">**Identities**- Monitor the identities in your organization and keep track of suspicious or risky behaviors.</span></span> <span data-ttu-id="88795-181">[ID 보호에 대해 자세히 알아보시다.](/azure/active-directory/identity-protection/overview-identity-protection)</span><span class="sxs-lookup"><span data-stu-id="88795-181">[Learn more about identity protection](/azure/active-directory/identity-protection/overview-identity-protection).</span></span>
- <span data-ttu-id="88795-182">**데이터** - 무단 데이터 공개로 이어질 수 있는 사용자 활동을 추적하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="88795-182">**Data** - Help track user activity that could lead to unauthorized data disclosure.</span></span>
- <span data-ttu-id="88795-183">**장치** - 장치의 경고, 위반 활동 및 기타 위협에 대한 최신 정보를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="88795-183">**Devices** - Get up-to-date information on alerts, breach activity, and other threats on your devices.</span></span>
- <span data-ttu-id="88795-184">**앱** - 조직에서 클라우드 앱이 어떻게 사용되는지 파악합니다.</span><span class="sxs-lookup"><span data-stu-id="88795-184">**Apps** - Gain insight into how cloud apps are being used in your organization.</span></span> <span data-ttu-id="88795-185">[검색된 앱의 Cloud App Security 자세히 알아보아야 합니다.](/cloud-app-security/discovered-apps)</span><span class="sxs-lookup"><span data-stu-id="88795-185">[Learn more about Cloud App Security discovered apps](/cloud-app-security/discovered-apps).</span></span>

## <a name="threat-analytics-with-better-data-coverage"></a><span data-ttu-id="88795-186">더 나은 데이터 범위를 제공하는 위협 분석</span><span class="sxs-lookup"><span data-stu-id="88795-186">Threat analytics with better data coverage</span></span>
<span data-ttu-id="88795-187">다음과 같은 위협 분석 통합 환경을 Microsoft 365 Defender 새로운 위협을 추적하고 대응합니다.</span><span class="sxs-lookup"><span data-stu-id="88795-187">Track and respond to emerging threats with the following Microsoft 365 Defender threat analytics integrated experience:</span></span>

- <span data-ttu-id="88795-188">엔드포인트용 Microsoft Defender와 Microsoft Defender for Office 365 통합된 인시던트 관리, 자동 조사, 수정 및 사전 또는 사후 위협 헌팅을 도메인 전체에서 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="88795-188">Better data coverage between Microsoft Defender for Endpoint and Microsoft Defender for Office 365, making combined incident management, automatic investigation, remediation, and proactive or reactive threat hunting across-domain possible.</span></span> 
- <span data-ttu-id="88795-189">끝점용 Microsoft Defender에서 이미 사용할 수 있는 끝점 데이터 외에 Office 365 Microsoft Defender의 전자 메일 관련 검색 및 완화 기능</span><span class="sxs-lookup"><span data-stu-id="88795-189">Email-related detections and mitigations from Microsoft Defender for Office 365, in addition to the endpoint data already available from Microsoft Defender for Endpoint.</span></span>
- <span data-ttu-id="88795-190">Microsoft Defender for Endpoint 및 Microsoft Defender for Office 365 전반에 걸쳐 종합적인 공격 사례로 경고를 집계하여 작업 큐를 줄이고 조사를 단순화하고 빠르게 하는 위협 관련 인시던트 보기입니다.</span><span class="sxs-lookup"><span data-stu-id="88795-190">A view of threat-related incidents which aggregate alerts into end-to-end attack stories across Microsoft Defender for Endpoint and Microsoft Defender for Office 365 to reduce the work queue, as well as simplify and speed up your investigation.</span></span>
- <span data-ttu-id="88795-191">보안 솔루션에 의해 검색되고 차단된 공격 Microsoft 365 Defender 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88795-191">Attack attempts detected and blocked by Microsoft 365 Defender solutions.</span></span> <span data-ttu-id="88795-192">추가 노출 및 탄력성 증가 위험을 완화하는 예방 조치를 구동하는 데 사용할 수 있는 데이터도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88795-192">There's also data that you can use to drive preventive actions that mitigate the risk of further exposure and increase resilience.</span></span> 
- <span data-ttu-id="88795-193">실행 가능한 정보를 스포트라이트에 저장하여 보고서를 긴급하게 집중하고 조사하고 활용하기 위해 데이터를 빠르게 식별할 수 있도록 하는 향상된 디자인입니다.</span><span class="sxs-lookup"><span data-stu-id="88795-193">Enhanced design that puts actionable information in the spotlight to help you  quickly identify data to urgently focus on, investigate, and leverage from the reports.</span></span>

## <a name="a-centralized-learning-hub"></a><span data-ttu-id="88795-194">중앙 집중식 Learning 허브</span><span class="sxs-lookup"><span data-stu-id="88795-194">A centralized Learning Hub</span></span>

<span data-ttu-id="88795-195">Microsoft 365 보안 센터에는 Microsoft 보안 블로그, YouTube의 Microsoft 보안 커뮤니티 및 공식 설명서와 같은 리소스의 공식 지침을 버블업하는 학습 허브가 docs.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="88795-195">Microsoft 365 security center includes a learning hub that bubbles up official guidance from resources such as the Microsoft security blog, the Microsoft security community on YouTube, and the official documentation at docs.microsoft.com.</span></span>

<span data-ttu-id="88795-196">학습 허브 내에서 Email & Collaboration (Microsoft Defender for Office 365) 지침은 Endpoint(Endpoint용 Microsoft Defender) 및 Microsoft 365 Defender 리소스와 함께 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="88795-196">Inside the learning hub, Email & Collaboration (Microsoft Defender for Office 365) guidance is side-by-side with Endpoint (Microsoft Defender for Endpoint) and Microsoft 365 Defender learning resources.</span></span>

<span data-ttu-id="88795-197">학습 허브는 "Learning 사용하여 조사하는 방법"과 같은 주제에 대해 구성되는 Microsoft 365 Defender 경로로 열립니다.</span><span class="sxs-lookup"><span data-stu-id="88795-197">The learning hub opens with Learning paths organized around topics such as “How to Investigate Using Microsoft 365 Defender?”</span></span> <span data-ttu-id="88795-198">및 "Microsoft Defender for Office 365 모범 사례".</span><span class="sxs-lookup"><span data-stu-id="88795-198">and “Microsoft Defender for Office 365 Best Practices”.</span></span> <span data-ttu-id="88795-199">이 섹션은 현재 Microsoft 내부의 보안 제품 그룹에서 큐레이터합니다.</span><span class="sxs-lookup"><span data-stu-id="88795-199">This section is currently curated by the security Product Group inside Microsoft.</span></span> <span data-ttu-id="88795-200">각 Learning 경로는 개념을 통과하는 데 걸리는 시간을 반영합니다.</span><span class="sxs-lookup"><span data-stu-id="88795-200">Each Learning path reflects a projected time it takes to get through the concepts.</span></span> <span data-ttu-id="88795-201">예를 들어 'Office 365 사용자 계정이 손상될 때 수행되는 단계'는 8분 정도 소요될 것으로 예정되어 있으며, 중요한 학습이 진행됩니다.</span><span class="sxs-lookup"><span data-stu-id="88795-201">For example 'Steps to take when a Microsoft Defender for Office 365 user account is compromised' is projected to take 8 minutes, and is valuable learning on the fly.</span></span>

<span data-ttu-id="88795-202">콘텐츠를 클릭한 후 이 사이트를 책갈피로 지정하고 책갈피를 '보안' 또는 '중요' 폴더로 구성하는 것이 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88795-202">After clicking through to the content, it may be useful to bookmark this site and organize bookmarks into a 'Security' or 'Critical' folder.</span></span> <span data-ttu-id="88795-203">모든 Learning 보려면 주 패널에서 모두 표시 링크를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="88795-203">To see all Learning paths, click the Show all link in the main panel.</span></span>

> [!NOTE]
> <span data-ttu-id="88795-204">제품(현재  Microsoft 365 Defender Microsoft 365 Defender, 끝점용 Microsoft Defender 및 Microsoft Defender for Office 365) 간에 선택할 수 있는 유용한 필터가 Microsoft 365 Defender 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88795-204">There are helpful **filters** along the top of Microsoft 365 Defender learning hub that will let you choose between products (currently Microsoft 365 Defender, Microsoft Defender for Endpoint, and Microsoft Defender for Office 365).</span></span> <span data-ttu-id="88795-205">각 섹션의 학습 리소스 수가 나열되어 있으며, 이는 학습하는 사람이 교육 및 학습을 위해 얼마나 많은 리소스를 준비해야 하는지 추적하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88795-205">Notice that the number of learning resources for each section is listed, which can help learners keep track of how many resources they have at hand for training and learning.</span></span>
>
> <span data-ttu-id="88795-206">제품 필터, 현재 항목, 리소스 유형(비디오에서 웨비나까지), 보안 영역, 보안 역할 및 제품 기능에 대한 익숙하거나 경험 수준이 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="88795-206">Along with the Product filter, current topics, types of resources (from videos to webinars), levels of familiarity or experience with security areas, security roles, and product features are listed.</span></span>

> [!TIP]
> <span data-ttu-id="88795-207">Microsoft Learn 에는 다른 많은 학습 [기회가 있습니다.](/e/learn/)</span><span class="sxs-lookup"><span data-stu-id="88795-207">There are lots of other learning opportunities in [Microsoft Learn](/e/learn/).</span></span> <span data-ttu-id="88795-208">[Ms-500T02-A:](/learn/certifications/courses/ms-500t02)보안 위협 방지 구현과 같은 인증 Microsoft 365 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88795-208">You'll find certification training such as [Course MS-500T02-A: Implementing Microsoft 365 Threat Protection](/learn/certifications/courses/ms-500t02).</span></span>

## <a name="send-us-your-feedback"></a><span data-ttu-id="88795-209">피드백 보내기</span><span class="sxs-lookup"><span data-stu-id="88795-209">Send us your feedback</span></span>

<span data-ttu-id="88795-210">피드백이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="88795-210">We need your feedback.</span></span> <span data-ttu-id="88795-211">We're always looking to improve, so if there's something you're like to see, [send us your Microsoft 365 Defender feedback.](https://www.microsoft.com/videoplayer/embed/RE4K5Ci)</span><span class="sxs-lookup"><span data-stu-id="88795-211">We're always looking to improve, so if there's something you'd like to see, [send us your Microsoft 365 Defender feedback](https://www.microsoft.com/videoplayer/embed/RE4K5Ci).</span></span>

<span data-ttu-id="88795-212">이 문서에서 피드백을 남길 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88795-212">You can also leave feedback from this article.</span></span> <span data-ttu-id="88795-213">'피드백 제출 및 보기' 아래 끝에 있는 '피드백' 섹션에서 옵션은 이 제품 또는 *이 페이지입니다.*</span><span class="sxs-lookup"><span data-stu-id="88795-213">In the 'Feedback' section at the end under 'Submit and view feedback for', the options are *This product*, or *This page*.</span></span>

<span data-ttu-id="88795-214">제품 **피드백을 위해 이** 제품 *단추를* 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="88795-214">Use the **This product** button for *product* feedback:</span></span>

1. <span data-ttu-id="88795-215">문서 *아래쪽에서* 이 제품을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="88795-215">Select *This product* at the bottom of the article.</span></span>
    1. <span data-ttu-id="88795-216">단추를 마우스 오른쪽 단추로 클릭하고 다음 길안을 계속 읽으려면 '새 탭에서 열기'를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="88795-216">Right-click the button and 'Open in a new tab' if you want to keep reading these directions.</span></span>
2. <span data-ttu-id="88795-217">그러면 **UserVoice 포럼으로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="88795-217">This will navigate to the **UserVoice forum**.</span></span>
3. <span data-ttu-id="88795-218">다음과 같은 두 가지 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88795-218">You have 2 options:</span></span>
    1. <span data-ttu-id="88795-219">텍스트 상자까지 아래로 스크롤하여 규정 준수를 개선하거나 사용자를 보다 잘 보호할 수 *Office 365?를* 입력하고 *Microsoft 365 Defender.*</span><span class="sxs-lookup"><span data-stu-id="88795-219">Scroll down to the text box *How can we improve compliance or protect your users better in Office 365?* and paste in *Microsoft 365 Defender*.</span></span> <span data-ttu-id="88795-220">결과에서 사용자와 같은 아이디어를 검색하여 투표하거나 새 아이디어 게시 **단추를 사용할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="88795-220">You can search the results for an idea like yours and up-vote it, or use the button for **Post a new idea**.</span></span>
    1. <span data-ttu-id="88795-221">이 문제가 이미 보고된 것으로 생각되고 해당 프로필을 투표(또는 투표)로  올리고 싶은 경우 UserVoice의 오른쪽에 있는 피드백 보내기 상자를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="88795-221">If you feel certain this issue is already reported, and want to raise its profile with a vote (or votes), use the *Give Feedback* box on the right side of UserVoice.</span></span> <span data-ttu-id="88795-222">에서 *Microsoft 365 Defender* **검색하고,** 투표 단추를 사용하여 상태를 올렸다.</span><span class="sxs-lookup"><span data-stu-id="88795-222">Search for *Microsoft 365 Defender*, **find the issue, and use the vote button** to raise its status.</span></span>

<span data-ttu-id="88795-223">문서 *자체에* 대한 피드백을 위해 이 페이지를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="88795-223">Use *This page* for feedback on the article itself.</span></span> <span data-ttu-id="88795-224">사용자 의견을 보내 주셔서 감사합니다.</span><span class="sxs-lookup"><span data-stu-id="88795-224">Thanks for your feedback.</span></span> <span data-ttu-id="88795-225">음성은 제품을 개선하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="88795-225">Your voice helps us improve products.</span></span>

### <a name="explore-what-the-security-center-has-to-offer"></a><span data-ttu-id="88795-226">보안 센터에서 제공해야 하는 것 살펴보기</span><span class="sxs-lookup"><span data-stu-id="88795-226">Explore what the security center has to offer</span></span>

<span data-ttu-id="88795-227">다음과 같은 기능에 대해 계속 Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="88795-227">Keep exploring the features and capabilities in Microsoft 365 Defender:</span></span>

- [<span data-ttu-id="88795-228">인시던트 및 경고 관리</span><span class="sxs-lookup"><span data-stu-id="88795-228">Manage incidents and alerts</span></span>](manage-incidents.md)
- [<span data-ttu-id="88795-229">위협 분석을 사용하여 새로운 위협 추적 및 대응</span><span class="sxs-lookup"><span data-stu-id="88795-229">Track and respond to emerging threats with threat analytics</span></span>](threat-analytics.md)
- [<span data-ttu-id="88795-230">알림 센터</span><span class="sxs-lookup"><span data-stu-id="88795-230">The Action center</span></span>](m365d-action-center.md)
- [<span data-ttu-id="88795-231">장치, 전자 메일, 앱 및 ID에 대한 위협 검색</span><span class="sxs-lookup"><span data-stu-id="88795-231">Hunt for threats across devices, emails, apps, and identities</span></span>](./advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="88795-232">사용자 지정 검색 규칙</span><span class="sxs-lookup"><span data-stu-id="88795-232">Custom detection rules</span></span>](./custom-detection-rules.md)
- [<span data-ttu-id="88795-233">전자 메일 및 공동 작업 경고</span><span class="sxs-lookup"><span data-stu-id="88795-233">Email & collaboration alerts</span></span>](../../compliance/alert-policies.md#default-alert-policies)
- <span data-ttu-id="88795-234">[피싱 공격 시뮬레이션을](../office-365-security/attack-simulation-training.md) 만들고 팀 교육을 위한 [페이로드 만들기](/microsoft-365/security/office-365-security/attack-simulation-training-payloads)</span><span class="sxs-lookup"><span data-stu-id="88795-234">[Create a phishing attack simulation](../office-365-security/attack-simulation-training.md) and [create a payload for training your teams](/microsoft-365/security/office-365-security/attack-simulation-training-payloads)</span></span>
 
### <a name="related-information"></a><span data-ttu-id="88795-235">관련 정보</span><span class="sxs-lookup"><span data-stu-id="88795-235">Related information</span></span>
- [<span data-ttu-id="88795-236">Microsoft Defender for Office 365 Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="88795-236">Microsoft Defender for Office 365 in Microsoft 365 Defender</span></span>](microsoft-365-security-center-mdo.md)
- [<span data-ttu-id="88795-237">Microsoft Defender for Endpoint in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="88795-237">Microsoft Defender for Endpoint in Microsoft 365 Defender</span></span>](microsoft-365-security-center-mde.md)
- [<span data-ttu-id="88795-238">끝점용 Microsoft Defender에서 계정으로 Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="88795-238">Redirecting accounts from Microsoft Defender for Endpoint to Microsoft 365 Defender</span></span>](microsoft-365-security-mde-redirection.md)