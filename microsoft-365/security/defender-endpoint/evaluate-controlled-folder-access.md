---
title: 제어된 폴더 액세스 평가
description: 제어된 폴더 액세스를 통해 악성 앱에 의해 파일이 변경되지 못하게 보호하는 방법을 확인합니다.
keywords: Exploit Protection, windows 10, windows defender, 랜섬웨어, 보호, 평가, 테스트, 데모, 시도
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: levinec
ms.author: ellevin
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: e5da8ec3e4555af062aad1a4ebfa96d972bee23b
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51073911"
---
# <a name="evaluate-controlled-folder-access"></a><span data-ttu-id="b8678-104">제어된 폴더 액세스 평가</span><span class="sxs-lookup"><span data-stu-id="b8678-104">Evaluate controlled folder access</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b8678-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="b8678-105">**Applies to:**</span></span>
- [<span data-ttu-id="b8678-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="b8678-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="b8678-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b8678-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="b8678-108">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="b8678-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="b8678-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="b8678-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)


<span data-ttu-id="b8678-110">[제어된 폴더 액세스는](controlled-folders.md) 의심스러운 앱 또는 악성 앱에 의해 문서 및 파일을 수정하지 못하게 보호하는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="b8678-110">[Controlled folder access](controlled-folders.md) is a feature that helps protect your documents and files from modification by suspicious or malicious apps.</span></span> <span data-ttu-id="b8678-111">제어된 폴더 액세스는 Windows Server 2019 및 Windows 10 클라이언트에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8678-111">Controlled folder access is supported on Windows Server 2019 and Windows 10 clients.</span></span>

<span data-ttu-id="b8678-112">파일을 암호화하고 인질을 [](https://www.microsoft.com/wdsi/threats/ransomware) 보유하려는 랜섬웨어로부터 보호하는 데 특히 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="b8678-112">It is especially useful in helping protect against [ransomware](https://www.microsoft.com/wdsi/threats/ransomware) that attempts to encrypt your files and hold them hostage.</span></span>

<span data-ttu-id="b8678-113">이 문서는 제어된 폴더 액세스를 평가하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8678-113">This article helps you evaluate controlled folder access.</span></span> <span data-ttu-id="b8678-114">조직에서 직접 기능을 테스트할 수 있도록 감사 모드를 사용하도록 설정하는 방법에 대해 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8678-114">It explains how to enable audit mode so you can test the feature directly in your organization.</span></span>

> [!TIP]
> <span data-ttu-id="b8678-115">Microsoft Defender for [Endpoint](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) 데모 시나리오 웹 사이트(demo.wd.microsoft.com)를 방문하여 기능이 작동하는지 확인하고 작동 방법을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8678-115">You can also visit the Microsoft Defender for Endpoint demo scenario website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the feature is working and see how it works.</span></span>

## <a name="use-audit-mode-to-measure-impact"></a><span data-ttu-id="b8678-116">감사 모드를 사용하여 영향 측정</span><span class="sxs-lookup"><span data-stu-id="b8678-116">Use audit mode to measure impact</span></span>

<span data-ttu-id="b8678-117">감사 모드에서 제어된 폴더 액세스를 사용하도록 설정하여  완전히 활성화된 경우 어떤 일이 벌어질지 기록을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8678-117">Enable the controlled folder access in audit mode to see a record of what *would* have happened if it was fully enabled.</span></span> <span data-ttu-id="b8678-118">이 기능이 조직에서 어떻게 작동할지 테스트하여 업무 앱에 영향을 주지 않는지 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="b8678-118">Test how the feature will work in your organization to ensure it doesn't affect your line-of-business apps.</span></span> <span data-ttu-id="b8678-119">또한 일반적으로 특정 기간 동안 의심스러운 파일 수정 시도의 수를 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8678-119">You can also get an idea of how many suspicious file modification attempts generally occur over a certain period of time.</span></span>

<span data-ttu-id="b8678-120">감사 모드를 사용하도록 설정하려면 다음 PowerShell cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8678-120">To enable audit mode, use the following PowerShell cmdlet:</span></span>

```PowerShell
Set-MpPreference -EnableControlledFolderAccess AuditMode
```

> [!TIP]
> <span data-ttu-id="b8678-121">조직에서 제어된 폴더 액세스가 어떻게 작동할지 완전히 감사하려면 관리 도구를 사용하여 이 설정을 네트워크의 장치에 배포해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8678-121">If you want to fully audit how controlled folder access will work in your organization, you'll need to use a management tool to deploy this setting to devices in your network(s).</span></span>
<span data-ttu-id="b8678-122">주 제어된 폴더 액세스 항목에 설명된 바와 같이 그룹 정책, Intune, MDM(모바일 장치 관리) 또는 Microsoft Endpoint Manager를 사용하여 설정을 구성하고 배포할 [수도 있습니다.](controlled-folders.md)</span><span class="sxs-lookup"><span data-stu-id="b8678-122">You can also use Group Policy, Intune, mobile device management (MDM), or Microsoft Endpoint Manager to configure and deploy the setting, as described in the main [controlled folder access topic](controlled-folders.md).</span></span>

## <a name="review-controlled-folder-access-events-in-windows-event-viewer"></a><span data-ttu-id="b8678-123">Windows 이벤트 뷰어에서 제어된 폴더 액세스 이벤트 검토</span><span class="sxs-lookup"><span data-stu-id="b8678-123">Review controlled folder access events in Windows Event Viewer</span></span>

<span data-ttu-id="b8678-124">다음 제어된 폴더 액세스 이벤트는 Microsoft/Windows/Windows Defender/Operational 폴더 아래에 Windows 이벤트 뷰어에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8678-124">The following controlled folder access events appear in Windows Event Viewer under Microsoft/Windows/Windows Defender/Operational folder.</span></span>

<span data-ttu-id="b8678-125">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="b8678-125">Event ID</span></span> | <span data-ttu-id="b8678-126">설명</span><span class="sxs-lookup"><span data-stu-id="b8678-126">Description</span></span>
-|-
 <span data-ttu-id="b8678-127">5007</span><span class="sxs-lookup"><span data-stu-id="b8678-127">5007</span></span> | <span data-ttu-id="b8678-128">설정이 변경될 때의 이벤트</span><span class="sxs-lookup"><span data-stu-id="b8678-128">Event when settings are changed</span></span>
 <span data-ttu-id="b8678-129">1124</span><span class="sxs-lookup"><span data-stu-id="b8678-129">1124</span></span> | <span data-ttu-id="b8678-130">감사된 제어된 폴더 액세스 이벤트</span><span class="sxs-lookup"><span data-stu-id="b8678-130">Audited controlled folder access event</span></span>
 <span data-ttu-id="b8678-131">1123</span><span class="sxs-lookup"><span data-stu-id="b8678-131">1123</span></span> | <span data-ttu-id="b8678-132">차단된 제어된 폴더 액세스 이벤트</span><span class="sxs-lookup"><span data-stu-id="b8678-132">Blocked controlled folder access event</span></span>

> [!TIP]
> <span data-ttu-id="b8678-133">[로그를](https://docs.microsoft.com/windows/win32/wec/setting-up-a-source-initiated-subscription) 중앙에서 수집하도록 Windows 이벤트 전달 구독을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8678-133">You can configure a [Windows Event Forwarding subscription](https://docs.microsoft.com/windows/win32/wec/setting-up-a-source-initiated-subscription) to collect the logs centrally.</span></span> 

## <a name="customize-protected-folders-and-apps"></a><span data-ttu-id="b8678-134">보호된 폴더 및 앱 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="b8678-134">Customize protected folders and apps</span></span>

<span data-ttu-id="b8678-135">평가하는 동안 보호된 폴더 목록에 추가하거나 특정 앱에서 파일을 수정하도록 허용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8678-135">During your evaluation, you may wish to add to the list of protected folders, or allow certain apps to modify files.</span></span>

<span data-ttu-id="b8678-136">그룹 [정책,](controlled-folders.md) PowerShell 및 MDM CSP(구성 서비스 공급자)를 비롯한 관리 도구를 사용하여 기능을 구성하려면 제어된 폴더 액세스로 중요한 폴더 보호를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="b8678-136">See [Protect important folders with controlled folder access](controlled-folders.md) for configuring the feature with management tools, including Group Policy, PowerShell, and MDM configuration service providers (CSPs).</span></span>

## <a name="see-also"></a><span data-ttu-id="b8678-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b8678-137">See also</span></span>

* [<span data-ttu-id="b8678-138">제어된 폴더 액세스로 중요한 폴더 보호</span><span class="sxs-lookup"><span data-stu-id="b8678-138">Protect important folders with controlled folder access</span></span>](controlled-folders.md)
* [<span data-ttu-id="b8678-139">끝점에 대한 Microsoft Defender 평가</span><span class="sxs-lookup"><span data-stu-id="b8678-139">Evaluate Microsoft Defender for Endpoint</span></span>](evaluate-atp.md)
* [<span data-ttu-id="b8678-140">감사 모드 사용</span><span class="sxs-lookup"><span data-stu-id="b8678-140">Use audit mode</span></span>](audit-windows-defender.md)
