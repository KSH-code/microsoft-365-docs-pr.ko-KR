---
title: 구성 Microsoft Defender 보안 센터 구성
description: 설정 페이지를 사용하여 일반 설정, 사용 권한, api 및 규칙을 구성합니다.
keywords: 설정, 일반 설정, 사용 권한, api, 규칙
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 5869e8406158eb6d6b2f48b3083cb9011bb3951d
ms.sourcegitcommit: dc1ac43a57fac6f57438859dd668f927d94fdf34
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/07/2021
ms.locfileid: "51604348"
---
# <a name="configure-microsoft-defender-security-center-settings"></a><span data-ttu-id="fbf30-104">구성 Microsoft Defender 보안 센터 구성</span><span class="sxs-lookup"><span data-stu-id="fbf30-104">Configure Microsoft Defender Security Center settings</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="fbf30-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="fbf30-105">**Applies to:**</span></span>
- [<span data-ttu-id="fbf30-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="fbf30-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="fbf30-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fbf30-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="fbf30-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="fbf30-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="fbf30-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="fbf30-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-prefsettings-abovefoldlink)

<span data-ttu-id="fbf30-110">설정 메뉴를 사용하여 일반 설정, **고급** 기능을 수정하고 미리 보기 환경, 전자 메일 알림 및 사용자 지정 위협 인텔리전스 기능을 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbf30-110">Use the **Settings** menu to modify general settings, advanced features, enable the preview experience, email notifications, and the custom threat intelligence feature.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="fbf30-111">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="fbf30-111">In this section</span></span>

<span data-ttu-id="fbf30-112">항목</span><span class="sxs-lookup"><span data-stu-id="fbf30-112">Topic</span></span> | <span data-ttu-id="fbf30-113">설명</span><span class="sxs-lookup"><span data-stu-id="fbf30-113">Description</span></span>
:---|:---
<span data-ttu-id="fbf30-114">일반 설정</span><span class="sxs-lookup"><span data-stu-id="fbf30-114">General settings</span></span> | <span data-ttu-id="fbf30-115">이전에 온보더링 프로세스의 일부로 정의된 일반 설정을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="fbf30-115">Modify your general settings that were previously defined as part of the onboarding process.</span></span>
<span data-ttu-id="fbf30-116">사용 권한</span><span class="sxs-lookup"><span data-stu-id="fbf30-116">Permissions</span></span> | <span data-ttu-id="fbf30-117">RBAC 및 장치 그룹을 사용하여 포털 액세스를 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="fbf30-117">Manage portal access using RBAC as well as device groups.</span></span>
<span data-ttu-id="fbf30-118">API</span><span class="sxs-lookup"><span data-stu-id="fbf30-118">APIs</span></span> | <span data-ttu-id="fbf30-119">위협 인텔리전스 및 SIEM 통합을 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="fbf30-119">Enable the threat intel and SIEM integration.</span></span>
<span data-ttu-id="fbf30-120">규칙</span><span class="sxs-lookup"><span data-stu-id="fbf30-120">Rules</span></span> | <span data-ttu-id="fbf30-121">제거 규칙 및 자동화 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="fbf30-121">Configure suppressions rules and automation settings.</span></span>
<span data-ttu-id="fbf30-122">디바이스 관리</span><span class="sxs-lookup"><span data-stu-id="fbf30-122">Device management</span></span> | <span data-ttu-id="fbf30-123">장치를 온보드 및 오프보드합니다.</span><span class="sxs-lookup"><span data-stu-id="fbf30-123">Onboard and offboard devices.</span></span>
<span data-ttu-id="fbf30-124">네트워크 평가</span><span class="sxs-lookup"><span data-stu-id="fbf30-124">Network assessments</span></span> | <span data-ttu-id="fbf30-125">정기적으로 검사하여 장치 인벤토리에 추가할 장치를 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="fbf30-125">Choose devices to be scanned regularly and added to the device inventory.</span></span>
