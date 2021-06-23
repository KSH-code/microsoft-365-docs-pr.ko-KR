---
title: 위협 & 대응 기능 - Microsoft Defender for Office 365 계획 2
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 12/09/2019
audience: Admin
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 32405da5-bee1-4a4b-82e5-8399df94c512
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: Microsoft Defender for Office 365 대한 위협 조사 및 대응 기능에 대해 자세히 알아보습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b0a9ff9c06f7e97d6f74c901c156bfae6c9eb91d
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083707"
---
# <a name="threat-investigation-and-response"></a><span data-ttu-id="fd845-103">위협 조사 및 응답</span><span class="sxs-lookup"><span data-stu-id="fd845-103">Threat investigation and response</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="fd845-104">**적용**</span><span class="sxs-lookup"><span data-stu-id="fd845-104">**Applies To**</span></span>
- [<span data-ttu-id="fd845-105">Office 365용 Microsoft Defender 플랜 2</span><span class="sxs-lookup"><span data-stu-id="fd845-105">Microsoft Defender for Office 365 plan 2</span></span>](defender-for-office-365.md)


<span data-ttu-id="fd845-106">Microsoft [Defender](defender-for-office-365.md) for Office 365 위협 조사 및 대응 기능은 보안 분석가와 관리자가 다음을 통해 조직의 비즈니스 Microsoft 365 보호하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd845-106">Threat investigation and response capabilities in [Microsoft Defender for Office 365](defender-for-office-365.md) help security analysts and administrators protect their organization's Microsoft 365 for business users by:</span></span>

- <span data-ttu-id="fd845-107">사이버 공격을 쉽게 식별, 모니터링 및 이해</span><span class="sxs-lookup"><span data-stu-id="fd845-107">Making it easy to identify, monitor, and understand cyberattacks</span></span>
- <span data-ttu-id="fd845-108">온라인, 온라인, Exchange Online, SharePoint 위협을 비즈니스용 OneDrive Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="fd845-108">Helping to quickly address threats in Exchange Online, SharePoint Online, OneDrive for Business and Microsoft Teams</span></span>
- <span data-ttu-id="fd845-109">보안 운영으로 조직에 대한 사이버 공격을 방지하는 데 도움이 되는 인사이트 및 지식 제공</span><span class="sxs-lookup"><span data-stu-id="fd845-109">Providing insights and knowledge to help security operations prevent cyberattacks against their organization</span></span>
- <span data-ttu-id="fd845-110">중요한 전자 메일 기반 [위협에 대한 자동화된 조사 Office 365](automated-investigation-response-office.md) 대응</span><span class="sxs-lookup"><span data-stu-id="fd845-110">Employing [automated investigation and response in Office 365](automated-investigation-response-office.md) for critical email-based threats</span></span>

<span data-ttu-id="fd845-111">위협 조사 및 대응 기능은 보안 포털에서 사용할 수 있는 위협 및 관련 대응 Microsoft 365 Defender 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fd845-111">Threat investigation and response capabilities provide insights into threats and related response actions that are available in the Microsoft 365 Defender portal.</span></span> <span data-ttu-id="fd845-112">이러한 인사이트는 조직의 보안 팀이 전자 메일 또는 파일 기반 공격으로부터 사용자를 보호하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd845-112">These insights can help your organization's security team protect users from email- or file-based attacks.</span></span> <span data-ttu-id="fd845-113">이 기능은 신호를 모니터링하고 사용자 활동, 인증, 전자 메일, 손상된 PC 및 보안 인시던트와 같은 여러 원본에서 데이터를 수집하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd845-113">The capabilities help monitor signals and gather data from multiple sources, such as user activity, authentication, email, compromised PCs, and security incidents.</span></span> <span data-ttu-id="fd845-114">비즈니스 의사 결정권자 및 보안 운영 팀은 이 정보를 사용하여 조직에 대한 위협을 이해하고 대응하고 지적 재산을 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd845-114">Business decision makers and your security operations team can use this information to understand and respond to threats against your organization and protect your intellectual property.</span></span>

## <a name="get-acquainted-with-threat-investigation-and-response-tools"></a><span data-ttu-id="fd845-115">위협 조사 및 응답 도구에 대해 잘 아는 경우</span><span class="sxs-lookup"><span data-stu-id="fd845-115">Get acquainted with threat investigation and response tools</span></span>

<span data-ttu-id="fd845-116">위협 조사 및 응답 기능은 Microsoft 365 Defender 포털에서 다음과 같은 도구 및 응답 워크플로 집합으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd845-116">Threat investigation and response capabilities surface in the Microsoft 365 Defender portal, as a set of tools and response workflows, including the following:</span></span>

- [<span data-ttu-id="fd845-117">탐색기</span><span class="sxs-lookup"><span data-stu-id="fd845-117">Explorer</span></span>](#explorer)
- [<span data-ttu-id="fd845-118">인시던트</span><span class="sxs-lookup"><span data-stu-id="fd845-118">Incidents</span></span>](#incidents)
- [<span data-ttu-id="fd845-119">공격 시뮬레이션 교육</span><span class="sxs-lookup"><span data-stu-id="fd845-119">Attack simulation training</span></span>](attack-simulation-training.md)
- [<span data-ttu-id="fd845-120">자동화된 조사 및 응답</span><span class="sxs-lookup"><span data-stu-id="fd845-120">Automated investigation and response</span></span>](automated-investigation-response-office.md)

### <a name="explorer"></a><span data-ttu-id="fd845-121">탐색기</span><span class="sxs-lookup"><span data-stu-id="fd845-121">Explorer</span></span>

<span data-ttu-id="fd845-122">[탐색기(및 실시간](threat-explorer.md) 검색)를 사용하여 위협을 분석하고, 시간이 지날수록 공격의 양을 보고, 위협 패밀리, 공격자 인프라 등에서 데이터를 분석합니다.</span><span class="sxs-lookup"><span data-stu-id="fd845-122">Use [Explorer (and real-time detections)](threat-explorer.md) to analyze threats, see the volume of attacks over time, and analyze data by threat families, attacker infrastructure, and more.</span></span> <span data-ttu-id="fd845-123">탐색기(위협 탐색기라고도 지칭)는 모든 보안 분석가의 조사 워크플로를 위한 시작 장소입니다.</span><span class="sxs-lookup"><span data-stu-id="fd845-123">Explorer (also referred to as Threat Explorer) is the starting place for any security analyst's investigation workflow.</span></span>

![위협 탐색기](../../media/7a7cecee-17f0-4134-bcb8-7cee3f3c3890.png)

<span data-ttu-id="fd845-125">이 보고서를 보고 사용하려면 Microsoft 365 Defender 포털에서 전자 메일 & **탐색기 로**  >  **이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="fd845-125">To view and use this report, in the Microsoft 365 Defender portal, go to **Email & collaboration** > **Explorer**.</span></span>

### <a name="incidents"></a><span data-ttu-id="fd845-126">인시던트</span><span class="sxs-lookup"><span data-stu-id="fd845-126">Incidents</span></span>

<span data-ttu-id="fd845-127">인시던트 목록(조사라고도 합니다)을 사용하여 플라이트 보안 인시던트 목록을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd845-127">Use the Incidents list (this is also called Investigations) to see a list of in flight security incidents.</span></span> <span data-ttu-id="fd845-128">인시던트는 의심스러운 전자 메일 메시지와 같은 위협을 추적하고 추가 조사 및 수정을 수행하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd845-128">Incidents are used to track threats such as suspicious email messages, and to conduct further investigation and remediation.</span></span>

![보안 위협의 현재 위협 Office 365](../../media/acadd4c7-d2de-4146-aeb8-90cfad805a9c.png)

<span data-ttu-id="fd845-130">조직의 현재 인시던트 목록을 확인하면 Microsoft 365 Defender 포털에서 인시던트 및 &   >  **로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="fd845-130">To view the list of current incidents for your organization, in the Microsoft 365 Defender portal, go to **Incidents & alerts** > **Incidents**.</span></span>

![보안 및 & 센터에서 위협 관리 검토를 \> 선택](../../media/e0f46454-fa38-40f0-a120-b595614d1d22.png)

### <a name="attack-simulation-training"></a><span data-ttu-id="fd845-132">공격 시뮬레이션 교육</span><span class="sxs-lookup"><span data-stu-id="fd845-132">Attack simulation training</span></span>

<span data-ttu-id="fd845-133">공격 시뮬레이션 교육을 사용하여 조직에서 실제 사이버 공격을 설정하고 실행하고 실제 사이버 공격이 비즈니스에 영향을 미치기 전에 취약한 인물 식별</span><span class="sxs-lookup"><span data-stu-id="fd845-133">Use Attack simulation training to set up and run realistic cyberattacks in your organization, and identify vulnerable people before a real cyberattack affects your business.</span></span> <span data-ttu-id="fd845-134">자세한 내용은 피싱 공격 [시뮬레이트를 참조합니다.](attack-simulation-training.md)</span><span class="sxs-lookup"><span data-stu-id="fd845-134">To learn more, see [Simulate a phishing attack](attack-simulation-training.md).</span></span>

<span data-ttu-id="fd845-135">Microsoft 365 Defender 포털에서 이 기능을 보고 사용하세요. 전자 메일 & **공격**  >  **시뮬레이션 교육으로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="fd845-135">To view and use this feature in the Microsoft 365 Defender portal, go to **Email & collaboration** > **Attack simulation training**.</span></span>

### <a name="automated-investigation-and-response"></a><span data-ttu-id="fd845-136">자동 조사 및 응답</span><span class="sxs-lookup"><span data-stu-id="fd845-136">Automated investigation and response</span></span>

<span data-ttu-id="fd845-137">자동화된 조사 및 대응(AIR) 기능을 사용하여 조직의 위협으로부터 콘텐츠, 장치 및 사용자와 관련한 시간과 노력을 절약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd845-137">Use automated investigation and response (AIR) capabilities to save time and effort correlating content, devices, and people at risk from threats in your organization.</span></span> <span data-ttu-id="fd845-138">AIR 프로세스는 특정 경고가 트리거될 때마다 또는 보안 운영 팀에서 시작할 때 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd845-138">AIR processes can begin whenever certain alerts are triggered, or when started by your security operations team.</span></span> <span data-ttu-id="fd845-139">자세한 내용은 에서 자동화된 조사 [및 대응을 Office 365.](automated-investigation-response-office.md)</span><span class="sxs-lookup"><span data-stu-id="fd845-139">To learn more, see [automated investigation and response in Office 365](automated-investigation-response-office.md).</span></span>

## <a name="threat-intelligence-widgets"></a><span data-ttu-id="fd845-140">위협 인텔리전스 위젯</span><span class="sxs-lookup"><span data-stu-id="fd845-140">Threat intelligence widgets</span></span>

<span data-ttu-id="fd845-141">Microsoft Defender for Office 365 계획 2의 일부로 보안 분석가가 알려진 위협에 대한 세부 정보를 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd845-141">As part of the Microsoft Defender for Office 365 Plan 2 offering, security analysts can review details about a known threat.</span></span> <span data-ttu-id="fd845-142">이는 사용자를 안전하게 유지하기 위해 추가로 예방 조치/단계가 있는지 여부를 확인하는 데 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="fd845-142">This is useful to determine whether there are additional preventative measures/steps that can be taken to keep users safe.</span></span>

![최근 위협에 대한 정보를 보여주는 보안 추세](../../media/11e7d40d-139b-4c56-8d52-c091c8654151.png)

## <a name="how-do-we-get-these-capabilities"></a><span data-ttu-id="fd845-144">이러한 기능을 어떻게 얻을 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="fd845-144">How do we get these capabilities?</span></span>

<span data-ttu-id="fd845-145">Microsoft 365 위협 조사 및 응답 기능은 Enterprise E5 또는 특정 구독의 추가 기능으로 포함된 Office 365 계획 2용 Microsoft Defender에 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd845-145">Microsoft 365 threat investigation and response capabilities are included in Microsoft Defender for Office 365 Plan 2, which is included in Enterprise E5 or as an add-on to certain subscriptions.</span></span> <span data-ttu-id="fd845-146">자세한 내용은 [Defender for Office 365 요금제 1 및 계획 2를 참조합니다.](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2)</span><span class="sxs-lookup"><span data-stu-id="fd845-146">To learn more, see [Defender for Office 365 Plan 1 and Plan 2](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2).</span></span>

## <a name="required-roles-and-permissions"></a><span data-ttu-id="fd845-147">필요한 역할 및 사용 권한 할당</span><span class="sxs-lookup"><span data-stu-id="fd845-147">Required roles and permissions</span></span>

<span data-ttu-id="fd845-148">Microsoft Defender for Office 365 역할 기반 액세스 제어를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd845-148">Microsoft Defender for Office 365 uses role-based access control.</span></span> <span data-ttu-id="fd845-149">사용 권한은 Azure Active Directory, Microsoft 365 관리 센터 또는 Microsoft 365 Defender 포털의 특정 역할을 통해 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd845-149">Permissions are assigned through certain roles in Azure Active Directory, the Microsoft 365 admin center, or the Microsoft 365 Defender portal.</span></span>

> [!TIP]
> <span data-ttu-id="fd845-150">보안 관리자와 같은 일부 역할은 Microsoft 365 Defender 포털에서 할당할 수 Microsoft 365 관리 센터 Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="fd845-150">Although some roles, such as Security Administrator, can be assigned in the Microsoft 365 Defender portal, consider using either the Microsoft 365 admin center or Azure Active Directory instead.</span></span> <span data-ttu-id="fd845-151">역할, 역할 그룹 및 사용 권한에 대한 자세한 내용은 다음 리소스를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="fd845-151">For information about roles, role groups, and permissions, see the following resources:</span></span>
>
> - [<span data-ttu-id="fd845-152">Microsoft 365 Defender 포털 사용 권한</span><span class="sxs-lookup"><span data-stu-id="fd845-152">Permissions in the Microsoft 365 Defender portal</span></span>](permissions-microsoft-365-security-center.md)
> - [<span data-ttu-id="fd845-153">Azure Active Directory의 관리자 역할 권한</span><span class="sxs-lookup"><span data-stu-id="fd845-153">Administrator role permissions in Azure Active Directory</span></span>](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)

<br>

****

|<span data-ttu-id="fd845-154">활동</span><span class="sxs-lookup"><span data-stu-id="fd845-154">Activity</span></span>|<span data-ttu-id="fd845-155">역할 및 사용 권한</span><span class="sxs-lookup"><span data-stu-id="fd845-155">Roles and permissions</span></span>|
|---|---|
|<span data-ttu-id="fd845-156">위협 및 & 관리 대시보드(또는 새 보안 대시보드) [사용](security-dashboard.md)</span><span class="sxs-lookup"><span data-stu-id="fd845-156">Use the Threat & Vulnerability Management dashboard (or the new [Security dashboard](security-dashboard.md))</span></span> <p> <span data-ttu-id="fd845-157">최근 또는 현재 위협에 대한 정보 보기</span><span class="sxs-lookup"><span data-stu-id="fd845-157">View information about recent or current threats</span></span>|<span data-ttu-id="fd845-158">다음 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="fd845-158">One of the following:</span></span> <ul><li><span data-ttu-id="fd845-159">**전역 관리자**</span><span class="sxs-lookup"><span data-stu-id="fd845-159">**Global Administrator**</span></span></li><li><span data-ttu-id="fd845-160">**보안 관리자**</span><span class="sxs-lookup"><span data-stu-id="fd845-160">**Security Administrator**</span></span></li><li><span data-ttu-id="fd845-161">**보안 읽기**</span><span class="sxs-lookup"><span data-stu-id="fd845-161">**Security Reader**</span></span></li></ul> <p> <span data-ttu-id="fd845-162">이러한 역할은 Azure Active Directory ( ) 또는 <https://portal.azure.com> Microsoft 365 관리 센터( )에서 할당할 수 <https://admin.microsoft.com> 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd845-162">These roles can be assigned in either Azure Active Directory (<https://portal.azure.com>) or the Microsoft 365 admin center (<https://admin.microsoft.com>).</span></span>|
|<span data-ttu-id="fd845-163">[탐색기(및 실시간 검색)를](threat-explorer.md) 사용하여 위협 분석</span><span class="sxs-lookup"><span data-stu-id="fd845-163">Use [Explorer (and real-time detections)](threat-explorer.md) to analyze threats</span></span>|<span data-ttu-id="fd845-164">다음 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="fd845-164">One of the following:</span></span> <ul><li><span data-ttu-id="fd845-165">**전역 관리자**</span><span class="sxs-lookup"><span data-stu-id="fd845-165">**Global Administrator**</span></span></li><li><span data-ttu-id="fd845-166">**보안 관리자**</span><span class="sxs-lookup"><span data-stu-id="fd845-166">**Security Administrator**</span></span></li><li><span data-ttu-id="fd845-167">**보안 읽기**</span><span class="sxs-lookup"><span data-stu-id="fd845-167">**Security Reader**</span></span></li></ul> <p> <span data-ttu-id="fd845-168">이러한 역할은 Azure Active Directory ( ) 또는 <https://portal.azure.com> Microsoft 365 관리 센터( )에서 할당할 수 <https://admin.microsoft.com> 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd845-168">These roles can be assigned in either Azure Active Directory (<https://portal.azure.com>) or the Microsoft 365 admin center (<https://admin.microsoft.com>).</span></span>|
|<span data-ttu-id="fd845-169">인시던트 보기(조사라고도 지칭)</span><span class="sxs-lookup"><span data-stu-id="fd845-169">View Incidents (also referred to as Investigations)</span></span> <p> <span data-ttu-id="fd845-170">인시던트에 전자 메일 메시지 추가</span><span class="sxs-lookup"><span data-stu-id="fd845-170">Add email messages to an incident</span></span>|<span data-ttu-id="fd845-171">다음 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="fd845-171">One of the following:</span></span> <ul><li><span data-ttu-id="fd845-172">**전역 관리자**</span><span class="sxs-lookup"><span data-stu-id="fd845-172">**Global Administrator**</span></span></li><li><span data-ttu-id="fd845-173">**보안 관리자**</span><span class="sxs-lookup"><span data-stu-id="fd845-173">**Security Administrator**</span></span></li><li><span data-ttu-id="fd845-174">**보안 읽기**</span><span class="sxs-lookup"><span data-stu-id="fd845-174">**Security Reader**</span></span></li></ul> <p> <span data-ttu-id="fd845-175">이러한 역할은 Azure Active Directory ( ) 또는 <https://portal.azure.com> Microsoft 365 관리 센터( )에서 할당할 수 <https://admin.microsoft.com> 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd845-175">These roles can be assigned in either Azure Active Directory (<https://portal.azure.com>) or the Microsoft 365 admin center (<https://admin.microsoft.com>).</span></span>|
|<span data-ttu-id="fd845-176">인시던트에서 전자 메일 작업 트리거</span><span class="sxs-lookup"><span data-stu-id="fd845-176">Trigger email actions in an incident</span></span> <p> <span data-ttu-id="fd845-177">의심스러운 전자 메일 메시지 찾기 및 삭제</span><span class="sxs-lookup"><span data-stu-id="fd845-177">Find and delete suspicious email messages</span></span>|<span data-ttu-id="fd845-178">다음 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="fd845-178">One of the following:</span></span> <ul><li><span data-ttu-id="fd845-179">**전역 관리자**</span><span class="sxs-lookup"><span data-stu-id="fd845-179">**Global Administrator**</span></span></li><li><span data-ttu-id="fd845-180">**보안 관리자** 및 **검색 및** 제거 역할</span><span class="sxs-lookup"><span data-stu-id="fd845-180">**Security Administrator** plus the **Search and Purge** role</span></span></li></ul> <p> <span data-ttu-id="fd845-181">**전역 관리자**  및 보안 관리자 역할은 Azure Active Directory ( ) 또는 <https://portal.azure.com> Microsoft 365 관리 센터()로 할당할 수 <https://admin.microsoft.com> 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd845-181">The **Global Administrator** and **Security Administrator** roles can be assigned in either Azure Active Directory (<https://portal.azure.com>) or the Microsoft 365 admin center (<https://admin.microsoft.com>).</span></span> <p> <span data-ttu-id="fd845-182">검색 **및** 제거 역할은 Microsoft 36 Defender 포털의 전자 메일 & 공동 작업 **역할()에** 할당해야 <https://security.microsoft.com> 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd845-182">The **Search and Purge** role must be assigned in the **Email & collaboration roles** in the Microsoft 36 Defender portal (<https://security.microsoft.com>).</span></span>|
|<span data-ttu-id="fd845-183">Microsoft Defender for Office 365 Microsoft Defender for Endpoint와 통합</span><span class="sxs-lookup"><span data-stu-id="fd845-183">Integrate Microsoft Defender for Office 365 Plan 2 with Microsoft Defender for Endpoint</span></span> <p> <span data-ttu-id="fd845-184">MICROSOFT Defender for Office 365 Plan 2와 SIEM 서버 통합</span><span class="sxs-lookup"><span data-stu-id="fd845-184">Integrate Microsoft Defender for Office 365 Plan 2 with a SIEM server</span></span>|<span data-ttu-id="fd845-185">전역 관리자 **또는** 보안  관리자 역할() 또는 Azure Active Directory( ) 또는 <https://portal.azure.com> Microsoft 365 관리 센터( <https://admin.microsoft.com> ).</span><span class="sxs-lookup"><span data-stu-id="fd845-185">Either the **Global Administrator** or the **Security Administrator** role assigned in either Azure Active Directory (<https://portal.azure.com>) or the Microsoft 365 admin center (<https://admin.microsoft.com>).</span></span> <p> <span data-ttu-id="fd845-186">--- **plus** --- </span><span class="sxs-lookup"><span data-stu-id="fd845-186">--- **plus** --- </span></span><p> <span data-ttu-id="fd845-187">추가 응용 프로그램(예: Microsoft Defender 보안 센터 또는 SIEM [서버)에](/windows/security/threat-protection/microsoft-defender-atp/user-roles) 할당된 적절한 역할입니다.</span><span class="sxs-lookup"><span data-stu-id="fd845-187">An appropriate role assigned in additional applications (such as [Microsoft Defender Security Center](/windows/security/threat-protection/microsoft-defender-atp/user-roles) or your SIEM server).</span></span>|
|

## <a name="next-steps"></a><span data-ttu-id="fd845-188">다음 단계</span><span class="sxs-lookup"><span data-stu-id="fd845-188">Next steps</span></span>

- [<span data-ttu-id="fd845-189">위협 트래커에 대한 자세한 내용은 신규 및 주목할 만한 정보를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="fd845-189">Learn about Threat Trackers - New and Noteworthy</span></span>](threat-trackers.md)
- [<span data-ttu-id="fd845-190">배달된 악성 전자 메일 찾기 및 조사(Office 365 위협 조사 및 대응)</span><span class="sxs-lookup"><span data-stu-id="fd845-190">Find and investigate malicious email that was delivered (Office 365 Threat Investigation and Response)</span></span>](investigate-malicious-email-that-was-delivered.md)
- [<span data-ttu-id="fd845-191">위협 Office 365 및 대응을 끝점용 Microsoft Defender와 통합</span><span class="sxs-lookup"><span data-stu-id="fd845-191">Integrate Office 365 Threat Investigation and Response with Microsoft Defender for Endpoint</span></span>](integrate-office-365-ti-with-mde.md)
- [<span data-ttu-id="fd845-192">피싱 공격 시뮬레이션</span><span class="sxs-lookup"><span data-stu-id="fd845-192">Simulate a phishing attack</span></span>](attack-simulation-training.md)
