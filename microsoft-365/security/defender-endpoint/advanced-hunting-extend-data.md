---
title: 올바른 설정을 사용하여 고급 헌팅 범위 확장
description: Windows 장치 및 기타 설정의 감사 설정을 확인하여 고급 헌팅에서 가장 포괄적인 데이터를 얻을 수 있도록 합니다.
keywords: 고급 헌팅, 인시던트, 피벗, 엔터티, 감사 설정, 사용자 계정 관리, 보안 그룹 관리, 위협 헌팅, 사이버 위협 헌팅, 검색, 쿼리, 원격 분석, mdatp, Microsoft Defender ATP, 끝점용 Microsoft Defender, Windows Defender, Windows Defender ATP, Windows Defender Advanced Threat Protection
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 10/10/2020
ms.technology: mde
ms.openlocfilehash: ea2524cb214d3cf7c784162a472722727cf0d57c
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500612"
---
# <a name="extend-advanced-hunting-coverage-with-the-right-settings"></a><span data-ttu-id="f5d87-104">올바른 설정을 사용하여 고급 헌팅 범위 확장</span><span class="sxs-lookup"><span data-stu-id="f5d87-104">Extend advanced hunting coverage with the right settings</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f5d87-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="f5d87-105">**Applies to:**</span></span>
- [<span data-ttu-id="f5d87-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="f5d87-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

<span data-ttu-id="f5d87-107">[고급 헌팅은](advanced-hunting-overview.md) 조직 전체에서 데이터를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f5d87-107">[Advanced hunting](advanced-hunting-overview.md) relies on data coming from across your organization.</span></span> <span data-ttu-id="f5d87-108">가능한 가장 포괄적인 데이터를 얻습니다. 해당 데이터 원본에 올바른 설정이 적용되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="f5d87-108">To get the most comprehensive data possible, ensure that you have the correct settings in the corresponding data sources.</span></span>

## <a name="advanced-security-auditing-on-windows-devices"></a><span data-ttu-id="f5d87-109">Windows 장치의 고급 보안 감사</span><span class="sxs-lookup"><span data-stu-id="f5d87-109">Advanced security auditing on Windows devices</span></span>

<span data-ttu-id="f5d87-110">이러한 고급 감사 설정을 켜서 로컬 계정 관리, 로컬 보안 그룹 관리 및 서비스 만들기를 비롯한 장치의 활동에 대한 데이터를 얻을 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="f5d87-110">Turn on these advanced auditing settings to ensure you get data about activities on your devices, including local account management, local security group management, and service creation.</span></span>

<span data-ttu-id="f5d87-111">데이터</span><span class="sxs-lookup"><span data-stu-id="f5d87-111">Data</span></span> | <span data-ttu-id="f5d87-112">설명</span><span class="sxs-lookup"><span data-stu-id="f5d87-112">Description</span></span> | <span data-ttu-id="f5d87-113">Schema 테이블</span><span class="sxs-lookup"><span data-stu-id="f5d87-113">Schema table</span></span> | <span data-ttu-id="f5d87-114">구성 방법</span><span class="sxs-lookup"><span data-stu-id="f5d87-114">How to configure</span></span>
-|-|-|-
<span data-ttu-id="f5d87-115">계정 관리</span><span class="sxs-lookup"><span data-stu-id="f5d87-115">Account management</span></span> | <span data-ttu-id="f5d87-116">로컬 계정 생성, 삭제 및 기타 계정 관련 활동을 나타내는 다양한 값으로 `ActionType` 캡처된 이벤트</span><span class="sxs-lookup"><span data-stu-id="f5d87-116">Events captured as various `ActionType` values indicating local account creation, deletion, and other account-related activities</span></span> | [<span data-ttu-id="f5d87-117">DeviceEvents</span><span class="sxs-lookup"><span data-stu-id="f5d87-117">DeviceEvents</span></span>](advanced-hunting-deviceevents-table.md) | <span data-ttu-id="f5d87-118">- 고급 보안 감사 정책 배포: [사용자 계정 관리 감사](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-user-account-management)</span><span class="sxs-lookup"><span data-stu-id="f5d87-118">- Deploy an advanced security audit policy: [Audit User Account Management](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-user-account-management)</span></span><br> <span data-ttu-id="f5d87-119">- [고급 보안 감사 정책에 대한 자세한 정보](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing)</span><span class="sxs-lookup"><span data-stu-id="f5d87-119">- [Learn about advanced security audit policies](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing)</span></span>
<span data-ttu-id="f5d87-120">보안 그룹 관리</span><span class="sxs-lookup"><span data-stu-id="f5d87-120">Security group management</span></span> | <span data-ttu-id="f5d87-121">로컬 보안 그룹 만들기 및 기타 로컬 그룹 관리 활동을 나타내는 다양한 `ActionType` 값으로 캡처된 이벤트</span><span class="sxs-lookup"><span data-stu-id="f5d87-121">Events captured as various `ActionType` values indicating local security group creation and other local group management activities</span></span> | [<span data-ttu-id="f5d87-122">DeviceEvents</span><span class="sxs-lookup"><span data-stu-id="f5d87-122">DeviceEvents</span></span>](advanced-hunting-deviceevents-table.md) | <span data-ttu-id="f5d87-123">- 고급 보안 감사 정책 배포: [보안 그룹 관리 감사](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-group-management)</span><span class="sxs-lookup"><span data-stu-id="f5d87-123">- Deploy an advanced security audit policy: [Audit Security Group Management](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-group-management)</span></span><br> <span data-ttu-id="f5d87-124">- [고급 보안 감사 정책에 대한 자세한 정보](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing)</span><span class="sxs-lookup"><span data-stu-id="f5d87-124">- [Learn about advanced security audit policies](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing)</span></span>
<span data-ttu-id="f5d87-125">서비스 설치</span><span class="sxs-lookup"><span data-stu-id="f5d87-125">Service installation</span></span> | <span data-ttu-id="f5d87-126">값이 으로 `ActionType` 캡처된 이벤트는 서비스가 `ServiceInstalled` 생성되었음을 나타내는 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="f5d87-126">Events captured with the `ActionType` value `ServiceInstalled`, indicating that a service has been created</span></span> | [<span data-ttu-id="f5d87-127">DeviceEvents</span><span class="sxs-lookup"><span data-stu-id="f5d87-127">DeviceEvents</span></span>](advanced-hunting-deviceevents-table.md) | <span data-ttu-id="f5d87-128">- 고급 보안 감사 정책 배포: [보안 시스템 확장 감사](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-system-extension)</span><span class="sxs-lookup"><span data-stu-id="f5d87-128">- Deploy an advanced security audit policy: [Audit Security System Extension](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-system-extension)</span></span><br> <span data-ttu-id="f5d87-129">- [고급 보안 감사 정책에 대한 자세한 정보](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing)</span><span class="sxs-lookup"><span data-stu-id="f5d87-129">- [Learn about advanced security audit policies](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing)</span></span>

## <a name="related-topics"></a><span data-ttu-id="f5d87-130">관련 항목</span><span class="sxs-lookup"><span data-stu-id="f5d87-130">Related topics</span></span>

- [<span data-ttu-id="f5d87-131">지능형 헌팅 개요</span><span class="sxs-lookup"><span data-stu-id="f5d87-131">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="f5d87-132">쿼리 언어 배우기</span><span class="sxs-lookup"><span data-stu-id="f5d87-132">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="f5d87-133">스키마에 대한 이해</span><span class="sxs-lookup"><span data-stu-id="f5d87-133">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="f5d87-134">쿼리 결과로 작업</span><span class="sxs-lookup"><span data-stu-id="f5d87-134">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="f5d87-135">쿼리 모범 사례 적용</span><span class="sxs-lookup"><span data-stu-id="f5d87-135">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="f5d87-136">사용자 지정 검색 개요</span><span class="sxs-lookup"><span data-stu-id="f5d87-136">Custom detections overview</span></span>](overview-custom-detections.md)
