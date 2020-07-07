---
title: '3단계: 원격 작업자를 위한 보안 및 규정 준수 구현'
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 06/22/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
- M365solutions
ms.custom: ''
description: Microsoft 365 보안 및 규정 준수 서비스를 사용하여 원격 작업자를 위한 애플리케이션, 데이터 및 장치를 보호할 수 있습니다.
ms.openlocfilehash: d8419c00bc4d8b99d9456abafbd5869ca26f4556
ms.sourcegitcommit: 7c1b34205746ff0690ffc774a74bdfd434256cf5
ms.contentlocale: ko-KR
ms.lasthandoff: 07/07/2020
ms.locfileid: "45049871"
---
# <a name="step-3-deploy-security-and-compliance-for-remote-workers"></a><span data-ttu-id="ef95a-103">3단계: 원격 작업자를 위한 보안 및 규정 준수 구현</span><span class="sxs-lookup"><span data-stu-id="ef95a-103">Step 3: Deploy security and compliance for remote workers</span></span>

<span data-ttu-id="ef95a-104">사무실에 들어오지 않거나 매우 드물게 출근하는 원격 작업자의 경우 보안 및 규정 준수는 전체 솔루션의 중요한 부분입니다.</span><span class="sxs-lookup"><span data-stu-id="ef95a-104">For remote workers, some of whom never go into the office or who go infrequently, security and compliance are an important part of the overall solution.</span></span> <span data-ttu-id="ef95a-105">모든 커뮤니케이션은 조직 인트라넷에 국한되지 않고 인터넷을 통해 이루어집니다.</span><span class="sxs-lookup"><span data-stu-id="ef95a-105">All of their communications occur over the Internet instead of being confined to an organizational intranet.</span></span> 

<span data-ttu-id="ef95a-106">사이버 보안 위험을 줄이고 내부 정책 및 데이터 규정을 준수하는 동시에 생산성을 유지하기 위해 귀하와 귀사의 직원이 할 수 있는 일이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef95a-106">There are things you and your workers can do to remain productive while decreasing cybersecurity risk and maintaining compliance with your internal policies and data regulations.</span></span>

<span data-ttu-id="ef95a-107">원격 작업에는 다음과 같은 보안 및 규정 준수 요소가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ef95a-107">Remote work needs these elements of security and compliance:</span></span>

- <span data-ttu-id="ef95a-108">Microsoft Teams와 같이 원격 작업자가 사용하는 생산성 애플리케이션에 대한 액세스 제어</span><span class="sxs-lookup"><span data-stu-id="ef95a-108">Controlled access to the productivity apps that remote workers use, such as Microsoft Teams</span></span> 
- <span data-ttu-id="ef95a-109">채팅 대화 또는 공유 파일과 같이 원격 작업자가 만들고 사용하는 데이터에 대한 액세스 및 보호를 제어</span><span class="sxs-lookup"><span data-stu-id="ef95a-109">Controlled access to and protection of the data that remote workers create and use, such as chat conversations or shared files</span></span>
- <span data-ttu-id="ef95a-110">악성 프로그램 및 기타 유형의 사이버 공격으로부터 Windows 10 장치를 보호</span><span class="sxs-lookup"><span data-stu-id="ef95a-110">Protection of Windows 10 devices from malware and other types of cyberattacks</span></span>
- <span data-ttu-id="ef95a-111">민감도 및 보호 수준에 대한 일관된 레이블을 사용하여 전자 메일, 파일 및 사이트 보호</span><span class="sxs-lookup"><span data-stu-id="ef95a-111">Protection of email, files, and site with consistent labeling for levels of sensitivity and protection</span></span>
- <span data-ttu-id="ef95a-112">정보유출 방지</span><span class="sxs-lookup"><span data-stu-id="ef95a-112">Prevention of leaked information</span></span>
- <span data-ttu-id="ef95a-113">지역 데이터 규정을 준수</span><span class="sxs-lookup"><span data-stu-id="ef95a-113">Adherence to regional data regulations</span></span>

![이러한 Microsoft 365 서비스를 사용하여 보안을 유지하고 규정 준수](../media/empower-people-to-work-remotely/remote-workers-security-compliance-grid.png)

## <a name="security"></a><span data-ttu-id="ef95a-115">보안</span><span class="sxs-lookup"><span data-stu-id="ef95a-115">Security</span></span>

<span data-ttu-id="ef95a-116">Microsoft 365의 이러한 보안 기능으로 애플리케이션과 데이터를 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="ef95a-116">Protect your applications and data with these security features of Microsoft 365.</span></span>

| <span data-ttu-id="ef95a-117">기능 또는 특징</span><span class="sxs-lookup"><span data-stu-id="ef95a-117">Capability or feature</span></span> | <span data-ttu-id="ef95a-118">설명</span><span class="sxs-lookup"><span data-stu-id="ef95a-118">Description</span></span> | <span data-ttu-id="ef95a-119">라이선싱</span><span class="sxs-lookup"><span data-stu-id="ef95a-119">Licensing</span></span> |
|:-------|:-----|:-------|
| <span data-ttu-id="ef95a-120">Office 365 Advanced Threat Protection (ATP)</span><span class="sxs-lookup"><span data-stu-id="ef95a-120">Office 365 Advanced Threat Protection (ATP)</span></span> | <span data-ttu-id="ef95a-121">전자 메일 메시지, 사무실 문서 및 협업 도구와 같은 Microsoft 365 앱과 데이터를 공격으로부터 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="ef95a-121">Protect your Microsoft 365 apps and data—such as email messages, Office documents, and collaboration tools—from attack.</span></span> <br><br> <span data-ttu-id="ef95a-122">Office ATP는 보안 위험을 탐지, 조사 및 교정하기 위해 앱에서 보내는 신호를 수집 및 분석하고 전자 메일 메시지, 링크(URL) 및 협업 도구로 인해 발생하는 악의적인 위협으로부터 조직을 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="ef95a-122">Office ATP collects and analyzes signals from your apps for detection, investigation, and remediation of security risks and safeguards your organization against malicious threats posed by email messages, links (URLs), and collaboration tools.</span></span> | <span data-ttu-id="ef95a-123">Microsoft 365 E3 및 E5</span><span class="sxs-lookup"><span data-stu-id="ef95a-123">Microsoft 365 E3 and E5</span></span> | 
| <span data-ttu-id="ef95a-124">악성 프로그램 차단</span><span class="sxs-lookup"><span data-stu-id="ef95a-124">Malware protection</span></span> | <span data-ttu-id="ef95a-125">Windows Defender Antivirus and Device Guard는 장치 기반 악성 프로그램 보호 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ef95a-125">‎Windows Defender Antivirus and Device Guard provides device-based malware protection.</span></span> <br><br> <span data-ttu-id="ef95a-126">쉐어포인트 온라인에서는 알려진 악성 프로그램이 있는지 파일 업로드를 자동으로 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="ef95a-126">SharePoint‎ Online automatically scans file uploads for known malware.</span></span> <span data-ttu-id="ef95a-127">‎</span><span class="sxs-lookup"><span data-stu-id="ef95a-127">‎</span></span><br><br> <span data-ttu-id="ef95a-128">EOP(Exchange Online Protection)는 클라우드 편지함을 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="ef95a-128">Exchange Online Protection‎ (‎EOP‎) secures cloud mailboxes.</span></span> | <span data-ttu-id="ef95a-129">Microsoft 365 E3 및 E5</span><span class="sxs-lookup"><span data-stu-id="ef95a-129">Microsoft 365 E3 and E5</span></span> |
| <span data-ttu-id="ef95a-130">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="ef95a-130">Microsoft Defender ATP</span></span> | <span data-ttu-id="ef95a-131">사이버 위협 및 데이터 침해로부터 조직의 장치보호하고 지능적 위협을 탐지, 조사 및 대응합니다.</span><span class="sxs-lookup"><span data-stu-id="ef95a-131">Protect your organization’s devices from cyberthreats and data breaches and detect, investigate, and respond to advanced threats.</span></span> | <span data-ttu-id="ef95a-132">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="ef95a-132">Microsoft 365 E5</span></span> |
| <span data-ttu-id="ef95a-133">클라우드 앱 보안</span><span class="sxs-lookup"><span data-stu-id="ef95a-133">Cloud App Security</span></span> | <span data-ttu-id="ef95a-134">Microsoft 365 및 기타 SaaS 애플리케이션 모두 클라우드 기반 서비스를 공격으로부터 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="ef95a-134">Protect your cloud-based services—both Microsoft 365 and other SaaS apps— from attack.</span></span> | <span data-ttu-id="ef95a-135">Microsoft 365 E5 또는 개별 클라우드 앱 보안 라이선를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ef95a-135">Microsoft 365 E5 or individual Cloud App Security licenses</span></span> |
| <span data-ttu-id="ef95a-136">Azure AD ID 보호</span><span class="sxs-lookup"><span data-stu-id="ef95a-136">Azure AD Identity Protection</span></span>  | <span data-ttu-id="ef95a-137">ID 기반 리스크의 감지 및 해결 작업을 자동화합니다.</span><span class="sxs-lookup"><span data-stu-id="ef95a-137">Automate detection and remediation of identity-based risks.</span></span> <br><br><span data-ttu-id="ef95a-138">위험 기반 조건부 액세스 정책을 만들어 위험 로그인에 대한 MFA(다단계 인증)를 요구합니다.</span><span class="sxs-lookup"><span data-stu-id="ef95a-138">Create risk-based Conditional Access policies to require multi-factor authentication (MFA) for risky sign-ins.</span></span> | <span data-ttu-id="ef95a-139">Azure AD Premium P2 라이선스를 포함한 Microsoft 365 E5 또는 E3</span><span class="sxs-lookup"><span data-stu-id="ef95a-139">Microsoft 365 E5 or E3 with Azure AD Premium P2 licenses</span></span> |
||||

## <a name="compliance"></a><span data-ttu-id="ef95a-140">규정 준수</span><span class="sxs-lookup"><span data-stu-id="ef95a-140">Compliance</span></span>

<span data-ttu-id="ef95a-141">Microsoft 365의 이러한 규정 준수 기능을 사용하여 내부 정책 또는 규정 요구 사항을 준수합니다.</span><span class="sxs-lookup"><span data-stu-id="ef95a-141">Comply with internal policies or regulatory requirements with these compliance features of Microsoft 365.</span></span>

| <span data-ttu-id="ef95a-142">기능 또는 특징</span><span class="sxs-lookup"><span data-stu-id="ef95a-142">Capability or feature</span></span> | <span data-ttu-id="ef95a-143">설명</span><span class="sxs-lookup"><span data-stu-id="ef95a-143">Description</span></span> | <span data-ttu-id="ef95a-144">라이선싱</span><span class="sxs-lookup"><span data-stu-id="ef95a-144">Licensing</span></span> |
|:-------|:-----|:-------|
| <span data-ttu-id="ef95a-145">민감도 레이블</span><span class="sxs-lookup"><span data-stu-id="ef95a-145">Sensitivity labels</span></span> | <span data-ttu-id="ef95a-146">전자 메일, 파일 또는 사이트에 다양한 수준의 보호 기능을 갖춘 레이블을 배치하여 사용자의 생산성과 협업 능력을 저해하지 않고 조직의 데이터를 분류하고 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="ef95a-146">Classify and protect your organization's data without hindering the productivity of users and their ability to collaborate by placing labels with various levels of protection on email, files, or sites.</span></span> | <span data-ttu-id="ef95a-147">Microsoft 365 E3 및 E5</span><span class="sxs-lookup"><span data-stu-id="ef95a-147">Microsoft 365 E3 and E5</span></span> |
| <span data-ttu-id="ef95a-148">데이터 손실 방지(DLP).</span><span class="sxs-lookup"><span data-stu-id="ef95a-148">Data Loss Protection (DLP)</span></span> | <span data-ttu-id="ef95a-149">개인 정보가 포함된 데이터 공유와 같은 위험하거나 부주의하거나 부적절한 공유를 내외부적으로 탐지, 경고 및 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="ef95a-149">Detect, warn, and block risky, inadvertent, or inappropriate sharing, such as sharing of data containing personal information, both internally and externally.</span></span> | <span data-ttu-id="ef95a-150">Microsoft 365 E3 및 E5</span><span class="sxs-lookup"><span data-stu-id="ef95a-150">Microsoft 365 E3 and E5</span></span> | 
| <span data-ttu-id="ef95a-151">조건부 액세스 앱 컨트롤.</span><span class="sxs-lookup"><span data-stu-id="ef95a-151">Conditional Access App Control</span></span> | <span data-ttu-id="ef95a-152">중요한 데이터가 사용자의 개인 기기에 다운로드되지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef95a-152">Prevent sensitive data from being downloaded to users' personal devices.</span></span> | <span data-ttu-id="ef95a-153">Microsoft 365 E3 및 E5</span><span class="sxs-lookup"><span data-stu-id="ef95a-153">Microsoft 365 E3 and E5</span></span> |
| <span data-ttu-id="ef95a-154">데이터 보존 레이블 및 정책.</span><span class="sxs-lookup"><span data-stu-id="ef95a-154">Data retention labels and policies</span></span> | <span data-ttu-id="ef95a-155">조직의 정책 또는 데이터 규정을 준수하기 위해 고객의 개인 데이터 스토리지에 대한 데이터 및 요구사항을 보관하는 기간과 같은 정보 거버넌스 제어를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="ef95a-155">Implement information governance controls, such as how long to keep data and requirements on the storage of personal data on customers, to comply with your organization's policies or data regulations.</span></span> | <span data-ttu-id="ef95a-156">Microsoft 365 E3 및 E5</span><span class="sxs-lookup"><span data-stu-id="ef95a-156">Microsoft 365 E3 and E5</span></span> |
| <span data-ttu-id="ef95a-157">전자 메일 암호화</span><span class="sxs-lookup"><span data-stu-id="ef95a-157">Email encryption</span></span> | <span data-ttu-id="ef95a-158">고객의 개인 데이터와 같이 규제 데이터가 들어 있는 조직 내외부의 사용자 간에 암호화된 전자 메일 메시지를 주고 받습니다.</span><span class="sxs-lookup"><span data-stu-id="ef95a-158">Send and receive encrypted email messages between people inside and outside your organization that contains regulated data, such as personal data on customers.</span></span> | <span data-ttu-id="ef95a-159">Microsoft 365 E3 및 E5</span><span class="sxs-lookup"><span data-stu-id="ef95a-159">Microsoft 365 E3 and E5</span></span> |
| <span data-ttu-id="ef95a-160">규정 관리자</span><span class="sxs-lookup"><span data-stu-id="ef95a-160">Compliance Manager</span></span> | <span data-ttu-id="ef95a-161">Microsoft 서비스 신뢰 포털에서 이 워크플로우 기반 위험 평가 도구를 사용하여 Microsoft 클라우드 서비스와 관련된 규정 준수 활동을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="ef95a-161">Manage regulatory compliance activities related to Microsoft cloud services with this workflow-based risk assessment tool in the Microsoft Service Trust Portal.</span></span> | <span data-ttu-id="ef95a-162">Microsoft 365 E3 및 E5</span><span class="sxs-lookup"><span data-stu-id="ef95a-162">Microsoft 365 E3 and E5</span></span> |
| <span data-ttu-id="ef95a-163">준수 점수(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="ef95a-163">Compliance Score (preview)</span></span> | <span data-ttu-id="ef95a-164">Microsoft 365 Compliance Center에서 현재 규정 준수 구성의 전체 점수와 이를 개선하기 위한 권장 사항을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="ef95a-164">See an overall score of your current compliance configuration and recommendations for improving it in the Microsoft 365 Compliance Center.</span></span> | <span data-ttu-id="ef95a-165">Microsoft 365 E3 및 E5</span><span class="sxs-lookup"><span data-stu-id="ef95a-165">Microsoft 365 E3 and E5</span></span> |
||||

## <a name="results-of-step-3"></a><span data-ttu-id="ef95a-166">3단계의 결과</span><span class="sxs-lookup"><span data-stu-id="ef95a-166">Results of Step 3</span></span>

<span data-ttu-id="ef95a-167">원격 작업자의 경우 다음을 구현했습니다.</span><span class="sxs-lookup"><span data-stu-id="ef95a-167">For your remote workers, you have implemented:</span></span>

- <span data-ttu-id="ef95a-168">보안:</span><span class="sxs-lookup"><span data-stu-id="ef95a-168">Security:</span></span>
  - <span data-ttu-id="ef95a-169">원격 작업자가 통신하고 협업하는 데 사용하는 애플리케이션 및 데이터에 대한 액세스를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="ef95a-169">Controlled access to apps and data that remote workers use to communicate and collaborate</span></span>
  - <span data-ttu-id="ef95a-170">클라우드 서비스 데이터, 전자 메일 및 Windows 10 장치를 위한 악성 프로그램 차단 기능</span><span class="sxs-lookup"><span data-stu-id="ef95a-170">Malware protection for cloud service data, email, and Windows 10 devices</span></span> 
- <span data-ttu-id="ef95a-171">규정 준수</span><span class="sxs-lookup"><span data-stu-id="ef95a-171">Compliance:</span></span>
  - <span data-ttu-id="ef95a-172">민감도 및 보호 수준에 대한 일관된 라벨링</span><span class="sxs-lookup"><span data-stu-id="ef95a-172">Consistent labeling for levels of sensitivity and protection</span></span>
  - <span data-ttu-id="ef95a-173">정보 누출을 방지하기 위한 정책</span><span class="sxs-lookup"><span data-stu-id="ef95a-173">Policies to prevention information leakage</span></span>
  - <span data-ttu-id="ef95a-174">지역 데이터 규정을 준수</span><span class="sxs-lookup"><span data-stu-id="ef95a-174">Adherence to regional data regulations</span></span>

## <a name="next-step"></a><span data-ttu-id="ef95a-175">다음 단계</span><span class="sxs-lookup"><span data-stu-id="ef95a-175">Next step</span></span>

<span data-ttu-id="ef95a-176">디바이스, PC 및 기타 엔드포인트를 관리하려면 [4단계](empower-people-to-work-remotely-manage-endpoints.md)를 계속 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="ef95a-176">Continue with [Step 4](empower-people-to-work-remotely-manage-endpoints.md) to manage your devices, PCs, and other endpoints.</span></span>
