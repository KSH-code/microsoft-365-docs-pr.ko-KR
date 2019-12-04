---
title: Office 365 위협 조사 및 응답
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 12/03/2019
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
description: Office 365 Advanced Threat Protection의 위협 인텔리전스 기능을 통해 조직에 대 한 위협을 파악 하 고, 맬웨어, 피싱 및 기타 공격에 대처 하 고 사용자를 대신 하 여 Office 365에서 검색 한 기타 공격과 위협을 검색할 수 있는 방법을 알아봅니다. 슬라이더.
ms.openlocfilehash: 63b5579c5a3e52273064f85a901a6b592e7dd939
ms.sourcegitcommit: 8fda7852b2a5baa92b8a365865b014ea6d100bbc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "39813738"
---
# <a name="office-365-threat-investigation-and-response"></a><span data-ttu-id="ef03a-103">Office 365 위협 조사 및 응답</span><span class="sxs-lookup"><span data-stu-id="ef03a-103">Office 365 threat investigation and response</span></span>

<span data-ttu-id="ef03a-104">위협 조사 및 [Office 365 Advanced Threat Protection](office-365-atp.md) 의 응답 기능은 보안 분석가와 관리자가 조직의 Office 365 사용자를 보호 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ef03a-104">Threat investigation and response capabilities in [Office 365 Advanced Threat Protection](office-365-atp.md) help security analysts and administrators protect their organization's Office 365 users by:</span></span>
  
- <span data-ttu-id="ef03a-105">고 사이버 공격를 쉽게 식별, 모니터링 및 이해할 수 있도록 설정</span><span class="sxs-lookup"><span data-stu-id="ef03a-105">Making it easy to identify, monitor and understand cyberattacks</span></span>
    
- <span data-ttu-id="ef03a-106">Exchange Online, SharePoint Online, 비즈니스용 OneDrive 및 Microsoft 팀의 위협에 빠르게 문제를 해결 하는 데 도움을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ef03a-106">Helping to quickly address threats in Exchange Online, SharePoint Online, OneDrive for Business and Microsoft Teams</span></span>
    
- <span data-ttu-id="ef03a-107">보안 작업에 도움이 되는 통찰력 및 지식을 제공 하 여 조직에 대 한 고 사이버 공격 방지</span><span class="sxs-lookup"><span data-stu-id="ef03a-107">Providing insights and knowledge to help security operations prevent cyberattacks against their organization</span></span>

- <span data-ttu-id="ef03a-108">중요 전자 메일 기반 위협에 대 한 [자동 인시던트 응답](automated-investigation-response-office.md) 채택</span><span class="sxs-lookup"><span data-stu-id="ef03a-108">Employing [automated incident response](automated-investigation-response-office.md) for critical email-based threats</span></span>
    
<span data-ttu-id="ef03a-109">위협 조사 및 응답 기능은 Office 365 보안 &amp; 및 준수 센터에서 사용할 수 있는 위협 및 관련 된 응답 작업에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef03a-109">Threat investigation and response capabilities provide insights into threats and related response actions that are available in the Office 365 Security &amp; Compliance Center.</span></span> <span data-ttu-id="ef03a-110">이러한 정보를 활용 하면 조직의 보안 팀이 전자 메일 이나 파일 기반 공격 으로부터 Office 365 사용자를 보호 하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef03a-110">These insights can help your organization's security team protect Office 365 users from email- or file-based attacks.</span></span> <span data-ttu-id="ef03a-111">이 기능은 신호를 모니터링 하 고 사용자 활동, 인증, 전자 메일, 손상 된 Pc 및 보안 인시던트와 같은 여러 원본의 데이터를 수집 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ef03a-111">The capabilities help monitor signals and gathers data from multiple sources, such as user activity, authentication, email, compromised PCs, and security incidents.</span></span> <span data-ttu-id="ef03a-112">비즈니스 의사 결정권자 및 Office 365 전역 관리자, 보안 관리자 및 보안 분석가는이 정보를 사용 하 여 Office 365 사용자에 대 한 위협에 대 한 이해를 받고 지적 재산을 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef03a-112">Business decision makers and Office 365 global administrators, security administrators, and security analysts can all use this information to understand and respond to threats against Office 365 users and protect intellectual property.</span></span>

## <a name="get-acquainted-with-threat-investigation-and-response-tools"></a><span data-ttu-id="ef03a-113">위협 조사 및 응답 도구 익히기</span><span class="sxs-lookup"><span data-stu-id="ef03a-113">Get acquainted with threat investigation and response tools</span></span>

<span data-ttu-id="ef03a-114">보안 &amp; 준수 센터의 위협 조사 및 응답 기능- [위협 대시보드](#threat-dashboard), [탐색기](#threat-explorer), [인시던트](#incidents), [공격 시뮬레이터](#attack-simulator)및 [자동화 된 사건 대응](automated-investigation-response-office.md)을 비롯 한 도구 및 응답 워크플로 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="ef03a-114">Threat investigation and response capabilities surface in the Security &amp; Compliance Center, as a set of tools and response workflows, including the [threat dashboard](#threat-dashboard), [Explorer](#threat-explorer), [Incidents](#incidents), [Attack Simulator](#attack-simulator), and [Automated incident response](automated-investigation-response-office.md).</span></span>
  
### <a name="threat-dashboard"></a><span data-ttu-id="ef03a-115">위협 대시보드</span><span class="sxs-lookup"><span data-stu-id="ef03a-115">Threat dashboard</span></span>

<span data-ttu-id="ef03a-116">위협 대시보드 ( [보안 대시보드](security-dashboard.md)라고도 함)를 사용 하 여 해결 된 위협을 빠르게 확인 하 고, Office 365 서비스가 비즈니스를 보호 하는 방법을 비즈니스 의사 결정권자에 게 보고 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef03a-116">Use the Threat dashboard (this is also referred to as the [Security dashboard](security-dashboard.md)) to quickly see what threats have been addressed, and as a visual way to report to business decision makers how Office 365 services are securing your business.</span></span>
  
![위협 대시보드](../media/ce013a31-3f80-4d09-bb95-bfb7623b8bc4.png)
  
<span data-ttu-id="ef03a-118">이 대시보드 &amp; 를 보고 사용 하려면 Office 365 보안 및 준수 센터에서 **위협 관리** \> **대시보드로**이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef03a-118">To view and use this dashboard, in the Office 365 Security &amp; Compliance Center, go to **Threat management** \> **Dashboard**.</span></span>
  
### <a name="threat-explorer"></a><span data-ttu-id="ef03a-119">위협 탐색기</span><span class="sxs-lookup"><span data-stu-id="ef03a-119">Threat Explorer</span></span>

<span data-ttu-id="ef03a-120">위협 [탐색기 (및 실시간 검색)](threat-explorer.md) 를 사용 하 여 위협을 분석 하 고, 시간에 따른 공격 량을 확인 하 고, 위협 계열, 침입자 인프라 등을 기준으로 데이터를 분석 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef03a-120">Use [Threat Explorer (and real-time detections)](threat-explorer.md) to analyze threats, see the volume of attacks over time, and analyze data by threat families, attacker infrastructure, and more.</span></span> <span data-ttu-id="ef03a-121">위협 탐색기 (탐색기 라고도 함)는 모든 보안 분석가의 조사 워크플로에서 시작 되는 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="ef03a-121">Threat Explorer (also referred to as Explorer) is the starting place for any security analyst's investigation workflow.</span></span>
  
![위협 탐색기](../media/7a7cecee-17f0-4134-bcb8-7cee3f3c3890.png)
  
<span data-ttu-id="ef03a-123">이 보고서 &amp; 를 보고 사용 하려면 Office 365 보안 및 준수 센터에서 **위협 관리** \> **탐색기**로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef03a-123">To view and use this report, in the Office 365 Security &amp; Compliance Center, go to **Threat management** \> **Explorer**.</span></span>
  
### <a name="incidents"></a><span data-ttu-id="ef03a-124">인시던트</span><span class="sxs-lookup"><span data-stu-id="ef03a-124">Incidents</span></span>

<span data-ttu-id="ef03a-125">문제 목록 (조사가 라고도 함)을 사용 하 여 비행 보안 인시던트 목록을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef03a-125">Use the Incidents list (this is also called Investigations) to see a list of in flight security incidents.</span></span> <span data-ttu-id="ef03a-126">인시던트는 의심 스러운 전자 메일 메시지와 같은 위협을 추적 하 고 추가 조사 및 수정을 수행 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ef03a-126">Incidents are used to track threats such as suspicious email messages, and to conduct further investigation and remediation.</span></span>
  
![Office 365의 현재 위협 인시던트 목록](../media/acadd4c7-d2de-4146-aeb8-90cfad805a9c.png)
  
<span data-ttu-id="ef03a-128">조직의 현재 인시던트 &amp; 목록을 보려면 보안 및 준수 센터에서 **위협 관리** \> **검토** \> **인시던트**로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef03a-128">To view the list of current incidents for your organization, in the Security &amp; Compliance Center, go to **Threat management** \> **Review** \> **Incidents**.</span></span>
  
![보안 &amp; 및 준수 센터에서 위협 관리 \> 검토를 선택 합니다.](../media/e0f46454-fa38-40f0-a120-b595614d1d22.png)

### <a name="attack-simulator"></a><span data-ttu-id="ef03a-130">공격 시뮬레이터</span><span class="sxs-lookup"><span data-stu-id="ef03a-130">Attack Simulator</span></span>

<span data-ttu-id="ef03a-131">공격 시뮬레이터를 사용 하 여 조직에서 현실적인 고 사이버 공격를 설정 및 실행 하 고, 실제에서는 사이버 공격과 비즈니스에 영향을 주기 전에 취약 한 사용자를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef03a-131">Use Attack Simulator to set up and run realistic cyberattacks in your organization, and identify vulnerable people before a real cyberattack affects your business.</span></span> <span data-ttu-id="ef03a-132">자세한 내용은 [Office 365의 Attack 시뮬레이터](attack-simulator.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ef03a-132">To learn more, see [Attack Simulator in Office 365](attack-simulator.md).</span></span>

### <a name="automated-investigation-and-response"></a><span data-ttu-id="ef03a-133">자동화된 조사 및 응답</span><span class="sxs-lookup"><span data-stu-id="ef03a-133">Automated investigation and response</span></span>

<span data-ttu-id="ef03a-134">자동화 된 조사 및 응답 (AIR) 기능을 사용 하 여 조직의 위협 으로부터 발생 하는 콘텐츠, 장치 및 사용자와 관련 된 시간과 노력을 절감할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef03a-134">Use automated investigation and response (AIR) capabilities to save time and effort correlating content, devices, and people at risk from threats in your organization.</span></span> <span data-ttu-id="ef03a-135">AIR 프로세스는 특정 알림이 트리거될 때 또는 보안 운영 팀이 시작 될 때 시작 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef03a-135">AIR processes can begin whenever certain alerts are triggered, or when started by your security operations team.</span></span> <span data-ttu-id="ef03a-136">자세한 내용은 [Office 365의 자동화된 사고 대응](automated-investigation-response-office.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ef03a-136">To learn more, see [Automated incident response in Office 365](automated-investigation-response-office.md).</span></span> 
  
## <a name="threat-intelligence-widgets"></a><span data-ttu-id="ef03a-137">위협 인텔리전스 위젯</span><span class="sxs-lookup"><span data-stu-id="ef03a-137">Threat intelligence widgets</span></span>

<span data-ttu-id="ef03a-138">보안 분석가는 Office 365 Advanced Threat Protection 계획 2 제공의 일부로 알려진 위협에 대 한 세부 정보를 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef03a-138">As part of the Office 365 Advanced Threat Protection Plan 2 offering, security analysts can review details about a known threat.</span></span> <span data-ttu-id="ef03a-139">이 기능은 사용자가 안전 하 게 유지 하기 위해 수행할 수 있는 추가 예방 조치/단계가 있는지 여부를 확인 하는 데 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef03a-139">This is useful to determine whether there are additional preventative measures/steps that can be taken to keep users safe.</span></span>
  
![최근 위협에 대 한 정보를 보여 주는 보안 경향](../media/11e7d40d-139b-4c56-8d52-c091c8654151.png) 
  
## <a name="how-do-we-get-these-capabilities"></a><span data-ttu-id="ef03a-141">이러한 기능은 어떻게 얻을 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="ef03a-141">How do we get these capabilities?</span></span>

<span data-ttu-id="ef03a-142">Office 365 위협 조사 및 응답 기능은 Office 365 Advanced Threat Protection 계획 2 및 Enterprise E5에 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef03a-142">Office 365 threat investigation and response capabilities are included in Office 365 Advanced Threat Protection Plan 2 and Enterprise E5.</span></span> 

> [!TIP]
> <span data-ttu-id="ef03a-143">조직에 이러한 위협 조사 및 응답 기능이 포함 되지 않은 Office 365 구독이 있는 경우 Office 365 Advanced Threat Protection 계획 2를 추가 기능으로 구입할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef03a-143">If your organization has an Office 365 subscription that does not include these threat investigation and response capabilities, you can potentially purchase Office 365 Advanced Threat Protection Plan 2 as an add-on.</span></span> <span data-ttu-id="ef03a-144">계획 옵션에 대 한 자세한 내용은 [office 365 Advanced Threat Protection 서비스 설명](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) 및 [비즈니스용 office 365 용 추가 기능 구입 또는 편집](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/buy-or-edit-an-add-on)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ef03a-144">For more information about plan options, see [Office 365 Advanced Threat Protection service description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) and [Buy or edit an add-on for Office 365 for business](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/buy-or-edit-an-add-on).</span></span>
  
1. <span data-ttu-id="ef03a-145">Office 365 전역 관리자 인 경우로 이동 [https://admin.microsoft.com](https://admin.microsoft.com) 하 여 office 365에 대 한 회사 또는 학교 계정을 사용 하 여 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef03a-145">As an Office 365 global administrator, go to [https://admin.microsoft.com](https://admin.microsoft.com) and sign in using your work or school account for Office 365.</span></span> 
    
2. <span data-ttu-id="ef03a-146">**관리자 \*\* \> \*\* 청구**을 선택하여 현재 구독에 포함된 내용을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="ef03a-146">Choose **Admin** \> **Billing** to see what your current subscription includes.</span></span> 
    - <span data-ttu-id="ef03a-147">**Office 365 Enterprise**e 5가 표시 되 면 조직에 Office 365 Advanced Threat Protection 계획 2 (위협 조사 및 응답 기능 포함)가 있는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ef03a-147">If you see **Office 365 Enterprise E5**, then your organization has Office 365 Advanced Threat Protection Plan 2 (which includes threat investigation and response capabilities).</span></span> 
    - <span data-ttu-id="ef03a-148">**Office 365 Enterprise E3** 또는 **Office 365 enterprise E1**과 같은 다른 구독이 표시 되는 경우 Office 365 Advanced Threat Protection 계획 2를 추가 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ef03a-148">If you see a different subscription, such as **Office 365 Enterprise E3** or **Office 365 Enterprise E1**, consider adding Office 365 Advanced Threat Protection Plan 2.</span></span> <span data-ttu-id="ef03a-149">이 작업을 수행 하려면 **+ 구독 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef03a-149">(To do that, choose **+ Add subscription**.)</span></span>
    
3. <span data-ttu-id="ef03a-150">Microsoft 365 관리 센터에서 **사용자** \> **활성 사용자**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef03a-150">In the Microsoft 365 admin center, choose **Users** \> **Active users**.</span></span>
    
4. <span data-ttu-id="ef03a-151">모든 활성 사용자에 게 Office 365 Advanced Threat Protection 계획 2 라이선스를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef03a-151">Assign Office 365 Advanced Threat Protection Plan 2 licenses to all active users.</span></span> <span data-ttu-id="ef03a-152">(이에 대 한 라이선스가 있는 사용자만 탐색기와 같은 보고서에 표시 됩니다.)</span><span class="sxs-lookup"><span data-stu-id="ef03a-152">(Only users who have a license for this will show up in reports, such as Explorer.)</span></span>
    
5. <span data-ttu-id="ef03a-153">Office 365 Advanced Threat Protection으로 작업할 조직의 사용자에 게 역할을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef03a-153">Assign roles to people in your organization who will be working with the Office 365 Advanced Threat Protection.</span></span> <span data-ttu-id="ef03a-154">[사용자에 게 Office 365 보안 &amp; 및 준수 센터에 대 한 액세스 권한을 부여](grant-access-to-the-security-and-compliance-center.md)하 고 다음 표를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ef03a-154">See [Give users access to the Office 365 Security &amp; Compliance Center](grant-access-to-the-security-and-compliance-center.md), and refer to the following table:</span></span><br/><br/>


  |<span data-ttu-id="ef03a-155">**이 작업을 수행 하려면 ...**</span><span class="sxs-lookup"><span data-stu-id="ef03a-155">**To do this activity...**</span></span> <br/> |<span data-ttu-id="ef03a-156">**다음 역할이 있어야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="ef03a-156">**You must have these roles**</span></span> <br/> |  
  |:-----|:-----|
  |<span data-ttu-id="ef03a-157">위협 대시보드 (또는 새 [보안 대시보드](security-dashboard.md)) 사용</span><span class="sxs-lookup"><span data-stu-id="ef03a-157">Use the Threat dashboard (or the new [Security dashboard](security-dashboard.md))</span></span><br/> <span data-ttu-id="ef03a-158">최근 또는 현재 위협에 대 한 정보 보기</span><span class="sxs-lookup"><span data-stu-id="ef03a-158">View information about recent or current threats</span></span>  <br/> |<span data-ttu-id="ef03a-159">Azure Active Directory 또는 Office 365 보안 &amp; 및 준수 센터에 할당 된 다음 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="ef03a-159">One of the following (assigned in either Azure Active Directory or the Office 365 Security &amp; Compliance Center):</span></span> <br/><span data-ttu-id="ef03a-160">- **Office 365 전역 관리자**</span><span class="sxs-lookup"><span data-stu-id="ef03a-160">- **Office 365 Global Administrator**</span></span>  <br/> <span data-ttu-id="ef03a-161">- **보안 관리자**</span><span class="sxs-lookup"><span data-stu-id="ef03a-161">- **Security Administrator**</span></span> <br/><span data-ttu-id="ef03a-162">- **보안 독자**</span><span class="sxs-lookup"><span data-stu-id="ef03a-162">- **Security Reader**</span></span> <br/> |
  |<span data-ttu-id="ef03a-163">[위협 탐색기 (및 실시간 검색)](threat-explorer.md) 를 사용 하 여 위협 분석</span><span class="sxs-lookup"><span data-stu-id="ef03a-163">Use [Threat Explorer (and real-time detections)](threat-explorer.md) to analyze threats</span></span>  <br/> |<span data-ttu-id="ef03a-164">Azure Active Directory 또는 Office 365 보안 &amp; 및 준수 센터에 할당 된 다음 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="ef03a-164">One of the following (assigned in either Azure Active Directory or the Office 365 Security &amp; Compliance Center):</span></span> <br/><span data-ttu-id="ef03a-165">- **Office 365 전역 관리자**</span><span class="sxs-lookup"><span data-stu-id="ef03a-165">- **Office 365 Global Administrator**</span></span>  <br/> <span data-ttu-id="ef03a-166">- **보안 관리자**</span><span class="sxs-lookup"><span data-stu-id="ef03a-166">- **Security Administrator**</span></span> <br/><span data-ttu-id="ef03a-167">- **보안 독자**</span><span class="sxs-lookup"><span data-stu-id="ef03a-167">- **Security Reader**</span></span> <br/> |
  |<span data-ttu-id="ef03a-168">인시던트 보기 (조사가 라고도 함)</span><span class="sxs-lookup"><span data-stu-id="ef03a-168">View Incidents (also referred to as Investigations)</span></span> <br/> <span data-ttu-id="ef03a-169">인시던트에 전자 메일 메시지 추가</span><span class="sxs-lookup"><span data-stu-id="ef03a-169">Add email messages to an incident</span></span>  <br/> |<span data-ttu-id="ef03a-170">Azure Active Directory 또는 Office 365 보안 &amp; 및 준수 센터에 할당 된 다음 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="ef03a-170">One of the following (assigned in either Azure Active Directory or the Office 365 Security &amp; Compliance Center):</span></span> <br/><span data-ttu-id="ef03a-171">- **Office 365 전역 관리자**</span><span class="sxs-lookup"><span data-stu-id="ef03a-171">- **Office 365 Global Administrator**</span></span>  <br/> <span data-ttu-id="ef03a-172">- **보안 관리자**</span><span class="sxs-lookup"><span data-stu-id="ef03a-172">- **Security Administrator**</span></span> <br/><span data-ttu-id="ef03a-173">- **보안 독자**</span><span class="sxs-lookup"><span data-stu-id="ef03a-173">- **Security Reader**</span></span> <br/>  <br/> |
  |<span data-ttu-id="ef03a-174">인시던트에서 전자 메일 작업 트리거</span><span class="sxs-lookup"><span data-stu-id="ef03a-174">Trigger email actions in an incident</span></span>  <br/> <span data-ttu-id="ef03a-175">의심 스러운 전자 메일 메시지 찾기 및 삭제</span><span class="sxs-lookup"><span data-stu-id="ef03a-175">Find and delete suspicious email messages</span></span>  <br/> |<span data-ttu-id="ef03a-176">Azure Active Directory 또는 Office 365 보안 &amp; 및 준수 센터에 할당 된 다음 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="ef03a-176">One of the following (assigned in either Azure Active Directory or the Office 365 Security &amp; Compliance Center):</span></span> <br/><span data-ttu-id="ef03a-177">- **Office 365 전역 관리자**</span><span class="sxs-lookup"><span data-stu-id="ef03a-177">- **Office 365 Global Administrator**</span></span>  <br/> <span data-ttu-id="ef03a-178">- **보안 관리자**</span><span class="sxs-lookup"><span data-stu-id="ef03a-178">- **Security Administrator**</span></span> <br/><span data-ttu-id="ef03a-179">---및---</span><span class="sxs-lookup"><span data-stu-id="ef03a-179">--- and ---</span></span><br/><span data-ttu-id="ef03a-180">- **검색 및 제거** (Office 365 보안 &amp; 및 준수 센터에만 할당 됨)</span><span class="sxs-lookup"><span data-stu-id="ef03a-180">- **Search and Purge** (assigned only in the Office 365 Security &amp; Compliance Center)</span></span>  <br/> |
  |<span data-ttu-id="ef03a-181">Microsoft Defender ATP에 Office 365 Advanced Threat Protection 계획 2 통합</span><span class="sxs-lookup"><span data-stu-id="ef03a-181">Integrate Office 365 Advanced Threat Protection Plan 2 with Microsoft Defender ATP</span></span>  <br/> <span data-ttu-id="ef03a-182">SIEM 서버를 사용 하 여 Office 365 Advanced Threat Protection 계획 2 통합</span><span class="sxs-lookup"><span data-stu-id="ef03a-182">Integrate Office 365 Advanced Threat Protection Plan 2 with a SIEM server</span></span>  <br/> |<span data-ttu-id="ef03a-183">Azure Active Directory 또는 Office 365 보안 &amp; 및 준수 센터에 할당 된 다음 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="ef03a-183">One of the following (assigned in either Azure Active Directory or the Office 365 Security &amp; Compliance Center):</span></span> <br/><span data-ttu-id="ef03a-184">- **Office 365 전역 관리자**</span><span class="sxs-lookup"><span data-stu-id="ef03a-184">- **Office 365 Global Administrator**</span></span>  <br/> <span data-ttu-id="ef03a-185">- **보안 관리자**</span><span class="sxs-lookup"><span data-stu-id="ef03a-185">- **Security Administrator**</span></span> <br/><span data-ttu-id="ef03a-186">---및---</span><span class="sxs-lookup"><span data-stu-id="ef03a-186">--- and ---</span></span><br/><span data-ttu-id="ef03a-187">추가 응용 프로그램에서 할당 되는 적절 한 역할 (예: Microsoft Defender 보안 센터 또는 SIEM server)</span><span class="sxs-lookup"><span data-stu-id="ef03a-187">An appropriate role assigned in additional applications (such as Microsoft Defender Security Center or a SIEM server)</span></span>  <br/> |
   
<span data-ttu-id="ef03a-188">역할, 역할 그룹 및 권한에 대 한 자세한 내용은 [Office 365 보안 &amp; 및 준수 센터의 사용 권한을](permissions-in-the-security-and-compliance-center.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ef03a-188">For information about roles, role groups, and permissions, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    
## <a name="next-steps"></a><span data-ttu-id="ef03a-189">다음 단계</span><span class="sxs-lookup"><span data-stu-id="ef03a-189">Next steps</span></span>

- [<span data-ttu-id="ef03a-190">위협 추적기에 대해 알아보기-신규 및 중요</span><span class="sxs-lookup"><span data-stu-id="ef03a-190">Learn about Threat Trackers - New and Noteworthy</span></span>](threat-trackers.md)
    
- [<span data-ttu-id="ef03a-191">배달 된 악성 전자 메일 찾기 및 조사 (Office 365 위협 조사 및 응답)</span><span class="sxs-lookup"><span data-stu-id="ef03a-191">Find and investigate malicious email that was delivered (Office 365 Threat Investigation and Response)</span></span>](investigate-malicious-email-that-was-delivered.md)
    
- [<span data-ttu-id="ef03a-192">Microsoft Defender Advanced Threat Protection을 사용 하 여 Office 365 위협 조사 및 응답 통합</span><span class="sxs-lookup"><span data-stu-id="ef03a-192">Integrate Office 365 Threat Investigation and Response with Microsoft Defender Advanced Threat Protection</span></span>](integrate-office-365-ti-with-wdatp.md)
    
- [<span data-ttu-id="ef03a-193">공격 시뮬레이터에 대 한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="ef03a-193">Learn about Attack Simulator</span></span>](attack-simulator.md)
  

