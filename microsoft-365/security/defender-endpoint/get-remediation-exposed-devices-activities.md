---
title: 한 번의 수정 작업이 있는 노출된 장치 목록
description: 지정된 수정 작업에 대해 노출된 장치에 대한 정보를 반환합니다.
keywords: api, 수정, 수정 api, get, 수정 작업, 노출된 장치 수정
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 9b10659f76e5b05bea11f5c6c55ca7c2a34a2db5
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772164"
---
# <a name="list-exposed-devices-of-one-remediation-activity"></a><span data-ttu-id="2fbc3-104">한 번의 수정 작업이 있는 노출된 장치 목록</span><span class="sxs-lookup"><span data-stu-id="2fbc3-104">List exposed devices of one remediation activity</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2fbc3-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="2fbc3-105">**Applies to:**</span></span>

- [<span data-ttu-id="2fbc3-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="2fbc3-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="2fbc3-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2fbc3-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="2fbc3-108">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="2fbc3-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="2fbc3-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="2fbc3-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="2fbc3-110">API 설명</span><span class="sxs-lookup"><span data-stu-id="2fbc3-110">API Description</span></span>

<span data-ttu-id="2fbc3-111">지정된 수정 작업에 대해 노출된 장치에 대한 정보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="2fbc3-111">Returns information about exposed devices for the specified remediation task.</span></span>

<span data-ttu-id="2fbc3-112">[재구성 활동에 대해 자세히 알아보시다.](tvm-remediation.md)</span><span class="sxs-lookup"><span data-stu-id="2fbc3-112">[Learn more about remediation activities](tvm-remediation.md).</span></span>

## <a name="list-exposed-devices-associated-with-a-remediation-task-id"></a><span data-ttu-id="2fbc3-113">재구성 작업과 연결된 노출된 장치 나열(ID)</span><span class="sxs-lookup"><span data-stu-id="2fbc3-113">List exposed devices associated with a remediation task (id)</span></span>

<span data-ttu-id="2fbc3-114">**URL:** GET: /api/remediationTasks/ \{ id \} /machineReferences</span><span class="sxs-lookup"><span data-stu-id="2fbc3-114">**URL:** GET: /api/remediationTasks/\{id\}/machineReferences</span></span>

## <a name="permissions"></a><span data-ttu-id="2fbc3-115">사용 권한</span><span class="sxs-lookup"><span data-stu-id="2fbc3-115">Permissions</span></span>

<span data-ttu-id="2fbc3-116">이 API를 호출하려면 다음 권한 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="2fbc3-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="2fbc3-117">사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [Use Microsoft Defender for Endpoint API for details을 참조합니다.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="2fbc3-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="2fbc3-118">사용 권한 유형</span><span class="sxs-lookup"><span data-stu-id="2fbc3-118">Permission type</span></span> | <span data-ttu-id="2fbc3-119">사용 권한</span><span class="sxs-lookup"><span data-stu-id="2fbc3-119">Permission</span></span> | <span data-ttu-id="2fbc3-120">사용 권한 표시 이름</span><span class="sxs-lookup"><span data-stu-id="2fbc3-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="2fbc3-121">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="2fbc3-121">Application</span></span> | <span data-ttu-id="2fbc3-122">RemediationTask.Read.All</span><span class="sxs-lookup"><span data-stu-id="2fbc3-122">RemediationTask.Read.All</span></span> | <span data-ttu-id="2fbc3-123">\'위협 및 취약성 관리 취약성 정보 읽기\'</span><span class="sxs-lookup"><span data-stu-id="2fbc3-123">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="2fbc3-124">위임(직장 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="2fbc3-124">Delegated (work or school account)</span></span> | <span data-ttu-id="2fbc3-125">RemediationTask.Read.Read</span><span class="sxs-lookup"><span data-stu-id="2fbc3-125">RemediationTask.Read.Read</span></span> | <span data-ttu-id="2fbc3-126">\'위협 및 취약성 관리 취약성 정보 읽기\'</span><span class="sxs-lookup"><span data-stu-id="2fbc3-126">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

## <a name="properties-details"></a><span data-ttu-id="2fbc3-127">속성 세부 정보</span><span class="sxs-lookup"><span data-stu-id="2fbc3-127">Properties details</span></span>

<span data-ttu-id="2fbc3-128">속성(id)</span><span class="sxs-lookup"><span data-stu-id="2fbc3-128">Property (id)</span></span> | <span data-ttu-id="2fbc3-129">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="2fbc3-129">Data type</span></span> | <span data-ttu-id="2fbc3-130">설명</span><span class="sxs-lookup"><span data-stu-id="2fbc3-130">Description</span></span> | <span data-ttu-id="2fbc3-131">예제</span><span class="sxs-lookup"><span data-stu-id="2fbc3-131">Example</span></span>
:---|:---|:---|:---
<span data-ttu-id="2fbc3-132">id</span><span class="sxs-lookup"><span data-stu-id="2fbc3-132">id</span></span> | <span data-ttu-id="2fbc3-133">String</span><span class="sxs-lookup"><span data-stu-id="2fbc3-133">String</span></span> | <span data-ttu-id="2fbc3-134">장치 ID</span><span class="sxs-lookup"><span data-stu-id="2fbc3-134">Device ID</span></span> | <span data-ttu-id="2fbc3-135">w2957837fwda8w9ae7f023dba081059dw8d94503</span><span class="sxs-lookup"><span data-stu-id="2fbc3-135">w2957837fwda8w9ae7f023dba081059dw8d94503</span></span>
<span data-ttu-id="2fbc3-136">computerDnsName</span><span class="sxs-lookup"><span data-stu-id="2fbc3-136">computerDnsName</span></span> | <span data-ttu-id="2fbc3-137">String</span><span class="sxs-lookup"><span data-stu-id="2fbc3-137">String</span></span> | <span data-ttu-id="2fbc3-138">장치 이름</span><span class="sxs-lookup"><span data-stu-id="2fbc3-138">Device name</span></span> | <span data-ttu-id="2fbc3-139">PC-SRV2012R2Foo.UserNameVldNet.local</span><span class="sxs-lookup"><span data-stu-id="2fbc3-139">PC-SRV2012R2Foo.UserNameVldNet.local</span></span>
<span data-ttu-id="2fbc3-140">osPlatform</span><span class="sxs-lookup"><span data-stu-id="2fbc3-140">osPlatform</span></span> | <span data-ttu-id="2fbc3-141">String</span><span class="sxs-lookup"><span data-stu-id="2fbc3-141">String</span></span> | <span data-ttu-id="2fbc3-142">장치 운영 체제</span><span class="sxs-lookup"><span data-stu-id="2fbc3-142">Device operating system</span></span> | <span data-ttu-id="2fbc3-143">WindowsServer2012R2</span><span class="sxs-lookup"><span data-stu-id="2fbc3-143">WindowsServer2012R2</span></span>
<span data-ttu-id="2fbc3-144">rbacGroupName</span><span class="sxs-lookup"><span data-stu-id="2fbc3-144">rbacGroupName</span></span> | <span data-ttu-id="2fbc3-145">String</span><span class="sxs-lookup"><span data-stu-id="2fbc3-145">String</span></span> | <span data-ttu-id="2fbc3-146">이 장치가 연결된 장치 그룹의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="2fbc3-146">Name of the device group this device is associated with</span></span> | <span data-ttu-id="2fbc3-147">서버</span><span class="sxs-lookup"><span data-stu-id="2fbc3-147">Servers</span></span>

## <a name="example"></a><span data-ttu-id="2fbc3-148">예시</span><span class="sxs-lookup"><span data-stu-id="2fbc3-148">Example</span></span>

### <a name="request-example"></a><span data-ttu-id="2fbc3-149">요청 예제</span><span class="sxs-lookup"><span data-stu-id="2fbc3-149">Request example</span></span>

```http
GET https://api-luna.securitycenter.windows.com/api/remediationtasks/03942ef5-aecb-4c6e-b555-d6a97013844c/machinereferences
```

### <a name="response-example"></a><span data-ttu-id="2fbc3-150">응답 예제</span><span class="sxs-lookup"><span data-stu-id="2fbc3-150">Response example</span></span>

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

## <a name="see-also"></a><span data-ttu-id="2fbc3-151">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2fbc3-151">See also</span></span>

- [<span data-ttu-id="2fbc3-152">수정 방법 및 속성</span><span class="sxs-lookup"><span data-stu-id="2fbc3-152">Remediation methods and properties</span></span>](get-remediation-methods-properties.md)

- [<span data-ttu-id="2fbc3-153">ID로 수정 작업 1개 가져오기</span><span class="sxs-lookup"><span data-stu-id="2fbc3-153">Get one remediation activity by Id</span></span>](get-remediation-one-activity.md)

- [<span data-ttu-id="2fbc3-154">모든 수정 작업 나열s</span><span class="sxs-lookup"><span data-stu-id="2fbc3-154">List all remediation activities</span></span>](get-remediation-all-activities.md)

- [<span data-ttu-id="2fbc3-155">위험 기반 위협 & 취약성 관리</span><span class="sxs-lookup"><span data-stu-id="2fbc3-155">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="2fbc3-156">조직의 취약성</span><span class="sxs-lookup"><span data-stu-id="2fbc3-156">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
