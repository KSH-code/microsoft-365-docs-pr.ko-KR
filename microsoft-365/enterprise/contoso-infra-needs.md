---
title: Contoso의 IT 인프라 및 비즈니스 요구 사항
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
description: Contoso 온-프레미스 IT 인프라의 기본 구조와 Microsoft 365 for enterprise의 비즈니스 요구 사항을 충족 하는 방법을 이해 합니다.
ms.openlocfilehash: 3dd744a8d936307c61303bf8ba0f2f198af59d91
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46685833"
---
# <a name="contosos-it-infrastructure-and-business-needs"></a><span data-ttu-id="e7ffa-103">Contoso의 IT 인프라 및 비즈니스 요구 사항</span><span class="sxs-lookup"><span data-stu-id="e7ffa-103">Contoso's IT infrastructure and business needs</span></span>

<span data-ttu-id="e7ffa-104">Contoso는 중앙 집중식 온-프레미스 IT 인프라에서 클라우드 기반 개인 생산성 워크로드 및 응용 프로그램을 통합하는 클라우드 포함 인프라로의 전환을 진행하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7ffa-104">Contoso has been transitioning from an on-premises, centralized IT infrastructure to a cloud-inclusive one that incorporates cloud-based personal productivity workloads and applications.</span></span>

## <a name="contosos-existing-it-infrastructure"></a><span data-ttu-id="e7ffa-105">Contoso의 기존 IT 인프라</span><span class="sxs-lookup"><span data-stu-id="e7ffa-105">Contoso's existing IT infrastructure</span></span>

<span data-ttu-id="e7ffa-106">Contoso는 주로 중앙 집중식 온-프레미스 IT 인프라를 사용하며, 응용 프로그램 데이터 센터는 파리 본사에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7ffa-106">Contoso uses a mostly centralized on-premises IT infrastructure, with application datacenters in the Paris headquarters.</span></span>

<span data-ttu-id="e7ffa-107">그림 1에서는 데이터 센터, DMZ 및 인터넷이 구비된 본사 사무실을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7ffa-107">Figure 1 shows a headquarters office with application datacenters, a DMZ, and the Internet.</span></span>

![Contoso의 기존 IT 인프라](../media/contoso-infra-needs/contoso-infra-needs-fig1.png)

<span data-ttu-id="e7ffa-109">**그림 1: Contoso의 기존 IT 인프라**</span><span class="sxs-lookup"><span data-stu-id="e7ffa-109">**Figure 1: Contoso's existing IT infrastructure**</span></span>
 
<span data-ttu-id="e7ffa-110">온-프레미스 응용 프로그램 데이터 센터에서는 다음과 같은 것들을 호스팅합니다.</span><span class="sxs-lookup"><span data-stu-id="e7ffa-110">The on-premises application datacenters host:</span></span> 

- <span data-ttu-id="e7ffa-111">SQL Server 및 기타 Linux 데이터베이스를 사용하는 사용자 지정 LOB(기간 업무) 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="e7ffa-111">Custom line of business applications that use SQL Server and other Linux databases.</span></span>
- <span data-ttu-id="e7ffa-112">레거시 SharePoint 서버 집합</span><span class="sxs-lookup"><span data-stu-id="e7ffa-112">A set of legacy SharePoint servers.</span></span>
- <span data-ttu-id="e7ffa-113">파일 저장을 위한 조직 및 팀 수준 서버</span><span class="sxs-lookup"><span data-stu-id="e7ffa-113">Organization and team-level servers for file storage.</span></span>

<span data-ttu-id="e7ffa-114">또한 각 지역 허브 사무소는 유사한 응용 프로그램 집합을 가진 서버 집합을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="e7ffa-114">Additionally, each regional hub office supports a set of servers with a similar set of applications.</span></span> <span data-ttu-id="e7ffa-115">이 서버들은 지역 IT부서의 통제를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="e7ffa-115">These servers are under the control of regional IT departments.</span></span>

<span data-ttu-id="e7ffa-116">이러한 별도의 다중 지역 데이터 센터에 있는 응용 프로그램 및 데이터에 대한 검색 가능성은 계속해서 해결 과제로 남아 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7ffa-116">Searchability across the applications and data of these separate multi-geographical datacenters continues to be a challenge.</span></span>

<span data-ttu-id="e7ffa-117">Contoso의 본사 DMZ에서는 각 서버 집합이 다음을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e7ffa-117">In Contoso's headquarters DMZ, different sets of servers provide:</span></span>

- <span data-ttu-id="e7ffa-118">Contoso 공용 웹 사이트 호스팅 기능. 이러한 사이트에서 고객이 제품, 부품, 소모품 또는 서비스를 주문할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7ffa-118">Hosting for the Contoso public web site, from which customers can order products, parts, supplies, or service.</span></span>
- <span data-ttu-id="e7ffa-119">파트너와의 정보 교환 및 공동 작업을 위한 Contoso 파트너 엑스트라넷 호스팅 기능</span><span class="sxs-lookup"><span data-stu-id="e7ffa-119">Hosting for the Contoso partner extranet for partner communication and collaboration.</span></span>
- <span data-ttu-id="e7ffa-120">파리 본사 직원을 위한 Contoso 인트라넷 및 웹 프록시에 대한 VPN (가상 사설망) 기반 원격 액세스 기능</span><span class="sxs-lookup"><span data-stu-id="e7ffa-120">Virtual private network (VPN)-based remote access to the Contoso intranet and web proxying for workers in the Paris headquarters.</span></span>

## <a name="contosos-business-needs"></a><span data-ttu-id="e7ffa-121">Contoso의 비즈니스 요구 사항</span><span class="sxs-lookup"><span data-stu-id="e7ffa-121">Contoso's business needs</span></span>

<span data-ttu-id="e7ffa-122">Contoso의 비즈니스 요구 사항은 다섯 가지 주요 범주로 나뉩니다.</span><span class="sxs-lookup"><span data-stu-id="e7ffa-122">Contoso's business needs fall into five main categories.</span></span>

<span data-ttu-id="e7ffa-123">생산성:</span><span class="sxs-lookup"><span data-stu-id="e7ffa-123">Productivity:</span></span>

- <span data-ttu-id="e7ffa-124">보다 쉽게 공동으로 작업</span><span class="sxs-lookup"><span data-stu-id="e7ffa-124">Make collaboration easier</span></span>

  <span data-ttu-id="e7ffa-125">전자 메일 및 파일 공유 기반 공동 작업을 실시간으로 문서 변경, 보다 간편해진 온라인 모임, 캡처한 대화 스레드를 지원하는 온라인 모델로 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="e7ffa-125">Replace the email and file share-based collaboration with an online model that allows real-time changes on documents, easier online meetings, and captured conversation threads.</span></span>
- <span data-ttu-id="e7ffa-126">원격 및 모바일 작업자의 생산성 향상</span><span class="sxs-lookup"><span data-stu-id="e7ffa-126">Improve productivity for remote and mobile workers</span></span>

  <span data-ttu-id="e7ffa-127">많은 직원들이 가정 또는 현장에서 작업하는 경우, 병목 상태가 나타나는 VPN 솔루션을 클라우드의 Contoso 데이터 및 리소스 액세스 방식으로 대체하여 성능을 높입니다.</span><span class="sxs-lookup"><span data-stu-id="e7ffa-127">With many employees working from homes or in the field, replace the bottlenecked VPN solution with performant access to Contoso data and resources in the cloud.</span></span>
- <span data-ttu-id="e7ffa-128">창의성 및 혁신 증대</span><span class="sxs-lookup"><span data-stu-id="e7ffa-128">Increase creativity and innovation</span></span>

  <span data-ttu-id="e7ffa-129">수동 입력과 3D 시각화를 포함하여 최신 수준의 시각적 학습 및 아이디어 개발 방식을 활용할 수 있습니다.
</span><span class="sxs-lookup"><span data-stu-id="e7ffa-129">Take advantage of the latest visual learning and idea development methods, including inking and 3D visualization.</span></span>

<span data-ttu-id="e7ffa-130">보안:</span><span class="sxs-lookup"><span data-stu-id="e7ffa-130">Security:</span></span>

- <span data-ttu-id="e7ffa-131">ID 및 액세스 관리</span><span class="sxs-lookup"><span data-stu-id="e7ffa-131">Identity and access management</span></span>

  <span data-ttu-id="e7ffa-132">다중 요소 및 기타 형태의 인증을 적용하고 사용자 및 관리자 계정 자격 증명을 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="e7ffa-132">Enforce multi-factor and other forms of authentication and protect user and administrator account credentials.</span></span>

- <span data-ttu-id="e7ffa-133">위협 방지</span><span class="sxs-lookup"><span data-stu-id="e7ffa-133">Threat protection</span></span>

  <span data-ttu-id="e7ffa-134">맬웨어를 포함하는 외부 보안 위협으로부터 보호 -> 맬웨어를 포함하여 외부 보안 위협으로부터 보호</span><span class="sxs-lookup"><span data-stu-id="e7ffa-134">Protect against external security threats, including email and operating system-based malware.</span></span>

- <span data-ttu-id="e7ffa-135">정보 보호</span><span class="sxs-lookup"><span data-stu-id="e7ffa-135">Information protection</span></span>

  <span data-ttu-id="e7ffa-136">고객 데이터, 디자인 및 제조 사양 및 직원 정보와 같은 고가치 디지털 자산에 대한 액세스를 잠그고 암호화합니다.</span><span class="sxs-lookup"><span data-stu-id="e7ffa-136">Lock down access to and encrypt high-value digital assets, such as customer data, design and manufacturing specifications, and employee information.</span></span>

- <span data-ttu-id="e7ffa-137">보안 관리</span><span class="sxs-lookup"><span data-stu-id="e7ffa-137">Security management</span></span>

  <span data-ttu-id="e7ffa-138">보안 환경을 모니터링하고 위협을 실시간으로 감지하고 대응할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7ffa-138">Monitor security posture and be able to detect and respond to threats in real time.</span></span>

<span data-ttu-id="e7ffa-139">원격 및 모바일 액세스 및 비즈니스 파트너:</span><span class="sxs-lookup"><span data-stu-id="e7ffa-139">Remote and mobile access and business partners:</span></span>

- <span data-ttu-id="e7ffa-140">원격 및 모바일 작업자를 위한 향상된 보안</span><span class="sxs-lookup"><span data-stu-id="e7ffa-140">Better security for remote and mobile workers</span></span>

  <span data-ttu-id="e7ffa-141">BYOD(Bring Your Own Device) 및 회사 소유의 장치 관리를 도입하여 보안 액세스, 올바른 응용 프로그램 동작 및 회사 데이터 보호를 보장합니다.</span><span class="sxs-lookup"><span data-stu-id="e7ffa-141">Institute Bring Your Own Device (BYOD) and company-owned device management to ensure secured access, correct application behavior, and company data protection.</span></span>

- <span data-ttu-id="e7ffa-142">직원을 위한 원격 액세스 인프라 감소</span><span class="sxs-lookup"><span data-stu-id="e7ffa-142">Reduce remote access infrastructure for employees</span></span>

  <span data-ttu-id="e7ffa-143">일반적으로 액세스하는 리소스를 클라우드로 이동하여 유지 관리 및 지원 비용을 절감하고 원격 액세스 솔루션의 성능을 향상시킵니다.</span><span class="sxs-lookup"><span data-stu-id="e7ffa-143">Reduce maintenance and support costs and improve performance for remote access solution by moving commonly-accessed resources to the cloud.</span></span>

- <span data-ttu-id="e7ffa-144">B2B(기업 간) 거래에 대해 더 나은 연결 제공 및 오버헤드 감소</span><span class="sxs-lookup"><span data-stu-id="e7ffa-144">Provide better connectivity and lower overhead for Business-to-Business (B2B) transactions</span></span>

  <span data-ttu-id="e7ffa-145">페더레이션 인증을 사용하는 클라우드 기반 솔루션으로 노후되고 비용이 많이 드는 파트너 엑스트라넷을 교체합니다.</span><span class="sxs-lookup"><span data-stu-id="e7ffa-145">Replace aging and expensive partner extranet with a cloud-based solution that uses federated authentication.</span></span>

<span data-ttu-id="e7ffa-146">규정 준수</span><span class="sxs-lookup"><span data-stu-id="e7ffa-146">Compliance:</span></span>

- <span data-ttu-id="e7ffa-147">지역별 규정 준수</span><span class="sxs-lookup"><span data-stu-id="e7ffa-147">Adhere to regional regulatory requirements</span></span>

  <span data-ttu-id="e7ffa-148">데이터 저장소, 암호화, 데이터 개인 정보 보호에 대한 업계 및 지역별 규정과 개인 데이터 규정[예: 유럽 연합을 위한 GDPR(일반 데이터 보호 규정)]을 준수합니다.</span><span class="sxs-lookup"><span data-stu-id="e7ffa-148">Become and remain compliant with industry and regional regulations for data storage, encryption, data privacy, and personal data regulations, such as the General Data Protection Regulation (GDPR) for the Europe Union.</span></span>

<span data-ttu-id="e7ffa-149">관리:</span><span class="sxs-lookup"><span data-stu-id="e7ffa-149">Management:</span></span>

- <span data-ttu-id="e7ffa-150">클라이언트 PC 및 장치에서 실행되는 소프트웨어를 관리하기 위한 IT 오버헤드를 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="e7ffa-150">Lower the IT overhead for managing software running on client PCs and devices</span></span>

  <span data-ttu-id="e7ffa-151">조직 전체에서 Windows 운영 체제 및 Microsoft 365 앱의 업데이트 설치를 자동화합니다.</span><span class="sxs-lookup"><span data-stu-id="e7ffa-151">Automate the installation of updates to the Windows operating system and Microsoft 365 Apps for enterprise across the organization.</span></span>

## <a name="mapping-contosos-business-needs-to-microsoft-365-for-enterprise"></a><span data-ttu-id="e7ffa-152">Contoso의 비즈니스 요구 사항을 엔터프라이즈에 대 한 Microsoft 365로 매핑</span><span class="sxs-lookup"><span data-stu-id="e7ffa-152">Mapping Contoso's business needs to Microsoft 365 for enterprise</span></span>

<span data-ttu-id="e7ffa-153">Contoso의 IT 부서는 배포 전에 Microsoft 365 E5 기능에 대한 비즈니스 요구 사항의 매핑을 다음과 같이 결정했습니다.</span><span class="sxs-lookup"><span data-stu-id="e7ffa-153">Contoso's IT department determined the following mapping of business needs to Microsoft 365 E5 features prior to deployment:</span></span>


| <span data-ttu-id="e7ffa-154">Category</span><span class="sxs-lookup"><span data-stu-id="e7ffa-154">Category</span></span> | <span data-ttu-id="e7ffa-155">비즈니스 요구</span><span class="sxs-lookup"><span data-stu-id="e7ffa-155">Business need</span></span> | <span data-ttu-id="e7ffa-156">Enterprise 제품 또는 기능에 대 한 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e7ffa-156">Microsoft 365 for enterprise products or features</span></span> |
|:-------|:-----|:-----|
| <span data-ttu-id="e7ffa-157">생산성</span><span class="sxs-lookup"><span data-stu-id="e7ffa-157">Productivity</span></span> |  |  |
|  | <span data-ttu-id="e7ffa-158">보다 쉽게 공동으로 작업</span><span class="sxs-lookup"><span data-stu-id="e7ffa-158">Make collaboration easier</span></span> | <span data-ttu-id="e7ffa-159">Microsoft Teams, SharePoint, OneDrive</span><span class="sxs-lookup"><span data-stu-id="e7ffa-159">Microsoft Teams, SharePoint, OneDrive</span></span> |
|  | <span data-ttu-id="e7ffa-160">원격 및 모바일 작업자의 생산성 향상</span><span class="sxs-lookup"><span data-stu-id="e7ffa-160">Improve productivity for remote and mobile workers</span></span> | <span data-ttu-id="e7ffa-161">Microsoft 365 워크로드 및 클라우드 기반 데이터</span><span class="sxs-lookup"><span data-stu-id="e7ffa-161">Microsoft 365 workloads and cloud-based data</span></span> |
|  | <span data-ttu-id="e7ffa-162">창의성 및 혁신 증대</span><span class="sxs-lookup"><span data-stu-id="e7ffa-162">Increase creativity and innovation</span></span> | <span data-ttu-id="e7ffa-163">Windows Ink, Cortana at Work, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="e7ffa-163">Windows Ink, Cortana at Work, PowerPoint</span></span> |
| <span data-ttu-id="e7ffa-164">보안</span><span class="sxs-lookup"><span data-stu-id="e7ffa-164">Security</span></span> |  |  |
|  | <span data-ttu-id="e7ffa-165">ID & 액세스 관리</span><span class="sxs-lookup"><span data-stu-id="e7ffa-165">Identity & access management</span></span> | <span data-ttu-id="e7ffa-166">Azure MFA (Multi-Factor Authentication) 및 Azure PIM (Privileged Identity Management다)를 포함하는 전용 전역 관리자 계정</span><span class="sxs-lookup"><span data-stu-id="e7ffa-166">Dedicated global administrator accounts with Azure Multi-Factor Authentication (MFA) and Azure AD Privileged Identity Management (PIM)</span></span> <BR> <span data-ttu-id="e7ffa-167">모든 사용자 계정에 대한 MFA</span><span class="sxs-lookup"><span data-stu-id="e7ffa-167">MFA for all user accounts</span></span> <BR> <span data-ttu-id="e7ffa-168">조건부 액세스</span><span class="sxs-lookup"><span data-stu-id="e7ffa-168">Conditional Access</span></span> <BR> <span data-ttu-id="e7ffa-169">Windows Hello</span><span class="sxs-lookup"><span data-stu-id="e7ffa-169">Windows Hello</span></span> <BR> <span data-ttu-id="e7ffa-170">Windows Credential Guard</span><span class="sxs-lookup"><span data-stu-id="e7ffa-170">Windows Credential Guard</span></span> |
|  | <span data-ttu-id="e7ffa-171">위협 방지</span><span class="sxs-lookup"><span data-stu-id="e7ffa-171">Threat protection</span></span> | <span data-ttu-id="e7ffa-172">Advanced Threat Analytics</span><span class="sxs-lookup"><span data-stu-id="e7ffa-172">Advanced Threat Analytics</span></span> <BR> <span data-ttu-id="e7ffa-173">Windows Defender</span><span class="sxs-lookup"><span data-stu-id="e7ffa-173">Windows Defender</span></span> <BR> <span data-ttu-id="e7ffa-174">Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="e7ffa-174">Advanced Threat Protection</span></span> <BR> <span data-ttu-id="e7ffa-175">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="e7ffa-175">Office 365 Advanced Threat Protection</span></span> <BR> <span data-ttu-id="e7ffa-176">Microsoft 365 위협 조사 및 대응</span><span class="sxs-lookup"><span data-stu-id="e7ffa-176">Microsoft 365 threat investigation and response</span></span> <BR> |
|  | <span data-ttu-id="e7ffa-177">정보 보호</span><span class="sxs-lookup"><span data-stu-id="e7ffa-177">Information protection</span></span> | <span data-ttu-id="e7ffa-178">Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="e7ffa-178">Azure Information Protection</span></span> <BR> <span data-ttu-id="e7ffa-179">DLP(데이터 손실 방지)</span><span class="sxs-lookup"><span data-stu-id="e7ffa-179">Data Loss Prevention (DLP)</span></span> <BR> <span data-ttu-id="e7ffa-180">WIP(Windows Information Protection)</span><span class="sxs-lookup"><span data-stu-id="e7ffa-180">Windows Information Protection (WIP)</span></span> <BR> <span data-ttu-id="e7ffa-181">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="e7ffa-181">Microsoft Cloud App Security</span></span> <BR> <span data-ttu-id="e7ffa-182">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="e7ffa-182">Microsoft Intune</span></span> |
|  | <span data-ttu-id="e7ffa-183">보안 관리</span><span class="sxs-lookup"><span data-stu-id="e7ffa-183">Security management</span></span> | <span data-ttu-id="e7ffa-184">Azure Security Center</span><span class="sxs-lookup"><span data-stu-id="e7ffa-184">Azure Security Center</span></span>  <BR> <span data-ttu-id="e7ffa-185">Windows Defender 보안 센터</span><span class="sxs-lookup"><span data-stu-id="e7ffa-185">Windows Defender Security Center</span></span> |
| <span data-ttu-id="e7ffa-186">원격 및 모바일 액세스 및 비즈니스 파트너</span><span class="sxs-lookup"><span data-stu-id="e7ffa-186">Remote and mobile access and business partners</span></span> |  |  |
|  | <span data-ttu-id="e7ffa-187">원격 및 모바일 작업자를 위한 향상된 보안</span><span class="sxs-lookup"><span data-stu-id="e7ffa-187">Better security for remote and mobile workers</span></span> | <span data-ttu-id="e7ffa-188">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="e7ffa-188">Microsoft Intune</span></span> |
|  | <span data-ttu-id="e7ffa-189">직원을 위한 원격 액세스 인프라 감소</span><span class="sxs-lookup"><span data-stu-id="e7ffa-189">Reduce remote access infrastructure for employees</span></span> | <span data-ttu-id="e7ffa-190">Microsoft 365 워크로드 및 클라우드 기반 데이터</span><span class="sxs-lookup"><span data-stu-id="e7ffa-190">Microsoft 365 workloads and cloud-based data</span></span> |
|  | <span data-ttu-id="e7ffa-191">B2B 거래에 대해 더 나은 연결 제공 및 오버헤드 감소</span><span class="sxs-lookup"><span data-stu-id="e7ffa-191">Provide better connectivity and lower overhead for B2B transactions</span></span> | <span data-ttu-id="e7ffa-192">페더레이션된 인증 및 클라우드 기반 리소스</span><span class="sxs-lookup"><span data-stu-id="e7ffa-192">Federated authentication and cloud-based resources</span></span> |
| <span data-ttu-id="e7ffa-193">규정 준수</span><span class="sxs-lookup"><span data-stu-id="e7ffa-193">Compliance</span></span> |  |  |
|  | <span data-ttu-id="e7ffa-194">지역별 규정 준수</span><span class="sxs-lookup"><span data-stu-id="e7ffa-194">Adhere to regional regulatory requirements</span></span> | <span data-ttu-id="e7ffa-195">Microsoft 365의 GDPR 기능</span><span class="sxs-lookup"><span data-stu-id="e7ffa-195">GDPR features in Microsoft 365</span></span> |
| <span data-ttu-id="e7ffa-196">관리</span><span class="sxs-lookup"><span data-stu-id="e7ffa-196">Management</span></span> |  |  |
|  | <span data-ttu-id="e7ffa-197">클라이언트 업데이트 설치에 대한 IT 오버헤드 감소</span><span class="sxs-lookup"><span data-stu-id="e7ffa-197">Lower the IT overhead for installing client updates</span></span> | <span data-ttu-id="e7ffa-198">배포 링</span><span class="sxs-lookup"><span data-stu-id="e7ffa-198">Deployment rings</span></span> <BR> <span data-ttu-id="e7ffa-199">Windows 10 Enterprise 업데이트</span><span class="sxs-lookup"><span data-stu-id="e7ffa-199">Windows 10 Enterprise updates</span></span> <BR> <span data-ttu-id="e7ffa-200">Microsoft Office 365 ProPlus 업데이트</span><span class="sxs-lookup"><span data-stu-id="e7ffa-200">Microsoft 365 Apps for enterprise updates</span></span> |
||||

## <a name="next-step"></a><span data-ttu-id="e7ffa-201">다음 단계</span><span class="sxs-lookup"><span data-stu-id="e7ffa-201">Next step</span></span>

<span data-ttu-id="e7ffa-202">Contoso Corporation의 온-프레미스 네트워크 및 이러한 네트워크가 Microsoft 365 클라우드 기반 리소스에 대해 최적화된 액세스 및 대기 시간을 지원하는 방식을 [자세히 알아봅니다](contoso-networking.md).</span><span class="sxs-lookup"><span data-stu-id="e7ffa-202">[Learn](contoso-networking.md) about the Contoso Corporation’s on-premises network and how it was optimized for access and latency to Microsoft 365 cloud-based resources.</span></span>

## <a name="see-also"></a><span data-ttu-id="e7ffa-203">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e7ffa-203">See also</span></span>

[<span data-ttu-id="e7ffa-204">엔터프라이즈용 Microsoft 365 개요</span><span class="sxs-lookup"><span data-stu-id="e7ffa-204">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="e7ffa-205">테스트 랩 가이드</span><span class="sxs-lookup"><span data-stu-id="e7ffa-205">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
