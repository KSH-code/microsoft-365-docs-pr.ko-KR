---
title: Contoso IT 인프라 및 비즈니스 요구 사항
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/01/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Contoso 온-프레미스 IT 인프라의 기본 구조와 기업에 대 한 Microsoft 365에서 회사의 비즈니스 요구 사항을 충족 하는 방법을 이해 합니다.
ms.openlocfilehash: bc2b34254da01a3d49085082ab8ee8632df2d434
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/21/2020
ms.locfileid: "48637178"
---
# <a name="contoso-it-infrastructure-and-business-needs"></a><span data-ttu-id="f9977-103">Contoso IT 인프라 및 비즈니스 요구 사항</span><span class="sxs-lookup"><span data-stu-id="f9977-103">Contoso IT infrastructure and business needs</span></span>

<span data-ttu-id="f9977-104">Contoso는 온-프레미스 중앙 IT 인프라에서 클라우드 기반 개인 생산성 워크 로드 및 응용 프로그램을 통합 하는 클라우드 포함 설정으로 전환 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9977-104">Contoso is transitioning from an on-premises, centralized IT infrastructure to a cloud-inclusive setup that incorporates cloud-based personal productivity workloads and applications.</span></span>

## <a name="existing-contoso-it-infrastructure"></a><span data-ttu-id="f9977-105">기존 Contoso IT 인프라</span><span class="sxs-lookup"><span data-stu-id="f9977-105">Existing Contoso IT infrastructure</span></span>

<span data-ttu-id="f9977-106">Contoso는 주로 중앙 집중식 온-프레미스 IT 인프라를 사용하며, 응용 프로그램 데이터 센터는 파리 본사에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9977-106">Contoso uses a mostly centralized on-premises IT infrastructure, with application datacenters in the Paris headquarters.</span></span>

<span data-ttu-id="f9977-107">그림 1은 응용 프로그램 데이터 센터, DMZ 및 인터넷이 포함 된 본사 사무실을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f9977-107">Figure 1 shows the headquarters office with application datacenters, a DMZ, and the internet.</span></span>

![기존 Contoso IT 인프라](../media/contoso-infra-needs/contoso-infra-needs-fig1.png)

<span data-ttu-id="f9977-109">**그림 1: 기존 Contoso IT 인프라**</span><span class="sxs-lookup"><span data-stu-id="f9977-109">**Figure 1: Existing Contoso IT infrastructure**</span></span>
 
<span data-ttu-id="f9977-110">온-프레미스 응용 프로그램 데이터 센터에서는 다음과 같은 것들을 호스팅합니다.</span><span class="sxs-lookup"><span data-stu-id="f9977-110">The on-premises application datacenters host:</span></span> 

- <span data-ttu-id="f9977-111">SQL Server 및 기타 Linux 데이터베이스를 사용 하는 사용자 지정 lob (기간 업무) 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="f9977-111">Custom line-of-business applications that use SQL Server and other Linux databases.</span></span>
- <span data-ttu-id="f9977-112">레거시 SharePoint 서버 집합</span><span class="sxs-lookup"><span data-stu-id="f9977-112">A set of legacy SharePoint servers.</span></span>
- <span data-ttu-id="f9977-113">파일 저장을 위한 조직 및 팀 수준 서버</span><span class="sxs-lookup"><span data-stu-id="f9977-113">Organization and team-level servers for file storage.</span></span>

<span data-ttu-id="f9977-114">또한 각 지역 허브 사무소는 유사한 응용 프로그램 집합을 가진 서버 집합을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="f9977-114">Additionally, each regional hub office supports a set of servers with a similar set of applications.</span></span> <span data-ttu-id="f9977-115">이 서버들은 지역 IT부서의 통제를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="f9977-115">These servers are under the control of regional IT departments.</span></span>

<span data-ttu-id="f9977-116">이러한 별도의 다중 지역 데이터 센터에 있는 응용 프로그램 및 데이터에 대한 검색 가능성은 계속해서 해결 과제로 남아 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9977-116">Searchability across the applications and data of these separate multi-geographical datacenters continues to be a challenge.</span></span>

<span data-ttu-id="f9977-117">Contoso 본사 DMZ에서는 각 서버 집합이 다음을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9977-117">In the Contoso headquarters DMZ, different sets of servers provide:</span></span>

- <span data-ttu-id="f9977-118">고객이 제품, 부품, 소모품 및 서비스를 주문할 수 있는 Contoso 공용 웹 사이트용 호스팅입니다.</span><span class="sxs-lookup"><span data-stu-id="f9977-118">Hosting for the Contoso public web site, from which customers can order products, parts, supplies, and service.</span></span>
- <span data-ttu-id="f9977-119">파트너와의 정보 교환 및 공동 작업을 위한 Contoso 파트너 엑스트라넷 호스팅 기능</span><span class="sxs-lookup"><span data-stu-id="f9977-119">Hosting for the Contoso partner extranet for partner communication and collaboration.</span></span>
- <span data-ttu-id="f9977-120">파리 본사 직원을 위한 Contoso 인트라넷 및 웹 프록시에 대한 VPN (가상 사설망) 기반 원격 액세스 기능</span><span class="sxs-lookup"><span data-stu-id="f9977-120">Virtual private network (VPN)-based remote access to the Contoso intranet and web proxying for workers in the Paris headquarters.</span></span>

## <a name="contoso-business-needs"></a><span data-ttu-id="f9977-121">Contoso 비즈니스 요구 사항</span><span class="sxs-lookup"><span data-stu-id="f9977-121">Contoso business needs</span></span>

<span data-ttu-id="f9977-122">Contoso 비즈니스 요구 사항은 다음과 같은 다섯 가지 주요 범주로 나뉩니다.</span><span class="sxs-lookup"><span data-stu-id="f9977-122">Contoso business needs fall into five main categories:</span></span>

<span data-ttu-id="f9977-123">**생산성**</span><span class="sxs-lookup"><span data-stu-id="f9977-123">**Productivity**</span></span>

- <span data-ttu-id="f9977-124">보다 쉽게 공동으로 작업</span><span class="sxs-lookup"><span data-stu-id="f9977-124">Make collaboration easier</span></span>

  <span data-ttu-id="f9977-125">전자 메일 및 파일 공유 기반 공동 작업을 문서에 대 한 실시간 변경, 보다 쉬운 온라인 모임 및 캡처된 대화 스레드를 지 원하는 온라인 모델로 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9977-125">Replace email and file share-based collaboration with an online model that allows real-time changes on documents, easier online meetings, and captured conversation threads.</span></span>
- <span data-ttu-id="f9977-126">원격 및 모바일 작업자의 생산성 향상</span><span class="sxs-lookup"><span data-stu-id="f9977-126">Improve productivity for remote and mobile workers</span></span>

  <span data-ttu-id="f9977-127">집 이나 현장에서 근무 하는 직원이 많은 경우에는 병목 현상이 일어난 VPN 솔루션을 클라우드의 Contoso 데이터 및 리소스에 대 한 성능이 뛰어난 액세스로 교체 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9977-127">With many employees working from home or in the field, replace the bottlenecked VPN solution with performant access to Contoso data and resources in the cloud.</span></span>
- <span data-ttu-id="f9977-128">창의성 및 혁신 증대</span><span class="sxs-lookup"><span data-stu-id="f9977-128">Increase creativity and innovation</span></span>

  <span data-ttu-id="f9977-129">수동 입력과 3D 시각화를 포함하여 최신 수준의 시각적 학습 및 아이디어 개발 방식을 활용할 수 있습니다.
</span><span class="sxs-lookup"><span data-stu-id="f9977-129">Take advantage of the latest visual learning and idea development methods, including inking and 3D visualization.</span></span>

<span data-ttu-id="f9977-130">**보안**</span><span class="sxs-lookup"><span data-stu-id="f9977-130">**Security**</span></span>

- <span data-ttu-id="f9977-131">ID 및 액세스 관리</span><span class="sxs-lookup"><span data-stu-id="f9977-131">Identity and access management</span></span>

  <span data-ttu-id="f9977-132">다단계 및 기타 형태의 인증을 적용 하 고 사용자 및 관리자 계정 자격 증명을 보호 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9977-132">Enforce multifactor and other forms of authentication and protect user and administrator account credentials.</span></span>

- <span data-ttu-id="f9977-133">위협 방지</span><span class="sxs-lookup"><span data-stu-id="f9977-133">Threat protection</span></span>

  <span data-ttu-id="f9977-134">맬웨어를 포함하는 외부 보안 위협으로부터 보호 -> 맬웨어를 포함하여 외부 보안 위협으로부터 보호</span><span class="sxs-lookup"><span data-stu-id="f9977-134">Protect against external security threats, including email and operating system-based malware.</span></span>

- <span data-ttu-id="f9977-135">정보 보호</span><span class="sxs-lookup"><span data-stu-id="f9977-135">Information protection</span></span>

  <span data-ttu-id="f9977-136">고객 데이터, 디자인 및 제조 사양 및 직원 정보와 같은 고가치 디지털 자산에 대한 액세스를 잠그고 암호화합니다.</span><span class="sxs-lookup"><span data-stu-id="f9977-136">Lock down access to and encrypt high-value digital assets, such as customer data, design and manufacturing specifications, and employee information.</span></span>

- <span data-ttu-id="f9977-137">보안 관리</span><span class="sxs-lookup"><span data-stu-id="f9977-137">Security management</span></span>

  <span data-ttu-id="f9977-138">보안 환경을 모니터링 하 고 위협을 실시간으로 감지 하 고 대응 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9977-138">Monitor security posture and detect and respond to threats in real time.</span></span>

<span data-ttu-id="f9977-139">**원격 및 모바일 액세스 및 비즈니스 파트너**</span><span class="sxs-lookup"><span data-stu-id="f9977-139">**Remote and mobile access and business partners**</span></span>

- <span data-ttu-id="f9977-140">원격 및 모바일 작업자에 대 한 보안 강화</span><span class="sxs-lookup"><span data-stu-id="f9977-140">Improve security for remote and mobile workers</span></span>

  <span data-ttu-id="f9977-141">사용자 고유의 장치 (BYOD) 및 회사 소유 장치 관리를 가져와 보안 액세스, 올바른 응용 프로그램 동작 및 회사 데이터 보호를 보장 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9977-141">Implement bring your own device (BYOD) and company-owned device management to ensure secured access, correct application behavior, and company data protection.</span></span>

- <span data-ttu-id="f9977-142">직원을 위한 원격 액세스 인프라 감소</span><span class="sxs-lookup"><span data-stu-id="f9977-142">Reduce remote access infrastructure for employees</span></span>

  <span data-ttu-id="f9977-143">일반적으로 액세스 하는 리소스를 클라우드로 이동 하 여 유지 관리 및 지원 비용을 줄이고 원격 액세스 솔루션의 성능을 향상 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="f9977-143">Reduce maintenance and support costs and improve performance for remote access solution by moving commonly accessed resources to the cloud.</span></span>

- <span data-ttu-id="f9977-144">B2B (susiness) 트랜잭션에 대 한 보다 효율적인 연결 및 오버 헤드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9977-144">Provide better connectivity and lower overhead for business-to-susiness (B2B) transactions</span></span>

  <span data-ttu-id="f9977-145">에이징 및 비싼 파트너 엑스트라넷을 페더레이션 인증을 사용 하는 클라우드 기반 솔루션으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="f9977-145">Replace an aging and expensive partner extranet with a cloud-based solution that uses federated authentication.</span></span>

<span data-ttu-id="f9977-146">**규정 준수**</span><span class="sxs-lookup"><span data-stu-id="f9977-146">**Compliance**</span></span>

- <span data-ttu-id="f9977-147">지역별 규정 준수</span><span class="sxs-lookup"><span data-stu-id="f9977-147">Adhere to regional regulatory requirements</span></span>

  <span data-ttu-id="f9977-148">유럽 연합의 GDPR (일반 데이터 보호 규정)과 같은 개인 데이터 규정, 데이터 저장, 암호화, 데이터 개인 정보 보호에 대 한 업계 및 지역별 규정 준수를 보장 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9977-148">Ensure compliance with industry and regional regulations for data storage, encryption, data privacy, and personal data regulations, such as the General Data Protection Regulation (GDPR) for the Europe Union.</span></span>

<span data-ttu-id="f9977-149">**관리**</span><span class="sxs-lookup"><span data-stu-id="f9977-149">**Management**</span></span>

- <span data-ttu-id="f9977-150">클라이언트 Pc 및 장치에서 실행 되는 소프트웨어를 관리 하기 위한 IT 오버 헤드 감소</span><span class="sxs-lookup"><span data-stu-id="f9977-150">Lower IT overhead for managing software running on client PCs and devices</span></span>

  <span data-ttu-id="f9977-151">조직 전체에서 Windows 운영 체제 및 Microsoft 365 앱에 대 한 업데이트 설치를 자동화 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9977-151">Automate installation of updates to the Windows operating system and Microsoft 365 Apps for enterprise across the organization.</span></span>

## <a name="mapping-contoso-business-needs-to-microsoft-365-for-enterprise"></a><span data-ttu-id="f9977-152">Contoso 비즈니스 요구 사항을 엔터프라이즈에 대 한 Microsoft 365로 매핑</span><span class="sxs-lookup"><span data-stu-id="f9977-152">Mapping Contoso business needs to Microsoft 365 for enterprise</span></span>

<span data-ttu-id="f9977-153">Contoso IT 부서는 배포 전에 Microsoft 365 E5 기능에 다음과 같은 비즈니스 요구 사항을 매핑하는 것을 확인 했습니다.</span><span class="sxs-lookup"><span data-stu-id="f9977-153">The Contoso IT department determined the following mapping of business needs to Microsoft 365 E5 features prior to deployment:</span></span>


| <span data-ttu-id="f9977-154">범주</span><span class="sxs-lookup"><span data-stu-id="f9977-154">Category</span></span> | <span data-ttu-id="f9977-155">비즈니스 요구</span><span class="sxs-lookup"><span data-stu-id="f9977-155">Business need</span></span> | <span data-ttu-id="f9977-156">Enterprise 제품 또는 기능에 대 한 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f9977-156">Microsoft 365 for enterprise products or features</span></span> |
|:-------|:-----|:-----|
| <span data-ttu-id="f9977-157">생산성</span><span class="sxs-lookup"><span data-stu-id="f9977-157">Productivity</span></span> |  |  |
|  | <span data-ttu-id="f9977-158">보다 쉽게 공동으로 작업</span><span class="sxs-lookup"><span data-stu-id="f9977-158">Make collaboration easier</span></span> | <span data-ttu-id="f9977-159">Microsoft Teams, SharePoint, OneDrive</span><span class="sxs-lookup"><span data-stu-id="f9977-159">Microsoft Teams, SharePoint, OneDrive</span></span> |
|  | <span data-ttu-id="f9977-160">원격 및 모바일 작업자의 생산성 향상</span><span class="sxs-lookup"><span data-stu-id="f9977-160">Improve productivity for remote and mobile workers</span></span> | <span data-ttu-id="f9977-161">Microsoft 365 워크로드 및 클라우드 기반 데이터</span><span class="sxs-lookup"><span data-stu-id="f9977-161">Microsoft 365 workloads and cloud-based data</span></span> |
|  | <span data-ttu-id="f9977-162">창의성 및 혁신 증대</span><span class="sxs-lookup"><span data-stu-id="f9977-162">Increase creativity and innovation</span></span> | <span data-ttu-id="f9977-163">Windows Ink, Cortana at Work, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="f9977-163">Windows Ink, Cortana at Work, PowerPoint</span></span> |
| <span data-ttu-id="f9977-164">보안</span><span class="sxs-lookup"><span data-stu-id="f9977-164">Security</span></span> |  |  |
|  | <span data-ttu-id="f9977-165">ID & 액세스 관리</span><span class="sxs-lookup"><span data-stu-id="f9977-165">Identity & access management</span></span> | <span data-ttu-id="f9977-166">MFA (Multi-factor Authentication) 및 Azure Active Directory 권한이 있는 Id 관리 (PIM)를 사용 하는 전용 전역 관리자 계정</span><span class="sxs-lookup"><span data-stu-id="f9977-166">Dedicated global administrator accounts with Azure Multi-Factor Authentication (MFA) and Azure Active Directory Privileged Identity Management (PIM)</span></span> <BR> <span data-ttu-id="f9977-167">모든 사용자 계정에 대한 MFA</span><span class="sxs-lookup"><span data-stu-id="f9977-167">MFA for all user accounts</span></span> <BR> <span data-ttu-id="f9977-168">조건부 액세스</span><span class="sxs-lookup"><span data-stu-id="f9977-168">Conditional Access</span></span> <BR> <span data-ttu-id="f9977-169">Windows Hello</span><span class="sxs-lookup"><span data-stu-id="f9977-169">Windows Hello</span></span> <BR> <span data-ttu-id="f9977-170">Windows Credential Guard</span><span class="sxs-lookup"><span data-stu-id="f9977-170">Windows Credential Guard</span></span> |
|  | <span data-ttu-id="f9977-171">위협 방지</span><span class="sxs-lookup"><span data-stu-id="f9977-171">Threat protection</span></span> | <span data-ttu-id="f9977-172">Advanced Threat Analytics</span><span class="sxs-lookup"><span data-stu-id="f9977-172">Advanced Threat Analytics</span></span> <BR> <span data-ttu-id="f9977-173">Windows Defender</span><span class="sxs-lookup"><span data-stu-id="f9977-173">Windows Defender</span></span> <BR> <span data-ttu-id="f9977-174">Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="f9977-174">Advanced Threat Protection</span></span> <BR> <span data-ttu-id="f9977-175">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="f9977-175">Office 365 Advanced Threat Protection</span></span> <BR> <span data-ttu-id="f9977-176">Microsoft 365 위협 조사 및 대응</span><span class="sxs-lookup"><span data-stu-id="f9977-176">Microsoft 365 threat investigation and response</span></span> <BR> |
|  | <span data-ttu-id="f9977-177">정보 보호</span><span class="sxs-lookup"><span data-stu-id="f9977-177">Information protection</span></span> | <span data-ttu-id="f9977-178">Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="f9977-178">Azure Information Protection</span></span> <BR> <span data-ttu-id="f9977-179">DLP(데이터 손실 방지)</span><span class="sxs-lookup"><span data-stu-id="f9977-179">Data Loss Prevention (DLP)</span></span> <BR> <span data-ttu-id="f9977-180">WIP(Windows Information Protection)</span><span class="sxs-lookup"><span data-stu-id="f9977-180">Windows Information Protection (WIP)</span></span> <BR> <span data-ttu-id="f9977-181">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="f9977-181">Microsoft Cloud App Security</span></span> <BR> <span data-ttu-id="f9977-182">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="f9977-182">Microsoft Intune</span></span> |
|  | <span data-ttu-id="f9977-183">보안 관리</span><span class="sxs-lookup"><span data-stu-id="f9977-183">Security management</span></span> | <span data-ttu-id="f9977-184">Azure Security Center</span><span class="sxs-lookup"><span data-stu-id="f9977-184">Azure Security Center</span></span>  <BR> <span data-ttu-id="f9977-185">Windows Defender 보안 센터</span><span class="sxs-lookup"><span data-stu-id="f9977-185">Windows Defender Security Center</span></span> |
| <span data-ttu-id="f9977-186">원격 및 모바일 액세스 및 비즈니스 파트너</span><span class="sxs-lookup"><span data-stu-id="f9977-186">Remote and mobile access and business partners</span></span> |  |  |
|  | <span data-ttu-id="f9977-187">원격 및 모바일 작업자를 위한 향상된 보안</span><span class="sxs-lookup"><span data-stu-id="f9977-187">Better security for remote and mobile workers</span></span> | <span data-ttu-id="f9977-188">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="f9977-188">Microsoft Intune</span></span> |
|  | <span data-ttu-id="f9977-189">직원을 위한 원격 액세스 인프라 감소</span><span class="sxs-lookup"><span data-stu-id="f9977-189">Reduce remote access infrastructure for employees</span></span> | <span data-ttu-id="f9977-190">Microsoft 365 워크로드 및 클라우드 기반 데이터</span><span class="sxs-lookup"><span data-stu-id="f9977-190">Microsoft 365 workloads and cloud-based data</span></span> |
|  | <span data-ttu-id="f9977-191">B2B 거래에 대 한 연결 및 오버 헤드 감소</span><span class="sxs-lookup"><span data-stu-id="f9977-191">Improve connectivity and lower overhead for B2B transactions</span></span> | <span data-ttu-id="f9977-192">페더레이션된 인증 및 클라우드 기반 리소스</span><span class="sxs-lookup"><span data-stu-id="f9977-192">Federated authentication and cloud-based resources</span></span> |
| <span data-ttu-id="f9977-193">규정 준수</span><span class="sxs-lookup"><span data-stu-id="f9977-193">Compliance</span></span> |  |  |
|  | <span data-ttu-id="f9977-194">지역별 규정 준수</span><span class="sxs-lookup"><span data-stu-id="f9977-194">Adhere to regional regulatory requirements</span></span> | <span data-ttu-id="f9977-195">Microsoft 365의 GDPR 기능</span><span class="sxs-lookup"><span data-stu-id="f9977-195">GDPR features in Microsoft 365</span></span> |
| <span data-ttu-id="f9977-196">관리</span><span class="sxs-lookup"><span data-stu-id="f9977-196">Management</span></span> |  |  |
|  | <span data-ttu-id="f9977-197">클라이언트 업데이트 설치에 대 한 IT 오버 헤드 감소</span><span class="sxs-lookup"><span data-stu-id="f9977-197">Lower IT overhead for installing client updates</span></span> | <span data-ttu-id="f9977-198">배포 링</span><span class="sxs-lookup"><span data-stu-id="f9977-198">Deployment rings</span></span> <BR> <span data-ttu-id="f9977-199">Windows 10 Enterprise 업데이트</span><span class="sxs-lookup"><span data-stu-id="f9977-199">Windows 10 Enterprise updates</span></span> <BR> <span data-ttu-id="f9977-200">Microsoft Office 365 ProPlus 업데이트</span><span class="sxs-lookup"><span data-stu-id="f9977-200">Microsoft 365 Apps for enterprise updates</span></span> |
||||

## <a name="next-step"></a><span data-ttu-id="f9977-201">다음 단계</span><span class="sxs-lookup"><span data-stu-id="f9977-201">Next step</span></span>

<span data-ttu-id="f9977-202">Contoso Corporation 온-프레미스 네트워크와 Microsoft 365 클라우드 기반 리소스에 대 한 액세스 및 대기 시간에 최적화 된 방식을 [알아봅니다](contoso-networking.md) .</span><span class="sxs-lookup"><span data-stu-id="f9977-202">[Learn](contoso-networking.md) about the Contoso Corporation on-premises network and how it was optimized for access and latency to Microsoft 365 cloud-based resources.</span></span>

## <a name="see-also"></a><span data-ttu-id="f9977-203">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f9977-203">See also</span></span>

[<span data-ttu-id="f9977-204">엔터프라이즈용 Microsoft 365 개요</span><span class="sxs-lookup"><span data-stu-id="f9977-204">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="f9977-205">테스트 랩 가이드</span><span class="sxs-lookup"><span data-stu-id="f9977-205">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
