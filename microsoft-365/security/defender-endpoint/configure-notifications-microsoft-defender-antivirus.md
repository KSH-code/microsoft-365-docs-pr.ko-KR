---
title: Microsoft Defender 바이러스 백신 알림 구성
description: 엔드포인트에서 표준 및 추가 Microsoft Defender 바이러스 백신 알림을 모두 구성하고 사용자 지정하는 방법을 알아봅니다.
keywords: 알림, 수비수, 바이러스 백신, 끝점, 관리, 관리자
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 05/17/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: f885b6d7991e4175cd14be5bbe9e0a7c96b1580f
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572348"
---
# <a name="configure-the-notifications-that-appear-on-endpoints"></a><span data-ttu-id="d2d22-104">끝점에 나타나는 알림 구성</span><span class="sxs-lookup"><span data-stu-id="d2d22-104">Configure the notifications that appear on endpoints</span></span>

<span data-ttu-id="d2d22-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="d2d22-105">**Applies to:**</span></span>

- [<span data-ttu-id="d2d22-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="d2d22-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="d2d22-107">Windows 10 맬웨어 탐지 및 수정에 대한 응용 프로그램 알림은 보다 강력하고 일관되며 간결합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d22-107">In Windows 10, application notifications about malware detection and remediation are more robust, consistent, and concise.</span></span>

<span data-ttu-id="d2d22-108">수동으로 트리거되고 예약된 검사가 완료되고 위협이 감지되면 끝점에 알림이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2d22-108">Notifications appear on endpoints when manually triggered and scheduled scans are completed and threats are detected.</span></span> <span data-ttu-id="d2d22-109">이러한 알림은 **알림 센터에도** 표시되며 검사 및 위협 탐지 요약은 정기적인 시간 간격으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2d22-109">These notifications also appear in the **Notification Center**, and a summary of scans and threat detections appear at regular time intervals.</span></span>

<span data-ttu-id="d2d22-110">재부팅 알림 또는 위협이 검색되고 수정된 시기와 같이 끝점에 표준 알림이 표시되는 방식을 구성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d22-110">You can also configure how standard notifications appear on endpoints, such as notifications for reboot or when a threat has been detected and remediated.</span></span>

## <a name="configure-the-additional-notifications-that-appear-on-endpoints"></a><span data-ttu-id="d2d22-111">끝점에 나타나는 추가 알림 구성</span><span class="sxs-lookup"><span data-stu-id="d2d22-111">Configure the additional notifications that appear on endpoints</span></span>

<span data-ttu-id="d2d22-112">최근 위협 탐지 요약, [Windows 보안 앱](microsoft-defender-security-center-antivirus.md) 및 그룹 정책과 같은 추가 알림 표시를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d22-112">You can configure the display of additional notifications, such as recent threat detection summaries, in the [Windows Security app](microsoft-defender-security-center-antivirus.md) and with Group Policy.</span></span>

> [!NOTE]
> <span data-ttu-id="d2d22-113">Windows 10 버전 1607에서 기능은 **향상된 알림이라고** 불렸으며 **보안** Windows Defender Windows 설정 업데이트 & 아래에서 구성할 수  >    >  **있습니다.**</span><span class="sxs-lookup"><span data-stu-id="d2d22-113">In Windows 10, version 1607 the feature was called **Enhanced notifications** and could be configured under **Windows Settings** > **Update & security** > **Windows Defender**.</span></span> <span data-ttu-id="d2d22-114">Windows 10 모든 버전의 그룹 정책 설정에서 **향상된 알림이라고** 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d22-114">In Group Policy settings in all versions of Windows 10, it is called **Enhanced notifications**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d2d22-115">추가 알림을 사용하지 않도록 설정하면 위협 탐지 및 수정 경고와 같은 중요한 알림이 비활성화되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d22-115">Disabling additional notifications will not disable critical notifications, such as threat detection and remediation alerts.</span></span>

<span data-ttu-id="d2d22-116">**Windows 보안 앱을 사용하여 추가 알림을 사용하지 않도록 설정합니다.**</span><span class="sxs-lookup"><span data-stu-id="d2d22-116">**Use the Windows Security app to disable additional notifications:**</span></span>

1. <span data-ttu-id="d2d22-117">작업 표시줄의 쉴드 아이콘을 클릭하거나 보안에 대한 시작 메뉴를 검색하여 Windows 보안 앱을 **엽니다.**</span><span class="sxs-lookup"><span data-stu-id="d2d22-117">Open the Windows Security app by clicking the shield icon in the task bar or searching the start menu for **Security**.</span></span>

2. <span data-ttu-id="d2d22-118">**바이러스 & 위협 보호** 타일(또는 왼쪽 메뉴 표시줄의 쉴드 아이콘)을 선택한 다음 위협 보호 설정을 & 바이러스를 선택합니다. </span><span class="sxs-lookup"><span data-stu-id="d2d22-118">Select **Virus & threat protection** tile (or the shield icon on the left menu bar) and, then select **Virus & threat protection settings**</span></span>

3. <span data-ttu-id="d2d22-119">**알림** 섹션으로 스크롤하여 **알림 설정 변경을** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d22-119">Scroll to the **Notifications** section and click **Change notification settings**.</span></span>

4. <span data-ttu-id="d2d22-120">스위치를 **끄거나** **켜기로** 밀어 내거나 추가 알림을 비활성화하거나 활성화합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d22-120">Slide the switch to **Off** or **On** to disable or enable additional notifications.</span></span>

<span data-ttu-id="d2d22-121">**그룹 정책을 사용하여 추가 알림을 사용하지 않도록 설정합니다.**</span><span class="sxs-lookup"><span data-stu-id="d2d22-121">**Use Group Policy to disable additional notifications:**</span></span>

1. <span data-ttu-id="d2d22-122">그룹 정책 관리 컴퓨터에서 [그룹 정책 관리 콘솔을](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))열고 구성하려는 그룹 정책 개체를 마우스 오른쪽 단추로 클릭하고 **편집을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d2d22-122">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="d2d22-123">그룹 **정책 관리 편집기에서** **컴퓨터 구성으로** 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d22-123">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="d2d22-124">**관리 템플릿을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d2d22-124">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="d2d22-125">트리를 확장하여 **> Microsoft Defender 바이러스 백신 > 구성 요소를 Windows 보고할 > Microsoft Defender 바이러스 백신 >** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d22-125">Expand the tree to **Windows components > Microsoft Defender Antivirus > Reporting**.</span></span>

5. <span data-ttu-id="d2d22-126">향상된 알림을 두 번 **클릭하고** 활성화할 수 있는 옵션을 **설정합니다.**</span><span class="sxs-lookup"><span data-stu-id="d2d22-126">Double-click **Turn off enhanced notifications** and set the option to **Enabled**.</span></span> <span data-ttu-id="d2d22-127">**확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d22-127">Click **OK**.</span></span> <span data-ttu-id="d2d22-128">이렇게 하면 추가 알림이 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d22-128">This will prevent additional notifications from appearing.</span></span>

## <a name="configure-standard-notifications-on-endpoints"></a><span data-ttu-id="d2d22-129">끝점에 표준 알림 구성</span><span class="sxs-lookup"><span data-stu-id="d2d22-129">Configure standard notifications on endpoints</span></span>

<span data-ttu-id="d2d22-130">그룹 정책을 사용하여 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d22-130">You can use Group Policy to:</span></span>

- <span data-ttu-id="d2d22-131">사용자가 작업을 수행해야 할 때 끝점에 사용자 지정 된 추가 텍스트 표시</span><span class="sxs-lookup"><span data-stu-id="d2d22-131">Display additional, customized text on endpoints when the user needs to perform an action</span></span>
- <span data-ttu-id="d2d22-132">끝점에 모든 알림 숨기기</span><span class="sxs-lookup"><span data-stu-id="d2d22-132">Hide all notifications on endpoints</span></span>
- <span data-ttu-id="d2d22-133">끝점에 재부팅 알림 숨기기</span><span class="sxs-lookup"><span data-stu-id="d2d22-133">Hide reboot notifications on endpoints</span></span>

<span data-ttu-id="d2d22-134">알림을 숨기는 것은 전체 Microsoft Defender 바이러스 백신 인터페이스를 숨길 수 없는 경우에 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d22-134">Hiding notifications can be useful in situations where you can't hide the entire Microsoft Defender Antivirus interface.</span></span> <span data-ttu-id="d2d22-135">자세한 내용은 [사용자가 Microsoft Defender 바이러스 백신 사용자 인터페이스를 보거나 상호 작용하지 못하도록 하십시오.](prevent-end-user-interaction-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="d2d22-135">See [Prevent users from seeing or interacting with the Microsoft Defender Antivirus user interface](prevent-end-user-interaction-microsoft-defender-antivirus.md) for more information.</span></span> 

> [!NOTE]
> <span data-ttu-id="d2d22-136">숨기기 알림은 정책이 배포된 끝점에서만 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d22-136">Hiding notifications will only occur on endpoints to which the policy has been deployed.</span></span> <span data-ttu-id="d2d22-137">수행해야 하는 작업(예: 재부팅)과 관련된 알림은 [대시보드 및 보고서에 Microsoft Endpoint Manager Endpoint Protection 모니터링됩니다.](/configmgr/protect/deploy-use/monitor-endpoint-protection)</span><span class="sxs-lookup"><span data-stu-id="d2d22-137">Notifications related to actions that must be taken (such as a reboot) will still appear on the [Microsoft Endpoint Manager Endpoint Protection monitoring dashboard and reports](/configmgr/protect/deploy-use/monitor-endpoint-protection).</span></span> 

<span data-ttu-id="d2d22-138">사용자가 컴퓨터에 표시되는 알림에 사용자 지정 연락처 정보를 추가하는 지침은 [조직에 대한 Windows 보안 앱 사용자 지정을](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d2d22-138">See [Customize the Windows Security app for your organization](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) for instructions to add custom contact information to the notifications that users see on their machines.</span></span>

<span data-ttu-id="d2d22-139">**그룹 정책을 사용하여 알림을 숨깁니다.**</span><span class="sxs-lookup"><span data-stu-id="d2d22-139">**Use Group Policy to hide notifications:**</span></span>

1. <span data-ttu-id="d2d22-140">그룹 정책 관리 컴퓨터에서 [그룹 정책 관리 콘솔을](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))열고 구성할 그룹 정책 개체를 마우스 오른쪽 단추로 클릭하고 **편집을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d2d22-140">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure, and click **Edit**.</span></span>

2. <span data-ttu-id="d2d22-141">그룹 **정책 관리 편집기에서** **컴퓨터 구성으로** 이동하여 **관리 템플릿을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d2d22-141">In the **Group Policy Management Editor** go to **Computer configuration** and click **Administrative templates**.</span></span>

3. <span data-ttu-id="d2d22-142">**클라이언트 인터페이스에 > Microsoft Defender 바이러스 백신 > 구성 요소Windows** 로트리를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d22-142">Expand the tree to **Windows components > Microsoft Defender Antivirus > Client interface**.</span></span> 

4. <span data-ttu-id="d2d22-143">두 번 **클릭하면 모든 알림 억제** 및 활성화 옵션을 **설정합니다.**</span><span class="sxs-lookup"><span data-stu-id="d2d22-143">Double-click **Suppress all notifications** and set the option to **Enabled**.</span></span> <span data-ttu-id="d2d22-144">**확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d22-144">Click **OK**.</span></span> <span data-ttu-id="d2d22-145">이렇게 하면 추가 알림이 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d22-145">This will prevent additional notifications from appearing.</span></span>

<span data-ttu-id="d2d22-146">**그룹 정책을 사용하여 재부팅 알림을 숨깁니다.**</span><span class="sxs-lookup"><span data-stu-id="d2d22-146">**Use Group Policy to hide reboot notifications:**</span></span>

1. <span data-ttu-id="d2d22-147">그룹 정책 관리 컴퓨터에서 [그룹 정책 관리 콘솔을](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))열고 구성하려는 그룹 정책 개체를 마우스 오른쪽 단추로 클릭하고 **편집을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d2d22-147">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="d2d22-148">그룹 **정책 관리 편집기에서** **컴퓨터 구성으로** 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d22-148">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="d2d22-149">**관리 템플릿을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d2d22-149">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="d2d22-150">**클라이언트 인터페이스에 > Microsoft Defender 바이러스 백신 > 구성 요소Windows** 로트리를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d22-150">Expand the tree to **Windows components > Microsoft Defender Antivirus > Client interface**.</span></span>

5. <span data-ttu-id="d2d22-151">두 번 **클릭으로 알림을 재부팅하지 않으며** **활성화옵션을 설정합니다.**</span><span class="sxs-lookup"><span data-stu-id="d2d22-151">Double-click **Suppresses reboot notifications** and set the option to **Enabled**.</span></span> <span data-ttu-id="d2d22-152">**확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d22-152">Click **OK**.</span></span> <span data-ttu-id="d2d22-153">이렇게 하면 추가 알림이 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d22-153">This will prevent additional notifications from appearing.</span></span>

## <a name="related-topics"></a><span data-ttu-id="d2d22-154">관련 항목</span><span class="sxs-lookup"><span data-stu-id="d2d22-154">Related topics</span></span>

- [<span data-ttu-id="d2d22-155">Windows 10의 Microsoft Defender 바이러스 백신</span><span class="sxs-lookup"><span data-stu-id="d2d22-155">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="d2d22-156">Microsoft Defender 바이러스 백신 최종 사용자 상호 작용 구성</span><span class="sxs-lookup"><span data-stu-id="d2d22-156">Configure end-user interaction with Microsoft Defender Antivirus</span></span>](configure-end-user-interaction-microsoft-defender-antivirus.md)
