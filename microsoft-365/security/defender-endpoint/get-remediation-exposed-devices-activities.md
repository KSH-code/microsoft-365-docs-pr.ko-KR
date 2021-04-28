---
title: 한 가지 수정 활동의 노출된 장치 나열
description: 지정된 수정 작업에 대해 노출된 장치에 대한 정보를 반환합니다.
keywords: api, 수정, 수정 api, get, 수정 작업,
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-jweston
author: jweston-1
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 097d8d784ca7c02fce1fc0e9fc51bdc272951f4a
ms.sourcegitcommit: e5b1a900043e2e41650ea1cbf4227043729c6053
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2021
ms.locfileid: "52061197"
---
# <a name="list-exposed-devices-of-one-remediation-activity"></a><span data-ttu-id="6cad7-104">한 가지 수정 활동의 노출된 장치 나열</span><span class="sxs-lookup"><span data-stu-id="6cad7-104">List exposed devices of one remediation activity</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="6cad7-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="6cad7-105">**Applies to:**</span></span>

- [<span data-ttu-id="6cad7-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="6cad7-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="6cad7-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6cad7-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="6cad7-108">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="6cad7-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="6cad7-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="6cad7-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="6cad7-110">API 설명</span><span class="sxs-lookup"><span data-stu-id="6cad7-110">API Description</span></span>

<span data-ttu-id="6cad7-111">지정된 수정 작업에 대해 노출된 장치에 대한 정보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6cad7-111">Returns information about exposed devices for the specified remediation task.</span></span>

<span data-ttu-id="6cad7-112">[재구성 활동에 대해 자세히 알아보시다.](tvm-remediation.md)</span><span class="sxs-lookup"><span data-stu-id="6cad7-112">[Learn more about remediation activities](tvm-remediation.md).</span></span>

## <a name="list-exposed-devices-associated-with-a-remediation-task-id"></a><span data-ttu-id="6cad7-113">재구성 작업과 연결된 노출된 장치 나열(ID)</span><span class="sxs-lookup"><span data-stu-id="6cad7-113">List exposed devices associated with a remediation task (id)</span></span>

<span data-ttu-id="6cad7-114">**URL:** GET: /api/remediationTasks/ \{ id \} /machineReferences</span><span class="sxs-lookup"><span data-stu-id="6cad7-114">**URL:** GET: /api/remediationTasks/\{id\}/machineReferences</span></span>

<span data-ttu-id="6cad7-115">**속성** 세부 정보</span><span class="sxs-lookup"><span data-stu-id="6cad7-115">**Properties** details</span></span>

<span data-ttu-id="6cad7-116">속성(id)</span><span class="sxs-lookup"><span data-stu-id="6cad7-116">Property (id)</span></span> | <span data-ttu-id="6cad7-117">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="6cad7-117">Data type</span></span> | <span data-ttu-id="6cad7-118">설명</span><span class="sxs-lookup"><span data-stu-id="6cad7-118">Description</span></span> | <span data-ttu-id="6cad7-119">예제</span><span class="sxs-lookup"><span data-stu-id="6cad7-119">Example</span></span>
:---|:---|:---|:---
<span data-ttu-id="6cad7-120">id</span><span class="sxs-lookup"><span data-stu-id="6cad7-120">id</span></span> | <span data-ttu-id="6cad7-121">문자열</span><span class="sxs-lookup"><span data-stu-id="6cad7-121">String</span></span> | <span data-ttu-id="6cad7-122">장치 ID</span><span class="sxs-lookup"><span data-stu-id="6cad7-122">Device ID</span></span> | <span data-ttu-id="6cad7-123">w2957837fwda8w9ae7f023dba081059dw8d94503</span><span class="sxs-lookup"><span data-stu-id="6cad7-123">w2957837fwda8w9ae7f023dba081059dw8d94503</span></span>
<span data-ttu-id="6cad7-124">computerDnsName</span><span class="sxs-lookup"><span data-stu-id="6cad7-124">computerDnsName</span></span> | <span data-ttu-id="6cad7-125">문자열</span><span class="sxs-lookup"><span data-stu-id="6cad7-125">String</span></span> | <span data-ttu-id="6cad7-126">장치 이름</span><span class="sxs-lookup"><span data-stu-id="6cad7-126">Device name</span></span> | <span data-ttu-id="6cad7-127">PC-SRV2012R2Foo.UserNameVldNet.local</span><span class="sxs-lookup"><span data-stu-id="6cad7-127">PC-SRV2012R2Foo.UserNameVldNet.local</span></span>
<span data-ttu-id="6cad7-128">osPlatform</span><span class="sxs-lookup"><span data-stu-id="6cad7-128">osPlatform</span></span> | <span data-ttu-id="6cad7-129">문자열</span><span class="sxs-lookup"><span data-stu-id="6cad7-129">String</span></span> | <span data-ttu-id="6cad7-130">장치 운영 체제</span><span class="sxs-lookup"><span data-stu-id="6cad7-130">Device operating system</span></span> | <span data-ttu-id="6cad7-131">WindowsServer2012R2</span><span class="sxs-lookup"><span data-stu-id="6cad7-131">WindowsServer2012R2</span></span>
<span data-ttu-id="6cad7-132">rbacGroupName</span><span class="sxs-lookup"><span data-stu-id="6cad7-132">rbacGroupName</span></span> | <span data-ttu-id="6cad7-133">문자열</span><span class="sxs-lookup"><span data-stu-id="6cad7-133">String</span></span> | <span data-ttu-id="6cad7-134">이 장치가 연결된 장치 그룹의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="6cad7-134">Name of the device group this device is associated with</span></span> | <span data-ttu-id="6cad7-135">서버</span><span class="sxs-lookup"><span data-stu-id="6cad7-135">Servers</span></span>

## <a name="example"></a><span data-ttu-id="6cad7-136">예시</span><span class="sxs-lookup"><span data-stu-id="6cad7-136">Example</span></span>

<span data-ttu-id="6cad7-137">**요청** 예제</span><span class="sxs-lookup"><span data-stu-id="6cad7-137">**Request** example</span></span>

```http
GET https://api-luna.securitycenter.windows.com/api/remediationtasks/03942ef5-aecb-4c6e-b555-d6a97013844c/machinereferences
```

<span data-ttu-id="6cad7-138">**응답** 예제</span><span class="sxs-lookup"><span data-stu-id="6cad7-138">**Response** example</span></span>

```json
{
    "@odata.context": "https://wpatdadi-luna-stg.cloudapp.net/api/$metadata#MachineReferences",
    "value": [
        {
            "id": "3cb5df6bb3640a2d37ad09fcd357b182d684fafc",
            "computerDnsName": "ComputerPII_2ea21b2d97c9df23c143ad9e3e454cb674232529.DomainPII_21eed80b086e79bdfa178eabfa25e8be9acfa346.corp.contoso.com",
            "osPlatform": "WindowsServer2016",
            "rbacGroupName": "UnassignedGroup",
            
        },
        {
            "id": "3d9b1ca53e8f077199c7dcbfc9dbfa78f9bf1918",
            "computerDnsName": "ComputerPII_001d606fc149567c192747f48fae304b43c0ddba.DomainxPII_21eed80b086e79bdfa178eabfa25e8be9acfa346.corp.contoso.com",
            "osPlatform": "WindowsServer2012R2",
            "rbacGroupName": "UnassignedGroup",
            
        },
        {
            "id": "3db8b27e6172951d7ea2e2d75945abec56feaf82",
            "computerDnsName": "ComputerPII_ce60cfbjj4b82a091deb5eae560332bba99a9bd7.DomainPII_0bc1aee0fa396d175e514bd61a9e7a5b2b07ee8e.corp.contoso.com",
            "osPlatform": "WindowsServer2016",
            "rbacGroupName": "UnassignedGroup",
            
        },
        {
            "id": "3bad326dcda5b53fab47408cd4a7080f3f3cc8ab",
            "computerDnsName": "ComputerPII_b6b35960dd6539d1d1cef5ada02e235e7b357408.DomainPII_21eed80b089e76bdfa178eadfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "WindowsServer2012R2",
            "rbacGroupName": "UnassignedGroup",
            
        }
]
}
```

## <a name="see-also"></a><span data-ttu-id="6cad7-139">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6cad7-139">See also</span></span>

- [<span data-ttu-id="6cad7-140">수정 방법 및 속성</span><span class="sxs-lookup"><span data-stu-id="6cad7-140">Remediation methods and properties</span></span>](get-remediation-methods-properties.md)

- [<span data-ttu-id="6cad7-141">ID로 하나의 재구성 활동 얻기</span><span class="sxs-lookup"><span data-stu-id="6cad7-141">Get one remediation activity by Id</span></span>](get-remediation-one-activity.md)

- [<span data-ttu-id="6cad7-142">모든 재구성 활동 나열</span><span class="sxs-lookup"><span data-stu-id="6cad7-142">List all remediation activities</span></span>](get-remediation-all-activities.md)

- [<span data-ttu-id="6cad7-143">위험 기반 위협 & 관리</span><span class="sxs-lookup"><span data-stu-id="6cad7-143">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="6cad7-144">조직의 취약성</span><span class="sxs-lookup"><span data-stu-id="6cad7-144">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
