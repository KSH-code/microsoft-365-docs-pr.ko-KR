---
title: 알림 Microsoft Defender 바이러스 백신 구성
description: 끝점에서 표준 및 기타 Microsoft Defender 바이러스 백신 알림을 구성하고 사용자 지정하는 방법을 학습합니다.
keywords: 알림, defender, 바이러스 백신, 끝점, 관리, 관리자
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.topic: article
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/16/2021
ms.reviewer: ''
manager: dansimp
ms.openlocfilehash: a7a838bb15cd011b750fbfa3d6df100ddf9f713c
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985411"
---
# <a name="configure-microsoft-defender-antivirus-notifications-that-appear-on-endpoints"></a><span data-ttu-id="54f01-104">끝점에 Microsoft Defender 바이러스 백신 알림 구성</span><span class="sxs-lookup"><span data-stu-id="54f01-104">Configure Microsoft Defender Antivirus notifications that appear on endpoints</span></span>

<span data-ttu-id="54f01-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="54f01-105">**Applies to:**</span></span>

- [<span data-ttu-id="54f01-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="54f01-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="54f01-107">이러한 Windows 10 맬웨어 검색 및 수정에 대한 응용 프로그램 알림은 더욱 강력하고 일관되고, 일관성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54f01-107">In Windows 10, application notifications about malware detection and remediation are more robust, consistent, and concise.</span></span> <span data-ttu-id="54f01-108">Microsoft Defender 바이러스 백신 검사가 완료되고 위협이 감지되면 끝점에 알림이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="54f01-108">Microsoft Defender Antivirus notifications appear on endpoints when scans are completed and threats are detected.</span></span> <span data-ttu-id="54f01-109">알림은 예약된 검사와 수동 트리거된 검사 모두를 따르게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="54f01-109">Notifications follow both scheduled and manually triggered scans.</span></span> <span data-ttu-id="54f01-110">이러한 알림은 알림 센터에도 **표시될** 수 있으며, 검사 및 위협 검색 요약은 정기적인 간격으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="54f01-110">These notifications also appear in the **Notification Center**, and a summary of scans and threat detections appear at regular time intervals.</span></span>

<span data-ttu-id="54f01-111">조직의 보안 팀에 속하는 경우 시스템 재부팅을 요청하는 알림이나 위협이 감지되고 수정된 것을 나타내는 알림과 같이 끝점에 알림이 나타나는 방법을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54f01-111">If you're part of your organization's security team, you can configure how notifications appear on endpoints, such as notifications that prompt for a system reboot or that indicate a threat has been detected and remediated.</span></span>

## <a name="configure-antivirus-notifications-using-group-policy-or-the-windows-security-app"></a><span data-ttu-id="54f01-112">그룹 정책 또는 앱 앱을 사용하여 바이러스 Windows 보안 구성</span><span class="sxs-lookup"><span data-stu-id="54f01-112">Configure antivirus notifications using Group Policy or the Windows Security app</span></span>

<span data-ttu-id="54f01-113">최신 위협 감지 요약과 같은 추가 알림 표시를 Windows 보안 [그룹](microsoft-defender-security-center-antivirus.md) 정책을 사용하여 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54f01-113">You can configure the display of additional notifications, such as recent threat detection summaries, in the [Windows Security app](microsoft-defender-security-center-antivirus.md) and with Group Policy.</span></span>

> [!NOTE]
> <span data-ttu-id="54f01-114">Windows 10 버전 1607에서는 이 기능을 고급  알림이라고 하여 Windows 설정 업데이트 &  >  **보안**  >  Windows Defender.</span><span class="sxs-lookup"><span data-stu-id="54f01-114">In Windows 10, version 1607 the feature was called **Enhanced notifications** and was configured under **Windows Settings** > **Update & security** > **Windows Defender**.</span></span> <span data-ttu-id="54f01-115">모든 버전의 사용자에 대한 그룹 정책 설정에서 Windows 10 기능을 **고급 알림이라고 합니다.**</span><span class="sxs-lookup"><span data-stu-id="54f01-115">In Group Policy settings for all versions of Windows 10, the notification feature is called **Enhanced notifications**.</span></span>

### <a name="use-group-policy-to-disable-additional-notifications"></a><span data-ttu-id="54f01-116">그룹 정책을 사용하여 추가 알림을 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="54f01-116">Use Group Policy to disable additional notifications</span></span>

1. <span data-ttu-id="54f01-117">그룹 정책 관리 컴퓨터에서 [그룹 정책 관리 콘솔](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="54f01-117">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span></span>

2. <span data-ttu-id="54f01-118">구성할 그룹 정책 개체를 마우스 오른쪽 단추로 클릭한 다음 편집 **을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="54f01-118">Right-click the Group Policy Object you want to configure, and then select **Edit**.</span></span>

3. <span data-ttu-id="54f01-119">그룹 정책 **관리 편집기에서** 컴퓨터 **구성으로 이동하십시오.**</span><span class="sxs-lookup"><span data-stu-id="54f01-119">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

4. <span data-ttu-id="54f01-120">관리 **템플릿 을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="54f01-120">Select **Administrative templates**.</span></span>

5. <span data-ttu-id="54f01-121">**보고**에서 Windows 구성\*\*  >  **Microsoft Defender 바이러스 백신** > 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="54f01-121">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > Reporting\*\*.</span></span>

6. <span data-ttu-id="54f01-122">향상된 알림 **끄기** 를 두 번 클릭하고 옵션을 사용으로 **설정합니다.**</span><span class="sxs-lookup"><span data-stu-id="54f01-122">Double-click **Turn off enhanced notifications**, and set the option to **Enabled**.</span></span> <span data-ttu-id="54f01-123">그런 다음 **확인** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="54f01-123">Then select **OK**.</span></span> <span data-ttu-id="54f01-124">이렇게 하면 추가 알림이 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="54f01-124">This will prevent additional notifications from appearing.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="54f01-125">추가 알림을 사용하지 않도록 설정하면 위협 감지 및 수정 경고와 같은 중요한 알림이 비활성화되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="54f01-125">Disabling additional notifications will not disable critical notifications, such as threat detection and remediation alerts.</span></span>

### <a name="use-the-windows-security-app-to-disable-additional-notifications"></a><span data-ttu-id="54f01-126">앱 Windows 보안 사용하여 추가 알림을 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="54f01-126">Use the Windows Security app to disable additional notifications</span></span>

1. <span data-ttu-id="54f01-127">작업 Windows 보안 방패 아이콘을 클릭하거나 보안에 대한 시작 메뉴를 검색하여 앱 앱을 열 **수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="54f01-127">Open the Windows Security app by clicking the shield icon in the task bar or searching the start menu for **Security**.</span></span>

2. <span data-ttu-id="54f01-128">바이러스 **& 보호** 타일(또는 왼쪽 메뉴 표시줄의 방패 아이콘)을 선택한 다음 바이러스 & 보호 설정을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="54f01-128">Select **Virus & threat protection** tile (or the shield icon on the left menu bar) and, then select **Virus & threat protection settings**</span></span>

3. <span data-ttu-id="54f01-129">알림 **섹션으로 스크롤하고** 알림 설정 **변경을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="54f01-129">Scroll to the **Notifications** section and select **Change notification settings**.</span></span>

4. <span data-ttu-id="54f01-130">스위치를 **끄기** 또는 **켜기로 밀어** 추가 알림을 사용하지 않도록 설정하거나 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54f01-130">Slide the switch to **Off** or **On** to disable or enable additional notifications.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="54f01-131">추가 알림을 사용하지 않도록 설정하면 위협 감지 및 수정 경고와 같은 중요한 알림이 비활성화되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="54f01-131">Disabling additional notifications will not disable critical notifications, such as threat detection and remediation alerts.</span></span>

## <a name="configure-standard-notifications-on-endpoints-using-group-policy"></a><span data-ttu-id="54f01-132">그룹 정책을 사용하여 끝점에서 표준 알림 구성</span><span class="sxs-lookup"><span data-stu-id="54f01-132">Configure standard notifications on endpoints using Group Policy</span></span>

<span data-ttu-id="54f01-133">그룹 정책을 사용하여 다음을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54f01-133">You can use Group Policy to:</span></span>

- <span data-ttu-id="54f01-134">사용자가 작업을 수행해야 하는 경우 끝점에 추가 사용자 지정 텍스트 표시</span><span class="sxs-lookup"><span data-stu-id="54f01-134">Display additional, customized text on endpoints when the user needs to perform an action</span></span>
- <span data-ttu-id="54f01-135">끝점에서 모든 알림 숨기기</span><span class="sxs-lookup"><span data-stu-id="54f01-135">Hide all notifications on endpoints</span></span>
- <span data-ttu-id="54f01-136">끝점에서 다시 시작 알림 숨기기</span><span class="sxs-lookup"><span data-stu-id="54f01-136">Hide reboot notifications on endpoints</span></span>

<span data-ttu-id="54f01-137">알림 숨기기는 전체 알림 인터페이스를 숨길 수 없는 Microsoft Defender 바이러스 백신 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54f01-137">Hiding notifications can be useful in situations where you can't hide the entire Microsoft Defender Antivirus interface.</span></span> <span data-ttu-id="54f01-138">자세한 내용은 사용자가 사용자 인터페이스를 [보거나](prevent-end-user-interaction-microsoft-defender-antivirus.md) 상호 작용하지 못하도록 Microsoft Defender 바이러스 백신 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="54f01-138">See [Prevent users from seeing or interacting with the Microsoft Defender Antivirus user interface](prevent-end-user-interaction-microsoft-defender-antivirus.md) for more information.</span></span> <span data-ttu-id="54f01-139">알림 숨기기는 정책이 배포된 끝점에서만 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="54f01-139">Hiding notifications will only occur on endpoints to which the policy has been deployed.</span></span> <span data-ttu-id="54f01-140">재부팅과 같이 취해야 하는 작업과 관련된 알림은 모니터링 대시보드 및 보고서의 Microsoft Endpoint Manager Endpoint Protection [표시됩니다.](/configmgr/protect/deploy-use/monitor-endpoint-protection)</span><span class="sxs-lookup"><span data-stu-id="54f01-140">Notifications related to actions that must be taken (such as a reboot) will still appear on the [Microsoft Endpoint Manager Endpoint Protection monitoring dashboard and reports](/configmgr/protect/deploy-use/monitor-endpoint-protection).</span></span> 

<span data-ttu-id="54f01-141">끝점 알림에 사용자 지정 연락처 정보를 추가하기 위해 조직에 대한 Windows 보안 [사용자 지정을 참조하세요.](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center)</span><span class="sxs-lookup"><span data-stu-id="54f01-141">To add custom contact information to endpoint notifications, see [Customize the Windows Security app for your organization](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center).</span></span>

### <a name="use-group-policy-to-hide-notifications"></a><span data-ttu-id="54f01-142">그룹 정책을 사용하여 알림 숨기기</span><span class="sxs-lookup"><span data-stu-id="54f01-142">Use Group Policy to hide notifications</span></span>

1. <span data-ttu-id="54f01-143">그룹 정책 관리 컴퓨터에서 [그룹 정책 관리 콘솔](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="54f01-143">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span></span>

2. <span data-ttu-id="54f01-144">구성할 그룹 정책 개체를 마우스 오른쪽 단추로 클릭한 다음 편집 **을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="54f01-144">Right-click the Group Policy Object you want to configure, and then select **Edit**.</span></span>

3. <span data-ttu-id="54f01-145">그룹 정책 **관리 편집기에서** 컴퓨터 **구성으로 이동한** 다음 관리 템플릿 **을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="54f01-145">In the **Group Policy Management Editor** go to **Computer configuration** and then select **Administrative templates**.</span></span>

4. <span data-ttu-id="54f01-146">클라이언트 인터페이스에서 **구성 Windows**  >  **트리를 Microsoft Defender 바이러스 백신**  >  **확장합니다.**</span><span class="sxs-lookup"><span data-stu-id="54f01-146">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Client interface**.</span></span> 

5. <span data-ttu-id="54f01-147">모든 알림 표시 **안 를 두 번 클릭하고** 옵션을 사용으로 **설정합니다.**</span><span class="sxs-lookup"><span data-stu-id="54f01-147">Double-click **Suppress all notifications** and set the option to **Enabled**.</span></span> 

6. <span data-ttu-id="54f01-148">**확인** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="54f01-148">Select **OK**.</span></span> <span data-ttu-id="54f01-149">이렇게 하면 추가 알림이 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="54f01-149">This will prevent additional notifications from appearing.</span></span>

### <a name="use-group-policy-to-hide-reboot-notifications"></a><span data-ttu-id="54f01-150">그룹 정책을 사용하여 재부팅 알림 숨기기</span><span class="sxs-lookup"><span data-stu-id="54f01-150">Use Group Policy to hide reboot notifications</span></span>

1. <span data-ttu-id="54f01-151">그룹 정책 관리 컴퓨터에서 [그룹 정책 관리 콘솔](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="54f01-151">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span></span>

2. <span data-ttu-id="54f01-152">구성할 그룹 정책 개체를 마우스 오른쪽 단추로 클릭한 다음 편집 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="54f01-152">Right-click the Group Policy Object you want to configure and then select **Edit**.</span></span>

2. <span data-ttu-id="54f01-153">그룹 정책 **관리 편집기에서** 컴퓨터 **구성으로 이동하십시오.**</span><span class="sxs-lookup"><span data-stu-id="54f01-153">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="54f01-154">관리 **템플릿 을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="54f01-154">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="54f01-155">클라이언트 인터페이스에서 **구성 Windows**  >  **트리를 Microsoft Defender 바이러스 백신**  >  **확장합니다.**</span><span class="sxs-lookup"><span data-stu-id="54f01-155">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Client interface**.</span></span>

5. <span data-ttu-id="54f01-156">다시 시작 알림 표시 안 를 두 번 **클릭하고** 옵션을 사용으로 **설정합니다.**</span><span class="sxs-lookup"><span data-stu-id="54f01-156">Double-click **Suppresses reboot notifications** and set the option to **Enabled**.</span></span> 

5. <span data-ttu-id="54f01-157">**확인** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="54f01-157">Select **OK**.</span></span> <span data-ttu-id="54f01-158">이렇게 하면 추가 알림이 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="54f01-158">This will prevent additional notifications from appearing.</span></span>

