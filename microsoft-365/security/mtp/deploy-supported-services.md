---
title: Microsoft Threat Protection에서 지원 되는 서비스 배포
description: Microsoft Threat Protection, 라이선스 요구 사항 및 배포 절차에 따라 통합 될 수 있는 Microsoft 보안 서비스에 대해 알아봅니다.
keywords: 배포, 라이선스, 지원 서비스, 프로 비전, 구성 Microsoft Threat Protection, M365, 라이선스 자격, Microsoft Defender ATP, MDATP, Office 365 ATP, Azure ATP, Microsoft Cloud App Security, MCAS, advanced Threat Protection, E5, A5, EMS
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365-initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 3a5db0b9709a9596ccd6560d7f2e546dd3753332
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/09/2020
ms.locfileid: "48413355"
---
# <a name="deploy-supported-services"></a><span data-ttu-id="cf7b5-104">지원 서비스 사용</span><span class="sxs-lookup"><span data-stu-id="cf7b5-104">Deploy supported services</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="cf7b5-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="cf7b5-105">**Applies to:**</span></span>
- <span data-ttu-id="cf7b5-106">Microsoft 위협 방지</span><span class="sxs-lookup"><span data-stu-id="cf7b5-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="cf7b5-107">[Microsoft Threat Protection](microsoft-threat-protection.md) 은 다양 한 Microsoft 보안 서비스를 통합 하 여 정교한 공격에 대 한 중앙 집중식 검색, 예방 및 조사 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf7b5-107">[Microsoft Threat Protection](microsoft-threat-protection.md) integrates various Microsoft security services to provide centralized detection, prevention, and investigation capabilities against sophisticated attacks.</span></span> <span data-ttu-id="cf7b5-108">이 문서에서는 지원 되는 서비스, 라이선스 요구 사항, 하나 이상의 서비스 배포와 관련 된 장점과 제한 사항에 대해 설명 하 고 개별적으로 배포 하는 방법에 대 한 링크를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf7b5-108">This article describes the supported services, their licensing requirements, the advantages and limitations associated with deploying one or more services, and links to how you can fully deploy them individually.</span></span>

## <a name="supported-services"></a><span data-ttu-id="cf7b5-109">지원 되는 서비스</span><span class="sxs-lookup"><span data-stu-id="cf7b5-109">Supported services</span></span>
<span data-ttu-id="cf7b5-110">Microsoft 365 E5, E5 Security, A5 또는 A5 보안 라이선스 또는 유효한 라이선스 조합을 사용 하면 지원 되는 다음 서비스에 대 한 액세스를 제공 하 고 통해 microsoft 365 보안 센터에서 Microsoft Threat Protection을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf7b5-110">A Microsoft 365 E5, E5 Security, A5, or A5 Security license or a valid combination of licenses provides access to the following supported services and entitles you to use Microsoft Threat Protection in Microsoft 365 security center.</span></span> [<span data-ttu-id="cf7b5-111">라이선스 요구 사항 참조</span><span class="sxs-lookup"><span data-stu-id="cf7b5-111">See licensing requirements</span></span>](prerequisites.md#licensing-requirements)

| <span data-ttu-id="cf7b5-112">지원 되는 서비스</span><span class="sxs-lookup"><span data-stu-id="cf7b5-112">Supported service</span></span> | <span data-ttu-id="cf7b5-113">설명</span><span class="sxs-lookup"><span data-stu-id="cf7b5-113">Description</span></span> |
| ------ | ------ |
| <span data-ttu-id="cf7b5-114">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="cf7b5-114">Microsoft Defender ATP</span></span> | <span data-ttu-id="cf7b5-115">강력한 행태 센서, 클라우드 분석 및 위협 인텔리전스를 기반으로 구축 된 Endpoint protection 제품군</span><span class="sxs-lookup"><span data-stu-id="cf7b5-115">Endpoint protection suite built around powerful behavioral sensors, cloud analytics, and threat intelligence</span></span> |
| <span data-ttu-id="cf7b5-116">Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="cf7b5-116">Office 365 ATP</span></span> | <span data-ttu-id="cf7b5-117">전자 메일 및 기타 공동 작업 도구를 비롯 하 여 Office 365의 앱 및 데이터에 대 한 고급 보호 기능</span><span class="sxs-lookup"><span data-stu-id="cf7b5-117">Advanced protection for your apps and data in Office 365, including email and other collaboration tools</span></span> |
| <span data-ttu-id="cf7b5-118">Azure ATP</span><span class="sxs-lookup"><span data-stu-id="cf7b5-118">Azure ATP</span></span> | <span data-ttu-id="cf7b5-119">상호 연관 된 Active Directory 신호를 사용 하 여 advanced threat, 손상 된 id 및 악의적인 참가자에 대해 방어</span><span class="sxs-lookup"><span data-stu-id="cf7b5-119">Defend against advanced threats, compromised identities, and malicious insiders using correlated Active Directory signals</span></span> |
| <span data-ttu-id="cf7b5-120">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="cf7b5-120">Microsoft Cloud App Security</span></span> | <span data-ttu-id="cf7b5-121">Microsoft 및 타사 클라우드 서비스를 통해 cyberthreats를 식별 하 고 공격 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf7b5-121">Identify and combat cyberthreats across your Microsoft and third-party cloud services</span></span> |

## <a name="deployed-services-and-functionality"></a><span data-ttu-id="cf7b5-122">배포 된 서비스 및 기능</span><span class="sxs-lookup"><span data-stu-id="cf7b5-122">Deployed services and functionality</span></span>
<span data-ttu-id="cf7b5-123">Microsoft 위협 보호를 통해 지원 되는 서비스를 배포 하는 것과 같은 향상 된 가시성, 상관 관계 및 수정이 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf7b5-123">Microsoft Threat Protection provides better visibility, correlation, and remediation as you deploy more supported services.</span></span>

### <a name="benefits-of-full-deployment"></a><span data-ttu-id="cf7b5-124">전체 배포의 장점</span><span class="sxs-lookup"><span data-stu-id="cf7b5-124">Benefits of full deployment</span></span>
<span data-ttu-id="cf7b5-125">Microsoft Threat Protection의 전체 이점을 얻으려면 지원 되는 모든 서비스를 배포 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="cf7b5-125">To get the complete benefits of Microsoft Threat Protection, we recommend deploying all supported services.</span></span> <span data-ttu-id="cf7b5-126">전체 배포의 주요 이점은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cf7b5-126">Here are some of the key benefits of full deployment:</span></span>
- <span data-ttu-id="cf7b5-127">사용 가능한 모든 센서 및 서비스 관련 분석 기능에서 발생 하는 경고 및 이벤트 신호의 기반 인시던트 식별 및 상관 관계</span><span class="sxs-lookup"><span data-stu-id="cf7b5-127">Incidents are identified and correlated based on alerts and event signals from all available sensors and service-specific analysis capabilities</span></span>
- <span data-ttu-id="cf7b5-128">장치, 사서함 및 사용자 계정을 비롯 한 다양 한 엔터티 유형에 서 자동 조사 및 재구성 (AIR) playbook가 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf7b5-128">Automated investigation and remediation (AIR) playbooks apply across various entity types, including devices, mailboxes, and user accounts</span></span>
- <span data-ttu-id="cf7b5-129">장치, 사서함 및 기타 엔터티에서 이벤트 및 엔터티 데이터에 대 한 보다 포괄적인 고급 구하기 스키마를 쿼리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf7b5-129">A more comprehensive advanced hunting schema can be queried for event and entity data from devices, mailboxes, and other entities</span></span>

### <a name="limited-deployment-scenarios"></a><span data-ttu-id="cf7b5-130">제한 된 배포 시나리오</span><span class="sxs-lookup"><span data-stu-id="cf7b5-130">Limited deployment scenarios</span></span>
<span data-ttu-id="cf7b5-131">배포 하는 지원 되는 각 서비스는 매우 다양 한 원시 신호의 집합 뿐 아니라 상호 연관 된 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf7b5-131">Each supported service that you deploy provides an extremely rich set of raw signals as well as correlated information.</span></span> <span data-ttu-id="cf7b5-132">제한 된 배포로 인해 Microsoft Threat Protection 기능을 사용 하지 않도록 설정 해도 끝점, 앱, 데이터 및 id에 대 한 포괄적인 가시성을 제공 하는 기능을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cf7b5-132">While limited deployment doesn’t cause Microsoft Threat Protection functionality to turn off, its ability to provide comprehensive visibility across your endpoints, apps, data, and identities is affected.</span></span> <span data-ttu-id="cf7b5-133">동시에 관리 기능은 배포한 서비스에서 관리할 수 있는 엔터티에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf7b5-133">At the same time, any remediation capabilities only apply to entities that can be managed by the services you’ve deployed.</span></span>

<span data-ttu-id="cf7b5-134">아래 표에는 지원 되는 각 서비스가 추가 데이터를 제공 하는 방법, 데이터를 연관 시켜 추가 정보를 얻을 수 있는 기회, 개선 및 대응 기능에 대 한 자세한 내용이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf7b5-134">The table below lists how each supported service provides additional data, opportunities to obtain additional insight by correlating the data, and better remediation and response capabilities.</span></span>

| <span data-ttu-id="cf7b5-135">서비스</span><span class="sxs-lookup"><span data-stu-id="cf7b5-135">Service</span></span> | <span data-ttu-id="cf7b5-136">데이터 (상호 연관 & 정보)</span><span class="sxs-lookup"><span data-stu-id="cf7b5-136">Data (signals & correlated info)</span></span> | <span data-ttu-id="cf7b5-137">업데이트 관리 & 응답 범위</span><span class="sxs-lookup"><span data-stu-id="cf7b5-137">Remediation & response scope</span></span> |
| ------ | ------ | ------ |
| <span data-ttu-id="cf7b5-138">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="cf7b5-138">Microsoft Defender ATP</span></span> | <span data-ttu-id="cf7b5-139">-끝점 상태 및 원시 이벤트</span><span class="sxs-lookup"><span data-stu-id="cf7b5-139">- Endpoint states and raw events</span></span><br /><span data-ttu-id="cf7b5-140">-바이러스 백신, EDR, attack surface reduction를 포함 한 끝점 감지 및 경고</span><span class="sxs-lookup"><span data-stu-id="cf7b5-140">- Endpoint detections and alerts, including antivirus, EDR, attack surface reduction</span></span><br /><span data-ttu-id="cf7b5-141">-끝점에서 관찰 된 파일 및 기타 엔터티에 대 한 정보</span><span class="sxs-lookup"><span data-stu-id="cf7b5-141">- Info on files and other entities observed on endpoints</span></span> | <span data-ttu-id="cf7b5-142">끝점</span><span class="sxs-lookup"><span data-stu-id="cf7b5-142">Endpoints</span></span> |
| <span data-ttu-id="cf7b5-143">Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="cf7b5-143">Office 365 ATP</span></span> | <span data-ttu-id="cf7b5-144">-메일 및 사서함 상태 및 원시 이벤트</span><span class="sxs-lookup"><span data-stu-id="cf7b5-144">- Mail and mailbox states and raw events</span></span><br /><span data-ttu-id="cf7b5-145">-전자 메일, 첨부 파일 및 링크 감지</span><span class="sxs-lookup"><span data-stu-id="cf7b5-145">- Email, attachment, and link detections</span></span> | <span data-ttu-id="cf7b5-146">-사서함</span><span class="sxs-lookup"><span data-stu-id="cf7b5-146">- Mailboxes</span></span><br /><span data-ttu-id="cf7b5-147">-Microsoft 365 계정</span><span class="sxs-lookup"><span data-stu-id="cf7b5-147">- Microsoft 365 accounts</span></span> |
| <span data-ttu-id="cf7b5-148">Azure ATP</span><span class="sxs-lookup"><span data-stu-id="cf7b5-148">Azure ATP</span></span> | <span data-ttu-id="cf7b5-149">-Active Directory 신호 (인증 이벤트 포함)</span><span class="sxs-lookup"><span data-stu-id="cf7b5-149">- Active Directory signals, including authentication events</span></span><br /><span data-ttu-id="cf7b5-150">-Id 관련 동작 감지</span><span class="sxs-lookup"><span data-stu-id="cf7b5-150">- Identity-related behavioral detections</span></span> | <span data-ttu-id="cf7b5-151">ID</span><span class="sxs-lookup"><span data-stu-id="cf7b5-151">Identities</span></span> |
| <span data-ttu-id="cf7b5-152">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="cf7b5-152">Microsoft Cloud App Security</span></span> | <span data-ttu-id="cf7b5-153">-Unsanctioned 클라우드 앱 및 서비스 검색 (섀도 IT)</span><span class="sxs-lookup"><span data-stu-id="cf7b5-153">- Detection of unsanctioned cloud apps and services (shadow IT)</span></span><br /><span data-ttu-id="cf7b5-154">-클라우드 앱에 대 한 데이터 노출</span><span class="sxs-lookup"><span data-stu-id="cf7b5-154">- Exposure of data to cloud apps</span></span><br /><span data-ttu-id="cf7b5-155">-클라우드 앱과 연결 된 위협 활동</span><span class="sxs-lookup"><span data-stu-id="cf7b5-155">- Threat activity associated with cloud apps</span></span> | <span data-ttu-id="cf7b5-156">클라우드 앱</span><span class="sxs-lookup"><span data-stu-id="cf7b5-156">Cloud apps</span></span> |

## <a name="deploy-the-services"></a><span data-ttu-id="cf7b5-157">서비스 배포</span><span class="sxs-lookup"><span data-stu-id="cf7b5-157">Deploy the services</span></span>
<span data-ttu-id="cf7b5-158">각 서비스를 배포 하려면 일반적으로 테 넌 트 및 몇 가지 초기 구성에 프로 비전을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf7b5-158">Deploying each service typically requires provisioning to your tenant and some initial configuration.</span></span> <span data-ttu-id="cf7b5-159">이러한 각 서비스가 배포 되는 방식을 이해 하려면 다음 표를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="cf7b5-159">See the following table to understand how each of these services are deployed.</span></span>

| <span data-ttu-id="cf7b5-160">서비스</span><span class="sxs-lookup"><span data-stu-id="cf7b5-160">Service</span></span> | <span data-ttu-id="cf7b5-161">프로 비전 지침</span><span class="sxs-lookup"><span data-stu-id="cf7b5-161">Provisioning instructions</span></span> | <span data-ttu-id="cf7b5-162">초기 구성</span><span class="sxs-lookup"><span data-stu-id="cf7b5-162">Initial configuration</span></span> |
| ------ | ------ | ------ |
| <span data-ttu-id="cf7b5-163">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="cf7b5-163">Microsoft Defender ATP</span></span> | [<span data-ttu-id="cf7b5-164">Microsoft Defender ATP 배포 가이드</span><span class="sxs-lookup"><span data-stu-id="cf7b5-164">Microsoft Defender ATP deployment guide</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/deployment-phases) | <span data-ttu-id="cf7b5-165">*프로비저닝 지침 참조*</span><span class="sxs-lookup"><span data-stu-id="cf7b5-165">*See provisioning instructions*</span></span> |
| <span data-ttu-id="cf7b5-166">Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="cf7b5-166">Office 365 ATP</span></span> | <span data-ttu-id="cf7b5-167">*없음, Office 365와 함께 구축 됨*</span><span class="sxs-lookup"><span data-stu-id="cf7b5-167">*None, provisioned with Office 365*</span></span> | [<span data-ttu-id="cf7b5-168">ATP 정책 구성</span><span class="sxs-lookup"><span data-stu-id="cf7b5-168">Configure ATP policies</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#configure-atp-policies) |
| <span data-ttu-id="cf7b5-169">Azure ATP</span><span class="sxs-lookup"><span data-stu-id="cf7b5-169">Azure ATP</span></span> | [<span data-ttu-id="cf7b5-170">빠른 시작: Azure ATP 인스턴스 만들기</span><span class="sxs-lookup"><span data-stu-id="cf7b5-170">Quickstart: Create your Azure ATP instance</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/install-atp-step1) | <span data-ttu-id="cf7b5-171">*프로비저닝 지침 참조*</span><span class="sxs-lookup"><span data-stu-id="cf7b5-171">*See provisioning instructions*</span></span> |
| <span data-ttu-id="cf7b5-172">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="cf7b5-172">Microsoft Cloud App Security</span></span> | <span data-ttu-id="cf7b5-173">*없음*</span><span class="sxs-lookup"><span data-stu-id="cf7b5-173">*None*</span></span> | [<span data-ttu-id="cf7b5-174">퀵 스타트: Microsoft Cloud App Security 시작</span><span class="sxs-lookup"><span data-stu-id="cf7b5-174">Quickstart: Get started with Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/getting-started-with-cloud-app-security) |

<span data-ttu-id="cf7b5-175">지원 되는 서비스를 배포한 후에는 [Microsoft Threat Protection을 켜십시오](mtp-enable.md).</span><span class="sxs-lookup"><span data-stu-id="cf7b5-175">Once you’ve deployed the supported services, [turn on Microsoft Threat Protection](mtp-enable.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="cf7b5-176">관련 항목</span><span class="sxs-lookup"><span data-stu-id="cf7b5-176">Related topics</span></span>

- [<span data-ttu-id="cf7b5-177">Microsoft 위협 방지 개요</span><span class="sxs-lookup"><span data-stu-id="cf7b5-177">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="cf7b5-178">Microsoft 위협 방지 설정</span><span class="sxs-lookup"><span data-stu-id="cf7b5-178">Turn on Microsoft Threat Protection</span></span>](mtp-enable.md)
- [<span data-ttu-id="cf7b5-179">Microsoft Defender ATP 개요</span><span class="sxs-lookup"><span data-stu-id="cf7b5-179">Microsoft Defender ATP overview</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [<span data-ttu-id="cf7b5-180">Office 365 ATP 개요</span><span class="sxs-lookup"><span data-stu-id="cf7b5-180">Office 365 ATP overview</span></span>](../office-365-security/office-365-atp.md)
- [<span data-ttu-id="cf7b5-181">Microsoft Cloud App Security 개요</span><span class="sxs-lookup"><span data-stu-id="cf7b5-181">Microsoft Cloud App Security overview</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [<span data-ttu-id="cf7b5-182">Azure ATP 개요</span><span class="sxs-lookup"><span data-stu-id="cf7b5-182">Azure ATP overview</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
