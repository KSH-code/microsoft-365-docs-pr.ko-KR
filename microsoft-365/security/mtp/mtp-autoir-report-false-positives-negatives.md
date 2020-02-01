---
title: Microsoft Threat Protection의 AIR에서 가양성 또는 거짓 네거티브를 보고 하는 방법
description: Microsoft Threat Protection의 AIR에서 누락 되었거나 지워지는이 감지 되었습니까? 분석을 위해 Microsoft에 가양성 또는 거짓 네거티브를 전송 하는 방법을 알아봅니다.
keywords: 자동, 조사, 경고, 트리거, 작업, 재구성, 거짓 긍정, 거짓 음수
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: d9175e78326832a2be874359babae5ae9c689420
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41600085"
---
# <a name="how-to-report-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a><span data-ttu-id="b8db1-105">자동화 된 조사 및 응답 기능에서 가양성/네거티브를 보고 하는 방법</span><span class="sxs-lookup"><span data-stu-id="b8db1-105">How to report false positives/negatives in automated investigation and response capabilities</span></span>

<span data-ttu-id="b8db1-106">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="b8db1-106">**Applies to:**</span></span>
- <span data-ttu-id="b8db1-107">Microsoft 위협 방지</span><span class="sxs-lookup"><span data-stu-id="b8db1-107">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="b8db1-108">Microsoft Threat Protection에 대 [한 자동화 된 조사 및 응답 기능이](mtp-autoir.md) 없거나 지워지는에서 감지 되었습니까?</span><span class="sxs-lookup"><span data-stu-id="b8db1-108">Did [automated investigation and response capabilities](mtp-autoir.md) in Microsoft Threat Protection miss or wrongly detect something?</span></span> <span data-ttu-id="b8db1-109">이를 Microsoft에 보고 하거나 필요한 경우 경고를 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8db1-109">You can report it to Microsoft or adjust your alerts (if needed).</span></span> <span data-ttu-id="b8db1-110">다음 표를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="b8db1-110">Use the following table as a guide:</span></span> 


|<span data-ttu-id="b8db1-111">항목</span><span class="sxs-lookup"><span data-stu-id="b8db1-111">Item</span></span>  |<span data-ttu-id="b8db1-112">검색 기준</span><span class="sxs-lookup"><span data-stu-id="b8db1-112">Detected by</span></span>  |<span data-ttu-id="b8db1-113">보고 방법</span><span class="sxs-lookup"><span data-stu-id="b8db1-113">How to report it</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="b8db1-114">전자 메일 메시지</span><span class="sxs-lookup"><span data-stu-id="b8db1-114">Email message</span></span> <br/><span data-ttu-id="b8db1-115">전자 메일 첨부 파일</span><span class="sxs-lookup"><span data-stu-id="b8db1-115">Email attachment</span></span> <br/><span data-ttu-id="b8db1-116">전자 메일 메시지 또는 Office 파일의 URL</span><span class="sxs-lookup"><span data-stu-id="b8db1-116">URL in an email message or Office file</span></span>      |[<span data-ttu-id="b8db1-117">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="b8db1-117">Office 365 Advanced Threat Protection</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)        |[<span data-ttu-id="b8db1-118">의심 스러운 스팸, 피싱, Url 및 파일을 Microsoft에 Office 365 검색에 제출</span><span class="sxs-lookup"><span data-stu-id="b8db1-118">Submit suspected spam, phish, URLs, and files to Microsoft for Office 365 scanning</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission)         |
|<span data-ttu-id="b8db1-119">장치에 있는 파일 또는 앱</span><span class="sxs-lookup"><span data-stu-id="b8db1-119">File or app on a device</span></span>    |[<span data-ttu-id="b8db1-120">Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="b8db1-120">Microsoft Defender Advanced Threat Protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection)         |[<span data-ttu-id="b8db1-121">맬웨어 분석을 위해 Microsoft에 파일 제출</span><span class="sxs-lookup"><span data-stu-id="b8db1-121">Submit a file to Microsoft for malware analysis</span></span>](https://www.microsoft.com/wdsi/filesubmission)         |
|<span data-ttu-id="b8db1-122">합법적인 사용에 의해 트리거되는 경고</span><span class="sxs-lookup"><span data-stu-id="b8db1-122">Alert triggered by legitimate use</span></span> <br/><span data-ttu-id="b8db1-123">부정확 한 경고</span><span class="sxs-lookup"><span data-stu-id="b8db1-123">Inaccurate alert</span></span>    |[<span data-ttu-id="b8db1-124">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="b8db1-124">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security)<br/> <span data-ttu-id="b8db1-125">또는</span><span class="sxs-lookup"><span data-stu-id="b8db1-125">or</span></span> <br/>[<span data-ttu-id="b8db1-126">Azure Advanced Threat Detection</span><span class="sxs-lookup"><span data-stu-id="b8db1-126">Azure Advanced Threat Detection</span></span>](https://docs.microsoft.com/azure/security/fundamentals/threat-detection)         |[<span data-ttu-id="b8db1-127">Cloud App Security 포털에서 알림 관리</span><span class="sxs-lookup"><span data-stu-id="b8db1-127">Manage alerts in the Cloud App Security portal</span></span>](https://docs.microsoft.com/cloud-app-security/managing-alerts)         |


## <a name="next-steps"></a><span data-ttu-id="b8db1-128">다음 단계</span><span class="sxs-lookup"><span data-stu-id="b8db1-128">Next steps</span></span>

- [<span data-ttu-id="b8db1-129">자동화된 조사 및 대응과 관련된 조치 승인 또는 거부</span><span class="sxs-lookup"><span data-stu-id="b8db1-129">Approve or reject actions related to automated investigation and response</span></span>](mtp-autoir-actions.md)
- [<span data-ttu-id="b8db1-130">알림 센터에 대한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="b8db1-130">Learn more about the Action center</span></span>](mtp-action-center.md)
- [<span data-ttu-id="b8db1-131">Microsoft Threat Protection의 고급 헌팅을 통한 위협에 대한 사전 대응</span><span class="sxs-lookup"><span data-stu-id="b8db1-131">Proactively hunt for threats with advanced hunting in Microsoft Threat Protection</span></span>](advanced-hunting-overview.md)
