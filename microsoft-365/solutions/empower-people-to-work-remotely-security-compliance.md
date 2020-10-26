---
title: '3단계: 원격 작업자를 위한 보안 및 규정 준수 구현'
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
- m365solution-remotework
- m365solution-scenario
ms.custom: ''
description: Microsoft 365 보안 및 규정 준수 서비스를 사용하여 원격 작업자를 위한 애플리케이션, 데이터 및 장치를 보호할 수 있습니다.
ms.openlocfilehash: 7607f3945d2e3c4e057162296df94dce4c611dbe
ms.sourcegitcommit: 554755bc9ce40228ce6e34bde6fc6e226869b6a1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2020
ms.locfileid: "48681471"
---
# <a name="step-3-deploy-security-and-compliance-for-remote-workers"></a><span data-ttu-id="97bdb-103">3단계: 원격 작업자를 위한 보안 및 규정 준수 구현</span><span class="sxs-lookup"><span data-stu-id="97bdb-103">Step 3: Deploy security and compliance for remote workers</span></span>

<span data-ttu-id="97bdb-104">사무실에 들어오지 않거나 매우 드물게 출근하는 원격 작업자의 경우 보안 및 규정 준수는 전체 솔루션의 중요한 부분입니다.</span><span class="sxs-lookup"><span data-stu-id="97bdb-104">For remote workers, some of whom never go into the office or who go infrequently, security and compliance are an important part of the overall solution.</span></span> <span data-ttu-id="97bdb-105">모든 커뮤니케이션은 조직 인트라넷에 국한되지 않고 인터넷을 통해 이루어집니다.</span><span class="sxs-lookup"><span data-stu-id="97bdb-105">All of their communications occur over the Internet instead of being confined to an organizational intranet.</span></span> 

<span data-ttu-id="97bdb-106">사이버 보안 위험을 줄이고 내부 정책 및 데이터 규정을 준수하는 동시에 생산성을 유지하기 위해 귀하와 귀사의 직원이 할 수 있는 일이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97bdb-106">There are things you and your workers can do to remain productive while decreasing cybersecurity risk and maintaining compliance with your internal policies and data regulations.</span></span>

<span data-ttu-id="97bdb-107">원격 작업에는 다음과 같은 보안 및 규정 준수 요소가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="97bdb-107">Remote work needs these elements of security and compliance:</span></span>

- <span data-ttu-id="97bdb-108">Microsoft Teams와 같이 원격 작업자가 사용하는 생산성 애플리케이션에 대한 액세스 제어</span><span class="sxs-lookup"><span data-stu-id="97bdb-108">Controlled access to the productivity apps that remote workers use, such as Microsoft Teams</span></span> 
- <span data-ttu-id="97bdb-109">채팅 대화 또는 공유 파일과 같이 원격 작업자가 만들고 사용하는 데이터에 대한 액세스 및 보호를 제어</span><span class="sxs-lookup"><span data-stu-id="97bdb-109">Controlled access to and protection of the data that remote workers create and use, such as chat conversations or shared files</span></span>
- <span data-ttu-id="97bdb-110">악성 프로그램 및 기타 유형의 사이버 공격으로부터 Windows 10 장치를 보호</span><span class="sxs-lookup"><span data-stu-id="97bdb-110">Protection of Windows 10 devices from malware and other types of cyberattacks</span></span>
- <span data-ttu-id="97bdb-111">민감도 및 보호 수준에 대한 일관된 레이블을 사용하여 전자 메일, 파일 및 사이트 보호</span><span class="sxs-lookup"><span data-stu-id="97bdb-111">Protection of email, files, and site with consistent labeling for levels of sensitivity and protection</span></span>
- <span data-ttu-id="97bdb-112">정보유출 방지</span><span class="sxs-lookup"><span data-stu-id="97bdb-112">Prevention of leaked information</span></span>
- <span data-ttu-id="97bdb-113">지역 데이터 규정을 준수</span><span class="sxs-lookup"><span data-stu-id="97bdb-113">Adherence to regional data regulations</span></span>

<span data-ttu-id="97bdb-114">다음은 원격 작업자에 대한 보안 및 규정 준수 서비스를 제공하는 Microsoft 365의 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="97bdb-114">Here are the features of Microsoft 365 that provide security and compliance services for remote workers.</span></span>

![이러한 Microsoft 365 서비스를 사용하여 보안을 유지하고 규정 준수](../media/empower-people-to-work-remotely/remote-workers-security-compliance-grid.png)

## <a name="security"></a><span data-ttu-id="97bdb-116">보안</span><span class="sxs-lookup"><span data-stu-id="97bdb-116">Security</span></span>

<span data-ttu-id="97bdb-117">Microsoft 365의 이러한 보안 기능으로 애플리케이션과 데이터를 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="97bdb-117">Protect your applications and data with these security features of Microsoft 365.</span></span>

| <span data-ttu-id="97bdb-118">기능 또는 특징</span><span class="sxs-lookup"><span data-stu-id="97bdb-118">Capability or feature</span></span> | <span data-ttu-id="97bdb-119">설명</span><span class="sxs-lookup"><span data-stu-id="97bdb-119">Description</span></span> | <span data-ttu-id="97bdb-120">라이선싱</span><span class="sxs-lookup"><span data-stu-id="97bdb-120">Licensing</span></span> |
|:-------|:-----|:-------|
| <span data-ttu-id="97bdb-121">Office 365 Advanced Threat Protection (ATP)</span><span class="sxs-lookup"><span data-stu-id="97bdb-121">Office 365 Advanced Threat Protection (ATP)</span></span> | <span data-ttu-id="97bdb-122">전자 메일 메시지, 사무실 문서 및 협업 도구와 같은 Microsoft 365 앱과 데이터를 공격으로부터 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="97bdb-122">Protect your Microsoft 365 apps and data—such as email messages, Office documents, and collaboration tools—from attack.</span></span> <br><br> <span data-ttu-id="97bdb-123">Office ATP는 보안 위험을 탐지, 조사 및 교정하기 위해 앱에서 보내는 신호를 수집 및 분석하고 전자 메일 메시지, 링크(URL) 및 협업 도구로 인해 발생하는 악의적인 위협으로부터 조직을 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="97bdb-123">Office ATP collects and analyzes signals from your apps for detection, investigation, and remediation of security risks and safeguards your organization against malicious threats posed by email messages, links (URLs), and collaboration tools.</span></span> | <span data-ttu-id="97bdb-124">Microsoft 365 E3 혹은 E5</span><span class="sxs-lookup"><span data-stu-id="97bdb-124">Microsoft 365 E3 or E5</span></span> | 
| <span data-ttu-id="97bdb-125">악성 프로그램 차단</span><span class="sxs-lookup"><span data-stu-id="97bdb-125">Malware protection</span></span> | <span data-ttu-id="97bdb-126">Microsoft Defender Antivirus 및 Device Guard는 장치 기반 말웨어 방지 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="97bdb-126">‎Microsoft Defender Antivirus and Device Guard provides device-based malware protection.</span></span> <br><br> <span data-ttu-id="97bdb-127">쉐어포인트 온라인에서는 알려진 악성 프로그램이 있는지 파일 업로드를 자동으로 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="97bdb-127">SharePoint‎ Online automatically scans file uploads for known malware.</span></span> <span data-ttu-id="97bdb-128">‎</span><span class="sxs-lookup"><span data-stu-id="97bdb-128">‎</span></span><br><br> <span data-ttu-id="97bdb-129">EOP(Exchange Online Protection)는 클라우드 편지함을 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="97bdb-129">Exchange Online Protection‎ (‎EOP‎) secures cloud mailboxes.</span></span> | <span data-ttu-id="97bdb-130">Microsoft 365 E3 혹은 E5</span><span class="sxs-lookup"><span data-stu-id="97bdb-130">Microsoft 365 E3 or E5</span></span> |
| <span data-ttu-id="97bdb-131">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="97bdb-131">Microsoft Defender ATP</span></span> | <span data-ttu-id="97bdb-132">사이버 위협 및 데이터 침해로부터 조직의 장치보호하고 지능적 위협을 탐지, 조사 및 대응합니다.</span><span class="sxs-lookup"><span data-stu-id="97bdb-132">Protect your organization’s devices from cyberthreats and data breaches and detect, investigate, and respond to advanced threats.</span></span> | <span data-ttu-id="97bdb-133">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="97bdb-133">Microsoft 365 E5</span></span> |
| <span data-ttu-id="97bdb-134">클라우드 앱 보안</span><span class="sxs-lookup"><span data-stu-id="97bdb-134">Cloud App Security</span></span> | <span data-ttu-id="97bdb-135">Microsoft 365 및 기타 SaaS 애플리케이션 모두 클라우드 기반 서비스를 공격으로부터 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="97bdb-135">Protect your cloud-based services—both Microsoft 365 and other SaaS apps— from attack.</span></span> | <span data-ttu-id="97bdb-136">Microsoft 365 E5 또는 개별 클라우드 앱 보안 라이선를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="97bdb-136">Microsoft 365 E5 or individual Cloud App Security licenses</span></span> |
| <span data-ttu-id="97bdb-137">Azure AD ID 보호</span><span class="sxs-lookup"><span data-stu-id="97bdb-137">Azure AD Identity Protection</span></span>  | <span data-ttu-id="97bdb-138">ID 기반 리스크의 감지 및 해결 작업을 자동화합니다.</span><span class="sxs-lookup"><span data-stu-id="97bdb-138">Automate detection and remediation of identity-based risks.</span></span> <br><br><span data-ttu-id="97bdb-139">위험 기반 조건부 액세스 정책을 만들어 위험 로그인에 대한 MFA(다단계 인증)를 요구합니다.</span><span class="sxs-lookup"><span data-stu-id="97bdb-139">Create risk-based Conditional Access policies to require multi-factor authentication (MFA) for risky sign-ins.</span></span> | <span data-ttu-id="97bdb-140">Azure AD Premium P2 라이선스를 포함한 Microsoft 365 E5 또는 E3</span><span class="sxs-lookup"><span data-stu-id="97bdb-140">Microsoft 365 E5 or E3 with Azure AD Premium P2 licenses</span></span> |
||||

<span data-ttu-id="97bdb-141">자세한 내용은 [보안 팀이 재택 근무를 지원하는 상위 12가지 작업](../security/top-security-tasks-for-remote-work.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="97bdb-141">See [Top 12 tasks for security teams to support working from home](../security/top-security-tasks-for-remote-work.md) for more information.</span></span>

## <a name="compliance"></a><span data-ttu-id="97bdb-142">규정 준수</span><span class="sxs-lookup"><span data-stu-id="97bdb-142">Compliance</span></span>

<span data-ttu-id="97bdb-143">Microsoft 365의 이러한 규정 준수 기능을 사용하여 내부 정책 또는 규정 요구 사항을 준수합니다.</span><span class="sxs-lookup"><span data-stu-id="97bdb-143">Comply with internal policies or regulatory requirements with these compliance features of Microsoft 365.</span></span>

| <span data-ttu-id="97bdb-144">기능 또는 특징</span><span class="sxs-lookup"><span data-stu-id="97bdb-144">Capability or feature</span></span> | <span data-ttu-id="97bdb-145">설명</span><span class="sxs-lookup"><span data-stu-id="97bdb-145">Description</span></span> | <span data-ttu-id="97bdb-146">라이선싱</span><span class="sxs-lookup"><span data-stu-id="97bdb-146">Licensing</span></span> |
|:-------|:-----|:-------|
| <span data-ttu-id="97bdb-147">민감도 레이블</span><span class="sxs-lookup"><span data-stu-id="97bdb-147">Sensitivity labels</span></span> | <span data-ttu-id="97bdb-148">전자 메일, 파일 또는 사이트에 다양한 수준의 보호 기능을 갖춘 레이블을 배치하여 사용자의 생산성과 협업 능력을 저해하지 않고 조직의 데이터를 분류하고 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="97bdb-148">Classify and protect your organization's data without hindering the productivity of users and their ability to collaborate by placing labels with various levels of protection on email, files, or sites.</span></span> | <span data-ttu-id="97bdb-149">Microsoft 365 E3 혹은 E5</span><span class="sxs-lookup"><span data-stu-id="97bdb-149">Microsoft 365 E3 or E5</span></span> |
| <span data-ttu-id="97bdb-150">데이터 손실 방지(DLP).</span><span class="sxs-lookup"><span data-stu-id="97bdb-150">Data Loss Protection (DLP)</span></span> | <span data-ttu-id="97bdb-151">개인 정보가 포함된 데이터 공유와 같은 위험하거나 부주의하거나 부적절한 공유를 내외부적으로 탐지, 경고 및 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="97bdb-151">Detect, warn, and block risky, inadvertent, or inappropriate sharing, such as sharing of data containing personal information, both internally and externally.</span></span> | <span data-ttu-id="97bdb-152">Microsoft 365 E3 혹은 E5</span><span class="sxs-lookup"><span data-stu-id="97bdb-152">Microsoft 365 E3 or E5</span></span> | 
| <span data-ttu-id="97bdb-153">조건부 액세스 앱 컨트롤.</span><span class="sxs-lookup"><span data-stu-id="97bdb-153">Conditional Access App Control</span></span> | <span data-ttu-id="97bdb-154">중요한 데이터가 사용자의 개인 기기에 다운로드되지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="97bdb-154">Prevent sensitive data from being downloaded to users' personal devices.</span></span> | <span data-ttu-id="97bdb-155">Microsoft 365 E3 혹은 E5</span><span class="sxs-lookup"><span data-stu-id="97bdb-155">Microsoft 365 E3 or E5</span></span> |
| <span data-ttu-id="97bdb-156">데이터 보존 레이블 및 정책.</span><span class="sxs-lookup"><span data-stu-id="97bdb-156">Data retention labels and policies</span></span> | <span data-ttu-id="97bdb-157">조직의 정책 또는 데이터 규정을 준수하기 위해 고객의 개인 데이터 스토리지에 대한 데이터 및 요구사항을 보관하는 기간과 같은 정보 거버넌스 제어를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="97bdb-157">Implement information governance controls, such as how long to keep data and requirements on the storage of personal data on customers, to comply with your organization's policies or data regulations.</span></span> | <span data-ttu-id="97bdb-158">Microsoft 365 E3 혹은 E5</span><span class="sxs-lookup"><span data-stu-id="97bdb-158">Microsoft 365 E3 or E5</span></span> |
| <span data-ttu-id="97bdb-159">OME(Office 메시지 암호화)</span><span class="sxs-lookup"><span data-stu-id="97bdb-159">Office message encryption (OME)</span></span> | <span data-ttu-id="97bdb-160">고객의 개인 데이터와 같이 규제 데이터가 들어 있는 조직 내외부의 사용자 간에 암호화된 전자 메일 메시지를 주고 받습니다.</span><span class="sxs-lookup"><span data-stu-id="97bdb-160">Send and receive encrypted email messages between people inside and outside your organization that contains regulated data, such as personal data on customers.</span></span> | <span data-ttu-id="97bdb-161">Microsoft 365 E3 혹은 E5</span><span class="sxs-lookup"><span data-stu-id="97bdb-161">Microsoft 365 E3 or E5</span></span> |
| <span data-ttu-id="97bdb-162">규정 관리자</span><span class="sxs-lookup"><span data-stu-id="97bdb-162">Compliance Manager</span></span> | <span data-ttu-id="97bdb-163">Microsoft 서비스 신뢰 포털에서 이 워크플로우 기반 위험 평가 도구를 사용하여 Microsoft 클라우드 서비스와 관련된 규정 준수 활동을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="97bdb-163">Manage regulatory compliance activities related to Microsoft cloud services with this workflow-based risk assessment tool in the Microsoft Service Trust Portal.</span></span> | <span data-ttu-id="97bdb-164">Microsoft 365 E3 혹은 E5</span><span class="sxs-lookup"><span data-stu-id="97bdb-164">Microsoft 365 E3 or E5</span></span> |
| <span data-ttu-id="97bdb-165">규정 관리자</span><span class="sxs-lookup"><span data-stu-id="97bdb-165">Compliance Manager</span></span> | <span data-ttu-id="97bdb-166">Microsoft 365 규정 준수 센터에서 현재 규정 준수 구성의 전체 점수와 이를 개선하기 위한 권장 사항을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="97bdb-166">See an overall score of your current compliance configuration and recommendations for improving it in the Microsoft 365 compliance center.</span></span> | <span data-ttu-id="97bdb-167">Microsoft 365 E3 혹은 E5</span><span class="sxs-lookup"><span data-stu-id="97bdb-167">Microsoft 365 E3 or E5</span></span> |
| <span data-ttu-id="97bdb-168">커뮤니케이션 규정 준수</span><span class="sxs-lookup"><span data-stu-id="97bdb-168">Communication Compliance</span></span>  | <span data-ttu-id="97bdb-169">조직에 부적합한 메시지를 탐지하고, 캡쳐하여, 수정하는 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="97bdb-169">Detect, capture, and take remediation actions for inappropriate messages in your organization.</span></span> | <span data-ttu-id="97bdb-170">규정 준수 혹은 내부자 위험 관리 추가 기능을 사용하는 Microsoft 365 E5 또는 Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="97bdb-170">Microsoft 365 E5 or Microsoft 365 E3 with the Compliance or Insider Risk Management add-ons</span></span> |
| <span data-ttu-id="97bdb-171">내부자 위험 관리</span><span class="sxs-lookup"><span data-stu-id="97bdb-171">Insider Risk Management</span></span> |  <span data-ttu-id="97bdb-172">조직의 악의적이고 부주의한 위험을 감지하고, 조사하고 조치를 취합니다.</span><span class="sxs-lookup"><span data-stu-id="97bdb-172">Detect, investigate, and act on malicious and inadvertent risks in your organization.</span></span> <span data-ttu-id="97bdb-173">Microsoft 365는 직원들이 관리되지 않는 장치를 사용하는 경우에도 이러한 위험을 감지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97bdb-173">Microsoft 365 can detect these kinds of risks even when a worker is using an unmanaged device.</span></span> | <span data-ttu-id="97bdb-174">규정 준수 혹은 내부자 위험 관리 추가 기능을 사용하는 Microsoft 365 E5 또는 Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="97bdb-174">Microsoft 365 E5 or Microsoft 365 E3 with the Compliance or Insider Risk Management add-ons</span></span> |
||||

<span data-ttu-id="97bdb-175">자세한 내용은 [Microsoft 365 규정 준수 시작을 위한 빠른 작업](../compliance/compliance-quick-tasks.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="97bdb-175">See [Quick tasks for getting started with Microsoft 365 compliance](../compliance/compliance-quick-tasks.md) for more information.</span></span>

## <a name="results-of-step-3"></a><span data-ttu-id="97bdb-176">3단계의 결과</span><span class="sxs-lookup"><span data-stu-id="97bdb-176">Results of Step 3</span></span>

<span data-ttu-id="97bdb-177">원격 작업자의 경우 다음을 구현했습니다.</span><span class="sxs-lookup"><span data-stu-id="97bdb-177">For your remote workers, you have implemented:</span></span>

- <span data-ttu-id="97bdb-178">보안</span><span class="sxs-lookup"><span data-stu-id="97bdb-178">Security</span></span>
  - <span data-ttu-id="97bdb-179">원격 작업자가 통신하고 협업하는 데 사용하는 애플리케이션 및 데이터에 대한 액세스를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="97bdb-179">Controlled access to apps and data that remote workers use to communicate and collaborate</span></span>
  - <span data-ttu-id="97bdb-180">클라우드 서비스 데이터, 전자 메일 및 Windows 10 장치를 위한 악성 프로그램 차단 기능</span><span class="sxs-lookup"><span data-stu-id="97bdb-180">Malware protection for cloud service data, email, and Windows 10 devices</span></span> 
- <span data-ttu-id="97bdb-181">규정 준수</span><span class="sxs-lookup"><span data-stu-id="97bdb-181">Compliance</span></span>
  - <span data-ttu-id="97bdb-182">민감도 및 보호 수준에 대한 일관된 라벨링</span><span class="sxs-lookup"><span data-stu-id="97bdb-182">Consistent labeling for levels of sensitivity and protection</span></span>
  - <span data-ttu-id="97bdb-183">정보 누출을 방지하기 위한 정책</span><span class="sxs-lookup"><span data-stu-id="97bdb-183">Policies to prevention information leakage</span></span>
  - <span data-ttu-id="97bdb-184">지역 데이터 규정을 준수</span><span class="sxs-lookup"><span data-stu-id="97bdb-184">Adherence to regional data regulations</span></span>

## <a name="next-step"></a><span data-ttu-id="97bdb-185">다음 단계</span><span class="sxs-lookup"><span data-stu-id="97bdb-185">Next step</span></span>

<span data-ttu-id="97bdb-186">[![4단계: 디바이스, PC 및 기타 끝점 관리](../media/empower-people-to-work-remotely/remote-workers-step-grid-4.png)](empower-people-to-work-remotely-manage-endpoints.md)</span><span class="sxs-lookup"><span data-stu-id="97bdb-186">[![Step 4: Manage your devices, PCs, and other endpoints](../media/empower-people-to-work-remotely/remote-workers-step-grid-4.png)](empower-people-to-work-remotely-manage-endpoints.md)</span></span>

<span data-ttu-id="97bdb-187">디바이스, PC 및 기타 엔드포인트를 관리하려면 [4단계](empower-people-to-work-remotely-manage-endpoints.md)를 계속 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="97bdb-187">Continue with [Step 4](empower-people-to-work-remotely-manage-endpoints.md) to manage your devices, PCs, and other endpoints.</span></span>
