---
title: 알림 Microsoft Defender 바이러스 백신 구성
description: 끝점에서 표준 및 추가 Microsoft Defender 바이러스 백신 알림을 구성하고 사용자 지정하는 방법을 학습합니다.
keywords: 알림, defender, 바이러스 백신, 끝점, 관리, 관리자
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 6e11c9394f250a6f3882183224f53954b1390a23
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274631"
---
# <a name="configure-the-notifications-that-appear-on-endpoints"></a><span data-ttu-id="8fd07-104">끝점에 나타나는 알림 구성</span><span class="sxs-lookup"><span data-stu-id="8fd07-104">Configure the notifications that appear on endpoints</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="8fd07-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="8fd07-105">**Applies to:**</span></span>

- [<span data-ttu-id="8fd07-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="8fd07-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="8fd07-107">이러한 Windows 10 맬웨어 검색 및 수정에 대한 응용 프로그램 알림은 더욱 강력하고 일관되고, 일관성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8fd07-107">In Windows 10, application notifications about malware detection and remediation are more robust, consistent, and concise.</span></span>

<span data-ttu-id="8fd07-108">수동으로 트리거되고 예약된 검사가 완료되고 위협이 감지되면 알림이 끝점에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8fd07-108">Notifications appear on endpoints when manually triggered and scheduled scans are completed and threats are detected.</span></span> <span data-ttu-id="8fd07-109">이러한 알림은 알림 센터에도 **표시될** 수 있으며, 검사 및 위협 검색 요약은 정기적인 간격으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8fd07-109">These notifications also appear in the **Notification Center**, and a summary of scans and threat detections appear at regular time intervals.</span></span>

<span data-ttu-id="8fd07-110">다시 시작 알림이나 위협이 감지되고 수정된 경우와 같이 끝점에 표준 알림이 나타나는 방법을 구성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8fd07-110">You can also configure how standard notifications appear on endpoints, such as notifications for reboot or when a threat has been detected and remediated.</span></span>

## <a name="configure-the-additional-notifications-that-appear-on-endpoints"></a><span data-ttu-id="8fd07-111">끝점에 나타나는 추가 알림 구성</span><span class="sxs-lookup"><span data-stu-id="8fd07-111">Configure the additional notifications that appear on endpoints</span></span>

<span data-ttu-id="8fd07-112">최신 위협 감지 요약과 같은 추가 알림 표시를 Windows 보안 [그룹](microsoft-defender-security-center-antivirus.md) 정책을 사용하여 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8fd07-112">You can configure the display of additional notifications, such as recent threat detection summaries, in the [Windows Security app](microsoft-defender-security-center-antivirus.md) and with Group Policy.</span></span>

> [!NOTE]
> <span data-ttu-id="8fd07-113">Windows 10 버전 1607에서는 이 기능을 고급  알림이라고 하여 Windows 설정 업데이트 &  >  **보안**  >  Windows Defender.</span><span class="sxs-lookup"><span data-stu-id="8fd07-113">In Windows 10, version 1607 the feature was called **Enhanced notifications** and could be configured under **Windows Settings** > **Update & security** > **Windows Defender**.</span></span> <span data-ttu-id="8fd07-114">모든 버전의 그룹 정책 설정에서 Windows 10 라고 **합니다.**</span><span class="sxs-lookup"><span data-stu-id="8fd07-114">In Group Policy settings in all versions of Windows 10, it is called **Enhanced notifications**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8fd07-115">추가 알림을 사용하지 않도록 설정하면 위협 감지 및 수정 경고와 같은 중요한 알림이 비활성화되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8fd07-115">Disabling additional notifications will not disable critical notifications, such as threat detection and remediation alerts.</span></span>

<span data-ttu-id="8fd07-116">**앱 Windows 보안 사용하여 추가 알림을 사용하지 않도록 설정할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="8fd07-116">**Use the Windows Security app to disable additional notifications:**</span></span>

1. <span data-ttu-id="8fd07-117">작업 표시줄에서 방패 아이콘을 클릭하거나 **Defender의** 시작 메뉴를 검색하여 Windows 보안 앱을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8fd07-117">Open the Windows Security app by clicking the shield icon in the task bar or searching the start menu for **Defender**.</span></span>

2. <span data-ttu-id="8fd07-118">바이러스 & **위협** 방지 타일(또는 왼쪽 메뉴 표시줄의 방패 **아이콘)을** 클릭한 다음 바이러스 & 보호 설정 레이블을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8fd07-118">Click the **Virus & threat protection** tile (or the shield icon on the left menu bar) and then the **Virus & threat protection settings** label:</span></span>

    ![& 앱의 바이러스 & 보호 설정 레이블의 Windows 보안 스크린샷](images/defender/wdav-protection-settings-wdsc.png)

3. <span data-ttu-id="8fd07-120">알림 **섹션으로 스크롤하고** 알림 설정 **변경을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="8fd07-120">Scroll to the **Notifications** section and click **Change notification settings**.</span></span>

4. <span data-ttu-id="8fd07-121">스위치를 **끄기** 또는 **켜기로 밀어** 추가 알림을 사용하지 않도록 설정하거나 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8fd07-121">Slide the switch to **Off** or **On** to disable or enable additional notifications.</span></span>

<span data-ttu-id="8fd07-122">**그룹 정책을 사용하여 추가 알림을 사용하지 않도록 설정:**</span><span class="sxs-lookup"><span data-stu-id="8fd07-122">**Use Group Policy to disable additional notifications:**</span></span>

1. <span data-ttu-id="8fd07-123">그룹 정책 관리 컴퓨터에서 그룹 [](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))정책 관리 콘솔을 열고 구성할 그룹 정책 개체를 마우스 오른쪽 단추로 클릭하고 편집을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="8fd07-123">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="8fd07-124">그룹 정책 **관리 편집기에서** 컴퓨터 **구성으로 이동하십시오.**</span><span class="sxs-lookup"><span data-stu-id="8fd07-124">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="8fd07-125">관리 **템플릿 을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="8fd07-125">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="8fd07-126">보고 에 **Windows 구성 > Microsoft Defender 바이러스 백신 > 확장합니다.**</span><span class="sxs-lookup"><span data-stu-id="8fd07-126">Expand the tree to **Windows components > Microsoft Defender Antivirus > Reporting**.</span></span>

5. <span data-ttu-id="8fd07-127">향상된 알림 **끄기** 를 두 번 클릭하고 옵션을 사용으로 **설정합니다.**</span><span class="sxs-lookup"><span data-stu-id="8fd07-127">Double-click **Turn off enhanced notifications** and set the option to **Enabled**.</span></span> <span data-ttu-id="8fd07-128">**확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8fd07-128">Click **OK**.</span></span> <span data-ttu-id="8fd07-129">이렇게 하면 추가 알림이 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8fd07-129">This will prevent additional notifications from appearing.</span></span>

## <a name="configure-standard-notifications-on-endpoints"></a><span data-ttu-id="8fd07-130">끝점에서 표준 알림 구성</span><span class="sxs-lookup"><span data-stu-id="8fd07-130">Configure standard notifications on endpoints</span></span>

<span data-ttu-id="8fd07-131">그룹 정책을 사용하여 다음을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8fd07-131">You can use Group Policy to:</span></span>

- <span data-ttu-id="8fd07-132">사용자가 작업을 수행해야 하는 경우 끝점에 추가 사용자 지정 텍스트 표시</span><span class="sxs-lookup"><span data-stu-id="8fd07-132">Display additional, customized text on endpoints when the user needs to perform an action</span></span>
- <span data-ttu-id="8fd07-133">끝점에서 모든 알림 숨기기</span><span class="sxs-lookup"><span data-stu-id="8fd07-133">Hide all notifications on endpoints</span></span>
- <span data-ttu-id="8fd07-134">끝점에서 다시 시작 알림 숨기기</span><span class="sxs-lookup"><span data-stu-id="8fd07-134">Hide reboot notifications on endpoints</span></span>

<span data-ttu-id="8fd07-135">알림 숨기기는 전체 알림 인터페이스를 숨길 수 없는 Microsoft Defender 바이러스 백신 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8fd07-135">Hiding notifications can be useful in situations where you can't hide the entire Microsoft Defender Antivirus interface.</span></span> <span data-ttu-id="8fd07-136">자세한 내용은 사용자가 사용자 인터페이스를 [보거나](prevent-end-user-interaction-microsoft-defender-antivirus.md) 상호 작용하지 못하도록 Microsoft Defender 바이러스 백신 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8fd07-136">See [Prevent users from seeing or interacting with the Microsoft Defender Antivirus user interface](prevent-end-user-interaction-microsoft-defender-antivirus.md) for more information.</span></span> 

> [!NOTE]
> <span data-ttu-id="8fd07-137">알림 숨기기는 정책이 배포된 끝점에서만 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="8fd07-137">Hiding notifications will only occur on endpoints to which the policy has been deployed.</span></span> <span data-ttu-id="8fd07-138">재부팅과 같이 취해야 하는 작업과 관련된 알림은 모니터링 대시보드 및 보고서의 Microsoft Endpoint Manager Endpoint Protection [표시됩니다.](/configmgr/protect/deploy-use/monitor-endpoint-protection)</span><span class="sxs-lookup"><span data-stu-id="8fd07-138">Notifications related to actions that must be taken (such as a reboot) will still appear on the [Microsoft Endpoint Manager Endpoint Protection monitoring dashboard and reports](/configmgr/protect/deploy-use/monitor-endpoint-protection).</span></span> 

<span data-ttu-id="8fd07-139">사용자가 [자신의 Windows 보안](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) 알림에 사용자 지정 연락처 정보를 추가하는 방법에 대한 지침은 조직용 Windows 보안 앱 사용자 지정을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8fd07-139">See [Customize the Windows Security app for your organization](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) for instructions to add custom contact information to the notifications that users see on their machines.</span></span>

<span data-ttu-id="8fd07-140">**그룹 정책을 사용하여 알림을 숨길 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="8fd07-140">**Use Group Policy to hide notifications:**</span></span>

1. <span data-ttu-id="8fd07-141">그룹 정책 관리 컴퓨터에서 그룹 [](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))정책 관리 콘솔을 열고 구성할 그룹 정책 개체를 마우스 오른쪽 단추로 클릭하고 편집을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="8fd07-141">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure, and click **Edit**.</span></span>

2. <span data-ttu-id="8fd07-142">그룹 정책 **관리 편집기에서** 컴퓨터 **구성으로 이동하여** 관리 템플릿 **을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="8fd07-142">In the **Group Policy Management Editor** go to **Computer configuration** and click **Administrative templates**.</span></span>

3. <span data-ttu-id="8fd07-143">클라이언트 인터페이스에서 **구성 Windows 트리를 > Microsoft Defender 바이러스 백신 > 확장합니다.**</span><span class="sxs-lookup"><span data-stu-id="8fd07-143">Expand the tree to **Windows components > Microsoft Defender Antivirus > Client interface**.</span></span> 

4. <span data-ttu-id="8fd07-144">모든 알림 표시 **안 를 두 번 클릭하고** 옵션을 사용으로 **설정합니다.**</span><span class="sxs-lookup"><span data-stu-id="8fd07-144">Double-click **Suppress all notifications** and set the option to **Enabled**.</span></span> <span data-ttu-id="8fd07-145">**확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8fd07-145">Click **OK**.</span></span> <span data-ttu-id="8fd07-146">이렇게 하면 추가 알림이 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8fd07-146">This will prevent additional notifications from appearing.</span></span>

<span data-ttu-id="8fd07-147">**그룹 정책을 사용하여 재부팅 알림을 숨길 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="8fd07-147">**Use Group Policy to hide reboot notifications:**</span></span>

1. <span data-ttu-id="8fd07-148">그룹 정책 관리 컴퓨터에서 그룹 [](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))정책 관리 콘솔을 열고 구성할 그룹 정책 개체를 마우스 오른쪽 단추로 클릭하고 편집을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="8fd07-148">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="8fd07-149">그룹 정책 **관리 편집기에서** 컴퓨터 **구성으로 이동하십시오.**</span><span class="sxs-lookup"><span data-stu-id="8fd07-149">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="8fd07-150">관리 **템플릿 을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="8fd07-150">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="8fd07-151">클라이언트 인터페이스에서 **구성 Windows 트리를 > Microsoft Defender 바이러스 백신 > 확장합니다.**</span><span class="sxs-lookup"><span data-stu-id="8fd07-151">Expand the tree to **Windows components > Microsoft Defender Antivirus > Client interface**.</span></span>

5. <span data-ttu-id="8fd07-152">다시 시작 알림 표시 안 를 두 번 **클릭하고** 옵션을 사용으로 **설정합니다.**</span><span class="sxs-lookup"><span data-stu-id="8fd07-152">Double-click **Suppresses reboot notifications** and set the option to **Enabled**.</span></span> <span data-ttu-id="8fd07-153">**확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8fd07-153">Click **OK**.</span></span> <span data-ttu-id="8fd07-154">이렇게 하면 추가 알림이 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8fd07-154">This will prevent additional notifications from appearing.</span></span>

## <a name="related-topics"></a><span data-ttu-id="8fd07-155">관련 항목</span><span class="sxs-lookup"><span data-stu-id="8fd07-155">Related topics</span></span>

- [<span data-ttu-id="8fd07-156">Microsoft Defender 바이러스 백신 Windows 10</span><span class="sxs-lookup"><span data-stu-id="8fd07-156">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="8fd07-157">사용자와의 최종 사용자 상호 작용 Microsoft Defender 바이러스 백신</span><span class="sxs-lookup"><span data-stu-id="8fd07-157">Configure end-user interaction with Microsoft Defender Antivirus</span></span>](configure-end-user-interaction-microsoft-defender-antivirus.md)