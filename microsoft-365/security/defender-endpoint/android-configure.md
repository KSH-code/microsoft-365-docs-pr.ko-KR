---
title: Microsoft Defender for Endpoint(Android용) 기능 구성
description: Android에서 끝점용 Microsoft Defender를 구성하는 방법을 설명
keywords: Microsoft, defender, Endpoint용 Microsoft Defender, mde, android, 구성
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 264ebbe0ceb6d6b83c006dbd1dd071a78ae219c3
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841357"
---
# <a name="configure-defender-for-endpoint-on-android-features"></a><span data-ttu-id="b9b55-104">Android 기능에서 끝점에 대한 Defender 구성</span><span class="sxs-lookup"><span data-stu-id="b9b55-104">Configure Defender for Endpoint on Android features</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b9b55-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="b9b55-105">**Applies to:**</span></span>
- [<span data-ttu-id="b9b55-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="b9b55-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="b9b55-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b9b55-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="conditional-access-with-defender-for-endpoint-on-android"></a><span data-ttu-id="b9b55-108">Android의 끝점용 Defender를 통해 조건부 액세스</span><span class="sxs-lookup"><span data-stu-id="b9b55-108">Conditional Access with Defender for Endpoint on Android</span></span>  
<span data-ttu-id="b9b55-109">Android의 끝점용 Microsoft Defender 및 Microsoft Intune Azure Active Directory 위험 수준에 따라 장치 준수 및 조건부 액세스 정책을 시행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9b55-109">Microsoft Defender for Endpoint on Android along with Microsoft Intune and Azure Active Directory enables enforcing Device compliance and Conditional Access policies based on device risk levels.</span></span> <span data-ttu-id="b9b55-110">Endpoint용 Defender는 Intune을 통해 이 기능을 활용하기 위해 배포할 수 있는 MTD(Mobile Threat Defense) 솔루션입니다.</span><span class="sxs-lookup"><span data-stu-id="b9b55-110">Defender for Endpoint is a Mobile Threat Defense (MTD) solution that you can deploy to leverage this capability via Intune.</span></span>

<span data-ttu-id="b9b55-111">Android 및 조건부 액세스에서 끝점용 Defender를 설정하는 방법에 대한 자세한 내용은 Endpoint 및 [Intune용 Defender를 참조하세요.](/mem/intune/protect/advanced-threat-protection)</span><span class="sxs-lookup"><span data-stu-id="b9b55-111">For more information about how to set up Defender for Endpoint on Android and Conditional Access, see [Defender for Endpoint and Intune](/mem/intune/protect/advanced-threat-protection).</span></span>

## <a name="configure-custom-indicators"></a><span data-ttu-id="b9b55-112">사용자 지정 표시기 구성</span><span class="sxs-lookup"><span data-stu-id="b9b55-112">Configure custom indicators</span></span>  

> [!NOTE]
> <span data-ttu-id="b9b55-113">Android의 끝점용 Defender는 IP 주소 및 URL/도메인에 대한 사용자 지정 표시기 만들기만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9b55-113">Defender for Endpoint on Android only supports creating custom indicators for IP addresses and URLs/domains.</span></span>

<span data-ttu-id="b9b55-114">Android의 끝점용 Defender를 사용하면 관리자가 Android 장치도 지원하도록 사용자 지정 표시기를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9b55-114">Defender for Endpoint on Android enables admins to configure custom indicators to support Android devices as well.</span></span> <span data-ttu-id="b9b55-115">사용자 지정 표시기를 구성하는 방법에 대한 자세한 내용은 [지표 관리를 참조하세요.](manage-indicators.md)</span><span class="sxs-lookup"><span data-stu-id="b9b55-115">For more information on how to configure custom indicators, see [Manage indicators](manage-indicators.md).</span></span>

## <a name="configure-web-protection"></a><span data-ttu-id="b9b55-116">웹 보호 구성</span><span class="sxs-lookup"><span data-stu-id="b9b55-116">Configure web protection</span></span>
<span data-ttu-id="b9b55-117">Android의 끝점용 Defender를 통해 IT 관리자는 웹 보호 기능을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9b55-117">Defender for Endpoint on Android allows IT Administrators the ability to configure the web protection feature.</span></span> <span data-ttu-id="b9b55-118">이 기능은 Microsoft Endpoint Manager 관리 센터에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9b55-118">This capability is available within the Microsoft Endpoint Manager Admin center.</span></span>

> [!NOTE]
> <span data-ttu-id="b9b55-119">Android의 끝점용 Defender는 웹 보호 기능을 제공하기 위해 VPN을 사용하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9b55-119">Defender for Endpoint on Android would use a VPN in order to provide the Web Protection feature.</span></span> <span data-ttu-id="b9b55-120">이는 일반 VPN이 아니며 장치 외부에서 트래픽을 취하지 않는 로컬/자체 루프 VPN입니다.</span><span class="sxs-lookup"><span data-stu-id="b9b55-120">This is not a regular VPN and is a local/self-looping VPN that does not take traffic outside the device.</span></span> <span data-ttu-id="b9b55-121">자세한 내용은 Android를 실행 하는 장치에서 웹 보호 [구성을 참조하세요.](/mem/intune/protect/advanced-threat-protection-manage-android)</span><span class="sxs-lookup"><span data-stu-id="b9b55-121">For more information, see [Configure web protection on devices that run Android](/mem/intune/protect/advanced-threat-protection-manage-android).</span></span>

## <a name="related-topics"></a><span data-ttu-id="b9b55-122">관련 항목</span><span class="sxs-lookup"><span data-stu-id="b9b55-122">Related topics</span></span>
- [<span data-ttu-id="b9b55-123">Microsoft Defender for Endpoint(iOS용) 개요</span><span class="sxs-lookup"><span data-stu-id="b9b55-123">Overview of Microsoft Defender for Endpoint on Android</span></span>](microsoft-defender-endpoint-android.md)
- [<span data-ttu-id="b9b55-124">Microsoft Intune으로 Microsoft Defender for Endpoint(Android용) 배포</span><span class="sxs-lookup"><span data-stu-id="b9b55-124">Deploy Microsoft Defender for Endpoint on Android with Microsoft Intune</span></span>](android-intune.md)
