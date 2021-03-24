---
title: Linux용 Microsoft Defender ATP를 통해 잠재적으로 원치 않는 응용 프로그램 검색 및 차단
description: Linux용 Microsoft Defender ATP를 사용하여 잠재적으로 원치 않는 응용 프로그램(PUA)을 검색하고 차단합니다.
keywords: microsoft, defender, atp, linux, pua, pus
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
ms.openlocfilehash: af4d1a548d34e1a9974ce5d4a6a32361d14d3548
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51073767"
---
# <a name="detect-and-block-potentially-unwanted-applications-with-microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="6a49c-104">Linux용 끝점용 Microsoft Defender를 통해 잠재적으로 원치 않는 응용 프로그램 검색 및 차단</span><span class="sxs-lookup"><span data-stu-id="6a49c-104">Detect and block potentially unwanted applications with Microsoft Defender for Endpoint for Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="6a49c-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="6a49c-105">**Applies to:**</span></span>
- [<span data-ttu-id="6a49c-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="6a49c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="6a49c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6a49c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="6a49c-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="6a49c-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="6a49c-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="6a49c-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="6a49c-110">Linux용 Endpoint용 Defender의 PUA(사용자 가능성이 원치 않는 응용 프로그램) 보호 기능은 네트워크의 끝점에서 PUA 파일을 검색하고 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a49c-110">The potentially unwanted application (PUA) protection feature in Defender for Endpoint for Linux can detect and block PUA files on endpoints in your network.</span></span>

<span data-ttu-id="6a49c-111">이러한 응용 프로그램은 바이러스, 맬웨어 또는 기타 유형의 위협으로 간주되지 않지만 성능이나 사용에 부정적인 영향을 주는 끝점에서 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a49c-111">These applications are not considered viruses, malware, or other types of threats, but might perform actions on endpoints that adversely affect their performance or use.</span></span> <span data-ttu-id="6a49c-112">PUA는 신뢰도가 낮은 것으로 간주되는 응용 프로그램을 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a49c-112">PUA can also refer to applications that are considered to have poor reputation.</span></span>

<span data-ttu-id="6a49c-113">이러한 응용 프로그램은 네트워크가 맬웨어에 감염될 위험을 높이고, 맬웨어 감염을 식별하기 더 어렵게 할 수 있으며, 응용 프로그램을 정리하는 데 IT 리소스를 낭비할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a49c-113">These applications can increase the risk of your network being infected with malware, cause malware infections to be harder to identify, and can waste IT resources in cleaning up the applications.</span></span>

## <a name="how-it-works"></a><span data-ttu-id="6a49c-114">작동 방식</span><span class="sxs-lookup"><span data-stu-id="6a49c-114">How it works</span></span>

<span data-ttu-id="6a49c-115">Linux용 끝점용 Defender는 PUA 파일을 검색하고 보고할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a49c-115">Defender for Endpoint for Linux can detect and report PUA files.</span></span> <span data-ttu-id="6a49c-116">차단 모드에서 구성하면 PUA 파일이 검지로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a49c-116">When configured in blocking mode, PUA files are moved to the quarantine.</span></span>

<span data-ttu-id="6a49c-117">끝점에서 PUA가 감지되면 Linux용 Endpoint용 Defender는 위협 기록에 감염 기록을 보관합니다.</span><span class="sxs-lookup"><span data-stu-id="6a49c-117">When a PUA is detected on an endpoint, Defender for Endpoint for Linux keeps a record of the infection in the threat history.</span></span> <span data-ttu-id="6a49c-118">기록은 Microsoft Defender 보안 센터 포털 또는 명령줄 도구를 통해 `mdatp` 시각화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a49c-118">The history can be visualized from the Microsoft Defender Security Center portal or through the `mdatp` command-line tool.</span></span> <span data-ttu-id="6a49c-119">위협 이름에는 "Application"이라는 단어가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a49c-119">The threat name will contain the word "Application".</span></span>

## <a name="configure-pua-protection"></a><span data-ttu-id="6a49c-120">PUA 보호 구성</span><span class="sxs-lookup"><span data-stu-id="6a49c-120">Configure PUA protection</span></span>

<span data-ttu-id="6a49c-121">Linux용 끝점용 Defender의 PUA 보호는 다음 방법 중 하나에서 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a49c-121">PUA protection in Defender for Endpoint for Linux can be configured in one of the following ways:</span></span>

- <span data-ttu-id="6a49c-122">**Off**: PUA 보호를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6a49c-122">**Off**: PUA protection is disabled.</span></span>
- <span data-ttu-id="6a49c-123">**감사**: PUA 파일이 제품 로그에 보고되지만 Microsoft Defender 보안 센터에는 보고되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6a49c-123">**Audit**: PUA files are reported in the product logs, but not in Microsoft Defender Security Center.</span></span> <span data-ttu-id="6a49c-124">감염에 대한 기록은 위협 기록에 저장되지 않습니다. 제품에 의해 수행된 조치가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6a49c-124">No record of the infection is stored in the threat history and no action is taken by the product.</span></span>
- <span data-ttu-id="6a49c-125">**차단:** PUA 파일이 제품 로그 및 Microsoft Defender 보안 센터에 보고됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a49c-125">**Block**: PUA files are reported in the product logs and in Microsoft Defender Security Center.</span></span> <span data-ttu-id="6a49c-126">감염 레코드는 위협 기록에 저장되고 제품이 조치를 취합니다.</span><span class="sxs-lookup"><span data-stu-id="6a49c-126">A record of the infection is stored in the threat history and action is taken by the product.</span></span>

>[!WARNING]
><span data-ttu-id="6a49c-127">기본적으로 PUA 보호는 감사 모드에서 **구성됩니다.**</span><span class="sxs-lookup"><span data-stu-id="6a49c-127">By default, PUA protection is configured in **Audit** mode.</span></span>

<span data-ttu-id="6a49c-128">명령줄 또는 관리 콘솔에서 PUA 파일이 처리되는 방법을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a49c-128">You can configure how PUA files are handled from the command line or from the management console.</span></span>

### <a name="use-the-command-line-tool-to-configure-pua-protection"></a><span data-ttu-id="6a49c-129">명령줄 도구를 사용하여 PUA 보호를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="6a49c-129">Use the command-line tool to configure PUA protection:</span></span>

<span data-ttu-id="6a49c-130">터미널에서 다음 명령을 실행하여 PUA 보호를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="6a49c-130">In Terminal, execute the following command to configure PUA protection:</span></span>

```bash
mdatp threat policy set --type potentially_unwanted_application --action [off|audit|block]
```

### <a name="use-the-management-console-to-configure-pua-protection"></a><span data-ttu-id="6a49c-131">관리 콘솔을 사용하여 PUA 보호를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="6a49c-131">Use the management console to configure PUA protection:</span></span>

<span data-ttu-id="6a49c-132">기업에서는 다른 제품 설정 구성 방법과 마찬가지로 Puppet 또는 Ansible과 같은 관리 콘솔에서 PUA 보호를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a49c-132">In your enterprise, you can configure PUA protection from a management console, such as Puppet or Ansible, similarly to how other product settings are configured.</span></span> <span data-ttu-id="6a49c-133">자세한 내용은 Linux용 [끝점용](linux-preferences.md#threat-type-settings) Defender에 대한 기본 설정 설정 문서의 위협 유형 설정 [섹션을 참조하세요.](linux-preferences.md)</span><span class="sxs-lookup"><span data-stu-id="6a49c-133">For more information, see the [Threat type settings](linux-preferences.md#threat-type-settings) section of the [Set preferences for Defender for Endpoint for Linux](linux-preferences.md) article.</span></span>

## <a name="related-articles"></a><span data-ttu-id="6a49c-134">관련 문서</span><span class="sxs-lookup"><span data-stu-id="6a49c-134">Related articles</span></span>

- [<span data-ttu-id="6a49c-135">Linux용 끝점에 대한 Defender 기본 설정 설정</span><span class="sxs-lookup"><span data-stu-id="6a49c-135">Set preferences for Defender for Endpoint for Linux</span></span>](linux-preferences.md)
