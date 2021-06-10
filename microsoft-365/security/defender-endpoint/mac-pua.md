---
title: Mac의 끝점용 Microsoft Defender를 통해 잠재적으로 원치 않는 응용 프로그램 검색 및 차단
description: Mac용 끝점에서 Microsoft Defender를 사용하여 PUA(사용자 없이 사용할 수 있는 응용 프로그램)를 검색하고 차단합니다.
keywords: microsoft, defender, Endpoint용 Microsoft Defender, mac, pua, pus
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
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 2d32dd96cd506ebf1752e48d2b7c66208b1abc11
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934540"
---
# <a name="detect-and-block-potentially-unwanted-applications-with-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="71d56-104">MacOS의 끝점용 Microsoft Defender를 통해 잠재적으로 원치 않는 응용 프로그램 검색 및 차단</span><span class="sxs-lookup"><span data-stu-id="71d56-104">Detect and block potentially unwanted applications with Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="71d56-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="71d56-105">**Applies to:**</span></span>
- [<span data-ttu-id="71d56-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="71d56-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="71d56-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="71d56-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="71d56-108">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="71d56-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="71d56-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="71d56-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


<span data-ttu-id="71d56-110">macOS의 끝점용 Microsoft Defender의 PUA(사용자 계정) 보호 기능은 네트워크의 끝점에서 PUA 파일을 검색하고 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71d56-110">The potentially unwanted application (PUA) protection feature in Microsoft Defender for Endpoint on macOS can detect and block PUA files on endpoints in your network.</span></span>

<span data-ttu-id="71d56-111">이러한 응용 프로그램은 바이러스, 맬웨어 또는 기타 유형의 위협으로 간주되지 않지만 성능이나 사용에 부정적인 영향을 주는 끝점에서 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71d56-111">These applications are not considered viruses, malware, or other types of threats, but might perform actions on endpoints that adversely affect their performance or use.</span></span> <span data-ttu-id="71d56-112">PUA는 신뢰도가 낮은 것으로 간주되는 응용 프로그램을 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71d56-112">PUA can also refer to applications that are considered to have poor reputation.</span></span>

<span data-ttu-id="71d56-113">이러한 응용 프로그램은 네트워크가 맬웨어에 감염될 위험을 높이고, 맬웨어 감염을 식별하기 더 어렵게 할 수 있으며, 응용 프로그램을 정리하는 데 IT 리소스를 낭비할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71d56-113">These applications can increase the risk of your network being infected with malware, cause malware infections to be harder to identify, and can waste IT resources in cleaning up the applications.</span></span>

## <a name="how-it-works"></a><span data-ttu-id="71d56-114">작동 방법</span><span class="sxs-lookup"><span data-stu-id="71d56-114">How it works</span></span>

<span data-ttu-id="71d56-115">MacOS의 끝점용 Microsoft Defender는 PUA 파일을 검색하고 보고할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71d56-115">Microsoft Defender for Endpoint on macOS can detect and report PUA files.</span></span> <span data-ttu-id="71d56-116">차단 모드에서 구성하면 PUA 파일이 검지로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="71d56-116">When configured in blocking mode, PUA files are moved to the quarantine.</span></span>

<span data-ttu-id="71d56-117">끝점에서 PUA가 감지되면 알림을 사용하지 않도록 설정하지 않은 경우 macOS의 끝점용 Microsoft Defender가 사용자에게 알림을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="71d56-117">When a PUA is detected on an endpoint, Microsoft Defender for Endpoint on macOS presents a notification to the user, unless notifications have been disabled.</span></span> <span data-ttu-id="71d56-118">위협 이름에는 "Application"이라는 단어가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71d56-118">The threat name will contain the word "Application".</span></span>

## <a name="configure-pua-protection"></a><span data-ttu-id="71d56-119">PUA 보호 구성</span><span class="sxs-lookup"><span data-stu-id="71d56-119">Configure PUA protection</span></span>

<span data-ttu-id="71d56-120">macOS의 끝점용 Microsoft Defender의 PUA 보호는 다음 방법 중 하나에서 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71d56-120">PUA protection in Microsoft Defender for Endpoint on macOS can be configured in one of the following ways:</span></span>

- <span data-ttu-id="71d56-121">**Off**: PUA 보호를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="71d56-121">**Off**: PUA protection is disabled.</span></span>
- <span data-ttu-id="71d56-122">**감사**: PUA 파일이 제품 로그에 보고되지만, PUA 파일에는 Microsoft Defender 보안 센터.</span><span class="sxs-lookup"><span data-stu-id="71d56-122">**Audit**: PUA files are reported in the product logs, but not in Microsoft Defender Security Center.</span></span> <span data-ttu-id="71d56-123">사용자에게 알림이 제공된 것이 아니며 제품에 의해 아무 작업도 수행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="71d56-123">No notification is presented to the user and no action is taken by the product.</span></span>
- <span data-ttu-id="71d56-124">**차단:** PUA 파일이 제품 로그 및 검색된 Microsoft Defender 보안 센터.</span><span class="sxs-lookup"><span data-stu-id="71d56-124">**Block**: PUA files are reported in the product logs and in Microsoft Defender Security Center.</span></span> <span data-ttu-id="71d56-125">사용자에게 알림이 표시된 후 제품에 의해 작업이 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="71d56-125">The user is presented with a notification and action is taken by the product.</span></span>

>[!WARNING]
><span data-ttu-id="71d56-126">기본적으로 PUA 보호는 감사 모드에서 **구성됩니다.**</span><span class="sxs-lookup"><span data-stu-id="71d56-126">By default, PUA protection is configured in **Audit** mode.</span></span>

<span data-ttu-id="71d56-127">명령줄 또는 관리 콘솔에서 PUA 파일이 처리되는 방법을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71d56-127">You can configure how PUA files are handled from the command line or from the management console.</span></span>

### <a name="use-the-command-line-tool-to-configure-pua-protection"></a><span data-ttu-id="71d56-128">명령줄 도구를 사용하여 PUA 보호를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="71d56-128">Use the command-line tool to configure PUA protection:</span></span>

<span data-ttu-id="71d56-129">터미널에서 다음 명령을 실행하여 PUA 보호를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="71d56-129">In Terminal, execute the following command to configure PUA protection:</span></span>

```bash
mdatp threat policy set --type potentially_unwanted_application --action [off|audit|block]
```

### <a name="use-the-management-console-to-configure-pua-protection"></a><span data-ttu-id="71d56-130">관리 콘솔을 사용하여 PUA 보호를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="71d56-130">Use the management console to configure PUA protection:</span></span>

<span data-ttu-id="71d56-131">기업에서는 다른 제품 설정 구성 방법과 마찬가지로 JAMF 또는 Intune과 같은 관리 콘솔에서 PUA 보호를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71d56-131">In your enterprise, you can configure PUA protection from a management console, such as JAMF or Intune, similarly to how other product settings are configured.</span></span> <span data-ttu-id="71d56-132">자세한 내용은 [MacOS에서 끝점용 Microsoft Defender에](mac-preferences.md) 대한 기본 설정 설정 항목의 위협 유형 설정 섹션을 참조하세요. [](mac-preferences.md#threat-type-settings)</span><span class="sxs-lookup"><span data-stu-id="71d56-132">For more information, see the [Threat type settings](mac-preferences.md#threat-type-settings) section of the [Set preferences for Microsoft Defender for Endpoint on macOS](mac-preferences.md) topic.</span></span>

## <a name="related-topics"></a><span data-ttu-id="71d56-133">관련 항목</span><span class="sxs-lookup"><span data-stu-id="71d56-133">Related topics</span></span>

- [<span data-ttu-id="71d56-134">macOS의 끝점에 대한 Microsoft Defender 기본 설정 설정</span><span class="sxs-lookup"><span data-stu-id="71d56-134">Set preferences for Microsoft Defender for Endpoint on macOS</span></span>](mac-preferences.md)
