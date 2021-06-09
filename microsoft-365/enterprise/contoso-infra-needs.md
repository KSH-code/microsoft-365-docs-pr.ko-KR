---
title: Contoso IT 인프라 및 비즈니스 요구
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Contoso 사내 IT 인프라의 기본 구조와 엔터프라이즈용 클라우드를 통해 회사의 비즈니스 요구를 Microsoft 365 이해합니다.
ms.openlocfilehash: 72d502b5078a1e572eeba27832550af52907e209
ms.sourcegitcommit: c1dd5be42fe0c5dcc7c05817c941edd9076febf8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2020
ms.locfileid: "49558409"
---
# <a name="contoso-it-infrastructure-and-business-needs"></a><span data-ttu-id="107bf-103">Contoso IT 인프라 및 비즈니스 요구</span><span class="sxs-lookup"><span data-stu-id="107bf-103">Contoso IT infrastructure and business needs</span></span>

<span data-ttu-id="107bf-104">Contoso는 중앙 집중식 사내 IT 인프라에서 클라우드 기반 개인 생산성 워크로드 및 응용 프로그램을 통합하는 클라우드 포함 설치로 전환하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="107bf-104">Contoso is transitioning from an on-premises, centralized IT infrastructure to a cloud-inclusive setup that incorporates cloud-based personal productivity workloads and applications.</span></span>

## <a name="existing-contoso-it-infrastructure"></a><span data-ttu-id="107bf-105">기존 Contoso IT 인프라</span><span class="sxs-lookup"><span data-stu-id="107bf-105">Existing Contoso IT infrastructure</span></span>

<span data-ttu-id="107bf-106">Contoso는 주로 중앙 집중식 온-프레미스 IT 인프라를 사용하며, 응용 프로그램 데이터 센터는 파리 본사에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="107bf-106">Contoso uses a mostly centralized on-premises IT infrastructure, with application datacenters in the Paris headquarters.</span></span>

<span data-ttu-id="107bf-107">다음은 응용 프로그램 데이터 센터, DMZ 및 인터넷이 있는 본사입니다.</span><span class="sxs-lookup"><span data-stu-id="107bf-107">Here is the headquarters office with application datacenters, a DMZ, and the internet.</span></span>

![기존 Contoso IT 인프라](../media/contoso-infra-needs/contoso-infra-needs-fig1.png)

<span data-ttu-id="107bf-109">온-프레미스 응용 프로그램 데이터 센터에서는 다음과 같은 것들을 호스팅합니다.</span><span class="sxs-lookup"><span data-stu-id="107bf-109">The on-premises application datacenters host:</span></span> 

- <span data-ttu-id="107bf-110">응용 프로그램 및 기타 Linux 데이터베이스를 SQL Server 사용자 지정 업무(LINE-OF-BUSINESS) 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="107bf-110">Custom line-of-business applications that use SQL Server and other Linux databases.</span></span>
- <span data-ttu-id="107bf-111">레거시 SharePoint 서버 집합</span><span class="sxs-lookup"><span data-stu-id="107bf-111">A set of legacy SharePoint servers.</span></span>
- <span data-ttu-id="107bf-112">파일 저장을 위한 조직 및 팀 수준 서버</span><span class="sxs-lookup"><span data-stu-id="107bf-112">Organization and team-level servers for file storage.</span></span>

<span data-ttu-id="107bf-113">또한 각 지역 허브 사무소는 유사한 응용 프로그램 집합을 가진 서버 집합을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="107bf-113">Additionally, each regional hub office supports a set of servers with a similar set of applications.</span></span> <span data-ttu-id="107bf-114">이 서버들은 지역 IT부서의 통제를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="107bf-114">These servers are under the control of regional IT departments.</span></span>

<span data-ttu-id="107bf-115">이러한 별도의 다중 지역 데이터 센터에 있는 응용 프로그램 및 데이터에 대한 검색 가능성은 계속해서 해결 과제로 남아 있습니다.</span><span class="sxs-lookup"><span data-stu-id="107bf-115">Searchability across the applications and data of these separate multi-geographical datacenters continues to be a challenge.</span></span>

<span data-ttu-id="107bf-116">Contoso 본사 DMZ에서는 여러 서버 집합이 다음을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="107bf-116">In the Contoso headquarters DMZ, different sets of servers provide:</span></span>

- <span data-ttu-id="107bf-117">고객이 제품, 파트, 소모품 및 서비스를 주문할 수 있는 Contoso 공용 웹 사이트에 대한 호스팅</span><span class="sxs-lookup"><span data-stu-id="107bf-117">Hosting for the Contoso public web site, from which customers can order products, parts, supplies, and service.</span></span>
- <span data-ttu-id="107bf-118">파트너와의 정보 교환 및 공동 작업을 위한 Contoso 파트너 엑스트라넷 호스팅 기능</span><span class="sxs-lookup"><span data-stu-id="107bf-118">Hosting for the Contoso partner extranet for partner communication and collaboration.</span></span>
- <span data-ttu-id="107bf-119">파리 본사 직원을 위한 Contoso 인트라넷 및 웹 프록시에 대한 VPN (가상 사설망) 기반 원격 액세스 기능</span><span class="sxs-lookup"><span data-stu-id="107bf-119">Virtual private network (VPN)-based remote access to the Contoso intranet and web proxying for workers in the Paris headquarters.</span></span>

## <a name="contoso-business-needs"></a><span data-ttu-id="107bf-120">Contoso 비즈니스 요구</span><span class="sxs-lookup"><span data-stu-id="107bf-120">Contoso business needs</span></span>

<span data-ttu-id="107bf-121">Contoso 비즈니스 요구는 다음과 같은 다섯 가지 주요 범주로 분류됩니다.</span><span class="sxs-lookup"><span data-stu-id="107bf-121">Contoso business needs fall into five main categories:</span></span>

<span data-ttu-id="107bf-122">**생산성**</span><span class="sxs-lookup"><span data-stu-id="107bf-122">**Productivity**</span></span>

- <span data-ttu-id="107bf-123">보다 쉽게 공동으로 작업</span><span class="sxs-lookup"><span data-stu-id="107bf-123">Make collaboration easier</span></span>

  <span data-ttu-id="107bf-124">전자 메일 및 파일 공유 기반 공동 작업을 문서에 대한 실시간 변경, 보다 쉬운 온라인 모임 및 캡처된 대화 스레드를 허용하는 온라인 모델로 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="107bf-124">Replace email and file share-based collaboration with an online model that allows real-time changes on documents, easier online meetings, and captured conversation threads.</span></span>
- <span data-ttu-id="107bf-125">원격 및 모바일 작업자의 생산성 향상</span><span class="sxs-lookup"><span data-stu-id="107bf-125">Improve productivity for remote and mobile workers</span></span>

  <span data-ttu-id="107bf-126">많은 직원이 재택 근무 또는 현장에서 작업하는 경우 병목 현상이 있는 VPN 솔루션을 클라우드의 Contoso 데이터 및 리소스에 대한 다양한 액세스로 대체하세요.</span><span class="sxs-lookup"><span data-stu-id="107bf-126">With many employees working from home or in the field, replace the bottlenecked VPN solution with performant access to Contoso data and resources in the cloud.</span></span>
- <span data-ttu-id="107bf-127">창의성 및 혁신 증대</span><span class="sxs-lookup"><span data-stu-id="107bf-127">Increase creativity and innovation</span></span>

  <span data-ttu-id="107bf-128">수동 입력과 3D 시각화를 포함하여 최신 수준의 시각적 학습 및 아이디어 개발 방식을 활용할 수 있습니다.
</span><span class="sxs-lookup"><span data-stu-id="107bf-128">Take advantage of the latest visual learning and idea development methods, including inking and 3D visualization.</span></span>

<span data-ttu-id="107bf-129">**보안**</span><span class="sxs-lookup"><span data-stu-id="107bf-129">**Security**</span></span>

- <span data-ttu-id="107bf-130">ID 및 액세스 관리</span><span class="sxs-lookup"><span data-stu-id="107bf-130">Identity and access management</span></span>

  <span data-ttu-id="107bf-131">다단계 및 기타 인증 형식을 적용하고 사용자 및 관리자 계정 자격 증명을 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="107bf-131">Enforce multifactor and other forms of authentication and protect user and administrator account credentials.</span></span>

- <span data-ttu-id="107bf-132">위협 방지</span><span class="sxs-lookup"><span data-stu-id="107bf-132">Threat protection</span></span>

  <span data-ttu-id="107bf-133">맬웨어를 포함하는 외부 보안 위협으로부터 보호 -> 맬웨어를 포함하여 외부 보안 위협으로부터 보호</span><span class="sxs-lookup"><span data-stu-id="107bf-133">Protect against external security threats, including email and operating system-based malware.</span></span>

- <span data-ttu-id="107bf-134">정보 보호</span><span class="sxs-lookup"><span data-stu-id="107bf-134">Information protection</span></span>

  <span data-ttu-id="107bf-135">고객 데이터, 디자인 및 제조 사양 및 직원 정보와 같은 고가치 디지털 자산에 대한 액세스를 잠그고 암호화합니다.</span><span class="sxs-lookup"><span data-stu-id="107bf-135">Lock down access to and encrypt high-value digital assets, such as customer data, design and manufacturing specifications, and employee information.</span></span>

- <span data-ttu-id="107bf-136">보안 관리</span><span class="sxs-lookup"><span data-stu-id="107bf-136">Security management</span></span>

  <span data-ttu-id="107bf-137">보안 자세를 모니터링하고 위협을 실시간으로 감지하고 대응합니다.</span><span class="sxs-lookup"><span data-stu-id="107bf-137">Monitor security posture and detect and respond to threats in real time.</span></span>

<span data-ttu-id="107bf-138">**원격 및 모바일 액세스 및 비즈니스 파트너**</span><span class="sxs-lookup"><span data-stu-id="107bf-138">**Remote and mobile access and business partners**</span></span>

- <span data-ttu-id="107bf-139">원격 및 모바일 작업자의 보안 향상</span><span class="sxs-lookup"><span data-stu-id="107bf-139">Improve security for remote and mobile workers</span></span>

  <span data-ttu-id="107bf-140">BYOD(Bring Your Own Device) 및 회사 소유의 장치 관리를 구현하여 보안 액세스, 올바른 응용 프로그램 동작 및 회사 데이터 보호를 보장합니다.</span><span class="sxs-lookup"><span data-stu-id="107bf-140">Implement bring your own device (BYOD) and company-owned device management to ensure secured access, correct application behavior, and company data protection.</span></span>

- <span data-ttu-id="107bf-141">직원을 위한 원격 액세스 인프라 감소</span><span class="sxs-lookup"><span data-stu-id="107bf-141">Reduce remote access infrastructure for employees</span></span>

  <span data-ttu-id="107bf-142">일반적으로 액세스하는 리소스를 클라우드로 이동하여 유지 관리 및 지원 비용을 절감하고 원격 액세스 솔루션의 성능을 향상합니다.</span><span class="sxs-lookup"><span data-stu-id="107bf-142">Reduce maintenance and support costs and improve performance for remote access solution by moving commonly accessed resources to the cloud.</span></span>

- <span data-ttu-id="107bf-143">B2B(비즈니스 대 Susiness) 트랜잭션에 대한 연결 향상 및 오버헤드 감소</span><span class="sxs-lookup"><span data-stu-id="107bf-143">Provide better connectivity and lower overhead for business-to-susiness (B2B) transactions</span></span>

  <span data-ttu-id="107bf-144">페더넷 인증을 사용하는 클라우드 기반 솔루션으로 고가의 고가의 파트너 엑스트라넷을 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="107bf-144">Replace an aging and expensive partner extranet with a cloud-based solution that uses federated authentication.</span></span>

<span data-ttu-id="107bf-145">**규정 준수**</span><span class="sxs-lookup"><span data-stu-id="107bf-145">**Compliance**</span></span>

- <span data-ttu-id="107bf-146">지역별 규정 준수</span><span class="sxs-lookup"><span data-stu-id="107bf-146">Adhere to regional regulatory requirements</span></span>

  <span data-ttu-id="107bf-147">데이터 저장, 암호화, 데이터 개인 정보 보호 및 유럽 연합에 대한 GDPR(일반 데이터 보호 규정)과 같은 개인 데이터 규정에 대한 산업 및 지역 규정을 준수합니다.</span><span class="sxs-lookup"><span data-stu-id="107bf-147">Ensure compliance with industry and regional regulations for data storage, encryption, data privacy, and personal data regulations, such as the General Data Protection Regulation (GDPR) for the Europe Union.</span></span>

<span data-ttu-id="107bf-148">**관리**</span><span class="sxs-lookup"><span data-stu-id="107bf-148">**Management**</span></span>

- <span data-ttu-id="107bf-149">클라이언트 PC 및 장치에서 실행되는 소프트웨어를 관리하기 위한 IT 오버헤드 감소</span><span class="sxs-lookup"><span data-stu-id="107bf-149">Lower IT overhead for managing software running on client PCs and devices</span></span>

  <span data-ttu-id="107bf-150">조직 전체에서 Windows 및 엔터프라이즈용 Microsoft 365 앱 업데이트 설치를 자동화합니다.</span><span class="sxs-lookup"><span data-stu-id="107bf-150">Automate installation of updates to the Windows operating system and Microsoft 365 Apps for enterprise across the organization.</span></span>

## <a name="mapping-contoso-business-needs-to-microsoft-365-for-enterprise"></a><span data-ttu-id="107bf-151">엔터프라이즈를 위해 Contoso 비즈니스 요구 Microsoft 365 매핑</span><span class="sxs-lookup"><span data-stu-id="107bf-151">Mapping Contoso business needs to Microsoft 365 for enterprise</span></span>

<span data-ttu-id="107bf-152">Contoso IT 부서는 배포 전에 비즈니스 요구 사항을 Microsoft 365 E5 매핑하기로 결정했습니다.</span><span class="sxs-lookup"><span data-stu-id="107bf-152">The Contoso IT department determined the following mapping of business needs to Microsoft 365 E5 features prior to deployment:</span></span>


| <span data-ttu-id="107bf-153">Category</span><span class="sxs-lookup"><span data-stu-id="107bf-153">Category</span></span> | <span data-ttu-id="107bf-154">비즈니스 요구</span><span class="sxs-lookup"><span data-stu-id="107bf-154">Business need</span></span> | <span data-ttu-id="107bf-155">Microsoft 365 제품 또는 기능에 대한 데이터 관리</span><span class="sxs-lookup"><span data-stu-id="107bf-155">Microsoft 365 for enterprise products or features</span></span> |
|:-------|:-----|:-----|
| <span data-ttu-id="107bf-156">생산성</span><span class="sxs-lookup"><span data-stu-id="107bf-156">Productivity</span></span> |  |  |
|  | <span data-ttu-id="107bf-157">보다 쉽게 공동으로 작업</span><span class="sxs-lookup"><span data-stu-id="107bf-157">Make collaboration easier</span></span> | <span data-ttu-id="107bf-158">Microsoft Teams, SharePoint, OneDrive</span><span class="sxs-lookup"><span data-stu-id="107bf-158">Microsoft Teams, SharePoint, OneDrive</span></span> |
|  | <span data-ttu-id="107bf-159">원격 및 모바일 작업자의 생산성 향상</span><span class="sxs-lookup"><span data-stu-id="107bf-159">Improve productivity for remote and mobile workers</span></span> | <span data-ttu-id="107bf-160">Microsoft 365 워크로드 및 클라우드 기반 데이터</span><span class="sxs-lookup"><span data-stu-id="107bf-160">Microsoft 365 workloads and cloud-based data</span></span> |
|  | <span data-ttu-id="107bf-161">창의성 및 혁신 증대</span><span class="sxs-lookup"><span data-stu-id="107bf-161">Increase creativity and innovation</span></span> | <span data-ttu-id="107bf-162">Windows Ink, Cortana at Work, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="107bf-162">Windows Ink, Cortana at Work, PowerPoint</span></span> |
| <span data-ttu-id="107bf-163">보안</span><span class="sxs-lookup"><span data-stu-id="107bf-163">Security</span></span> |  |  |
|  | <span data-ttu-id="107bf-164">ID 및 액세스 관리</span><span class="sxs-lookup"><span data-stu-id="107bf-164">Identity & access management</span></span> | <span data-ttu-id="107bf-165">Azure AD MFA(Multi-Factor Authentication) 및 Azure PIM(Azure AD 2013)Privileged Identity Management 전용 전역 관리자 계정</span><span class="sxs-lookup"><span data-stu-id="107bf-165">Dedicated global administrator accounts with Azure AD Multi-Factor Authentication (MFA) and Azure AD Privileged Identity Management (PIM)</span></span> <BR> <span data-ttu-id="107bf-166">모든 사용자 계정에 대한 MFA</span><span class="sxs-lookup"><span data-stu-id="107bf-166">MFA for all user accounts</span></span> <BR> <span data-ttu-id="107bf-167">조건부 액세스</span><span class="sxs-lookup"><span data-stu-id="107bf-167">Conditional Access</span></span> <BR> <span data-ttu-id="107bf-168">Windows Hello</span><span class="sxs-lookup"><span data-stu-id="107bf-168">Windows Hello</span></span> <BR> <span data-ttu-id="107bf-169">Windows Credential Guard</span><span class="sxs-lookup"><span data-stu-id="107bf-169">Windows Credential Guard</span></span> |
|  | <span data-ttu-id="107bf-170">위협 방지</span><span class="sxs-lookup"><span data-stu-id="107bf-170">Threat protection</span></span> | <span data-ttu-id="107bf-171">Advanced Threat Analytics</span><span class="sxs-lookup"><span data-stu-id="107bf-171">Advanced Threat Analytics</span></span> <BR> <span data-ttu-id="107bf-172">Windows Defender</span><span class="sxs-lookup"><span data-stu-id="107bf-172">Windows Defender</span></span> <BR> <span data-ttu-id="107bf-173">Office 365용 Defender</span><span class="sxs-lookup"><span data-stu-id="107bf-173">Defender for Office 365</span></span> <BR> <span data-ttu-id="107bf-174">Office 365용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="107bf-174">Microsoft Defender for Office 365</span></span> <BR> <span data-ttu-id="107bf-175">Microsoft 365 조사 및 대응</span><span class="sxs-lookup"><span data-stu-id="107bf-175">Microsoft 365 threat investigation and response</span></span> <BR> |
|  | <span data-ttu-id="107bf-176">정보 보호</span><span class="sxs-lookup"><span data-stu-id="107bf-176">Information protection</span></span> | <span data-ttu-id="107bf-177">Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="107bf-177">Azure Information Protection</span></span> <BR> <span data-ttu-id="107bf-178">DLP(데이터 손실 방지)</span><span class="sxs-lookup"><span data-stu-id="107bf-178">Data Loss Prevention (DLP)</span></span> <BR> <span data-ttu-id="107bf-179">WIP(Windows Information Protection)</span><span class="sxs-lookup"><span data-stu-id="107bf-179">Windows Information Protection (WIP)</span></span> <BR> <span data-ttu-id="107bf-180">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="107bf-180">Microsoft Cloud App Security</span></span> <BR> <span data-ttu-id="107bf-181">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="107bf-181">Microsoft Intune</span></span> |
|  | <span data-ttu-id="107bf-182">보안 관리</span><span class="sxs-lookup"><span data-stu-id="107bf-182">Security management</span></span> | <span data-ttu-id="107bf-183">Azure Defender</span><span class="sxs-lookup"><span data-stu-id="107bf-183">Azure Defender</span></span>  <BR> <span data-ttu-id="107bf-184">Windows Defender 보안 센터</span><span class="sxs-lookup"><span data-stu-id="107bf-184">Windows Defender Security Center</span></span> |
| <span data-ttu-id="107bf-185">원격 및 모바일 액세스 및 비즈니스 파트너</span><span class="sxs-lookup"><span data-stu-id="107bf-185">Remote and mobile access and business partners</span></span> |  |  |
|  | <span data-ttu-id="107bf-186">원격 및 모바일 작업자를 위한 향상된 보안</span><span class="sxs-lookup"><span data-stu-id="107bf-186">Better security for remote and mobile workers</span></span> | <span data-ttu-id="107bf-187">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="107bf-187">Microsoft Intune</span></span> |
|  | <span data-ttu-id="107bf-188">직원을 위한 원격 액세스 인프라 감소</span><span class="sxs-lookup"><span data-stu-id="107bf-188">Reduce remote access infrastructure for employees</span></span> | <span data-ttu-id="107bf-189">Microsoft 365 워크로드 및 클라우드 기반 데이터</span><span class="sxs-lookup"><span data-stu-id="107bf-189">Microsoft 365 workloads and cloud-based data</span></span> |
|  | <span data-ttu-id="107bf-190">B2B 트랜잭션에 대한 연결 향상 및 오버헤드 감소</span><span class="sxs-lookup"><span data-stu-id="107bf-190">Improve connectivity and lower overhead for B2B transactions</span></span> | <span data-ttu-id="107bf-191">페더레이션된 인증 및 클라우드 기반 리소스</span><span class="sxs-lookup"><span data-stu-id="107bf-191">Federated authentication and cloud-based resources</span></span> |
| <span data-ttu-id="107bf-192">규정 준수</span><span class="sxs-lookup"><span data-stu-id="107bf-192">Compliance</span></span> |  |  |
|  | <span data-ttu-id="107bf-193">지역별 규정 준수</span><span class="sxs-lookup"><span data-stu-id="107bf-193">Adhere to regional regulatory requirements</span></span> | <span data-ttu-id="107bf-194">GDPR의 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="107bf-194">GDPR features in Microsoft 365</span></span> |
| <span data-ttu-id="107bf-195">관리</span><span class="sxs-lookup"><span data-stu-id="107bf-195">Management</span></span> |  |  |
|  | <span data-ttu-id="107bf-196">클라이언트 업데이트 설치를 위한 IT 오버헤드 감소</span><span class="sxs-lookup"><span data-stu-id="107bf-196">Lower IT overhead for installing client updates</span></span> | <span data-ttu-id="107bf-197">Windows 10 Enterprise 업데이트</span><span class="sxs-lookup"><span data-stu-id="107bf-197">Windows 10 Enterprise updates</span></span> <BR> <span data-ttu-id="107bf-198">Microsoft Office 365 ProPlus 업데이트</span><span class="sxs-lookup"><span data-stu-id="107bf-198">Microsoft 365 Apps for enterprise updates</span></span> |
||||

## <a name="next-step"></a><span data-ttu-id="107bf-199">다음 단계</span><span class="sxs-lookup"><span data-stu-id="107bf-199">Next step</span></span>

<span data-ttu-id="107bf-200">Contoso [Corporation의](contoso-networking.md) 사내 네트워크와 클라우드 기반 리소스에 대한 액세스 및 대기 시간에 최적화된 Microsoft 365 대해 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="107bf-200">Learn about the Contoso Corporation [on-premises network](contoso-networking.md) and how it was optimized for access and latency to Microsoft 365 cloud-based resources.</span></span>

## <a name="see-also"></a><span data-ttu-id="107bf-201">참고 항목</span><span class="sxs-lookup"><span data-stu-id="107bf-201">See also</span></span>

[<span data-ttu-id="107bf-202">엔터프라이즈용 Microsoft 365 개요</span><span class="sxs-lookup"><span data-stu-id="107bf-202">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="107bf-203">테스트 랩 가이드</span><span class="sxs-lookup"><span data-stu-id="107bf-203">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
