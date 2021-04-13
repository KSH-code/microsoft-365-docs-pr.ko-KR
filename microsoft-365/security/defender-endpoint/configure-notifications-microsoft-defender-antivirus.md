---
title: Microsoft Defender 바이러스 백신 알림 구성
description: 끝점에서 표준 및 추가 Microsoft Defender 바이러스 백신 알림을 구성하고 사용자 지정하는 방법을 학습합니다.
keywords: 알림, defender, 바이러스 백신, 끝점, 관리, 관리자
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
ms.openlocfilehash: 82ca54e383943f4994f9647ce1e110a6621b1327
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51691418"
---
# <a name="configure-the-notifications-that-appear-on-endpoints"></a><span data-ttu-id="d88f7-104">끝점에 나타나는 알림 구성</span><span class="sxs-lookup"><span data-stu-id="d88f7-104">Configure the notifications that appear on endpoints</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="d88f7-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="d88f7-105">**Applies to:**</span></span>

- <span data-ttu-id="d88f7-106">[엔드포인트용 Microsoft Defender](/microsoft-365/security/defender-endpoint/) </span><span class="sxs-lookup"><span data-stu-id="d88f7-106">[Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)</span></span>

<span data-ttu-id="d88f7-107">Windows 10에서 맬웨어 검색 및 수정에 대한 응용 프로그램 알림은 더 강력하고 일관되고, 일관성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d88f7-107">In Windows 10, application notifications about malware detection and remediation are more robust, consistent, and concise.</span></span>

<span data-ttu-id="d88f7-108">수동으로 트리거되고 예약된 검사가 완료되고 위협이 감지되면 알림이 끝점에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d88f7-108">Notifications appear on endpoints when manually triggered and scheduled scans are completed and threats are detected.</span></span> <span data-ttu-id="d88f7-109">이러한 알림은 알림 센터에도 **표시될** 수 있으며, 검사 및 위협 검색 요약은 정기적인 간격으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d88f7-109">These notifications also appear in the **Notification Center**, and a summary of scans and threat detections appear at regular time intervals.</span></span>

<span data-ttu-id="d88f7-110">다시 시작 알림이나 위협이 감지되고 수정된 경우와 같이 끝점에 표준 알림이 나타나는 방법을 구성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d88f7-110">You can also configure how standard notifications appear on endpoints, such as notifications for reboot or when a threat has been detected and remediated.</span></span>

## <a name="configure-the-additional-notifications-that-appear-on-endpoints"></a><span data-ttu-id="d88f7-111">끝점에 나타나는 추가 알림 구성</span><span class="sxs-lookup"><span data-stu-id="d88f7-111">Configure the additional notifications that appear on endpoints</span></span>

<span data-ttu-id="d88f7-112">Windows 보안 앱 및 그룹 정책을 사용하여 [최근](microsoft-defender-security-center-antivirus.md) 위협 감지 요약과 같은 추가 알림 표시를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d88f7-112">You can configure the display of additional notifications, such as recent threat detection summaries, in the [Windows Security app](microsoft-defender-security-center-antivirus.md) and with Group Policy.</span></span>

> [!NOTE]
> <span data-ttu-id="d88f7-113">Windows 10 버전 1607에서는 이  기능을 고급 알림이라고 하여 **Windows** 설정 업데이트 및 보안 &  >  **에서 구성할**  >  **수 Windows Defender.**</span><span class="sxs-lookup"><span data-stu-id="d88f7-113">In Windows 10, version 1607 the feature was called **Enhanced notifications** and could be configured under **Windows Settings** > **Update & security** > **Windows Defender**.</span></span> <span data-ttu-id="d88f7-114">모든 버전의 Windows 10의 그룹 정책 설정에서 이를 고급 **알림이라고 합니다.**</span><span class="sxs-lookup"><span data-stu-id="d88f7-114">In Group Policy settings in all versions of Windows 10, it is called **Enhanced notifications**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d88f7-115">추가 알림을 사용하지 않도록 설정하면 위협 감지 및 수정 경고와 같은 중요한 알림이 비활성화되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d88f7-115">Disabling additional notifications will not disable critical notifications, such as threat detection and remediation alerts.</span></span>

<span data-ttu-id="d88f7-116">**Windows 보안 앱을 사용하여 추가 알림을 사용하지 않도록 설정할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="d88f7-116">**Use the Windows Security app to disable additional notifications:**</span></span>

1. <span data-ttu-id="d88f7-117">작업 표시줄에서 방패 아이콘을 클릭하거나 **Defender의** 시작 메뉴를 검색하여 Windows 보안 앱을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d88f7-117">Open the Windows Security app by clicking the shield icon in the task bar or searching the start menu for **Defender**.</span></span>

2. <span data-ttu-id="d88f7-118">바이러스 & **위협** 방지 타일(또는 왼쪽 메뉴 표시줄의 방패 **아이콘)을** 클릭한 다음 바이러스 & 보호 설정 레이블을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d88f7-118">Click the **Virus & threat protection** tile (or the shield icon on the left menu bar) and then the **Virus & threat protection settings** label:</span></span>

    ![Windows 보안 앱의 바이러스 & 보호 설정 레이블 스크린샷](images/defender/wdav-protection-settings-wdsc.png)

3. <span data-ttu-id="d88f7-120">알림 **섹션으로 스크롤하고** 알림 설정 **변경을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d88f7-120">Scroll to the **Notifications** section and click **Change notification settings**.</span></span>

4. <span data-ttu-id="d88f7-121">스위치를 **끄기** 또는 **켜기로 밀어** 추가 알림을 사용하지 않도록 설정하거나 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d88f7-121">Slide the switch to **Off** or **On** to disable or enable additional notifications.</span></span>

<span data-ttu-id="d88f7-122">**그룹 정책을 사용하여 추가 알림을 사용하지 않도록 설정:**</span><span class="sxs-lookup"><span data-stu-id="d88f7-122">**Use Group Policy to disable additional notifications:**</span></span>

1. <span data-ttu-id="d88f7-123">그룹 정책 관리 컴퓨터에서 그룹 [](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))정책 관리 콘솔을 열고 구성할 그룹 정책 개체를 마우스 오른쪽 단추로 클릭하고 편집을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d88f7-123">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="d88f7-124">그룹 정책 **관리 편집기에서** 컴퓨터 **구성으로 이동하십시오.**</span><span class="sxs-lookup"><span data-stu-id="d88f7-124">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="d88f7-125">관리 **템플릿 을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d88f7-125">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="d88f7-126">보고 에서 Microsoft Defender 바이러스 > Windows 구성 **> 확장합니다.**</span><span class="sxs-lookup"><span data-stu-id="d88f7-126">Expand the tree to **Windows components > Microsoft Defender Antivirus > Reporting**.</span></span>

5. <span data-ttu-id="d88f7-127">향상된 알림 **끄기** 를 두 번 클릭하고 옵션을 사용으로 **설정합니다.**</span><span class="sxs-lookup"><span data-stu-id="d88f7-127">Double-click **Turn off enhanced notifications** and set the option to **Enabled**.</span></span> <span data-ttu-id="d88f7-128">**확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d88f7-128">Click **OK**.</span></span> <span data-ttu-id="d88f7-129">이렇게 하면 추가 알림이 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d88f7-129">This will prevent additional notifications from appearing.</span></span>

## <a name="configure-standard-notifications-on-endpoints"></a><span data-ttu-id="d88f7-130">끝점에서 표준 알림 구성</span><span class="sxs-lookup"><span data-stu-id="d88f7-130">Configure standard notifications on endpoints</span></span>

<span data-ttu-id="d88f7-131">그룹 정책을 사용하여 다음을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d88f7-131">You can use Group Policy to:</span></span>

- <span data-ttu-id="d88f7-132">사용자가 작업을 수행해야 하는 경우 끝점에 추가 사용자 지정 텍스트 표시</span><span class="sxs-lookup"><span data-stu-id="d88f7-132">Display additional, customized text on endpoints when the user needs to perform an action</span></span>
- <span data-ttu-id="d88f7-133">끝점에서 모든 알림 숨기기</span><span class="sxs-lookup"><span data-stu-id="d88f7-133">Hide all notifications on endpoints</span></span>
- <span data-ttu-id="d88f7-134">끝점에서 다시 시작 알림 숨기기</span><span class="sxs-lookup"><span data-stu-id="d88f7-134">Hide reboot notifications on endpoints</span></span>

<span data-ttu-id="d88f7-135">알림 숨기기는 전체 Microsoft Defender 바이러스 백신 인터페이스를 숨길 수 없는 상황에서 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d88f7-135">Hiding notifications can be useful in situations where you can't hide the entire Microsoft Defender Antivirus interface.</span></span> <span data-ttu-id="d88f7-136">자세한 [내용은 사용자가 Microsoft Defender 바이러스](prevent-end-user-interaction-microsoft-defender-antivirus.md) 백신 사용자 인터페이스를 보거나 상호 작용하지 못하도록 방지를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d88f7-136">See [Prevent users from seeing or interacting with the Microsoft Defender Antivirus user interface](prevent-end-user-interaction-microsoft-defender-antivirus.md) for more information.</span></span> 

> [!NOTE]
> <span data-ttu-id="d88f7-137">알림 숨기기는 정책이 배포된 끝점에서만 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="d88f7-137">Hiding notifications will only occur on endpoints to which the policy has been deployed.</span></span> <span data-ttu-id="d88f7-138">재부팅과 같이 취해야 하는 작업과 관련된 알림은 Microsoft [Endpoint Manager Endpoint Protection](/configmgr/protect/deploy-use/monitor-endpoint-protection)모니터링 대시보드 및 보고서에 계속 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d88f7-138">Notifications related to actions that must be taken (such as a reboot) will still appear on the [Microsoft Endpoint Manager Endpoint Protection monitoring dashboard and reports](/configmgr/protect/deploy-use/monitor-endpoint-protection).</span></span> 

<span data-ttu-id="d88f7-139">사용자의 [컴퓨터 알림에](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) 사용자 지정 연락처 정보를 추가하는 방법에 대한 지침은 조직의 Windows 보안 앱 사용자 지정을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d88f7-139">See [Customize the Windows Security app for your organization](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) for instructions to add custom contact information to the notifications that users see on their machines.</span></span>

<span data-ttu-id="d88f7-140">**그룹 정책을 사용하여 알림을 숨길 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="d88f7-140">**Use Group Policy to hide notifications:**</span></span>

1. <span data-ttu-id="d88f7-141">그룹 정책 관리 컴퓨터에서 그룹 [](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))정책 관리 콘솔을 열고 구성할 그룹 정책 개체를 마우스 오른쪽 단추로 클릭하고 편집을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d88f7-141">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure, and click **Edit**.</span></span>

2. <span data-ttu-id="d88f7-142">그룹 정책 **관리 편집기에서** 컴퓨터 **구성으로 이동하여** 관리 템플릿 **을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d88f7-142">In the **Group Policy Management Editor** go to **Computer configuration** and click **Administrative templates**.</span></span>

3. <span data-ttu-id="d88f7-143">Microsoft Defender 바이러스 백신 및 클라이언트 > Windows 구성 **> 확장합니다.**</span><span class="sxs-lookup"><span data-stu-id="d88f7-143">Expand the tree to **Windows components > Microsoft Defender Antivirus > Client interface**.</span></span> 

4. <span data-ttu-id="d88f7-144">모든 알림 표시 **안 를 두 번 클릭하고** 옵션을 사용으로 **설정합니다.**</span><span class="sxs-lookup"><span data-stu-id="d88f7-144">Double-click **Suppress all notifications** and set the option to **Enabled**.</span></span> <span data-ttu-id="d88f7-145">**확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d88f7-145">Click **OK**.</span></span> <span data-ttu-id="d88f7-146">이렇게 하면 추가 알림이 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d88f7-146">This will prevent additional notifications from appearing.</span></span>

<span data-ttu-id="d88f7-147">**그룹 정책을 사용하여 재부팅 알림을 숨길 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="d88f7-147">**Use Group Policy to hide reboot notifications:**</span></span>

1. <span data-ttu-id="d88f7-148">그룹 정책 관리 컴퓨터에서 그룹 [](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))정책 관리 콘솔을 열고 구성할 그룹 정책 개체를 마우스 오른쪽 단추로 클릭하고 편집을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d88f7-148">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="d88f7-149">그룹 정책 **관리 편집기에서** 컴퓨터 **구성으로 이동하십시오.**</span><span class="sxs-lookup"><span data-stu-id="d88f7-149">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="d88f7-150">관리 **템플릿 을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d88f7-150">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="d88f7-151">Microsoft Defender 바이러스 백신 및 클라이언트 > Windows 구성 **> 확장합니다.**</span><span class="sxs-lookup"><span data-stu-id="d88f7-151">Expand the tree to **Windows components > Microsoft Defender Antivirus > Client interface**.</span></span>

5. <span data-ttu-id="d88f7-152">다시 시작 알림 표시 안 를 두 번 **클릭하고** 옵션을 사용으로 **설정합니다.**</span><span class="sxs-lookup"><span data-stu-id="d88f7-152">Double-click **Suppresses reboot notifications** and set the option to **Enabled**.</span></span> <span data-ttu-id="d88f7-153">**확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d88f7-153">Click **OK**.</span></span> <span data-ttu-id="d88f7-154">이렇게 하면 추가 알림이 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d88f7-154">This will prevent additional notifications from appearing.</span></span>

## <a name="related-topics"></a><span data-ttu-id="d88f7-155">관련 항목</span><span class="sxs-lookup"><span data-stu-id="d88f7-155">Related topics</span></span>

- [<span data-ttu-id="d88f7-156">Windows 10의 Microsoft Defender 바이러스 백신</span><span class="sxs-lookup"><span data-stu-id="d88f7-156">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="d88f7-157">Microsoft Defender 바이러스 백신과 최종 사용자 상호 작용 구성</span><span class="sxs-lookup"><span data-stu-id="d88f7-157">Configure end-user interaction with Microsoft Defender Antivirus</span></span>](configure-end-user-interaction-microsoft-defender-antivirus.md)