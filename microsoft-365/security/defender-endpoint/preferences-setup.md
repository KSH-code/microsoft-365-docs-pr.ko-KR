---
title: Microsoft Defender 보안 센터 설정 구성
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
ms.openlocfilehash: c1526190116c55ba6916b690583f224ee1e86fd8
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186164"
---
# <a name="configure-microsoft-defender-security-center-settings"></a><span data-ttu-id="affa0-104">Microsoft Defender 보안 센터 설정 구성</span><span class="sxs-lookup"><span data-stu-id="affa0-104">Configure Microsoft Defender Security Center settings</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="affa0-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="affa0-105">**Applies to:**</span></span>
- [<span data-ttu-id="affa0-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="affa0-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="affa0-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="affa0-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="affa0-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="affa0-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="affa0-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="affa0-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-prefsettings-abovefoldlink)

<span data-ttu-id="affa0-110">설정 **메뉴를** 사용하여 일반 설정, 고급 기능을 수정하고 미리 보기 환경, 전자 메일 알림 및 사용자 지정 위협 인텔리전스 기능을 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="affa0-110">Use the **Settings** menu to modify general settings, advanced features, enable the preview experience, email notifications, and the custom threat intelligence feature.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="affa0-111">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="affa0-111">In this section</span></span>

<span data-ttu-id="affa0-112">항목</span><span class="sxs-lookup"><span data-stu-id="affa0-112">Topic</span></span> | <span data-ttu-id="affa0-113">설명</span><span class="sxs-lookup"><span data-stu-id="affa0-113">Description</span></span>
:---|:---
<span data-ttu-id="affa0-114">일반 설정</span><span class="sxs-lookup"><span data-stu-id="affa0-114">General settings</span></span> | <span data-ttu-id="affa0-115">이전에 온보더링 프로세스의 일부로 정의된 일반 설정을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="affa0-115">Modify your general settings that were previously defined as part of the onboarding process.</span></span>
<span data-ttu-id="affa0-116">사용 권한</span><span class="sxs-lookup"><span data-stu-id="affa0-116">Permissions</span></span> | <span data-ttu-id="affa0-117">RBAC 및 장치 그룹을 사용하여 포털 액세스를 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="affa0-117">Manage portal access using RBAC as well as device groups.</span></span>
<span data-ttu-id="affa0-118">API</span><span class="sxs-lookup"><span data-stu-id="affa0-118">APIs</span></span> | <span data-ttu-id="affa0-119">위협 인텔리전스 및 SIEM 통합을 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="affa0-119">Enable the threat intel and SIEM integration.</span></span>
<span data-ttu-id="affa0-120">규칙</span><span class="sxs-lookup"><span data-stu-id="affa0-120">Rules</span></span> | <span data-ttu-id="affa0-121">제거 규칙 및 자동화 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="affa0-121">Configure suppressions rules and automation settings.</span></span>
<span data-ttu-id="affa0-122">장치 관리</span><span class="sxs-lookup"><span data-stu-id="affa0-122">Device management</span></span> | <span data-ttu-id="affa0-123">장치를 온보드 및 오프보드합니다.</span><span class="sxs-lookup"><span data-stu-id="affa0-123">Onboard and offboard devices.</span></span>
