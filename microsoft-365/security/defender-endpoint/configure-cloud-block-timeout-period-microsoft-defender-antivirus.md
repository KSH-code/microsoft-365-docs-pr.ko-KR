---
title: 클라우드 Microsoft Defender 바이러스 백신 제한 시간 구성
description: 클라우드 결정이 Microsoft Defender 바이러스 백신 동안 파일이 실행되지 못하도록 차단하는 기간을 구성할 수 있습니다.
keywords: Microsoft Defender 바이러스 백신, 맬웨어 방지, 보안, defender, 클라우드, 시간 제한, 차단, 기간, 초
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.date: 06/04/2021
ms.openlocfilehash: dfb75b77119d9550931c3e476323bde67a3b148f
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2021
ms.locfileid: "52789090"
---
# <a name="configure-the-cloud-block-timeout-period"></a><span data-ttu-id="8cf75-104">클라우드 차단 제한 시간 구성</span><span class="sxs-lookup"><span data-stu-id="8cf75-104">Configure the cloud block timeout period</span></span>

<span data-ttu-id="8cf75-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="8cf75-105">**Applies to:**</span></span>

- [<span data-ttu-id="8cf75-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="8cf75-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="8cf75-107">사용자가 Microsoft Defender 바이러스 백신 파일을 찾은 경우 클라우드 서비스 에 쿼리하는 동안 파일이 [실행되지 Microsoft Defender 바이러스 백신 있습니다.](cloud-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="8cf75-107">When Microsoft Defender Antivirus finds a suspicious file, it can prevent the file from running while it queries the [Microsoft Defender Antivirus cloud service](cloud-protection-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="8cf75-108">파일이 차단된 기본 [기간은](configure-block-at-first-sight-microsoft-defender-antivirus.md) 10초입니다.</span><span class="sxs-lookup"><span data-stu-id="8cf75-108">The default period that the file is [blocked](configure-block-at-first-sight-microsoft-defender-antivirus.md) is 10 seconds.</span></span> <span data-ttu-id="8cf75-109">보안 관리자인 경우 파일을 실행할 수 있도록 허용되기 전에 대기할 시간을 더 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cf75-109">If you're a security administrator, you can specify more time to wait before the file is allowed to run.</span></span> <span data-ttu-id="8cf75-110">클라우드 차단 시간 제한 기간을 연장하면 클라우드 서비스에서 적절한 확인을 받을 Microsoft Defender 바이러스 백신 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cf75-110">Extending the cloud block timeout period can help ensure there is enough time to receive a proper determination from the Microsoft Defender Antivirus cloud service.</span></span>

## <a name="prerequisites-to-use-the-extended-cloud-block-timeout"></a><span data-ttu-id="8cf75-111">확장된 클라우드 차단 시간 제한을 사용하기 위한 선행 준비</span><span class="sxs-lookup"><span data-stu-id="8cf75-111">Prerequisites to use the extended cloud block timeout</span></span>

<span data-ttu-id="8cf75-112">[제한 시간을](configure-block-at-first-sight-microsoft-defender-antivirus.md) 연장하려면 먼저 차단 및 해당 선행 조건이 활성화되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cf75-112">[Block at first sight](configure-block-at-first-sight-microsoft-defender-antivirus.md) and its prerequisites must be enabled before you can specify an extended timeout period.</span></span>

## <a name="specify-the-extended-timeout-period-using-microsoft-endpoint-manager"></a><span data-ttu-id="8cf75-113">제한 시간을 사용하여 연장된 시간 제한 Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="8cf75-113">Specify the extended timeout period using Microsoft Endpoint Manager</span></span>

<span data-ttu-id="8cf75-114">에서 끝점 보안 정책을 사용하여 클라우드 차단 시간 제한 기간을 [지정할 Microsoft Endpoint Manager.](/mem/intune/protect/endpoint-security-policy)</span><span class="sxs-lookup"><span data-stu-id="8cf75-114">You can specify the cloud block timeout period with an [endpoint security policy in Microsoft Endpoint Manager](/mem/intune/protect/endpoint-security-policy).</span></span>

1. <span data-ttu-id="8cf75-115">Endpoint Manager 관리 센터()로 이동하여 [https://endpoint.microsoft.com/](https://endpoint.microsoft.com/) 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="8cf75-115">Go to the Endpoint Manager admin center ([https://endpoint.microsoft.com/](https://endpoint.microsoft.com/)) and sign in.</span></span>

2. <span data-ttu-id="8cf75-116">끝점 **보안 을 선택한** 다음 관리 **에서** 바이러스 백신 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="8cf75-116">Select **Endpoint security**, and then under **Manage**, choose **Antivirus**.</span></span>

3. <span data-ttu-id="8cf75-117">바이러스 백신 정책을 선택(또는 만들기)합니다.</span><span class="sxs-lookup"><span data-stu-id="8cf75-117">Select (or create) an antivirus policy.</span></span>

4. <span data-ttu-id="8cf75-118">구성 **설정 섹션에서** 클라우드 **보호를 확장합니다.**</span><span class="sxs-lookup"><span data-stu-id="8cf75-118">In the **Configuration settings** section, expand **Cloud protection**.</span></span> <span data-ttu-id="8cf75-119">그런 다음 **Defender 클라우드** 확장 시간 제한(초) 상자에 1초에서 50초까지 더 많은 시간을 초당 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8cf75-119">Then, in the **Defender Cloud Extended Timeout In Seconds** box, specify the more time, in seconds, from 1 second to 50 seconds.</span></span> <span data-ttu-id="8cf75-120">지정한 모든 것이 기본 10초에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="8cf75-120">Whatever you specify is added to the default 10 seconds.</span></span>

5. <span data-ttu-id="8cf75-121">(이 단계는 선택 사항임) 바이러스 백신 정책을 다른 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="8cf75-121">(This step is optional) Make any other changes to your antivirus policy.</span></span> <span data-ttu-id="8cf75-122">(도움이 필요하세요?</span><span class="sxs-lookup"><span data-stu-id="8cf75-122">(Need help?</span></span> <span data-ttu-id="8cf75-123">자세한 [설정 에서 Microsoft Defender 바이러스 백신 정책에 대한 Microsoft Intune.)를 참조합니다.](/mem/intune/protect/antivirus-microsoft-defender-settings-windows)</span><span class="sxs-lookup"><span data-stu-id="8cf75-123">See [Settings for Microsoft Defender Antivirus policy in Microsoft Intune](/mem/intune/protect/antivirus-microsoft-defender-settings-windows).)</span></span>

6. <span data-ttu-id="8cf75-124">다음 **을** 선택하고 정책 구성을 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="8cf75-124">Choose **Next**, and finish configuring your policy.</span></span>

## <a name="specify-the-extended-timeout-period-using-group-policy"></a><span data-ttu-id="8cf75-125">그룹 정책을 사용하여 연장된 시간 제한 기간 지정</span><span class="sxs-lookup"><span data-stu-id="8cf75-125">Specify the extended timeout period using Group Policy</span></span>

<span data-ttu-id="8cf75-126">그룹 정책을 사용하여 클라우드 검사에 대한 연장된 시간 제한을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cf75-126">You can use Group Policy to specify an extended timeout for cloud checks.</span></span>

1. <span data-ttu-id="8cf75-127">그룹 정책 관리 컴퓨터에서 그룹 정책 관리 [콘솔을 열기](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))</span><span class="sxs-lookup"><span data-stu-id="8cf75-127">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))</span></span>

2. <span data-ttu-id="8cf75-128">구성할 그룹 정책 개체를 마우스 오른쪽 단추로 클릭한 다음 편집 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="8cf75-128">Right-click the Group Policy Object you want to configure and then select **Edit**.</span></span>

3. <span data-ttu-id="8cf75-129">그룹 **정책 관리 편집기에서** 컴퓨터 구성으로 **이동한** 다음 관리 템플릿 **을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="8cf75-129">In the **Group Policy Management Editor**, go to **Computer configuration**, and then select **Administrative templates**.</span></span>

3. <span data-ttu-id="8cf75-130">트리를 확장하여   >    >  **MpEngine** Windows 구성 Microsoft Defender 바이러스 백신 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="8cf75-130">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **MpEngine**.</span></span>

4. <span data-ttu-id="8cf75-131">확장된 클라우드 확인 구성을 두 **번 클릭하고** 옵션이 사용하도록 설정되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="8cf75-131">Double-click **Configure extended cloud check** and ensure the option is enabled.</span></span> 

   <span data-ttu-id="8cf75-132">클라우드 확인을 기다리는 동안 파일이 실행되지 않도록 추가 시간을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8cf75-132">Specify the extra amount of time to prevent the file from running while waiting for a cloud determination.</span></span> <span data-ttu-id="8cf75-133">추가 시간을 초당 1초에서 50초로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8cf75-133">Specify the extra time, in seconds, from 1 second to 50 seconds.</span></span> <span data-ttu-id="8cf75-134">지정한 모든 것이 기본 10초에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="8cf75-134">Whatever you specify is added to the default 10 seconds.</span></span>

5. <span data-ttu-id="8cf75-135">**확인** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8cf75-135">Select **OK**.</span></span>

 