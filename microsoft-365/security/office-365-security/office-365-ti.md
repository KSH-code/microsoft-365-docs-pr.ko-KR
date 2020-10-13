---
title: 위협 조사 & 응답 기능-Office 365 ATP 계획 2
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
description: Office 365 Advanced Threat Protection 계획의 위협 조사 및 응답 기능에 대해 알아봅니다.
ms.openlocfilehash: 4d51a172c3b6fb8641648ecd7a33e320b0a42b24
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/13/2020
ms.locfileid: "48431138"
---
# <a name="threat-investigation-and-response"></a><span data-ttu-id="2c449-103">위협 조사 및 응답</span><span class="sxs-lookup"><span data-stu-id="2c449-103">Threat investigation and response</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="2c449-104">위협 조사 및 응답 기능 [Office 365 Advanced Threat Protection](office-365-atp.md) 은 다음과 같은 방법으로 보안 분석가와 관리자에 게 조직의 Microsoft 365 비즈니스 사용자를 보호 하는 데 도움을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c449-104">Threat investigation and response capabilities in [Office 365 Advanced Threat Protection](office-365-atp.md) help security analysts and administrators protect their organization's Microsoft 365 for business users by:</span></span>
- <span data-ttu-id="2c449-105">고 사이버 공격를 쉽게 식별, 모니터링 및 이해할 수 있도록 설정</span><span class="sxs-lookup"><span data-stu-id="2c449-105">Making it easy to identify, monitor, and understand cyberattacks</span></span>
- <span data-ttu-id="2c449-106">Exchange Online, SharePoint Online, 비즈니스용 OneDrive 및 Microsoft 팀의 위협에 빠르게 문제를 해결 하는 데 도움을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2c449-106">Helping to quickly address threats in Exchange Online, SharePoint Online, OneDrive for Business and Microsoft Teams</span></span>
- <span data-ttu-id="2c449-107">보안 작업에 도움이 되는 통찰력 및 지식을 제공 하 여 조직에 대 한 고 사이버 공격 방지</span><span class="sxs-lookup"><span data-stu-id="2c449-107">Providing insights and knowledge to help security operations prevent cyberattacks against their organization</span></span>
- <span data-ttu-id="2c449-108">중요 전자 메일 기반 위협에 대 한 [Office 365의 자동화 된 조사 및 응답](automated-investigation-response-office.md) 채택</span><span class="sxs-lookup"><span data-stu-id="2c449-108">Employing [automated investigation and response in Office 365](automated-investigation-response-office.md) for critical email-based threats</span></span>
    
<span data-ttu-id="2c449-109">위협 조사 및 응답 기능은 보안 및 준수 센터에서 사용할 수 있는 위협 및 관련 된 응답 작업에 대 한 정보를 제공 &amp; 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c449-109">Threat investigation and response capabilities provide insights into threats and related response actions that are available in the Security &amp; Compliance Center.</span></span> <span data-ttu-id="2c449-110">이러한 통찰력은 조직의 보안 팀이 전자 메일 또는 파일 기반 공격 으로부터 사용자를 보호 하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c449-110">These insights can help your organization's security team protect users from email- or file-based attacks.</span></span> <span data-ttu-id="2c449-111">이 기능은 사용자 활동, 인증, 전자 메일, 손상 된 Pc 및 보안 인시던트와 같은 여러 원본의 데이터를 수집 하 고 신호를 모니터링 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c449-111">The capabilities help monitor signals and gather data from multiple sources, such as user activity, authentication, email, compromised PCs, and security incidents.</span></span> <span data-ttu-id="2c449-112">비즈니스 의사 결정권자 및 보안 운영 팀은이 정보를 사용 하 여 조직에 대 한 위협을 파악 하 고 대응 하 고 지적 재산을 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c449-112">Business decision makers and your security operations team can use this information to understand and respond to threats against your organization and protect your intellectual property.</span></span>

## <a name="get-acquainted-with-threat-investigation-and-response-tools"></a><span data-ttu-id="2c449-113">위협 조사 및 응답 도구 익히기</span><span class="sxs-lookup"><span data-stu-id="2c449-113">Get acquainted with threat investigation and response tools</span></span>

<span data-ttu-id="2c449-114">보안 & 준수 센터의 위협 조사 및 응답 기능으로, 다음을 비롯 한 도구 및 응답 워크플로 집합으로 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c449-114">Threat investigation and response capabilities surface in the Security & Compliance Center, as a set of tools and response workflows, including the following:</span></span>

- [<span data-ttu-id="2c449-115">위협 대시보드</span><span class="sxs-lookup"><span data-stu-id="2c449-115">Threat dashboard</span></span>](#threat-dashboard)
- [<span data-ttu-id="2c449-116">탐색기</span><span class="sxs-lookup"><span data-stu-id="2c449-116">Explorer</span></span>](#threat-explorer)
- [<span data-ttu-id="2c449-117">인시던트</span><span class="sxs-lookup"><span data-stu-id="2c449-117">Incidents</span></span>](#incidents)
- [<span data-ttu-id="2c449-118">공격 시뮬레이터</span><span class="sxs-lookup"><span data-stu-id="2c449-118">Attack Simulator</span></span>](#attack-simulator)
- [<span data-ttu-id="2c449-119">자동화된 조사 및 응답</span><span class="sxs-lookup"><span data-stu-id="2c449-119">Automated investigation and response</span></span>](automated-investigation-response-office.md)

### <a name="threat-dashboard"></a><span data-ttu-id="2c449-120">위협 대시보드</span><span class="sxs-lookup"><span data-stu-id="2c449-120">Threat dashboard</span></span>

<span data-ttu-id="2c449-121">위협 대시보드 ( [보안 대시보드](security-dashboard.md)라고도 함)를 사용 하 여 해결 된 위협을 빠르게 확인 하 고, Microsoft 365 서비스가 비즈니스를 보호 하는 방법을 비즈니스 의사 결정권자에 게 보고 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c449-121">Use the Threat dashboard (this is also referred to as the [Security dashboard](security-dashboard.md)) to quickly see what threats have been addressed, and as a visual way to report to business decision makers how Microsoft 365 services are securing your business.</span></span>
  
![위협 대시보드](../../media/ce013a31-3f80-4d09-bb95-bfb7623b8bc4.png)
  
<span data-ttu-id="2c449-123">이 대시보드를 보고 사용 하려면 보안 및 &amp; 준수 센터에서 **위협 관리** \> **대시보드로**이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c449-123">To view and use this dashboard, in the Security &amp; Compliance Center, go to **Threat management** \> **Dashboard**.</span></span>
  
### <a name="threat-explorer"></a><span data-ttu-id="2c449-124">위협 탐색기</span><span class="sxs-lookup"><span data-stu-id="2c449-124">Threat Explorer</span></span>

<span data-ttu-id="2c449-125">위협 [탐색기 (및 실시간 검색)](threat-explorer.md) 를 사용 하 여 위협을 분석 하 고, 시간에 따른 공격 량을 확인 하 고, 위협 계열, 침입자 인프라 등을 기준으로 데이터를 분석 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c449-125">Use [Threat Explorer (and real-time detections)](threat-explorer.md) to analyze threats, see the volume of attacks over time, and analyze data by threat families, attacker infrastructure, and more.</span></span> <span data-ttu-id="2c449-126">위협 탐색기 (탐색기 라고도 함)는 모든 보안 분석가의 조사 워크플로에서 시작 되는 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="2c449-126">Threat Explorer (also referred to as Explorer) is the starting place for any security analyst's investigation workflow.</span></span>

![위협 탐색기](../../media/7a7cecee-17f0-4134-bcb8-7cee3f3c3890.png)
  
<span data-ttu-id="2c449-128">이 보고서를 보고 사용 하려면 보안 및 &amp; 준수 센터에서 **위협 관리** \> **탐색기**로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c449-128">To view and use this report, in the Security &amp; Compliance Center, go to **Threat management** \> **Explorer**.</span></span>
  
### <a name="incidents"></a><span data-ttu-id="2c449-129">인시던트</span><span class="sxs-lookup"><span data-stu-id="2c449-129">Incidents</span></span>

<span data-ttu-id="2c449-130">문제 목록 (조사가 라고도 함)을 사용 하 여 비행 보안 인시던트 목록을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c449-130">Use the Incidents list (this is also called Investigations) to see a list of in flight security incidents.</span></span> <span data-ttu-id="2c449-131">인시던트는 의심 스러운 전자 메일 메시지와 같은 위협을 추적 하 고 추가 조사 및 수정을 수행 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c449-131">Incidents are used to track threats such as suspicious email messages, and to conduct further investigation and remediation.</span></span>

![Office 365의 현재 위협 인시던트 목록](../../media/acadd4c7-d2de-4146-aeb8-90cfad805a9c.png)

<span data-ttu-id="2c449-133">조직의 현재 인시던트 목록을 보려면 보안 & 준수 센터에서 **위협 관리** \> **검토** \> **인시던트**로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c449-133">To view the list of current incidents for your organization, in the Security & Compliance Center, go to **Threat management** \> **Review** \> **Incidents**.</span></span>

![보안 & 준수 센터에서 위협 관리 검토를 선택 합니다. \>](../../media/e0f46454-fa38-40f0-a120-b595614d1d22.png)

### <a name="attack-simulator"></a><span data-ttu-id="2c449-135">공격 시뮬레이터</span><span class="sxs-lookup"><span data-stu-id="2c449-135">Attack Simulator</span></span>

<span data-ttu-id="2c449-136">공격 시뮬레이터를 사용 하 여 조직에서 현실적인 고 사이버 공격를 설정 및 실행 하 고, 실제에서는 사이버 공격과 비즈니스에 영향을 주기 전에 취약 한 사용자를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c449-136">Use Attack Simulator to set up and run realistic cyberattacks in your organization, and identify vulnerable people before a real cyberattack affects your business.</span></span> <span data-ttu-id="2c449-137">자세한 내용은 [Office 365의 Attack 시뮬레이터](attack-simulator.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2c449-137">To learn more, see [Attack Simulator in Office 365](attack-simulator.md).</span></span>

### <a name="automated-investigation-and-response"></a><span data-ttu-id="2c449-138">자동화된 조사 및 응답</span><span class="sxs-lookup"><span data-stu-id="2c449-138">Automated investigation and response</span></span>

<span data-ttu-id="2c449-139">자동화 된 조사 및 응답 (AIR) 기능을 사용 하 여 조직의 위협 으로부터 발생 하는 콘텐츠, 장치 및 사용자와 관련 된 시간과 노력을 절감할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c449-139">Use automated investigation and response (AIR) capabilities to save time and effort correlating content, devices, and people at risk from threats in your organization.</span></span> <span data-ttu-id="2c449-140">AIR 프로세스는 특정 알림이 트리거될 때 또는 보안 운영 팀이 시작 될 때 시작 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c449-140">AIR processes can begin whenever certain alerts are triggered, or when started by your security operations team.</span></span> <span data-ttu-id="2c449-141">자세한 내용은 [Office 365의 자동화 된 조사 및 응답](automated-investigation-response-office.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2c449-141">To learn more, see [automated investigation and response in Office 365](automated-investigation-response-office.md).</span></span>

## <a name="threat-intelligence-widgets"></a><span data-ttu-id="2c449-142">위협 인텔리전스 위젯</span><span class="sxs-lookup"><span data-stu-id="2c449-142">Threat intelligence widgets</span></span>

<span data-ttu-id="2c449-143">보안 분석가는 Office 365 Advanced Threat Protection 계획 2 제공의 일부로 알려진 위협에 대 한 세부 정보를 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c449-143">As part of the Office 365 Advanced Threat Protection Plan 2 offering, security analysts can review details about a known threat.</span></span> <span data-ttu-id="2c449-144">이 기능은 사용자가 안전 하 게 유지 하기 위해 수행할 수 있는 추가 예방 조치/단계가 있는지 여부를 확인 하는 데 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c449-144">This is useful to determine whether there are additional preventative measures/steps that can be taken to keep users safe.</span></span>

![최근 위협에 대 한 정보를 보여 주는 보안 경향](../../media/11e7d40d-139b-4c56-8d52-c091c8654151.png)

## <a name="how-do-we-get-these-capabilities"></a><span data-ttu-id="2c449-146">이러한 기능은 어떻게 얻을 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="2c449-146">How do we get these capabilities?</span></span>

<span data-ttu-id="2c449-147">Microsoft 365 위협 조사 및 응답 기능은 Enterprise E5에 포함 되거나 특정 구독에 대 한 추가 기능으로 제공 되는 Office 365 Advanced Threat Protection 계획 2에 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c449-147">Microsoft 365 threat investigation and response capabilities are included in Office 365 Advanced Threat Protection Plan 2, which is included in Enterprise E5 or as an add-on to certain subscriptions.</span></span> <span data-ttu-id="2c449-148">자세한 내용은 [Office 365 ATP 계획 1 및 계획 2](office-365-atp.md#office-365-atp-plan-1-and-plan-2)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2c449-148">To learn more, see [Office 365 ATP Plan 1 and Plan 2](office-365-atp.md#office-365-atp-plan-1-and-plan-2).</span></span>

## <a name="required-roles-and-permissions"></a><span data-ttu-id="2c449-149">필요한 역할 및 사용 권한 할당</span><span class="sxs-lookup"><span data-stu-id="2c449-149">Required roles and permissions</span></span>

<span data-ttu-id="2c449-150">Office 365 Advanced Threat Protection은 역할 기반 액세스 제어를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c449-150">Office 365 Advanced Threat Protection uses role-based access control.</span></span> <span data-ttu-id="2c449-151">사용 권한은 Azure Active Directory의 특정 역할, Microsoft 365 관리 센터 또는 보안 & 준수 센터를 통해 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c449-151">Permissions are assigned through certain roles in Azure Active Directory, the Microsoft 365 admin center, or the Security & Compliance Center.</span></span>

> [!TIP]
> <span data-ttu-id="2c449-152">보안 관리자와 같은 일부 역할은 보안 & 준수 센터에서 할당할 수 있지만 대신 Microsoft 365 관리 센터 또는 Azure Active Directory를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="2c449-152">Although some roles, such as Security Administrator, can be assigned in the Security & Compliance Center, consider using either the Microsoft 365 admin center or Azure Active Directory instead.</span></span> <span data-ttu-id="2c449-153">역할, 역할 그룹 및 권한에 대 한 자세한 내용은 다음 리소스를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="2c449-153">For information about roles, role groups, and permissions, see the following resources:</span></span>
>
> - [<span data-ttu-id="2c449-154">보안 및 준수 센터의 사용 권한 &amp;</span><span class="sxs-lookup"><span data-stu-id="2c449-154">Permissions in the Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
>
> - [<span data-ttu-id="2c449-155">Azure Active Directory의 관리자 역할 권한</span><span class="sxs-lookup"><span data-stu-id="2c449-155">Administrator role permissions in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)

****

|<span data-ttu-id="2c449-156">활동</span><span class="sxs-lookup"><span data-stu-id="2c449-156">Activity</span></span>|<span data-ttu-id="2c449-157">역할 및 사용 권한</span><span class="sxs-lookup"><span data-stu-id="2c449-157">Roles and permissions</span></span>|
|---|---|
|<span data-ttu-id="2c449-158">위협 대시보드 (또는 새 [보안 대시보드](security-dashboard.md)) 사용</span><span class="sxs-lookup"><span data-stu-id="2c449-158">Use the Threat dashboard (or the new [Security dashboard](security-dashboard.md))</span></span><br/> <br/><span data-ttu-id="2c449-159">최근 또는 현재 위협에 대 한 정보 보기</span><span class="sxs-lookup"><span data-stu-id="2c449-159">View information about recent or current threats</span></span>|<span data-ttu-id="2c449-160">다음 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="2c449-160">One of the following:</span></span> <br/><span data-ttu-id="2c449-161">- **전역 관리자**</span><span class="sxs-lookup"><span data-stu-id="2c449-161">- **Global Administrator**</span></span>  <br/> <span data-ttu-id="2c449-162">- **보안 관리자**</span><span class="sxs-lookup"><span data-stu-id="2c449-162">- **Security Administrator**</span></span> <br/><span data-ttu-id="2c449-163">- **보안 독자**</span><span class="sxs-lookup"><span data-stu-id="2c449-163">- **Security Reader**</span></span> <br/> <br/><span data-ttu-id="2c449-164">이러한 역할은 Azure Active Directory ( [https://portal.azure.com](https://portal.azure.com) ) 또는 Microsoft 365 관리 센터 ()에서 할당할 수 있습니다 [https://admin.microsoft.com](https://admin.microsoft.com) .</span><span class="sxs-lookup"><span data-stu-id="2c449-164">These roles can be assigned in either Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) or the Microsoft 365 admin center ([https://admin.microsoft.com](https://admin.microsoft.com)).</span></span>|
|<span data-ttu-id="2c449-165">[위협 탐색기 (및 실시간 검색)](threat-explorer.md) 를 사용 하 여 위협 분석</span><span class="sxs-lookup"><span data-stu-id="2c449-165">Use [Threat Explorer (and real-time detections)](threat-explorer.md) to analyze threats</span></span>|<span data-ttu-id="2c449-166">다음 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="2c449-166">One of the following:</span></span> <br/><span data-ttu-id="2c449-167">- **전역 관리자**</span><span class="sxs-lookup"><span data-stu-id="2c449-167">- **Global Administrator**</span></span>  <br/> <span data-ttu-id="2c449-168">- **보안 관리자**</span><span class="sxs-lookup"><span data-stu-id="2c449-168">- **Security Administrator**</span></span> <br/><span data-ttu-id="2c449-169">- **보안 독자**</span><span class="sxs-lookup"><span data-stu-id="2c449-169">- **Security Reader**</span></span> <br/> <br/><span data-ttu-id="2c449-170">이러한 역할은 Azure Active Directory ( [https://portal.azure.com](https://portal.azure.com) ) 또는 Microsoft 365 관리 센터 ()에서 할당할 수 있습니다 [https://admin.microsoft.com](https://admin.microsoft.com) .</span><span class="sxs-lookup"><span data-stu-id="2c449-170">These roles can be assigned in either Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) or the Microsoft 365 admin center ([https://admin.microsoft.com](https://admin.microsoft.com)).</span></span>|
|<span data-ttu-id="2c449-171">인시던트 보기 (조사가 라고도 함)</span><span class="sxs-lookup"><span data-stu-id="2c449-171">View Incidents (also referred to as Investigations)</span></span> <br/> <span data-ttu-id="2c449-172">인시던트에 전자 메일 메시지 추가</span><span class="sxs-lookup"><span data-stu-id="2c449-172">Add email messages to an incident</span></span>|<span data-ttu-id="2c449-173">다음 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="2c449-173">One of the following:</span></span> <br/><span data-ttu-id="2c449-174">- **전역 관리자**</span><span class="sxs-lookup"><span data-stu-id="2c449-174">- **Global Administrator**</span></span>  <br/> <span data-ttu-id="2c449-175">- **보안 관리자**</span><span class="sxs-lookup"><span data-stu-id="2c449-175">- **Security Administrator**</span></span> <br/><span data-ttu-id="2c449-176">- **보안 독자**</span><span class="sxs-lookup"><span data-stu-id="2c449-176">- **Security Reader**</span></span> <br/> <br/><span data-ttu-id="2c449-177">이러한 역할은 Azure Active Directory ( [https://portal.azure.com](https://portal.azure.com) ) 또는 Microsoft 365 관리 센터 ()에서 할당할 수 있습니다 [https://admin.microsoft.com](https://admin.microsoft.com) .</span><span class="sxs-lookup"><span data-stu-id="2c449-177">These roles can be assigned in either Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) or the Microsoft 365 admin center ([https://admin.microsoft.com](https://admin.microsoft.com)).</span></span>|
|<span data-ttu-id="2c449-178">인시던트에서 전자 메일 작업 트리거</span><span class="sxs-lookup"><span data-stu-id="2c449-178">Trigger email actions in an incident</span></span> <br/> <br/> <span data-ttu-id="2c449-179">의심 스러운 전자 메일 메시지 찾기 및 삭제</span><span class="sxs-lookup"><span data-stu-id="2c449-179">Find and delete suspicious email messages</span></span>|<span data-ttu-id="2c449-180">다음 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="2c449-180">One of the following:</span></span> <br/><span data-ttu-id="2c449-181">- **전역 관리자**</span><span class="sxs-lookup"><span data-stu-id="2c449-181">- **Global Administrator**</span></span>  <br/> <span data-ttu-id="2c449-182">- **보안 관리자** 와 **검색 및 제거** 역할</span><span class="sxs-lookup"><span data-stu-id="2c449-182">- **Security Administrator** plus the **Search and Purge** role</span></span><br/><br/><span data-ttu-id="2c449-183">**전역 관리자** 및 **보안 관리자** 역할은 Azure Active Directory ( [https://portal.azure.com](https://portal.azure.com) ) 또는 Microsoft 365 관리 센터 ()에서 할당 될 수 있습니다 [https://admin.microsoft.com](https://admin.microsoft.com) .</span><span class="sxs-lookup"><span data-stu-id="2c449-183">The **Global Administrator** and **Security Administrator** roles can be assigned in either Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) or the Microsoft 365 admin center ([https://admin.microsoft.com](https://admin.microsoft.com)).</span></span> <br/><br/><span data-ttu-id="2c449-184">**검색 및 제거** 역할은 Security & 준수 센터 ()에서 할당 되어야 합니다 [https://protection.office.com](https://protection.office.com) .</span><span class="sxs-lookup"><span data-stu-id="2c449-184">The **Search and Purge** role must be assigned in the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)).</span></span>|
|<span data-ttu-id="2c449-185">Microsoft Defender Advanced Threat Protection과 Office 365 Advanced Threat Protection 계획 2 통합</span><span class="sxs-lookup"><span data-stu-id="2c449-185">Integrate Office 365 Advanced Threat Protection Plan 2 with Microsoft Defender Advanced Threat Protection</span></span>  <br/><br/> <span data-ttu-id="2c449-186">SIEM 서버를 사용 하 여 Office 365 Advanced Threat Protection 계획 2 통합</span><span class="sxs-lookup"><span data-stu-id="2c449-186">Integrate Office 365 Advanced Threat Protection Plan 2 with a SIEM server</span></span>|<span data-ttu-id="2c449-187">Azure Active Directory () 또는 Microsoft 365 관리 센터 ()에서 할당 된 **전역 관리자** 또는 **보안 관리자** 역할 [https://portal.azure.com](https://portal.azure.com) [https://admin.microsoft.com](https://admin.microsoft.com) 입니다.</span><span class="sxs-lookup"><span data-stu-id="2c449-187">Either the **Global Administrator** or the **Security Administrator** role assigned in either Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) or the Microsoft 365 admin center ([https://admin.microsoft.com](https://admin.microsoft.com)).</span></span><br/><span data-ttu-id="2c449-188">--- **기호** ---</span><span class="sxs-lookup"><span data-stu-id="2c449-188">--- **plus** ---</span></span><br/><span data-ttu-id="2c449-189">추가 응용 프로그램에서 할당 되는 적절 한 역할 (예: [Microsoft Defender Security Center](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles) 또는 siem server)</span><span class="sxs-lookup"><span data-stu-id="2c449-189">An appropriate role assigned in additional applications (such as [Microsoft Defender Security Center](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles) or your SIEM server)</span></span>|
|

## <a name="next-steps"></a><span data-ttu-id="2c449-190">다음 단계</span><span class="sxs-lookup"><span data-stu-id="2c449-190">Next steps</span></span>

- [<span data-ttu-id="2c449-191">위협 추적기에 대해 알아보기-신규 및 중요</span><span class="sxs-lookup"><span data-stu-id="2c449-191">Learn about Threat Trackers - New and Noteworthy</span></span>](threat-trackers.md)

- [<span data-ttu-id="2c449-192">배달 된 악성 전자 메일 찾기 및 조사 (Office 365 위협 조사 및 응답)</span><span class="sxs-lookup"><span data-stu-id="2c449-192">Find and investigate malicious email that was delivered (Office 365 Threat Investigation and Response)</span></span>](investigate-malicious-email-that-was-delivered.md)

- [<span data-ttu-id="2c449-193">Microsoft Defender Advanced Threat Protection을 사용 하 여 Office 365 위협 조사 및 응답 통합</span><span class="sxs-lookup"><span data-stu-id="2c449-193">Integrate Office 365 Threat Investigation and Response with Microsoft Defender Advanced Threat Protection</span></span>](integrate-office-365-ti-with-wdatp.md)

- [<span data-ttu-id="2c449-194">공격 시뮬레이터에 대 한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="2c449-194">Learn about Attack Simulator</span></span>](attack-simulator.md)
