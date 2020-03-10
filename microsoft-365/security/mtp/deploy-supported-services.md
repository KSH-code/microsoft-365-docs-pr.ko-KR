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
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 2b0e033bb80fd73d5b5194bd59ab9c9f14a644b3
ms.sourcegitcommit: cc3b64a91e16ccdaa9c338b9a9056dbe3963ba9e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/10/2020
ms.locfileid: "42569053"
---
# <a name="deploy-supported-services"></a><span data-ttu-id="ecbb1-104">지원 서비스 사용</span><span class="sxs-lookup"><span data-stu-id="ecbb1-104">Deploy supported services</span></span>

<span data-ttu-id="ecbb1-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="ecbb1-105">**Applies to:**</span></span>
- <span data-ttu-id="ecbb1-106">Microsoft 위협 방지</span><span class="sxs-lookup"><span data-stu-id="ecbb1-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="ecbb1-107">[Microsoft Threat Protection](microsoft-threat-protection.md) 은 다양 한 Microsoft 보안 서비스를 통합 하 여 정교한 공격에 대 한 중앙 집중식 검색, 예방 및 조사 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ecbb1-107">[Microsoft Threat Protection](microsoft-threat-protection.md) integrates various Microsoft security services to provide centralized detection, prevention, and investigation capabilities against sophisticated attacks.</span></span> <span data-ttu-id="ecbb1-108">이 문서에서는 지원 되는 서비스, 라이선스 요구 사항, 하나 이상의 서비스 배포와 관련 된 장점과 제한 사항에 대해 설명 하 고 개별적으로 배포 하는 방법에 대 한 링크를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ecbb1-108">This article describes the supported services, their licensing requirements, the advantages and limitations associated with deploying one or more services, and links to how you can fully deploy them individually.</span></span>

## <a name="supported-services"></a><span data-ttu-id="ecbb1-109">지원 되는 서비스</span><span class="sxs-lookup"><span data-stu-id="ecbb1-109">Supported services</span></span>
<span data-ttu-id="ecbb1-110">[Microsoft 365 E5, E5 Security 또는 A5 라이선스 또는 유효한 라이선스 조합을](prerequisites.md#licensing-requirements) 사용 하면 지원 되는 다음 서비스에 대 한 액세스를 제공 하 고 통해 microsoft 365 보안 센터에서 Microsoft Threat Protection을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ecbb1-110">A [Microsoft 365 E5, E5 Security, or A5 license or a valid combination of licenses](prerequisites.md#licensing-requirements) provides access to the following supported services and entitles you to use Microsoft Threat Protection in Microsoft 365 security center.</span></span>

| <span data-ttu-id="ecbb1-111">지원 되는 서비스</span><span class="sxs-lookup"><span data-stu-id="ecbb1-111">Supported service</span></span> | <span data-ttu-id="ecbb1-112">설명</span><span class="sxs-lookup"><span data-stu-id="ecbb1-112">Description</span></span> |
| ------ | ------ |
| <span data-ttu-id="ecbb1-113">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="ecbb1-113">Microsoft Defender ATP</span></span> | <span data-ttu-id="ecbb1-114">강력한 행태 센서, 클라우드 분석 및 위협 인텔리전스를 기반으로 구축 된 Endpoint protection 제품군</span><span class="sxs-lookup"><span data-stu-id="ecbb1-114">Endpoint protection suite built around powerful behavioral sensors, cloud analytics, and threat intelligence</span></span> |
| <span data-ttu-id="ecbb1-115">Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="ecbb1-115">Office 365 ATP</span></span> | <span data-ttu-id="ecbb1-116">전자 메일 및 기타 공동 작업 도구를 비롯 하 여 Office 365의 앱 및 데이터에 대 한 고급 보호 기능</span><span class="sxs-lookup"><span data-stu-id="ecbb1-116">Advanced protection for your apps and data in Office 365, including email and other collaboration tools</span></span> |
| <span data-ttu-id="ecbb1-117">Azure ATP</span><span class="sxs-lookup"><span data-stu-id="ecbb1-117">Azure ATP</span></span> | <span data-ttu-id="ecbb1-118">상호 연관 된 Active Directory 신호를 사용 하 여 advanced threat, 손상 된 id 및 악의적인 참가자에 대 한 보호</span><span class="sxs-lookup"><span data-stu-id="ecbb1-118">Safeguard against advanced threats, compromised identities, and malicious insiders using correlated Active Directory signals</span></span> |
| <span data-ttu-id="ecbb1-119">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="ecbb1-119">Microsoft Cloud App Security</span></span> | <span data-ttu-id="ecbb1-120">Microsoft 및 타사 클라우드 서비스에서 cyberthreats을 식별 하 고 combats를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ecbb1-120">Identifies and combats cyberthreats across your Microsoft and third-party cloud services</span></span> |

## <a name="deployed-services-and-functionality"></a><span data-ttu-id="ecbb1-121">배포 된 서비스 및 기능</span><span class="sxs-lookup"><span data-stu-id="ecbb1-121">Deployed services and functionality</span></span>
<span data-ttu-id="ecbb1-122">Microsoft 위협 보호를 통해 지원 되는 서비스를 배포 하는 것과 같은 향상 된 가시성, 상관 관계 및 수정이 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ecbb1-122">Microsoft Threat Protection provides better visibility, correlation, and remediation as you deploy more supported services.</span></span>

### <a name="benefits-of-full-deployment"></a><span data-ttu-id="ecbb1-123">전체 배포의 장점</span><span class="sxs-lookup"><span data-stu-id="ecbb1-123">Benefits of full deployment</span></span>
<span data-ttu-id="ecbb1-124">Microsoft Threat Protection의 전체 이점을 얻으려면 지원 되는 모든 서비스를 배포 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ecbb1-124">To get the complete benefits of Microsoft Threat Protection, we recommend deploying all supported services.</span></span> <span data-ttu-id="ecbb1-125">전체 배포의 주요 이점은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ecbb1-125">Here are some of the key benefits of full deployment:</span></span>
- <span data-ttu-id="ecbb1-126">사용 가능한 모든 센서 및 서비스 관련 분석 기능에서 발생 하는 경고 및 이벤트 신호의 기반 인시던트 식별 및 상관 관계</span><span class="sxs-lookup"><span data-stu-id="ecbb1-126">Incidents are identified and correlated based on alerts and event signals from all available sensors and service-specific analysis capabilities</span></span>
- <span data-ttu-id="ecbb1-127">장치, 사서함 및 사용자 계정을 비롯 한 다양 한 엔터티 유형에 서 자동 조사 및 재구성 (AIR) playbook가 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ecbb1-127">Automated investigation and remediation (AIR) playbooks apply across various entity types, including devices, mailboxes, and user accounts</span></span>
- <span data-ttu-id="ecbb1-128">장치, 사서함 및 기타 엔터티에서 이벤트 및 엔터티 데이터에 대 한 보다 포괄적인 고급 구하기 스키마를 쿼리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ecbb1-128">A more comprehensive advanced hunting schema can be queried for event and entity data from devices, mailboxes, and other entities</span></span>

### <a name="limited-deployment-scenarios"></a><span data-ttu-id="ecbb1-129">제한 된 배포 시나리오</span><span class="sxs-lookup"><span data-stu-id="ecbb1-129">Limited deployment scenarios</span></span>
<span data-ttu-id="ecbb1-130">배포 하는 지원 되는 각 서비스는 매우 다양 한 원시 신호의 집합 뿐 아니라 상호 연관 된 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ecbb1-130">Each supported service that you deploy provides an extremely rich set of raw signals as well as correlated information.</span></span> <span data-ttu-id="ecbb1-131">제한 된 배포로 인해 Microsoft Threat Protection 기능을 사용 하지 않도록 설정 해도 끝점, 앱, 데이터 및 id에 대 한 포괄적인 가시성을 제공 하는 기능을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ecbb1-131">While limited deployment doesn’t cause Microsoft Threat Protection functionality to turn off, its ability to provide comprehensive visibility across your endpoints, apps, data, and identities is affected.</span></span> <span data-ttu-id="ecbb1-132">동시에 관리 기능은 배포한 서비스에서 관리할 수 있는 엔터티에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ecbb1-132">At the same time, any remediation capabilities only apply to entities that can be managed by the services you’ve deployed.</span></span>

<span data-ttu-id="ecbb1-133">아래 표에는 지원 되는 각 서비스가 추가 데이터를 제공 하는 방법, 데이터를 연관 시켜 추가 정보를 얻을 수 있는 기회, 개선 및 대응 기능에 대 한 자세한 내용이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ecbb1-133">The table below lists how each supported service provides additional data, opportunities to obtain additional insight by correlating the data, and better remediation and response capabilities.</span></span>

| <span data-ttu-id="ecbb1-134">서비스</span><span class="sxs-lookup"><span data-stu-id="ecbb1-134">Service</span></span> | <span data-ttu-id="ecbb1-135">데이터 (상호 연관 & 정보)</span><span class="sxs-lookup"><span data-stu-id="ecbb1-135">Data (signals & correlated info)</span></span> | <span data-ttu-id="ecbb1-136">업데이트 관리 & 응답 범위</span><span class="sxs-lookup"><span data-stu-id="ecbb1-136">Remediation & response scope</span></span> |
| ------ | ------ | ------ |
| <span data-ttu-id="ecbb1-137">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="ecbb1-137">Microsoft Defender ATP</span></span> | <span data-ttu-id="ecbb1-138">-끝점 상태 및 원시 이벤트</span><span class="sxs-lookup"><span data-stu-id="ecbb1-138">- Endpoint states and raw events</span></span><br /><span data-ttu-id="ecbb1-139">-바이러스 백신, EDR, attack surface reduction를 포함 한 끝점 감지 및 경고</span><span class="sxs-lookup"><span data-stu-id="ecbb1-139">- Endpoint detections and alerts, including antivirus, EDR, attack surface reduction</span></span><br /><span data-ttu-id="ecbb1-140">-끝점에서 관찰 된 파일 및 기타 엔터티에 대 한 정보</span><span class="sxs-lookup"><span data-stu-id="ecbb1-140">- Info on files and other entities observed on endpoints</span></span> | <span data-ttu-id="ecbb1-141">엔드포인트</span><span class="sxs-lookup"><span data-stu-id="ecbb1-141">Endpoints</span></span> |
| <span data-ttu-id="ecbb1-142">Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="ecbb1-142">Office 365 ATP</span></span> | <span data-ttu-id="ecbb1-143">-메일 및 사서함 상태 및 원시 이벤트</span><span class="sxs-lookup"><span data-stu-id="ecbb1-143">- Mail and mailbox states and raw events</span></span><br /><span data-ttu-id="ecbb1-144">-전자 메일, 첨부 파일 및 링크 감지</span><span class="sxs-lookup"><span data-stu-id="ecbb1-144">- Email, attachment, and link detections</span></span> | <span data-ttu-id="ecbb1-145">-사서함</span><span class="sxs-lookup"><span data-stu-id="ecbb1-145">- Mailboxes</span></span><br /><span data-ttu-id="ecbb1-146">-Office 365 계정</span><span class="sxs-lookup"><span data-stu-id="ecbb1-146">- Office 365 accounts</span></span> |
| <span data-ttu-id="ecbb1-147">Azure ATP</span><span class="sxs-lookup"><span data-stu-id="ecbb1-147">Azure ATP</span></span> | <span data-ttu-id="ecbb1-148">-Active Directory 신호 (인증 이벤트 포함)</span><span class="sxs-lookup"><span data-stu-id="ecbb1-148">- Active Directory signals, including authentication events</span></span><br /><span data-ttu-id="ecbb1-149">-Id 관련 동작 감지</span><span class="sxs-lookup"><span data-stu-id="ecbb1-149">- Identity-related behavioral detections</span></span> | <span data-ttu-id="ecbb1-150">ID</span><span class="sxs-lookup"><span data-stu-id="ecbb1-150">Identities</span></span> |
| <span data-ttu-id="ecbb1-151">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="ecbb1-151">Microsoft Cloud App Security</span></span> | <span data-ttu-id="ecbb1-152">-Unsanctioned 클라우드 앱 & 서비스 검색 (섀도 IT)</span><span class="sxs-lookup"><span data-stu-id="ecbb1-152">- Detection of unsanctioned cloud apps & services (shadow IT)</span></span><br /><span data-ttu-id="ecbb1-153">-클라우드 앱에 대 한 데이터 노출</span><span class="sxs-lookup"><span data-stu-id="ecbb1-153">- Exposure of data to cloud apps</span></span><br /><span data-ttu-id="ecbb1-154">-위협 활동 연결 된 클라우드 앱</span><span class="sxs-lookup"><span data-stu-id="ecbb1-154">- Threat activity associated cloud apps</span></span> | <span data-ttu-id="ecbb1-155">클라우드 앱</span><span class="sxs-lookup"><span data-stu-id="ecbb1-155">Cloud apps</span></span> |

## <a name="deploy-the-services"></a><span data-ttu-id="ecbb1-156">서비스 배포</span><span class="sxs-lookup"><span data-stu-id="ecbb1-156">Deploy the services</span></span>
<span data-ttu-id="ecbb1-157">각 서비스를 배포 하려면 일반적으로 테 넌 트 및 몇 가지 초기 구성에 프로 비전을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ecbb1-157">Deploying each service typically requires provisioning to your tenant and some initial configuration.</span></span> <span data-ttu-id="ecbb1-158">이러한 각 서비스가 배포 되는 방식을 이해 하려면 다음 표를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="ecbb1-158">See the following table to understand how each of these services are deployed.</span></span>

| <span data-ttu-id="ecbb1-159">서비스</span><span class="sxs-lookup"><span data-stu-id="ecbb1-159">Service</span></span> | <span data-ttu-id="ecbb1-160">프로 비전 지침</span><span class="sxs-lookup"><span data-stu-id="ecbb1-160">Provisioning instructions</span></span> | <span data-ttu-id="ecbb1-161">초기 구성</span><span class="sxs-lookup"><span data-stu-id="ecbb1-161">Initial configuration</span></span> |
| ------ | ------ | ------ |
| <span data-ttu-id="ecbb1-162">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="ecbb1-162">Microsoft Defender ATP</span></span> | [<span data-ttu-id="ecbb1-163">Microsoft Defender ATP에 대 한 라이선스 프로비저닝 및 전체 설정 확인</span><span class="sxs-lookup"><span data-stu-id="ecbb1-163">Validate licensing provisioning and complete set up for Microsoft Defender ATP</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/licensing) | <span data-ttu-id="ecbb1-164">*프로비저닝 지침 참조*</span><span class="sxs-lookup"><span data-stu-id="ecbb1-164">*See provisioning instructions*</span></span> |
| <span data-ttu-id="ecbb1-165">Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="ecbb1-165">Office 365 ATP</span></span> | <span data-ttu-id="ecbb1-166">*없음, Office 365와 함께 구축 됨*</span><span class="sxs-lookup"><span data-stu-id="ecbb1-166">*None, provisioned with Office 365*</span></span> | [<span data-ttu-id="ecbb1-167">ATP 정책 구성</span><span class="sxs-lookup"><span data-stu-id="ecbb1-167">Configure ATP policies</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#configure-atp-policies) |
| <span data-ttu-id="ecbb1-168">Azure ATP</span><span class="sxs-lookup"><span data-stu-id="ecbb1-168">Azure ATP</span></span> | [<span data-ttu-id="ecbb1-169">빠른 시작: Azure ATP 인스턴스 만들기</span><span class="sxs-lookup"><span data-stu-id="ecbb1-169">Quickstart: Create your Azure ATP instance</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/install-atp-step1) | <span data-ttu-id="ecbb1-170">*프로비저닝 지침 참조*</span><span class="sxs-lookup"><span data-stu-id="ecbb1-170">*See provisioning instructions*</span></span> |
| <span data-ttu-id="ecbb1-171">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="ecbb1-171">Microsoft Cloud App Security</span></span> | <span data-ttu-id="ecbb1-172">*없음*</span><span class="sxs-lookup"><span data-stu-id="ecbb1-172">*None*</span></span> | [<span data-ttu-id="ecbb1-173">퀵 스타트: Microsoft Cloud App Security 시작</span><span class="sxs-lookup"><span data-stu-id="ecbb1-173">Quickstart: Get started with Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/getting-started-with-cloud-app-security) |

<span data-ttu-id="ecbb1-174">지원 되는 서비스를 배포한 후에는 [Microsoft Threat Protection을 켜십시오](mtp-enable.md).</span><span class="sxs-lookup"><span data-stu-id="ecbb1-174">Once you’ve deployed the supported services, [turn on Microsoft Threat Protection](mtp-enable.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="ecbb1-175">관련 항목</span><span class="sxs-lookup"><span data-stu-id="ecbb1-175">Related topics</span></span>

- [<span data-ttu-id="ecbb1-176">Microsoft 위협 방지 개요</span><span class="sxs-lookup"><span data-stu-id="ecbb1-176">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="ecbb1-177">Microsoft 위협 방지 설정</span><span class="sxs-lookup"><span data-stu-id="ecbb1-177">Turn on Microsoft Threat Protection</span></span>](mtp-enable.md)
- [<span data-ttu-id="ecbb1-178">Microsoft Defender ATP 개요</span><span class="sxs-lookup"><span data-stu-id="ecbb1-178">Microsoft Defender ATP overview</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [<span data-ttu-id="ecbb1-179">Office 365 ATP 개요</span><span class="sxs-lookup"><span data-stu-id="ecbb1-179">Office 365 ATP overview</span></span>](../office-365-security/office-365-atp.md)
- [<span data-ttu-id="ecbb1-180">Microsoft Cloud App Security 개요</span><span class="sxs-lookup"><span data-stu-id="ecbb1-180">Microsoft Cloud App Security overview</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [<span data-ttu-id="ecbb1-181">Azure ATP 개요</span><span class="sxs-lookup"><span data-stu-id="ecbb1-181">Azure ATP overview</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
