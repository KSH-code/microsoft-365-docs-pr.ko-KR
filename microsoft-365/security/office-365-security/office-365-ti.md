---
title: 위협 조사 & 대응 기능 - Office 365 계획 2용 Microsoft Defender
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 12/09/2019
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 32405da5-bee1-4a4b-82e5-8399df94c512
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.custom:
- seo-marvel-apr2020
description: Office 365 계획용 Microsoft Defender의 위협 조사 및 대응 기능에 대해 자세히 알아보는 방법을 설명하는 정보를 제공합니다.
ms.openlocfilehash: cbda50dacd6b892c976ce55632c8fc35813839b7
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2020
ms.locfileid: "49614777"
---
# <a name="threat-investigation-and-response"></a><span data-ttu-id="42ff5-103">위협 조사 및 응답</span><span class="sxs-lookup"><span data-stu-id="42ff5-103">Threat investigation and response</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="42ff5-104">[Office 365용 Microsoft Defender의](office-365-atp.md) 위협 조사 및 대응 기능은 보안 분석가 및 관리자가 다음을 통해 조직의 비즈니스용 Microsoft 365 사용자를 보호하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="42ff5-104">Threat investigation and response capabilities in [Microsoft Defender for Office 365](office-365-atp.md) help security analysts and administrators protect their organization's Microsoft 365 for business users by:</span></span>

- <span data-ttu-id="42ff5-105">사이버 공격을 쉽게 식별, 모니터링 및 이해</span><span class="sxs-lookup"><span data-stu-id="42ff5-105">Making it easy to identify, monitor, and understand cyberattacks</span></span>
- <span data-ttu-id="42ff5-106">Exchange Online, SharePoint Online, 비즈니스용 OneDrive 및 Microsoft Teams에서 위협을 빠르게 해결</span><span class="sxs-lookup"><span data-stu-id="42ff5-106">Helping to quickly address threats in Exchange Online, SharePoint Online, OneDrive for Business and Microsoft Teams</span></span>
- <span data-ttu-id="42ff5-107">보안 운영에서 조직에 대한 사이버 공격을 방지하는 데 도움이 되는 인사이트 및 지식 제공</span><span class="sxs-lookup"><span data-stu-id="42ff5-107">Providing insights and knowledge to help security operations prevent cyberattacks against their organization</span></span>
- <span data-ttu-id="42ff5-108">Office [365에서](automated-investigation-response-office.md) 중요한 전자 메일 기반 위협에 대한 자동화된 조사 및 대응 사용</span><span class="sxs-lookup"><span data-stu-id="42ff5-108">Employing [automated investigation and response in Office 365](automated-investigation-response-office.md) for critical email-based threats</span></span>

<span data-ttu-id="42ff5-109">위협 조사 및 대응 기능은 보안 및 준수 센터에서 사용할 수 있는 위협 및 관련 & 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="42ff5-109">Threat investigation and response capabilities provide insights into threats and related response actions that are available in the Security & Compliance Center.</span></span> <span data-ttu-id="42ff5-110">이러한 인사이트는 조직의 보안 팀이 전자 메일 또는 파일 기반 공격으로부터 사용자를 보호하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42ff5-110">These insights can help your organization's security team protect users from email- or file-based attacks.</span></span> <span data-ttu-id="42ff5-111">이 기능은 신호를 모니터링하고 사용자 활동, 인증, 전자 메일, 손상된 PC 및 보안 인시던트와 같은 여러 원본에서 데이터를 수집하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="42ff5-111">The capabilities help monitor signals and gather data from multiple sources, such as user activity, authentication, email, compromised PCs, and security incidents.</span></span> <span data-ttu-id="42ff5-112">비즈니스 의사 결정권자 및 보안 운영 팀은 이 정보를 사용하여 조직에 대한 위협을 이해하고 대응하고 지적 재산을 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42ff5-112">Business decision makers and your security operations team can use this information to understand and respond to threats against your organization and protect your intellectual property.</span></span>

## <a name="get-acquainted-with-threat-investigation-and-response-tools"></a><span data-ttu-id="42ff5-113">위협 조사 및 응답 도구에 대해 잘 아는 경우</span><span class="sxs-lookup"><span data-stu-id="42ff5-113">Get acquainted with threat investigation and response tools</span></span>

<span data-ttu-id="42ff5-114">위협 조사 및 대응 기능은 보안 & 준수 센터에 다음과 같은 도구 및 응답 워크플로 집합으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="42ff5-114">Threat investigation and response capabilities surface in the Security & Compliance Center, as a set of tools and response workflows, including the following:</span></span>

- [<span data-ttu-id="42ff5-115">위협 대시보드</span><span class="sxs-lookup"><span data-stu-id="42ff5-115">Threat dashboard</span></span>](#threat-dashboard)
- [<span data-ttu-id="42ff5-116">탐색기</span><span class="sxs-lookup"><span data-stu-id="42ff5-116">Explorer</span></span>](#threat-explorer)
- [<span data-ttu-id="42ff5-117">인시던트</span><span class="sxs-lookup"><span data-stu-id="42ff5-117">Incidents</span></span>](#incidents)
- [<span data-ttu-id="42ff5-118">공격 시뮬레이터</span><span class="sxs-lookup"><span data-stu-id="42ff5-118">Attack Simulator</span></span>](#attack-simulator)
- [<span data-ttu-id="42ff5-119">자동화된 조사 및 응답</span><span class="sxs-lookup"><span data-stu-id="42ff5-119">Automated investigation and response</span></span>](automated-investigation-response-office.md)

### <a name="threat-dashboard"></a><span data-ttu-id="42ff5-120">위협 대시보드</span><span class="sxs-lookup"><span data-stu-id="42ff5-120">Threat dashboard</span></span>

<span data-ttu-id="42ff5-121">위협 대시보드(보안 대시보드라고도 지칭)를 사용하여 해결된 위협을 빠르게 확인할 수 있으며, Microsoft 365 서비스가 비즈니스를 보호하는 방법을 비즈니스 의사 결정권자에게 시각적으로 보고할 수 있습니다. [](security-dashboard.md)</span><span class="sxs-lookup"><span data-stu-id="42ff5-121">Use the Threat dashboard (this is also referred to as the [Security dashboard](security-dashboard.md)) to quickly see what threats have been addressed, and as a visual way to report to business decision makers how Microsoft 365 services are securing your business.</span></span>

![위협 대시보드](../../media/ce013a31-3f80-4d09-bb95-bfb7623b8bc4.png)

<span data-ttu-id="42ff5-123">이 대시보드를 보고 사용하세요. 보안 및 준수 & 위협 관리 **대시보드로** \> **이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="42ff5-123">To view and use this dashboard, in the Security & Compliance Center, go to **Threat management** \> **Dashboard**.</span></span>

### <a name="threat-explorer"></a><span data-ttu-id="42ff5-124">위협 탐색기</span><span class="sxs-lookup"><span data-stu-id="42ff5-124">Threat Explorer</span></span>

<span data-ttu-id="42ff5-125">위협 탐색기(및 [실시간](threat-explorer.md) 검색)를 사용하여 위협을 분석하고, 시간의 따라 공격의 양을 보고, 위협 패밀리, 공격자 인프라 등에서 데이터를 분석합니다.</span><span class="sxs-lookup"><span data-stu-id="42ff5-125">Use [Threat Explorer (and real-time detections)](threat-explorer.md) to analyze threats, see the volume of attacks over time, and analyze data by threat families, attacker infrastructure, and more.</span></span> <span data-ttu-id="42ff5-126">위협 탐색기(탐색기라고도 지칭)는 보안 분석가의 조사 워크플로를 위한 시작점입니다.</span><span class="sxs-lookup"><span data-stu-id="42ff5-126">Threat Explorer (also referred to as Explorer) is the starting place for any security analyst's investigation workflow.</span></span>

![위협 탐색기](../../media/7a7cecee-17f0-4134-bcb8-7cee3f3c3890.png)

<span data-ttu-id="42ff5-128">이 보고서를 보고 사용하려면 보안 및 준수 & 위협 관리 **탐색기로** \> **이동해야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="42ff5-128">To view and use this report, in the Security & Compliance Center, go to **Threat management** \> **Explorer**.</span></span>

### <a name="incidents"></a><span data-ttu-id="42ff5-129">인시던트</span><span class="sxs-lookup"><span data-stu-id="42ff5-129">Incidents</span></span>

<span data-ttu-id="42ff5-130">인시던트 목록(조사라고도 합니다)을 사용하여 진행 보안 인시던트 목록을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42ff5-130">Use the Incidents list (this is also called Investigations) to see a list of in flight security incidents.</span></span> <span data-ttu-id="42ff5-131">인시던트는 의심스러운 전자 메일 메시지와 같은 위협을 추적하고 추가 조사 및 수정을 수행하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="42ff5-131">Incidents are used to track threats such as suspicious email messages, and to conduct further investigation and remediation.</span></span>

![Office 365의 현재 위협 인시던트 목록](../../media/acadd4c7-d2de-4146-aeb8-90cfad805a9c.png)

<span data-ttu-id="42ff5-133">조직의 현재 인시던트 목록을 확인하면 보안 및 준수 & 위협 **관리** 검토 인시던트로 \>  \> **이동하십시오.**</span><span class="sxs-lookup"><span data-stu-id="42ff5-133">To view the list of current incidents for your organization, in the Security & Compliance Center, go to **Threat management** \> **Review** \> **Incidents**.</span></span>

![보안 및 & 센터에서 위협 관리 \> 검토를 선택](../../media/e0f46454-fa38-40f0-a120-b595614d1d22.png)

### <a name="attack-simulator"></a><span data-ttu-id="42ff5-135">공격 시뮬레이터</span><span class="sxs-lookup"><span data-stu-id="42ff5-135">Attack Simulator</span></span>

<span data-ttu-id="42ff5-136">공격 시뮬레이터를 사용하여 조직에서 현실적인 사이버 공격을 설정하고 실행하고 실제 사이버 공격이 비즈니스에 영향을 미치기 전에 취약한 사용자 식별</span><span class="sxs-lookup"><span data-stu-id="42ff5-136">Use Attack Simulator to set up and run realistic cyberattacks in your organization, and identify vulnerable people before a real cyberattack affects your business.</span></span> <span data-ttu-id="42ff5-137">자세한 내용은 [Office 365의 공격 시뮬레이터를 참조하세요.](attack-simulator.md)</span><span class="sxs-lookup"><span data-stu-id="42ff5-137">To learn more, see [Attack Simulator in Office 365](attack-simulator.md).</span></span>

### <a name="automated-investigation-and-response"></a><span data-ttu-id="42ff5-138">자동화된 조사 및 응답</span><span class="sxs-lookup"><span data-stu-id="42ff5-138">Automated investigation and response</span></span>

<span data-ttu-id="42ff5-139">자동화된 조사 및 대응(AIR) 기능을 사용하여 조직에서 위협으로부터 콘텐츠, 장치 및 사용자와 관련한 시간과 노력을 절약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42ff5-139">Use automated investigation and response (AIR) capabilities to save time and effort correlating content, devices, and people at risk from threats in your organization.</span></span> <span data-ttu-id="42ff5-140">AIR 프로세스는 특정 경고가 트리거될 때마다 또는 보안 운영 팀에서 시작할 때 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42ff5-140">AIR processes can begin whenever certain alerts are triggered, or when started by your security operations team.</span></span> <span data-ttu-id="42ff5-141">자세한 내용은 [Office 365의](automated-investigation-response-office.md)자동화된 조사 및 응답을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="42ff5-141">To learn more, see [automated investigation and response in Office 365](automated-investigation-response-office.md).</span></span>

## <a name="threat-intelligence-widgets"></a><span data-ttu-id="42ff5-142">위협 인텔리전스 위젯</span><span class="sxs-lookup"><span data-stu-id="42ff5-142">Threat intelligence widgets</span></span>

<span data-ttu-id="42ff5-143">Microsoft Defender for Office 365 계획 2 제공의 일부로 보안 분석가가 알려진 위협에 대한 세부 정보를 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42ff5-143">As part of the Microsoft Defender for Office 365 Plan 2 offering, security analysts can review details about a known threat.</span></span> <span data-ttu-id="42ff5-144">이는 사용자를 안전하게 유지하기 위해 추가로 예방 조치/단계가 있는지 여부를 확인하는 데 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="42ff5-144">This is useful to determine whether there are additional preventative measures/steps that can be taken to keep users safe.</span></span>

![최근 위협에 대한 정보를 보여주는 보안 추세](../../media/11e7d40d-139b-4c56-8d52-c091c8654151.png)

## <a name="how-do-we-get-these-capabilities"></a><span data-ttu-id="42ff5-146">이러한 기능을 어떻게 얻을 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="42ff5-146">How do we get these capabilities?</span></span>

<span data-ttu-id="42ff5-147">Microsoft 365 위협 조사 및 응답 기능은 Enterprise E5 또는 특정 구독의 추가 기능으로 포함된 Microsoft Defender for Office 365 계획 2에 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42ff5-147">Microsoft 365 threat investigation and response capabilities are included in Microsoft Defender for Office 365 Plan 2, which is included in Enterprise E5 or as an add-on to certain subscriptions.</span></span> <span data-ttu-id="42ff5-148">자세한 내용은 Office 365 계획 1 및 계획 [2용 Defender를 참조합니다.](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2)</span><span class="sxs-lookup"><span data-stu-id="42ff5-148">To learn more, see [Defender for Office 365 Plan 1 and Plan 2](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2).</span></span>

## <a name="required-roles-and-permissions"></a><span data-ttu-id="42ff5-149">필요한 역할 및 사용 권한 할당</span><span class="sxs-lookup"><span data-stu-id="42ff5-149">Required roles and permissions</span></span>

<span data-ttu-id="42ff5-150">Office 365용 Microsoft Defender는 역할 기반 액세스 제어를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="42ff5-150">Microsoft Defender for Office 365 uses role-based access control.</span></span> <span data-ttu-id="42ff5-151">사용 권한은 Azure Active Directory, Microsoft 365 관리 센터 또는 보안 및 준수 센터의 특정 역할을 & 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="42ff5-151">Permissions are assigned through certain roles in Azure Active Directory, the Microsoft 365 admin center, or the Security & Compliance Center.</span></span>

> [!TIP]
> <span data-ttu-id="42ff5-152">보안 관리자와 같은 일부 역할은 보안 및 준수 센터에서 할당할 수 & Microsoft 365 관리 센터 또는 Azure Active Directory를 대신 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="42ff5-152">Although some roles, such as Security Administrator, can be assigned in the Security & Compliance Center, consider using either the Microsoft 365 admin center or Azure Active Directory instead.</span></span> <span data-ttu-id="42ff5-153">역할, 역할 그룹 및 사용 권한에 대한 자세한 내용은 다음 리소스를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="42ff5-153">For information about roles, role groups, and permissions, see the following resources:</span></span>
>
> - [<span data-ttu-id="42ff5-154">보안 및 준수 센터의 사용 권한</span><span class="sxs-lookup"><span data-stu-id="42ff5-154">Permissions in the Security & Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
>
> - [<span data-ttu-id="42ff5-155">Azure Active Directory의 관리자 역할 권한</span><span class="sxs-lookup"><span data-stu-id="42ff5-155">Administrator role permissions in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)

****

|<span data-ttu-id="42ff5-156">활동</span><span class="sxs-lookup"><span data-stu-id="42ff5-156">Activity</span></span>|<span data-ttu-id="42ff5-157">역할 및 사용 권한</span><span class="sxs-lookup"><span data-stu-id="42ff5-157">Roles and permissions</span></span>|
|---|---|
|<span data-ttu-id="42ff5-158">위협 대시보드(또는 새 [보안](security-dashboard.md)대시보드) 사용</span><span class="sxs-lookup"><span data-stu-id="42ff5-158">Use the Threat dashboard (or the new [Security dashboard](security-dashboard.md))</span></span> <p> <span data-ttu-id="42ff5-159">최근 또는 현재 위협에 대한 정보 보기</span><span class="sxs-lookup"><span data-stu-id="42ff5-159">View information about recent or current threats</span></span>|<span data-ttu-id="42ff5-160">다음 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="42ff5-160">One of the following:</span></span> <ul><li><span data-ttu-id="42ff5-161">**전역 관리자**</span><span class="sxs-lookup"><span data-stu-id="42ff5-161">**Global Administrator**</span></span></li><li><span data-ttu-id="42ff5-162">**보안 관리자**</span><span class="sxs-lookup"><span data-stu-id="42ff5-162">**Security Administrator**</span></span></li><li><span data-ttu-id="42ff5-163">**보안 읽기**</span><span class="sxs-lookup"><span data-stu-id="42ff5-163">**Security Reader**</span></span></li></ul> <p> <span data-ttu-id="42ff5-164">이러한 역할은 Azure Active Directory() 또는 Microsoft 365 관리 센터()에서 할당할 <https://portal.azure.com> 수 <https://admin.microsoft.com> 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42ff5-164">These roles can be assigned in either Azure Active Directory (<https://portal.azure.com>) or the Microsoft 365 admin center (<https://admin.microsoft.com>).</span></span>|
|<span data-ttu-id="42ff5-165">[위협 탐색기(및 실시간 검색)를](threat-explorer.md) 사용하여 위협 분석</span><span class="sxs-lookup"><span data-stu-id="42ff5-165">Use [Threat Explorer (and real-time detections)](threat-explorer.md) to analyze threats</span></span>|<span data-ttu-id="42ff5-166">다음 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="42ff5-166">One of the following:</span></span> <ul><li><span data-ttu-id="42ff5-167">**전역 관리자**</span><span class="sxs-lookup"><span data-stu-id="42ff5-167">**Global Administrator**</span></span></li><li><span data-ttu-id="42ff5-168">**보안 관리자**</span><span class="sxs-lookup"><span data-stu-id="42ff5-168">**Security Administrator**</span></span></li><li><span data-ttu-id="42ff5-169">**보안 읽기**</span><span class="sxs-lookup"><span data-stu-id="42ff5-169">**Security Reader**</span></span></li></ul> <p> <span data-ttu-id="42ff5-170">이러한 역할은 Azure Active Directory() 또는 Microsoft 365 관리 센터()에서 할당할 <https://portal.azure.com> 수 <https://admin.microsoft.com> 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42ff5-170">These roles can be assigned in either Azure Active Directory (<https://portal.azure.com>) or the Microsoft 365 admin center (<https://admin.microsoft.com>).</span></span>|
|<span data-ttu-id="42ff5-171">인시던트 보기(조사라고도 지칭)</span><span class="sxs-lookup"><span data-stu-id="42ff5-171">View Incidents (also referred to as Investigations)</span></span> <p> <span data-ttu-id="42ff5-172">인시던트에 전자 메일 메시지 추가</span><span class="sxs-lookup"><span data-stu-id="42ff5-172">Add email messages to an incident</span></span>|<span data-ttu-id="42ff5-173">다음 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="42ff5-173">One of the following:</span></span> <ul><li><span data-ttu-id="42ff5-174">**전역 관리자**</span><span class="sxs-lookup"><span data-stu-id="42ff5-174">**Global Administrator**</span></span></li><li><span data-ttu-id="42ff5-175">**보안 관리자**</span><span class="sxs-lookup"><span data-stu-id="42ff5-175">**Security Administrator**</span></span></li><li><span data-ttu-id="42ff5-176">**보안 읽기**</span><span class="sxs-lookup"><span data-stu-id="42ff5-176">**Security Reader**</span></span></li></ul> <p> <span data-ttu-id="42ff5-177">이러한 역할은 Azure Active Directory() 또는 Microsoft 365 관리 센터()에서 할당할 <https://portal.azure.com> 수 <https://admin.microsoft.com> 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42ff5-177">These roles can be assigned in either Azure Active Directory (<https://portal.azure.com>) or the Microsoft 365 admin center (<https://admin.microsoft.com>).</span></span>|
|<span data-ttu-id="42ff5-178">인시던트에서 전자 메일 작업 트리거</span><span class="sxs-lookup"><span data-stu-id="42ff5-178">Trigger email actions in an incident</span></span> <p> <span data-ttu-id="42ff5-179">의심스러운 전자 메일 메시지 찾기 및 삭제</span><span class="sxs-lookup"><span data-stu-id="42ff5-179">Find and delete suspicious email messages</span></span>|<span data-ttu-id="42ff5-180">다음 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="42ff5-180">One of the following:</span></span> <ul><li><span data-ttu-id="42ff5-181">**전역 관리자**</span><span class="sxs-lookup"><span data-stu-id="42ff5-181">**Global Administrator**</span></span></li><li><span data-ttu-id="42ff5-182">**보안 관리자** 및 **검색 및 제거 역할**</span><span class="sxs-lookup"><span data-stu-id="42ff5-182">**Security Administrator** plus the **Search and Purge** role</span></span></li></ul> <p> <span data-ttu-id="42ff5-183">전역 **관리자** **및** 보안 관리자 역할은 Azure Active Directory() 또는 Microsoft 365 관리 센터()에서 할당할 <https://portal.azure.com> 수 <https://admin.microsoft.com> 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42ff5-183">The **Global Administrator** and **Security Administrator** roles can be assigned in either Azure Active Directory (<https://portal.azure.com>) or the Microsoft 365 admin center (<https://admin.microsoft.com>).</span></span> <p> <span data-ttu-id="42ff5-184">검색 **및** 제거 역할은 보안 & 준수 센터()에 할당해야 <https://protection.office.com> 합니다.</span><span class="sxs-lookup"><span data-stu-id="42ff5-184">The **Search and Purge** role must be assigned in the Security & Compliance Center (<https://protection.office.com>).</span></span>|
|<span data-ttu-id="42ff5-185">Microsoft Defender for Office 365 계획 2와 끝점용 Microsoft Defender 통합</span><span class="sxs-lookup"><span data-stu-id="42ff5-185">Integrate Microsoft Defender for Office 365 Plan 2 with Microsoft Defender for Endpoint</span></span>  <p> <span data-ttu-id="42ff5-186">Microsoft Defender for Office 365 계획 2와 SIEM 서버 통합</span><span class="sxs-lookup"><span data-stu-id="42ff5-186">Integrate Microsoft Defender for Office 365 Plan 2 with a SIEM server</span></span>|<span data-ttu-id="42ff5-187">Azure Active  Directory()  또는 Microsoft 365 관리 센터()에 할당된 전역 관리자 또는 보안 관리자 <https://portal.azure.com> <https://admin.microsoft.com> 역할.</span><span class="sxs-lookup"><span data-stu-id="42ff5-187">Either the **Global Administrator** or the **Security Administrator** role assigned in either Azure Active Directory (<https://portal.azure.com>) or the Microsoft 365 admin center (<https://admin.microsoft.com>).</span></span> <p> <span data-ttu-id="42ff5-188">--- **plus** --- </span><span class="sxs-lookup"><span data-stu-id="42ff5-188">--- **plus** --- </span></span><p> <span data-ttu-id="42ff5-189">추가 응용 [프로그램(예: Microsoft Defender 보안](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles) 센터 또는 SIEM 서버)에 할당된 적절한 역할</span><span class="sxs-lookup"><span data-stu-id="42ff5-189">An appropriate role assigned in additional applications (such as [Microsoft Defender Security Center](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles) or your SIEM server).</span></span>|
|

## <a name="next-steps"></a><span data-ttu-id="42ff5-190">다음 단계</span><span class="sxs-lookup"><span data-stu-id="42ff5-190">Next steps</span></span>

- [<span data-ttu-id="42ff5-191">위협 트래커에 대한 자세한 내용은 신규 및 참고 사항</span><span class="sxs-lookup"><span data-stu-id="42ff5-191">Learn about Threat Trackers - New and Noteworthy</span></span>](threat-trackers.md)

- [<span data-ttu-id="42ff5-192">배달된 악성 전자 메일 찾기 및 조사(Office 365 위협 조사 및 대응)</span><span class="sxs-lookup"><span data-stu-id="42ff5-192">Find and investigate malicious email that was delivered (Office 365 Threat Investigation and Response)</span></span>](investigate-malicious-email-that-was-delivered.md)

- [<span data-ttu-id="42ff5-193">Office 365 위협 조사 및 대응을 끝점용 Microsoft Defender와 통합</span><span class="sxs-lookup"><span data-stu-id="42ff5-193">Integrate Office 365 Threat Investigation and Response with Microsoft Defender for Endpoint</span></span>](integrate-office-365-ti-with-wdatp.md)

- [<span data-ttu-id="42ff5-194">공격 시뮬레이터에 대해 자세히 알아보십시오.</span><span class="sxs-lookup"><span data-stu-id="42ff5-194">Learn about Attack Simulator</span></span>](attack-simulator.md)
