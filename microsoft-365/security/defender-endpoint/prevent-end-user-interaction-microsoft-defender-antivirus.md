---
title: Microsoft Defender 바이러스 백신 인터페이스 숨기기
description: Windows 보안 앱에서 바이러스 및 위협 방지 타일을 숨길 수 있습니다.
keywords: UI 잠금, 헤드리스 모드, 앱 숨기기, 설정 숨기기, 인터페이스 숨기기
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 6b5ce018db436aee35bfa1899fb42f1dca31efa6
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51691325"
---
# <a name="prevent-users-from-seeing-or-interacting-with-the-microsoft-defender-antivirus-user-interface"></a><span data-ttu-id="7b66b-104">사용자가 Microsoft Defender 바이러스 백신 사용자 인터페이스를 보거나 상호 작용하지 못하도록 차단</span><span class="sxs-lookup"><span data-stu-id="7b66b-104">Prevent users from seeing or interacting with the Microsoft Defender Antivirus user interface</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="7b66b-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="7b66b-105">**Applies to:**</span></span>

- <span data-ttu-id="7b66b-106">[엔드포인트용 Microsoft Defender](/microsoft-365/security/defender-endpoint/) </span><span class="sxs-lookup"><span data-stu-id="7b66b-106">[Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)</span></span>

<span data-ttu-id="7b66b-107">그룹 정책을 사용하여 끝점의 사용자가 Microsoft Defender 바이러스 백신 인터페이스를 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7b66b-107">You can use Group Policy to prevent users on endpoints from seeing the Microsoft Defender Antivirus interface.</span></span> <span data-ttu-id="7b66b-108">또한 검사가 더이상 실행되지 않도록 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b66b-108">You can also prevent them from pausing scans.</span></span>

## <a name="hide-the-microsoft-defender-antivirus-interface"></a><span data-ttu-id="7b66b-109">Microsoft Defender 바이러스 백신 인터페이스 숨기기</span><span class="sxs-lookup"><span data-stu-id="7b66b-109">Hide the Microsoft Defender Antivirus interface</span></span>

<span data-ttu-id="7b66b-110">Windows 10 버전 1703에서는 인터페이스를 숨기면 Microsoft Defender 바이러스 백신 알림이 숨겨지며 바이러스 & 위협 방지 타일이 Windows 보안 앱에 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7b66b-110">In Windows 10, versions 1703, hiding the interface will hide Microsoft Defender Antivirus notifications and prevent the Virus & threat protection tile from appearing in the Windows Security app.</span></span>

<span data-ttu-id="7b66b-111">설정이 **사용으로** 설정된 경우 :</span><span class="sxs-lookup"><span data-stu-id="7b66b-111">With the setting set to **Enabled**:</span></span>

![방패 아이콘 및 바이러스 및 위협 방지 섹션이 없는 Windows 보안 스크린샷](images/defender/wdav-headless-mode-1703.png)

<span data-ttu-id="7b66b-113">설정이 사용 안 하도록 **설정되거나** 구성되지 않은 경우:</span><span class="sxs-lookup"><span data-stu-id="7b66b-113">With the setting set to **Disabled** or not configured:</span></span>

![방패 아이콘 및 바이러스 및 위협 보호 섹션을 보여 주는 Windows 보안 스크린샷](images/defender/wdav-headless-mode-off-1703.png)

>[!NOTE]
><span data-ttu-id="7b66b-115">또한 인터페이스를 숨기면 끝점에 Microsoft Defender 바이러스 백신 알림이 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7b66b-115">Hiding the interface will also prevent Microsoft Defender Antivirus notifications from appearing on the endpoint.</span></span> <span data-ttu-id="7b66b-116">끝점용 Microsoft Defender 알림이 계속 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b66b-116">Microsoft Defender for Endpoint notifications will still appear.</span></span> <span data-ttu-id="7b66b-117">끝점에 나타나는 알림을 개별적으로 [구성할 수도 있습니다.](configure-notifications-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="7b66b-117">You can also individually [configure the notifications that appear on endpoints](configure-notifications-microsoft-defender-antivirus.md)</span></span>

<span data-ttu-id="7b66b-118">이전 버전의 Windows 10에서는 이 설정이 클라이언트 Windows Defender 숨겨지게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b66b-118">In earlier versions of Windows 10, the setting will hide the Windows Defender client interface.</span></span> <span data-ttu-id="7b66b-119">사용자가 앱을 열려고 하면 "시스템 관리자가 이 앱에 대한 액세스를 제한했습니다."라는 경고가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b66b-119">If the user attempts to open it, they will receive a warning that says, "Your system administrator has restricted access to this app."</span></span>

![Windows 10, 1703 이전 버전에서 헤드리스 모드를 사용하도록 설정한 경우 경고 메시지](images/defender/wdav-headless-mode-1607.png)

## <a name="use-group-policy-to-hide-the-microsoft-defender-av-interface-from-users"></a><span data-ttu-id="7b66b-121">그룹 정책을 사용하여 사용자로부터 Microsoft Defender AV 인터페이스 숨기기</span><span class="sxs-lookup"><span data-stu-id="7b66b-121">Use Group Policy to hide the Microsoft Defender AV interface from users</span></span>

1. <span data-ttu-id="7b66b-122">그룹 정책 관리 컴퓨터의 [](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)그룹 정책 관리 콘솔을 열고 구성할 그룹 정책 개체를 마우스 오른쪽 단추로 클릭하고 편집을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="7b66b-122">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="7b66b-123">그룹 정책 **관리 편집기를 사용하여 컴퓨터** **구성으로 이동하십시오.**</span><span class="sxs-lookup"><span data-stu-id="7b66b-123">Using the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="7b66b-124">관리 **템플릿 을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="7b66b-124">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="7b66b-125">Microsoft Defender 바이러스 백신 및 클라이언트 > Windows 구성 **> 확장합니다.**</span><span class="sxs-lookup"><span data-stu-id="7b66b-125">Expand the tree to **Windows components > Microsoft Defender Antivirus > Client interface**.</span></span>

5. <span data-ttu-id="7b66b-126">헤드리스 UI 모드 사용 설정을 **두 번 클릭하고** 옵션을 사용으로 **설정합니다.**</span><span class="sxs-lookup"><span data-stu-id="7b66b-126">Double-click the **Enable headless UI mode** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="7b66b-127">**확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7b66b-127">Click **OK**.</span></span> 

<span data-ttu-id="7b66b-128">사용자가 [PC에서](configure-local-policy-overrides-microsoft-defender-antivirus.md) 보호를 수정하지 못하도록 하는 데 대한 자세한 옵션은 사용자가 로컬에서 정책 설정을 수정하지 못하도록 방지를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7b66b-128">See [Prevent users from locally modifying policy settings](configure-local-policy-overrides-microsoft-defender-antivirus.md) for more options on preventing users form modifying protection on their PCs.</span></span>

## <a name="prevent-users-from-pausing-a-scan"></a><span data-ttu-id="7b66b-129">사용자가 검색을 시작하지 못하게 방지</span><span class="sxs-lookup"><span data-stu-id="7b66b-129">Prevent users from pausing a scan</span></span>

<span data-ttu-id="7b66b-130">사용자가 스캔을 중단하지 못하게 할 수 있습니다. 이렇게 하면 예약된 검사나 필요한 경우 검사가 중단되지 않도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b66b-130">You can prevent users from pausing scans, which can be helpful to ensure scheduled or on-demand scans are not interrupted by users.</span></span>

> [!NOTE]
> <span data-ttu-id="7b66b-131">이 설정은 Windows 10에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7b66b-131">This setting is not supported on Windows 10.</span></span>

### <a name="use-group-policy-to-prevent-users-from-pausing-a-scan"></a><span data-ttu-id="7b66b-132">그룹 정책을 사용하여 사용자가 스캔을 시작하지 못하게 차단</span><span class="sxs-lookup"><span data-stu-id="7b66b-132">Use Group Policy to prevent users from pausing a scan</span></span>

1. <span data-ttu-id="7b66b-133">그룹 정책 관리 컴퓨터의 [](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)그룹 정책 관리 콘솔을 열고 구성할 그룹 정책 개체를 마우스 오른쪽 단추로 클릭하고 편집을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="7b66b-133">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="7b66b-134">그룹 정책 **관리 편집기를 사용하여 컴퓨터** **구성으로 이동하십시오.**</span><span class="sxs-lookup"><span data-stu-id="7b66b-134">Using the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="7b66b-135">관리 **템플릿 을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="7b66b-135">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="7b66b-136">Windows 구성 요소 **Microsoft** Defender 바이러스 백신  >  **검사까지 트리를**  >  **확장합니다.**</span><span class="sxs-lookup"><span data-stu-id="7b66b-136">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Scan**.</span></span>

5. <span data-ttu-id="7b66b-137">사용자가 스캔을 일시 **중지할** 수 있도록 허용 설정을 두 번 클릭하고 옵션을 사용 안 **하도록 설정하십시오.**</span><span class="sxs-lookup"><span data-stu-id="7b66b-137">Double-click the **Allow users to pause scan** setting and set the option to **Disabled**.</span></span> <span data-ttu-id="7b66b-138">**확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7b66b-138">Click **OK**.</span></span> 

## <a name="related-articles"></a><span data-ttu-id="7b66b-139">관련 문서</span><span class="sxs-lookup"><span data-stu-id="7b66b-139">Related articles</span></span>

- [<span data-ttu-id="7b66b-140">끝점에 나타나는 알림 구성</span><span class="sxs-lookup"><span data-stu-id="7b66b-140">Configure the notifications that appear on endpoints</span></span>](configure-notifications-microsoft-defender-antivirus.md)

- [<span data-ttu-id="7b66b-141">Microsoft Defender 바이러스 백신과 최종 사용자 상호 작용 구성</span><span class="sxs-lookup"><span data-stu-id="7b66b-141">Configure end-user interaction with Microsoft Defender Antivirus</span></span>](configure-end-user-interaction-microsoft-defender-antivirus.md)

- [<span data-ttu-id="7b66b-142">Windows 10의 Microsoft Defender 바이러스 백신</span><span class="sxs-lookup"><span data-stu-id="7b66b-142">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)