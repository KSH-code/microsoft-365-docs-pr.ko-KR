---
title: Microsoft Defender 바이러스 백신 클라우드 차단 제한 시간 구성
description: 클라우드 확인을 기다리는 동안 Microsoft Defender 바이러스 백신에서 파일이 실행되지 못하도록 차단하는 기간을 구성할 수 있습니다.
keywords: Microsoft Defender 바이러스 백신, 맬웨어 방지, 보안, defender, 클라우드, 시간 제한, 차단, 기간, 초
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 372d679f45d6f87392b612f757e6bdf1c6c6b9ad
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765806"
---
# <a name="configure-the-cloud-block-timeout-period"></a><span data-ttu-id="95b77-104">클라우드 차단 시간 제한 기간 구성</span><span class="sxs-lookup"><span data-stu-id="95b77-104">Configure the cloud block timeout period</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="95b77-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="95b77-105">**Applies to:**</span></span>

- <span data-ttu-id="95b77-106">[엔드포인트용 Microsoft Defender](/microsoft-365/security/defender-endpoint/) </span><span class="sxs-lookup"><span data-stu-id="95b77-106">[Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)</span></span>

<span data-ttu-id="95b77-107">Microsoft Defender 바이러스 백신이 의심스러운 파일을 발견하면 Microsoft Defender 바이러스 백신 클라우드 서비스를 쿼리하는 동안 파일이 실행되지 [않도록 할 수 있습니다.](cloud-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="95b77-107">When Microsoft Defender Antivirus finds a suspicious file, it can prevent the file from running while it queries the [Microsoft Defender Antivirus cloud service](cloud-protection-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="95b77-108">파일이 차단될 기본 기간은 10초입니다. [](configure-block-at-first-sight-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="95b77-108">The default period that the file will be [blocked](configure-block-at-first-sight-microsoft-defender-antivirus.md) is 10 seconds.</span></span> <span data-ttu-id="95b77-109">파일을 실행할 수 있도록 허용되기 전에 대기할 시간을 추가로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95b77-109">You can specify an additional period of time to wait before the file is allowed to run.</span></span> <span data-ttu-id="95b77-110">이를 통해 Microsoft Defender 바이러스 백신 클라우드 서비스에서 적절한 확인을 받을 충분한 시간을 확보할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95b77-110">This can help ensure there is enough time to receive a proper determination from the Microsoft Defender Antivirus cloud service.</span></span>

## <a name="prerequisites-to-use-the-extended-cloud-block-timeout"></a><span data-ttu-id="95b77-111">확장된 클라우드 차단 시간 제한을 사용하기 위한 선행 준비</span><span class="sxs-lookup"><span data-stu-id="95b77-111">Prerequisites to use the extended cloud block timeout</span></span>

<span data-ttu-id="95b77-112">[제한 시간을](configure-block-at-first-sight-microsoft-defender-antivirus.md) 연장하려면 먼저 차단 및 해당 선행 조건이 활성화되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="95b77-112">[Block at first sight](configure-block-at-first-sight-microsoft-defender-antivirus.md) and its prerequisites must be enabled before you can specify an extended timeout period.</span></span>

## <a name="specify-the-extended-timeout-period"></a><span data-ttu-id="95b77-113">연장된 제한 시간 지정</span><span class="sxs-lookup"><span data-stu-id="95b77-113">Specify the extended timeout period</span></span>

<span data-ttu-id="95b77-114">그룹 정책을 사용하여 클라우드 검사에 대한 연장된 시간 제한을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95b77-114">You can use Group Policy to specify an extended timeout for cloud checks.</span></span>

1. <span data-ttu-id="95b77-115">그룹 정책 관리 컴퓨터에서 그룹 [](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))정책 관리 콘솔을 열고 구성할 그룹 정책 개체를 마우스 오른쪽 단추로 클릭하고 편집을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="95b77-115">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="95b77-116">그룹 정책 **관리 편집기에서** 컴퓨터 **구성으로 이동하여** 관리 템플릿 **을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="95b77-116">In the **Group Policy Management Editor** go to **Computer configuration** and click **Administrative templates**.</span></span>

3. <span data-ttu-id="95b77-117">**Microsoft Defender** 바이러스 백신 > Windows 구성 > 확장</span><span class="sxs-lookup"><span data-stu-id="95b77-117">Expand the tree to **Windows components > Microsoft Defender Antivirus > MpEngine**</span></span>

4. <span data-ttu-id="95b77-118">확장된 클라우드 확인 구성을 두 **번 클릭하고** 옵션이 사용하도록 설정되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="95b77-118">Double-click **Configure extended cloud check** and ensure the option is enabled.</span></span> <span data-ttu-id="95b77-119">클라우드 확인을 기다리는 동안 파일이 실행되지 않도록 추가 시간을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="95b77-119">Specify the additional amount of time to prevent the file from running while waiting for a cloud determination.</span></span> <span data-ttu-id="95b77-120">추가 시간을 초당 1초에서 50초로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95b77-120">You can specify the additional time, in seconds, from 1 second to 50 seconds.</span></span> <span data-ttu-id="95b77-121">이 시간은 기본값인 10초에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="95b77-121">This time will be added to the default 10 seconds.</span></span>

5. <span data-ttu-id="95b77-122">**확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="95b77-122">Click **OK**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="95b77-123">관련 항목</span><span class="sxs-lookup"><span data-stu-id="95b77-123">Related topics</span></span>

- [<span data-ttu-id="95b77-124">Windows 10의 Microsoft Defender 바이러스 백신</span><span class="sxs-lookup"><span data-stu-id="95b77-124">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="95b77-125">클라우드 제공 보호를 통해 차세대 바이러스 백신 기술 사용</span><span class="sxs-lookup"><span data-stu-id="95b77-125">Use next-generation antivirus technologies through cloud-delivered protection</span></span>](cloud-protection-microsoft-defender-antivirus.md)
- [<span data-ttu-id="95b77-126">최초 차단 구성</span><span class="sxs-lookup"><span data-stu-id="95b77-126">Configure block at first sight</span></span>](configure-block-at-first-sight-microsoft-defender-antivirus.md)
- [<span data-ttu-id="95b77-127">클라우드 제공 보호 사용</span><span class="sxs-lookup"><span data-stu-id="95b77-127">Enable cloud-delivered protection</span></span>](enable-cloud-protection-microsoft-defender-antivirus.md)