---
title: 최신 끝점에 Microsoft Defender AV 보호 업데이트 적용
description: 한 동안 업데이트되지 않은 끝점에 대해 업데이트를 적용하는 경우와 방법을 정의합니다.
keywords: 업데이트, 보호, 오래된, 오래된, 오래된, catch-up
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
ms.openlocfilehash: 4199f55488ef0dc5989af88e8be83a3d51190d1f
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275063"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-scans-for-endpoints-that-are-out-of-date"></a><span data-ttu-id="7484b-104">Microsoft Defender 바이러스 백신 업데이트 및 만료된 엔드포인트에 대한 검사 관리</span><span class="sxs-lookup"><span data-stu-id="7484b-104">Manage Microsoft Defender Antivirus updates and scans for endpoints that are out of date</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="7484b-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="7484b-105">**Applies to:**</span></span>

- [<span data-ttu-id="7484b-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="7484b-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="7484b-107">Microsoft Defender 바이러스 백신 끝점에서 업데이트를 피할 수 있는 기간 또는 끝점에서 누락할 수 있는 검색 수를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7484b-107">Microsoft Defender Antivirus lets you define how long an endpoint can avoid an update or how many scans it can miss before it is required to update and scan itself.</span></span> <span data-ttu-id="7484b-108">이 기능은 장치가 회사 또는 외부 네트워크에 자주 연결되지 않는 환경이나 매일 사용되지 않는 장치에서 특히 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="7484b-108">This is especially useful in environments where devices are not often connected to a corporate or external network, or devices that are not used on a daily basis.</span></span>

<span data-ttu-id="7484b-109">예를 들어 특정 PC를 사용하는 직원은 3일 동안 중단을 시하며 해당 시간 동안 PC에 로그온하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7484b-109">For example, an employee that uses a particular PC is on break for three days and does not log on to their PC during that time.</span></span>

<span data-ttu-id="7484b-110">사용자가 직장으로 돌아와 PC에 로그온하면 Microsoft Defender 바이러스 백신 즉시 최신 보호 업데이트를 확인하고 다운로드하고 검사를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="7484b-110">When the user returns to work and logs on to their PC, Microsoft Defender Antivirus will immediately check and download the latest protection updates, and run a scan.</span></span>

## <a name="set-up-catch-up-protection-updates-for-endpoints-that-havent-updated-for-a-while"></a><span data-ttu-id="7484b-111">한 동안 업데이트되지 않은 끝점에 대한 추가 보호 업데이트 설정</span><span class="sxs-lookup"><span data-stu-id="7484b-111">Set up catch-up protection updates for endpoints that haven't updated for a while</span></span>

<span data-ttu-id="7484b-112">지정된 Microsoft Defender 바이러스 백신 동안 보호 업데이트를 다운로드하지 않은 경우 다음 로그온 시 최신 업데이트를 자동으로 확인하고 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7484b-112">If Microsoft Defender Antivirus did not download protection updates for a specified period, you can set it up to automatically check and download the latest update at the next log on.</span></span> <span data-ttu-id="7484b-113">이 기능은 시작 시 자동 업데이트 다운로드를 전역적으로 사용하지 않도록 [설정한 경우 유용합니다.](manage-event-based-updates-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="7484b-113">This is useful if you have [globally disabled automatic update downloads on startup](manage-event-based-updates-microsoft-defender-antivirus.md).</span></span>

### <a name="use-configuration-manager-to-configure-catch-up-protection-updates"></a><span data-ttu-id="7484b-114">Configuration Manager를 사용하여 추가 보호 업데이트 구성</span><span class="sxs-lookup"><span data-stu-id="7484b-114">Use Configuration Manager to configure catch-up protection updates</span></span>

1.  <span data-ttu-id="7484b-115">Microsoft Endpoint Manager 콘솔에서 변경할 맬웨어 방지 정책을 열고(왼쪽의 탐색 창에서 자산 및 규정 준수를 클릭한 다음 개요 Endpoint Protection 맬웨어 방지 정책)   >    >  </span><span class="sxs-lookup"><span data-stu-id="7484b-115">On your Microsoft Endpoint Manager console, open the antimalware policy you want to change (click **Assets and Compliance** in the navigation pane on the left, then expand the tree to **Overview** > **Endpoint Protection** > **Antimalware Policies**)</span></span>

2.  <span data-ttu-id="7484b-116">보안 **인텔리전스 업데이트 섹션으로 이동하여** 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="7484b-116">Go to the **Security intelligence updates** section and configure the following settings:</span></span>

    1. <span data-ttu-id="7484b-117">클라이언트 **컴퓨터가** 두 개 이상의 연속으로 예약된 업데이트에 대해 오프라인 상태일 경우 보안 인텔리전스 업데이트 강제 적용을 **예로 설정하세요.**</span><span class="sxs-lookup"><span data-stu-id="7484b-117">Set **Force a security intelligence update if the client computer is offline for more than two consecutive scheduled updates** to **Yes**.</span></span>
    2. <span data-ttu-id="7484b-118">Configuration  **Manager를** 보안 인텔리전스 업데이트의 원본으로 사용하는 경우... 의 경우 Configuration Manager에서 제공한 보호 업데이트를 최신 시간으로 간주할 시간을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7484b-118">For the  **If Configuration Manager is used as a source for security intelligence updates...**, specify the hours before which the protection updates delivered by Configuration Manager should be considered out-of-date.</span></span> <span data-ttu-id="7484b-119">이렇게 하면 정의된 폴백 원본 순서에 따라 다음 업데이트 [위치가 사용됩니다.](manage-protection-updates-microsoft-defender-antivirus.md#fallback-order)</span><span class="sxs-lookup"><span data-stu-id="7484b-119">This will cause the next update location to be used, based on the defined [fallback source order](manage-protection-updates-microsoft-defender-antivirus.md#fallback-order).</span></span>

3. <span data-ttu-id="7484b-120">**확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7484b-120">Click **OK**.</span></span>

4.  <span data-ttu-id="7484b-121">[평소와 같이 업데이트된 정책을 배포합니다.](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers)</span><span class="sxs-lookup"><span data-stu-id="7484b-121">[Deploy the updated policy as usual](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers).</span></span>

### <a name="use-group-policy-to-enable-and-configure-the-catch-up-update-feature"></a><span data-ttu-id="7484b-122">그룹 정책을 사용하여 추가 업데이트 기능을 사용하도록 설정 및 구성</span><span class="sxs-lookup"><span data-stu-id="7484b-122">Use Group Policy to enable and configure the catch-up update feature</span></span>

1. <span data-ttu-id="7484b-123">그룹 정책 관리 컴퓨터에서 그룹 [](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))정책 관리 콘솔을 열고 구성할 그룹 정책 개체를 마우스 오른쪽 단추로 클릭하고 편집을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="7484b-123">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="7484b-124">그룹 정책 **관리 편집기에서** 컴퓨터 **구성으로 이동하십시오.**</span><span class="sxs-lookup"><span data-stu-id="7484b-124">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="7484b-125">정책을 **클릭한** 다음 **관리 템플릿을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="7484b-125">Click **Policies** then **Administrative templates**.</span></span>

4. <span data-ttu-id="7484b-126">트리를 확장하여 **서명 Windows 구성 > Microsoft Defender 바이러스 백신 > 확장합니다.**</span><span class="sxs-lookup"><span data-stu-id="7484b-126">Expand the tree to **Windows components > Microsoft Defender Antivirus > Signature Updates**.</span></span>

5. <span data-ttu-id="7484b-127">추가 보안  인텔리전스 업데이트가 필요한 날짜까지의 일 수 정의 설정을 두 번 클릭하고 옵션을 사용으로 **설정합니다.**</span><span class="sxs-lookup"><span data-stu-id="7484b-127">Double-click the **Define the number of days after which a catch-up security intelligence update is required** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="7484b-128">Microsoft Defender AV에서 최신 보호 업데이트를 확인하고 다운로드할 일 수를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="7484b-128">Enter the number of days after which you want Microsoft Defender AV to check for and download the latest protection update.</span></span>

6. <span data-ttu-id="7484b-129">**확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7484b-129">Click **OK**.</span></span>

### <a name="use-powershell-cmdlets-to-configure-catch-up-protection-updates"></a><span data-ttu-id="7484b-130">PowerShell cmdlet을 사용하여 추가 보호 업데이트 구성</span><span class="sxs-lookup"><span data-stu-id="7484b-130">Use PowerShell cmdlets to configure catch-up protection updates</span></span>

<span data-ttu-id="7484b-131">다음 cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7484b-131">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -SignatureUpdateCatchupInterval
```

<span data-ttu-id="7484b-132">PowerShell과 함께 PowerShell을 사용하는 방법에 대한 자세한 내용은 [PowerShell cmdlet을](use-powershell-cmdlets-microsoft-defender-antivirus.md) 사용하여 Microsoft Defender 바이러스 백신 및 [Defender cmdlet을](/powershell/module/defender/) 구성하고 실행을 Microsoft Defender 바이러스 백신.</span><span class="sxs-lookup"><span data-stu-id="7484b-132">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md)  and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi-to-configure-catch-up-protection-updates"></a><span data-ttu-id="7484b-133">WMI(Windows Management Instruction)를 사용하여 추가 보호 업데이트 구성</span><span class="sxs-lookup"><span data-stu-id="7484b-133">Use Windows Management Instruction (WMI) to configure catch-up protection updates</span></span>

<span data-ttu-id="7484b-134">다음 [  속성에 MSFT_MpPreference  ](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) 클래스의 Set 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7484b-134">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
SignatureUpdateCatchupInterval
```

<span data-ttu-id="7484b-135">자세한 정보 및 허용되는 매개 변수는 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7484b-135">See the following for more information and allowed parameters:</span></span>
- [<span data-ttu-id="7484b-136">Windows Defender WMIv2 API</span><span class="sxs-lookup"><span data-stu-id="7484b-136">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


## <a name="set-the-number-of-days-before-protection-is-reported-as-out-of-date"></a><span data-ttu-id="7484b-137">보호가 기한이 지난 것으로 보고되기 전까지의 일 수 설정</span><span class="sxs-lookup"><span data-stu-id="7484b-137">Set the number of days before protection is reported as out-of-date</span></span>

<span data-ttu-id="7484b-138">또한 이전 또는 오래된 보호로 간주되는 Microsoft Defender 바이러스 백신 일 수를 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7484b-138">You can also specify the number of days after which Microsoft Defender Antivirus protection is considered old or out-of-date.</span></span> <span data-ttu-id="7484b-139">지정된 일 수가 지난 후 클라이언트는 자체적으로 기한이 지난 것으로 보고하고 PC 사용자에게 오류를 보여 주게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7484b-139">After the specified number of days, the client will report itself as out-of-date, and show an error to the user of the PC.</span></span> <span data-ttu-id="7484b-140">또한 WSUS Microsoft Defender 바이러스 백신 Microsoft Update를 첫 번째 원본으로 설정한 [](manage-protection-updates-microsoft-defender-antivirus.md#fallback-order)후 MMPC를 보조 원본으로 사용하는 경우와 같이 정의된 폴백 원본 순서에 따라 다른 원본에서 업데이트를 다운로드하려고 시도할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7484b-140">It may also cause Microsoft Defender Antivirus to attempt to download an update from other sources (based on the defined [fallback source order](manage-protection-updates-microsoft-defender-antivirus.md#fallback-order)), such as when using MMPC as a secondary source after setting WSUS or Microsoft Update as the first source.</span></span>

### <a name="use-group-policy-to-specify-the-number-of-days-before-protection-is-considered-out-of-date"></a><span data-ttu-id="7484b-141">그룹 정책을 사용하여 보호가 기한이 지난 것으로 간주될 날짜 수 지정</span><span class="sxs-lookup"><span data-stu-id="7484b-141">Use Group Policy to specify the number of days before protection is considered out-of-date</span></span>

1.  <span data-ttu-id="7484b-142">그룹 정책 관리 컴퓨터의 [](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))그룹 정책 관리 콘솔을 열고 구성할 그룹 정책 개체를 마우스 오른쪽 단추로 클릭하고 편집을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="7484b-142">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

3.  <span data-ttu-id="7484b-143">그룹 정책 **관리 편집기에서** 컴퓨터 **구성으로 이동하십시오.**</span><span class="sxs-lookup"><span data-stu-id="7484b-143">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

4.  <span data-ttu-id="7484b-144">정책을 **클릭한** 다음 **관리 템플릿을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="7484b-144">Click **Policies** then **Administrative templates**.</span></span>

5.  <span data-ttu-id="7484b-145">트리를 확장하여 서명 Windows 구성 > Microsoft Defender 바이러스 백신 > 구성 **요소를 확장하고** 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="7484b-145">Expand the tree to **Windows components > Microsoft Defender Antivirus > Signature Updates** and configure the following settings:</span></span>

    1.  <span data-ttu-id="7484b-146">스파이웨어  정의가 기한이 지난 것으로 간주될 날짜까지의 기간(일) 정의를 두 번 클릭하고 옵션을 사용으로 **설정합니다.**</span><span class="sxs-lookup"><span data-stu-id="7484b-146">Double-click **Define the number of days before spyware definitions are considered out of date** and set the option to **Enabled**.</span></span> <span data-ttu-id="7484b-147">Microsoft Defender AV에서 스파이웨어 보안 인텔리전스가 최신이 아 없다고 고려할 날짜 수를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="7484b-147">Enter the number of days after which you want Microsoft Defender AV to consider spyware Security intelligence to be out-of-date.</span></span>

    2. <span data-ttu-id="7484b-148">**확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7484b-148">Click **OK**.</span></span>

    3.  <span data-ttu-id="7484b-149">바이러스 정의가 기한이 지난 것으로 간주될 날짜까지의 기간(일) 정의를 두 번 클릭하고 옵션을 사용으로 **설정합니다.** </span><span class="sxs-lookup"><span data-stu-id="7484b-149">Double-click **Define the number of days before virus definitions are considered out of date** and set the option to **Enabled**.</span></span> <span data-ttu-id="7484b-150">Microsoft Defender AV에서 바이러스 보안 인텔리전스가 최신이 아 없다고 고려할 날짜 수를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="7484b-150">Enter the number of days after which you want Microsoft Defender AV to consider virus Security intelligence to be out-of-date.</span></span>

    4. <span data-ttu-id="7484b-151">**확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7484b-151">Click **OK**.</span></span>


## <a name="set-up-catch-up-scans-for-endpoints-that-have-not-been-scanned-for-a-while"></a><span data-ttu-id="7484b-152">한 동안 검색되지 않은 끝점에 대한 업데이트 검사 설정</span><span class="sxs-lookup"><span data-stu-id="7484b-152">Set up catch-up scans for endpoints that have not been scanned for a while</span></span>

<span data-ttu-id="7484b-153">검색을 강제 실행하기 전에 누락될 수 있는 연속 예약된 Microsoft Defender 바이러스 백신 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7484b-153">You can set the number of consecutive scheduled scans that can be missed before Microsoft Defender Antivirus will force a scan.</span></span>

<span data-ttu-id="7484b-154">이 기능을 사용하도록 설정하는 프로세스는 다음입니다.</span><span class="sxs-lookup"><span data-stu-id="7484b-154">The process for enabling this feature is:</span></span>

1. <span data-ttu-id="7484b-155">하나 이상의 예약된 검색을 설치합니다(예약 [검사 항목 참조).](scheduled-catch-up-scans-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="7484b-155">Set up at least one scheduled scan (see the [Schedule scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md) topic).</span></span>
2. <span data-ttu-id="7484b-156">추가 검사 기능을 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7484b-156">Enable the catch-up scan feature.</span></span>
3. <span data-ttu-id="7484b-157">최대 검색이 발생하기 전에 건너뛴 검사 수를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="7484b-157">Define the number of scans that can be skipped before a catch-up scan occurs.</span></span>

<span data-ttu-id="7484b-158">이 기능은 전체 검사와 빠른 검사에 모두 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7484b-158">This feature can be enabled for both full and quick scans.</span></span>

### <a name="use-group-policy-to-enable-and-configure-the-catch-up-scan-feature"></a><span data-ttu-id="7484b-159">그룹 정책을 사용하여 추가 검사 기능 사용 및 구성</span><span class="sxs-lookup"><span data-stu-id="7484b-159">Use Group Policy to enable and configure the catch-up scan feature</span></span>

1.  <span data-ttu-id="7484b-160">예약된 검색을 하나 이상 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7484b-160">Ensure you have set up at least one scheduled scan.</span></span>

2.  <span data-ttu-id="7484b-161">그룹 정책 관리 컴퓨터의 [](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))그룹 정책 관리 콘솔을 열고 구성할 그룹 정책 개체를 마우스 오른쪽 단추로 클릭하고 편집을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="7484b-161">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

3.  <span data-ttu-id="7484b-162">그룹 정책 **관리 편집기에서** 컴퓨터 **구성으로 이동하십시오.**</span><span class="sxs-lookup"><span data-stu-id="7484b-162">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

4.  <span data-ttu-id="7484b-163">정책을 **클릭한** 다음 **관리 템플릿을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="7484b-163">Click **Policies** then **Administrative templates**.</span></span>

5.  <span data-ttu-id="7484b-164">트리를 **확장하여** Windows 구성 > Microsoft Defender 바이러스 백신 > 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="7484b-164">Expand the tree to **Windows components > Microsoft Defender Antivirus > Scan** and configure the following settings:</span></span>

    1.  <span data-ttu-id="7484b-165">예약된 빠른 검색을 설정한 경우 빠른  검색 켜기 설정을 두 번 클릭하고 옵션을 사용으로 **설정합니다.**</span><span class="sxs-lookup"><span data-stu-id="7484b-165">If you have set up scheduled quick scans, double-click the **Turn on catch-up quick scan** setting and set the option to **Enabled**.</span></span> 
    2. <span data-ttu-id="7484b-166">예약된 전체 검색을 설정한 경우 전체  검사 켜기 설정을 두 번 클릭하고 옵션을 사용으로 **설정합니다.**</span><span class="sxs-lookup"><span data-stu-id="7484b-166">If you have set up scheduled full scans, double-click the **Turn on catch-up full scan** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="7484b-167">**확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7484b-167">Click **OK**.</span></span>
    3. <span data-ttu-id="7484b-168">추가 검사가  강제로 실행되는 일 수 정의 설정을 두 번 클릭하고 옵션을 사용으로 **설정합니다.**</span><span class="sxs-lookup"><span data-stu-id="7484b-168">Double-click the **Define the number of days after which a catch-up scan is forced** setting and set the option to **Enabled**.</span></span> 
    4. <span data-ttu-id="7484b-169">다음에 사용자가 PC에 로그온할 때 검사가 자동으로 실행되기 전에 누락될 수 있는 검사 수를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="7484b-169">Enter the number of scans that can be missed before a scan will be automatically run when the user next logs on to the PC.</span></span> <span data-ttu-id="7484b-170">실행되는 검사 유형은 예약된  검사에 사용할 검사 유형 지정(Schedule [scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md) 항목 참조)에 따라 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="7484b-170">The type of scan that is run is determined by the **Specify the scan type to use for a scheduled scan** (see the [Schedule scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md) topic).</span></span> <span data-ttu-id="7484b-171">**확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7484b-171">Click **OK**.</span></span>

> [!NOTE]
> <span data-ttu-id="7484b-172">그룹 정책 설정 제목은 일 수를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="7484b-172">The Group Policy setting title refers to the number of days.</span></span> <span data-ttu-id="7484b-173">그러나 이 설정은 최대 검색을 실행하기 전에 검사 횟수(일 수 아)에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7484b-173">The setting, however, is applied to the number of scans (not days) before the catch-up scan will be run.</span></span>

### <a name="use-powershell-cmdlets-to-configure-catch-up-scans"></a><span data-ttu-id="7484b-174">PowerShell cmdlet을 사용하여 최대 검색 구성</span><span class="sxs-lookup"><span data-stu-id="7484b-174">Use PowerShell cmdlets to configure catch-up scans</span></span>

<span data-ttu-id="7484b-175">다음 cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7484b-175">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -DisableCatchupFullScan
Set-MpPreference -DisableCatchupQuickScan

```

<span data-ttu-id="7484b-176">PowerShell과 함께 PowerShell을 사용하는 방법에 대한 자세한 내용은 [PowerShell cmdlet을](use-powershell-cmdlets-microsoft-defender-antivirus.md) 사용하여 Microsoft Defender 바이러스 백신 및 [Defender cmdlet을](/powershell/module/defender/) Microsoft Defender 바이러스 백신.</span><span class="sxs-lookup"><span data-stu-id="7484b-176">See [Use PowerShell cmdlets to manage Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md)  and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi-to-configure-catch-up-scans"></a><span data-ttu-id="7484b-177">WMI(Windows 관리 명령)를 사용하여 최대 검색 구성</span><span class="sxs-lookup"><span data-stu-id="7484b-177">Use Windows Management Instruction (WMI) to configure catch-up scans</span></span>

<span data-ttu-id="7484b-178">다음 [  속성에 MSFT_MpPreference  ](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) 클래스의 Set 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7484b-178">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
DisableCatchupFullScan
DisableCatchupQuickScan
```

<span data-ttu-id="7484b-179">자세한 정보 및 허용되는 매개 변수는 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7484b-179">See the following for more information and allowed parameters:</span></span>
- [<span data-ttu-id="7484b-180">Windows Defender WMIv2 API</span><span class="sxs-lookup"><span data-stu-id="7484b-180">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


### <a name="use-configuration-manager-to-configure-catch-up-scans"></a><span data-ttu-id="7484b-181">Configuration Manager를 사용하여 추가 검사 구성</span><span class="sxs-lookup"><span data-stu-id="7484b-181">Use Configuration Manager to configure catch-up scans</span></span>

1.  <span data-ttu-id="7484b-182">Microsoft Endpoint Manager 콘솔에서 변경할 맬웨어 방지 정책을 열고(왼쪽의 탐색 창에서 자산 및 규정 준수를 클릭한 다음 개요 Endpoint Protection 맬웨어 방지 정책)   >    >  </span><span class="sxs-lookup"><span data-stu-id="7484b-182">On your Microsoft Endpoint Manager console, open the antimalware policy you want to change (click **Assets and Compliance** in the navigation pane on the left, then expand the tree to **Overview** > **Endpoint Protection** > **Antimalware Policies**)</span></span>

2.  <span data-ttu-id="7484b-183">예약된 검사 **섹션으로 이동하고** 클라이언트 컴퓨터가 오프라인 상태인 경우 선택한 검사 유형을 강제로 **검사...를** **예로 합니다.**</span><span class="sxs-lookup"><span data-stu-id="7484b-183">Go to the **Scheduled scans** section and **Force a scan of the selected scan type if client computer is offline...** to **Yes**.</span></span> 

3. <span data-ttu-id="7484b-184">**확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7484b-184">Click **OK**.</span></span>

4.  <span data-ttu-id="7484b-185">[평소와 같이 업데이트된 정책을 배포합니다.](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers)</span><span class="sxs-lookup"><span data-stu-id="7484b-185">[Deploy the updated policy as usual](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers).</span></span>

## <a name="related-articles"></a><span data-ttu-id="7484b-186">관련 문서</span><span class="sxs-lookup"><span data-stu-id="7484b-186">Related articles</span></span>

- [<span data-ttu-id="7484b-187">배포 Microsoft Defender 바이러스 백신</span><span class="sxs-lookup"><span data-stu-id="7484b-187">Deploy Microsoft Defender Antivirus</span></span>](deploy-manage-report-microsoft-defender-antivirus.md)
- [<span data-ttu-id="7484b-188">업데이트 Microsoft Defender 바이러스 백신 관리하고 기준 적용</span><span class="sxs-lookup"><span data-stu-id="7484b-188">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>](manage-updates-baselines-microsoft-defender-antivirus.md)
- [<span data-ttu-id="7484b-189">보호 업데이트를 다운로드하고 적용해야 하는 경우 관리</span><span class="sxs-lookup"><span data-stu-id="7484b-189">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md)
- [<span data-ttu-id="7484b-190">이벤트 기반 강제 업데이트 관리</span><span class="sxs-lookup"><span data-stu-id="7484b-190">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md)
- [<span data-ttu-id="7484b-191">모바일 장치 및 VM(가상 머신)에 대한 업데이트 관리</span><span class="sxs-lookup"><span data-stu-id="7484b-191">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [<span data-ttu-id="7484b-192">Windows 10의 Microsoft Defender 바이러스 백신</span><span class="sxs-lookup"><span data-stu-id="7484b-192">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)