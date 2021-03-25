---
title: 파일에 대한 표시기 만들기
ms.reviewer: ''
description: 엔터티의 검색, 방지 및 제외를 정의하는 파일 해시에 대한 표시기를 만들 수 있습니다.
keywords: 파일, 해시, 관리, 허용, 차단, 차단, 정리, 악성, 파일 해시, ip 주소, URL, 도메인
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
ms.openlocfilehash: 35a0b66a4cdc4cf39c15329eda2e0aafced79f34
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/25/2021
ms.locfileid: "51199612"
---
# <a name="create-indicators-for-files"></a><span data-ttu-id="b61be-104">파일에 대한 표시기 만들기</span><span class="sxs-lookup"><span data-stu-id="b61be-104">Create indicators for files</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="b61be-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="b61be-105">**Applies to:**</span></span>
- [<span data-ttu-id="b61be-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="b61be-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="b61be-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b61be-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)



> [!TIP]
> <span data-ttu-id="b61be-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="b61be-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="b61be-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="b61be-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

<span data-ttu-id="b61be-110">잠재적인 악성 파일 또는 의심되는 맬웨어를 금지하여 조직에서 공격이 추가로 전파되는 것을 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b61be-110">You can prevent further propagation of an attack in your organization by banning potentially malicious files or suspected malware.</span></span> <span data-ttu-id="b61be-111">잠재적으로 악의적인 PE(이식 가능한 실행 파일) 파일을 알고 있는 경우 해당 파일을 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b61be-111">If you know a potentially malicious portable executable (PE) file, you can block it.</span></span> <span data-ttu-id="b61be-112">이 작업을 수행하면 조직의 컴퓨터의 읽기, 작성 또는 실행이 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="b61be-112">This operation will prevent it from being read, written, or executed on machines in your organization.</span></span>

<span data-ttu-id="b61be-113">파일에 대한 표시기를 만드는 방법에는 다음 두 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b61be-113">There are two ways you can create indicators for files:</span></span>
- <span data-ttu-id="b61be-114">설정 페이지를 통해 표시기를 만들어</span><span class="sxs-lookup"><span data-stu-id="b61be-114">By creating an indicator through the settings page</span></span>
- <span data-ttu-id="b61be-115">파일 세부 정보 페이지에서 표시기 추가 단추를 사용하여 상황 표시기를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b61be-115">By creating a contextual indicator using the add indicator button from the file details page</span></span>

### <a name="before-you-begin"></a><span data-ttu-id="b61be-116">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="b61be-116">Before you begin</span></span>
<span data-ttu-id="b61be-117">파일에 대한 표시기를 만들기 전에 다음과 같은 선행 방법을 이해하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="b61be-117">It's important to understand the following prerequisites prior to creating indicators for files:</span></span>

- <span data-ttu-id="b61be-118">이 기능은 조직에서 바이러스 백신 및 클라우드 Windows Defender 사용하도록 설정된 경우 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b61be-118">This feature is available if your organization uses Windows Defender Antivirus and Cloud-based protection is enabled.</span></span> <span data-ttu-id="b61be-119">자세한 내용은 클라우드 제공 보호를 통해 Microsoft Defender 바이러스 백신에 [차세대 기술 사용을 참조하세요.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/utilize-microsoft-cloud-protection-microsoft-defender-antivirus)</span><span class="sxs-lookup"><span data-stu-id="b61be-119">For more information, see [Use next-generation technologies in Microsoft Defender Antivirus through cloud-delivered protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/utilize-microsoft-cloud-protection-microsoft-defender-antivirus).</span></span>
- <span data-ttu-id="b61be-120">맬웨어 방지 클라이언트 버전은 4.18.1901.x 이상입니다.</span><span class="sxs-lookup"><span data-stu-id="b61be-120">The Antimalware client version must be 4.18.1901.x or later.</span></span>
- <span data-ttu-id="b61be-121">Windows 10 버전 1703 이상, Windows server 2016 및 2019의 컴퓨터에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="b61be-121">Supported on machines on Windows 10, version 1703 or later, Windows server 2016 and 2019.</span></span>
- <span data-ttu-id="b61be-122">파일 차단을 시작하려면 먼저 설정에서 차단 또는 허용 [기능을 켜야  ](advanced-features.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="b61be-122">To start blocking files, you first need to [turn the **Block or allow** feature on](advanced-features.md) in Settings.</span></span>
- <span data-ttu-id="b61be-123">이 기능은 의심되는 맬웨어(또는 악성 파일)가 웹에서 다운로드되지 않도록 디자인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b61be-123">This feature is designed to prevent suspected malware (or potentially malicious files) from being downloaded from the web.</span></span> <span data-ttu-id="b61be-124">현재 _.exe_ 및 _.dll_ 파일을 비롯한 PE(이식 가능한 실행 파일) 파일을 지원하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b61be-124">It currently supports portable executable (PE) files, including _.exe_ and _.dll_ files.</span></span> <span data-ttu-id="b61be-125">적용 범위는 시간이 지날 때 연장됩니다.</span><span class="sxs-lookup"><span data-stu-id="b61be-125">The coverage will be extended over time.</span></span>

<span data-ttu-id="b61be-126">네트워크 공유에서 로컬 장치로 큰 파일을 복사하는 경우 특히 VPN 연결을 통해 성능에 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b61be-126">Performance can be affected if you are copying large files from a network share onto your local device, especially over a VPN connection.</span></span> 

> [!IMPORTANT]
> - <span data-ttu-id="b61be-127">허용 또는 차단 작업 전에 파일의 분류가 디바이스 캐시에 있는 경우 파일에서 허용 또는 차단 기능을 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b61be-127">The allow or block function cannot be done on files if the file's classification exists on the device's cache prior to the allow or block action</span></span> 
> - <span data-ttu-id="b61be-128">신뢰할 수 있는 서명된 파일은 다르게 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="b61be-128">Trusted signed files will be treated differently.</span></span> <span data-ttu-id="b61be-129">끝점용 Defender는 악성 파일을 처리하도록 최적화되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b61be-129">Defender for Endpoint is optimized to handle malicious files.</span></span> <span data-ttu-id="b61be-130">경우에 따라 신뢰할 수 있는 서명된 파일을 차단하려고 시도하면 성능에 의미가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b61be-130">Trying to block trusted signed files, in some cases, may have performance implications.</span></span>
> - <span data-ttu-id="b61be-131">일반적으로 파일 블록은 몇 분 이내에 적용되지만 30분까지 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b61be-131">Typically, file blocks are enforced within a couple of minutes, but can take upwards of 30 minutes.</span></span>
> - <span data-ttu-id="b61be-132">충돌하는 파일 표시기 정책이 있는 경우 보다 안전한 정책의 적용 정책이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b61be-132">If there are conflicting file indicator policies, the enforcement policy of the more secure policy is applied.</span></span> <span data-ttu-id="b61be-133">예를 들어 두 해시 유형이 동일한 파일을 정의하는 경우 SHA-256 파일 해시 표시기 정책이 MD5 파일 해시 표시기 정책보다 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="b61be-133">For example, a SHA-256 file hash indicator policy takes precedence over an MD5 file hash indicator policy if both hash types define the same file.</span></span>

### <a name="create-an-indicator-for-files-from-the-settings-page"></a><span data-ttu-id="b61be-134">설정 페이지에서 파일에 대한 표시기 만들기</span><span class="sxs-lookup"><span data-stu-id="b61be-134">Create an indicator for files from the settings page</span></span>

1. <span data-ttu-id="b61be-135">탐색 창에서 설정   >  **표시기를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="b61be-135">In the navigation pane, select **Settings** > **Indicators**.</span></span>  

2. <span data-ttu-id="b61be-136">파일 **해시 탭을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b61be-136">Select the **File hash** tab.</span></span>

3. <span data-ttu-id="b61be-137">표시기 **추가를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="b61be-137">Select **Add indicator**.</span></span>

4. <span data-ttu-id="b61be-138">다음 세부 정보를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b61be-138">Specify the following details:</span></span>
   - <span data-ttu-id="b61be-139">Indicator - 엔터티 세부 정보를 지정하고 표시기 만료를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b61be-139">Indicator - Specify the entity details and define the expiration of the indicator.</span></span>
   - <span data-ttu-id="b61be-140">작업 - 수행될 작업을 지정하고 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="b61be-140">Action - Specify the action to be taken and provide a description.</span></span>
   - <span data-ttu-id="b61be-141">범위 - 컴퓨터 그룹의 범위를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b61be-141">Scope - Define the scope of the machine group.</span></span>

5. <span data-ttu-id="b61be-142">요약 탭에서 세부 정보를 검토한 다음 저장을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="b61be-142">Review the details in the Summary tab, then click **Save**.</span></span>

### <a name="create-a-contextual-indicator-from-the-file-details-page"></a><span data-ttu-id="b61be-143">파일 세부 정보 페이지에서 상황 표시기 만들기</span><span class="sxs-lookup"><span data-stu-id="b61be-143">Create a contextual indicator from the file details page</span></span>
<span data-ttu-id="b61be-144">파일에 대한 응답 작업을 수행할 때의 옵션 중 하나는 [파일에](respond-file-alerts.md) 대한 표시기를 추가하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b61be-144">One of the options when taking [response actions on a file](respond-file-alerts.md) is adding an indicator for the file.</span></span> 

<span data-ttu-id="b61be-145">파일에 대한 표시기 해시를 추가할 때 조직의 컴퓨터로 실행을 시도할 때마다 경고를 발생하고 파일을 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b61be-145">When you add an indicator hash for a file, you can choose to raise an alert and block the file whenever a machine in your organization attempts to run it.</span></span>

<span data-ttu-id="b61be-146">표시기에서 자동으로 차단되는 파일은 파일의 알림 센터에 표시되지 않지만 경고 큐에 계속 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b61be-146">Files automatically blocked by an indicator won't show up in the file's Action center, but the alerts will still be visible in the Alerts queue.</span></span>


## <a name="related-topics"></a><span data-ttu-id="b61be-147">관련 항목</span><span class="sxs-lookup"><span data-stu-id="b61be-147">Related topics</span></span>
- [<span data-ttu-id="b61be-148">표시기 만들기</span><span class="sxs-lookup"><span data-stu-id="b61be-148">Create indicators</span></span>](manage-indicators.md)
- [<span data-ttu-id="b61be-149">IPS 및 URL/도메인에 대한 표시기 만들기</span><span class="sxs-lookup"><span data-stu-id="b61be-149">Create indicators for IPs and URLs/domains</span></span>](indicator-ip-domain.md)
- [<span data-ttu-id="b61be-150">인증서를 기반으로 표시기 만들기</span><span class="sxs-lookup"><span data-stu-id="b61be-150">Create indicators based on certificates</span></span>](indicator-certificates.md)
- [<span data-ttu-id="b61be-151">표시기 관리</span><span class="sxs-lookup"><span data-stu-id="b61be-151">Manage indicators</span></span>](indicator-manage.md)
