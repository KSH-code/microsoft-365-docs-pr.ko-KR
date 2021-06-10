---
title: 끝점 응답 API에 대해 지원되는 Microsoft Defender
description: 특정 응답 관련 Microsoft Defender for Endpoint API 호출에 대해 자세히 알아보습니다.
keywords: 응답 api, 그래프 api, 지원되는 api, 배우, 알림, 장치, 사용자, 도메인, ip, 파일
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.openlocfilehash: 36ed1f624fda7ae413ffbbf807925cf00e0a23ca
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933772"
---
# <a name="supported-microsoft-defender-for-endpoint-query-apis"></a><span data-ttu-id="05d1a-104">끝점 쿼리 API에 대해 지원되는 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="05d1a-104">Supported Microsoft Defender for Endpoint query APIs</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="05d1a-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="05d1a-105">**Applies to:**</span></span>
- [<span data-ttu-id="05d1a-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="05d1a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> [!TIP]
> <span data-ttu-id="05d1a-107">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="05d1a-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="05d1a-108">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="05d1a-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-supported-response-apis-abovefoldlink) 

<span data-ttu-id="05d1a-109">실행할 수 있는 지원되는 응답 관련 API 호출과 필요한 요청 헤더, 호출의 예상 응답 등의 세부 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="05d1a-109">Learn about the supported response-related API calls you can run and details such as the required request headers, and expected response from the calls.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="05d1a-110">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="05d1a-110">In this section</span></span>
<span data-ttu-id="05d1a-111">항목</span><span class="sxs-lookup"><span data-stu-id="05d1a-111">Topic</span></span> | <span data-ttu-id="05d1a-112">설명</span><span class="sxs-lookup"><span data-stu-id="05d1a-112">Description</span></span>
:---|:---
<span data-ttu-id="05d1a-113">조사 패키지 수집</span><span class="sxs-lookup"><span data-stu-id="05d1a-113">Collect investigation package</span></span> | <span data-ttu-id="05d1a-114">이 API를 실행하여 장치에서 조사 패키지를 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="05d1a-114">Run this API to collect an investigation package from a device.</span></span>
<span data-ttu-id="05d1a-115">장치 격리</span><span class="sxs-lookup"><span data-stu-id="05d1a-115">Isolate device</span></span> | <span data-ttu-id="05d1a-116">이 API를 실행하여 네트워크에서 장치를 격리합니다.</span><span class="sxs-lookup"><span data-stu-id="05d1a-116">Run this API to isolate a device from the network.</span></span>
<span data-ttu-id="05d1a-117">장치 고지 안</span><span class="sxs-lookup"><span data-stu-id="05d1a-117">Unisolate device</span></span> | <span data-ttu-id="05d1a-118">장치를 분리에서 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="05d1a-118">Remove a device from isolation.</span></span> 
<span data-ttu-id="05d1a-119">코드 실행 제한</span><span class="sxs-lookup"><span data-stu-id="05d1a-119">Restrict code execution</span></span> | <span data-ttu-id="05d1a-120">악성 프로세스를 중지하여 공격을 포함하기 위해 이 API를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="05d1a-120">Run this API to contain an attack by stopping malicious processes.</span></span> <span data-ttu-id="05d1a-121">또한 장치를 잠그고 잠재적인 악성 프로그램이 실행되지 않도록 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05d1a-121">You can also lock down a device and prevent subsequent attempts of potentially malicious programs from running.</span></span>
<span data-ttu-id="05d1a-122">코드 실행 제한 안</span><span class="sxs-lookup"><span data-stu-id="05d1a-122">Unrestrict code execution</span></span> | <span data-ttu-id="05d1a-123">손상된 장치가 수정된 것이 확인된 후 응용 프로그램 제한 정책을 되돌리기 위해 이 정책을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="05d1a-123">Run this to reverse the restriction of applications policy after you have verified that the compromised device has been remediated.</span></span>
<span data-ttu-id="05d1a-124">바이러스 백신 검사 실행</span><span class="sxs-lookup"><span data-stu-id="05d1a-124">Run antivirus scan</span></span> | <span data-ttu-id="05d1a-125">바이러스 백신 검색을 원격으로 시작하여 손상된 장치에 있을 수 있는 맬웨어를 식별하고 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="05d1a-125">Remotely initiate an antivirus scan to help identify and remediate malware that might be present on a compromised device.</span></span>
<span data-ttu-id="05d1a-126">파일을 중지하고 격리</span><span class="sxs-lookup"><span data-stu-id="05d1a-126">Stop and quarantine file</span></span> |  <span data-ttu-id="05d1a-127">이 호출을 실행하여 실행 중인 프로세스를 중지하고, 파일을 검지하고, 레지스트리 키와 같은 지속성도 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="05d1a-127">Run this call to stop running processes, quarantine  files, and delete persistency such as registry keys.</span></span>
<span data-ttu-id="05d1a-128">요청 샘플</span><span class="sxs-lookup"><span data-stu-id="05d1a-128">Request sample</span></span> | <span data-ttu-id="05d1a-129">특정 장치에서 파일의 샘플을 요청하려면 이 호출을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="05d1a-129">Run this call to request a sample of a file from a specific device.</span></span> <span data-ttu-id="05d1a-130">파일은 장치에서 수집되고 보안 저장소에 업로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="05d1a-130">The file will be collected from the device and uploaded to a secure storage.</span></span>
<span data-ttu-id="05d1a-131">파일 차단</span><span class="sxs-lookup"><span data-stu-id="05d1a-131">Block file</span></span> | <span data-ttu-id="05d1a-132">잠재적으로 악의적인 파일 또는 의심되는 맬웨어를 금지하여 조직에서 공격이 추가로 전파되지 않도록 방지하려면 이 API를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="05d1a-132">Run this API to prevent further propagation of an attack in your organization by banning potentially malicious files or suspected malware.</span></span> 
<span data-ttu-id="05d1a-133">파일 차단 해제</span><span class="sxs-lookup"><span data-stu-id="05d1a-133">Unblock file</span></span> | <span data-ttu-id="05d1a-134">조직에서 파일을 실행하도록 허용하는 Microsoft Defender 바이러스 백신.</span><span class="sxs-lookup"><span data-stu-id="05d1a-134">Allow a file run in the organization using Microsoft Defender Antivirus.</span></span>
<span data-ttu-id="05d1a-135">패키지 SAS URI를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="05d1a-135">Get package SAS URI</span></span> | <span data-ttu-id="05d1a-136">이 API를 실행하여 조사 패키지 다운로드를 허용하는 URI를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="05d1a-136">Run this API to get a URI that allows downloading an investigation package.</span></span>
<span data-ttu-id="05d1a-137">MachineAction 개체 Get</span><span class="sxs-lookup"><span data-stu-id="05d1a-137">Get MachineAction object</span></span> | <span data-ttu-id="05d1a-138">이 API를 실행하여 MachineAction 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="05d1a-138">Run this API to get MachineAction object.</span></span>
<span data-ttu-id="05d1a-139">MachineActions 컬렉션을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="05d1a-139">Get MachineActions collection</span></span> | <span data-ttu-id="05d1a-140">MachineAction 컬렉션을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="05d1a-140">Run this to get MachineAction collection.</span></span>
<span data-ttu-id="05d1a-141">FileActions 컬렉션 다운로드</span><span class="sxs-lookup"><span data-stu-id="05d1a-141">Get FileActions collection</span></span> | <span data-ttu-id="05d1a-142">이 API를 실행하여 FileActions 컬렉션을 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="05d1a-142">Run this API to get FileActions collection.</span></span>
<span data-ttu-id="05d1a-143">FileMachineAction 개체 다운로드</span><span class="sxs-lookup"><span data-stu-id="05d1a-143">Get FileMachineAction object</span></span> | <span data-ttu-id="05d1a-144">이 API를 실행하여 FileMachineAction 개체를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="05d1a-144">Run this API to get FileMachineAction object.</span></span>
<span data-ttu-id="05d1a-145">FileMachineActions 컬렉션 다운로드</span><span class="sxs-lookup"><span data-stu-id="05d1a-145">Get FileMachineActions collection</span></span> | <span data-ttu-id="05d1a-146">이 API를 실행하여 FileMachineAction 컬렉션을 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="05d1a-146">Run this API to get FileMachineAction collection.</span></span>
