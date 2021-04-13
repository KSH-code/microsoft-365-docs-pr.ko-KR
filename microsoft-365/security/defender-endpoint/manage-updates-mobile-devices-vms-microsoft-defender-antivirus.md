---
title: Microsoft Defender 바이러스 백신에서 모바일 장치를 업데이트하는 방법 정의
description: 랩톱과 같은 모바일 장치를 Microsoft Defender 바이러스 백신 보호 업데이트로 업데이트하는 방법을 관리합니다.
keywords: 업데이트, 보호, 업데이트 예약, 배터리, 모바일 장치, 노트북, 노트북, 옵트인, Microsoft 업데이트, wsus, override
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: f67330e1ccd7361c3982b76a6ab8754db23bd110
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690983"
---
# <a name="manage-updates-for-mobile-devices-and-virtual-machines-vms"></a><span data-ttu-id="9b5ae-104">모바일 장치 및 VM(가상 컴퓨터)에 대한 업데이트 관리</span><span class="sxs-lookup"><span data-stu-id="9b5ae-104">Manage updates for mobile devices and virtual machines (VMs)</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="9b5ae-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="9b5ae-105">**Applies to:**</span></span>

- <span data-ttu-id="9b5ae-106">[엔드포인트용 Microsoft Defender](/microsoft-365/security/defender-endpoint/) </span><span class="sxs-lookup"><span data-stu-id="9b5ae-106">[Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)</span></span>

<span data-ttu-id="9b5ae-107">모바일 장치 및 VM의 경우 업데이트로 성능에 영향을 끼치지 않도록 더 많은 구성이 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b5ae-107">Mobile devices and VMs may require more configuration to ensure performance is not impacted by updates.</span></span>

<span data-ttu-id="9b5ae-108">이러한 장치에 유용한 두 가지 설정이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b5ae-108">There are two settings that are useful for these devices:</span></span>

- <span data-ttu-id="9b5ae-109">WSUS 연결 없이 모바일 컴퓨터에서 Microsoft 업데이트에 옵트인</span><span class="sxs-lookup"><span data-stu-id="9b5ae-109">Opt in to Microsoft Update on mobile computers without a WSUS connection</span></span>
- <span data-ttu-id="9b5ae-110">배터리 전원으로 실행 시 보안 인텔리전스 업데이트 방지</span><span class="sxs-lookup"><span data-stu-id="9b5ae-110">Prevent Security intelligence updates when running on battery power</span></span>

<span data-ttu-id="9b5ae-111">다음 문서도 이러한 상황에서 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b5ae-111">The following articles may also be useful in these situations:</span></span>
- [<span data-ttu-id="9b5ae-112">예약된 검사 및 최대 검색 구성</span><span class="sxs-lookup"><span data-stu-id="9b5ae-112">Configuring scheduled and catch-up scans</span></span>](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [<span data-ttu-id="9b5ae-113">최신이 지난 끝점에 대한 업데이트 관리</span><span class="sxs-lookup"><span data-stu-id="9b5ae-113">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [<span data-ttu-id="9b5ae-114">VDI(가상 데스크톱 인프라) 환경의 Microsoft Defender 바이러스 백신 배포 가이드</span><span class="sxs-lookup"><span data-stu-id="9b5ae-114">Deployment guide for Microsoft Defender Antivirus in a virtual desktop infrastructure (VDI) environment</span></span>](deployment-vdi-microsoft-defender-antivirus.md)

## <a name="opt-in-to-microsoft-update-on-mobile-computers-without-a-wsus-connection"></a><span data-ttu-id="9b5ae-115">WSUS 연결 없이 모바일 컴퓨터에서 Microsoft 업데이트에 옵트인</span><span class="sxs-lookup"><span data-stu-id="9b5ae-115">Opt in to Microsoft Update on mobile computers without a WSUS connection</span></span>

<span data-ttu-id="9b5ae-116">Microsoft 업데이트를 사용하여 회사 네트워크에 연결되지 않은 경우 또는 WSUS 연결이 없는 경우 Microsoft Defender 바이러스 백신을 실행하는 모바일 장치에서 보안 인텔리전스를 최신 상태로 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b5ae-116">You can use Microsoft Update to keep Security intelligence on mobile devices running Microsoft Defender Antivirus up to date when they are not connected to the corporate network or don't otherwise have a WSUS connection.</span></span> 

<span data-ttu-id="9b5ae-117">즉, Microsoft 업데이트를 다시 적용하기 위해 WSUS를 설정한 경우에도 Microsoft 업데이트를 통해 보호 업데이트를 장치로 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b5ae-117">This means that protection updates can be delivered to devices (via Microsoft Update) even if you have set WSUS to override Microsoft Update.</span></span>

<span data-ttu-id="9b5ae-118">다음 방법 중 하나를 사용하여 모바일 장치에서 Microsoft 업데이트에 옵트인(opt in)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b5ae-118">You can opt in to Microsoft Update on the mobile device in one of the following ways:</span></span>

- <span data-ttu-id="9b5ae-119">그룹 정책을 사용하여 설정을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="9b5ae-119">Change the setting with Group Policy.</span></span>
- <span data-ttu-id="9b5ae-120">VBScript를 사용하여 스크립트를 만든 다음 네트워크의 각 컴퓨터에서 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="9b5ae-120">Use a VBScript to create a script, then run it on each computer in your network.</span></span>
- <span data-ttu-id="9b5ae-121">설정 메뉴를 통해 네트워크의 모든 컴퓨터를 수동으로 **옵트인합니다.**</span><span class="sxs-lookup"><span data-stu-id="9b5ae-121">Manually opt in every computer on your network through the **Settings** menu.</span></span>

### <a name="use-group-policy-to-opt-in-to-microsoft-update"></a><span data-ttu-id="9b5ae-122">그룹 정책을 사용하여 Microsoft 업데이트에 옵트인</span><span class="sxs-lookup"><span data-stu-id="9b5ae-122">Use Group Policy to opt in to Microsoft Update</span></span>

1. <span data-ttu-id="9b5ae-123">그룹 정책 관리 컴퓨터의 [](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))그룹 정책 관리 콘솔을 열고 구성할 그룹 정책 개체를 마우스 오른쪽 단추로 클릭하고 편집 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="9b5ae-123">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="9b5ae-124">그룹 정책 **관리 편집기에서** 컴퓨터 **구성으로 이동하십시오.**</span><span class="sxs-lookup"><span data-stu-id="9b5ae-124">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="9b5ae-125">정책을 **선택한** 다음 **관리 템플릿을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="9b5ae-125">Select **Policies** then **Administrative templates**.</span></span>

4. <span data-ttu-id="9b5ae-126">Windows 구성 요소 **Microsoft** Defender 바이러스 백신 서명  >  **업데이트까지**  >  **트리를 확장합니다.**</span><span class="sxs-lookup"><span data-stu-id="9b5ae-126">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Signature Updates**.</span></span>

5. <span data-ttu-id="9b5ae-127">Microsoft 업데이트의 보안 **인텔리전스** 업데이트 허용을 **사용으로** 설정하고 확인 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="9b5ae-127">Set **Allow security intelligence updates from Microsoft Update** to **Enabled**, and then select  **OK**.</span></span>


### <a name="use-a-vbscript-to-opt-in-to-microsoft-update"></a><span data-ttu-id="9b5ae-128">VBScript를 사용하여 Microsoft 업데이트에 옵트인</span><span class="sxs-lookup"><span data-stu-id="9b5ae-128">Use a VBScript to opt in to Microsoft Update</span></span>

1. <span data-ttu-id="9b5ae-129">MSDN 문서 [Microsoft 업데이트에 옵트인(Opt-In)의](/windows/win32/wua_sdk/opt-in-to-microsoft-update) 지침을 사용하여 VBScript를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b5ae-129">Use the instructions in the MSDN article [Opt-In to Microsoft Update](/windows/win32/wua_sdk/opt-in-to-microsoft-update) to create the VBScript.</span></span>

2. <span data-ttu-id="9b5ae-130">네트워크의 각 컴퓨터에서 만든 VBScript를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="9b5ae-130">Run the VBScript you created on each computer in your network.</span></span>

### <a name="manually-opt-in-to-microsoft-update"></a><span data-ttu-id="9b5ae-131">Microsoft 업데이트에 수동으로 옵트인</span><span class="sxs-lookup"><span data-stu-id="9b5ae-131">Manually opt in to Microsoft Update</span></span>

1. <span data-ttu-id="9b5ae-132">옵트인하려는 & 보안 설정 업데이트에서 **Windows** 업데이트를 하세요. </span><span class="sxs-lookup"><span data-stu-id="9b5ae-132">Open **Windows Update** in **Update & security** settings on the computer you want to opt in.</span></span>

2. <span data-ttu-id="9b5ae-133">고급 **옵션을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9b5ae-133">Select **Advanced** options.</span></span>

3. <span data-ttu-id="9b5ae-134">Windows를 업데이트할 때 다른 Microsoft 제품에 대한 업데이트 **제공 확인란을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="9b5ae-134">Select the checkbox for **Give me updates for other Microsoft products when I update Windows**.</span></span>

## <a name="prevent-security-intelligence-updates-when-running-on-battery-power"></a><span data-ttu-id="9b5ae-135">배터리 전원으로 실행 시 보안 인텔리전스 업데이트 방지</span><span class="sxs-lookup"><span data-stu-id="9b5ae-135">Prevent Security intelligence updates when running on battery power</span></span>

<span data-ttu-id="9b5ae-136">PC가 유선 전원에 연결되어 있는 경우 보호 업데이트만 다운로드하도록 Microsoft Defender 바이러스 백신을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b5ae-136">You can configure Microsoft Defender Antivirus to only download protection updates when the PC is connected to a wired power source.</span></span> 

### <a name="use-group-policy-to-prevent-security-intelligence-updates-on-battery-power"></a><span data-ttu-id="9b5ae-137">그룹 정책을 사용하여 배터리 전원의 보안 인텔리전스 업데이트 방지</span><span class="sxs-lookup"><span data-stu-id="9b5ae-137">Use Group Policy to prevent security intelligence updates on battery power</span></span>

1.  <span data-ttu-id="9b5ae-138">그룹 정책 관리 컴퓨터의 그룹 정책 관리 콘솔을 [열고](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))구성할 그룹 정책 개체를 선택한 다음 편집할 수 있도록 를 니다.</span><span class="sxs-lookup"><span data-stu-id="9b5ae-138">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), choose the Group Policy Object you want to configure, and open it for editing.</span></span>

2.  <span data-ttu-id="9b5ae-139">그룹 정책 **관리 편집기에서** 컴퓨터 **구성으로 이동하십시오.**</span><span class="sxs-lookup"><span data-stu-id="9b5ae-139">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3.  <span data-ttu-id="9b5ae-140">정책을 **선택한** 다음 **관리 템플릿을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="9b5ae-140">Select **Policies** then **Administrative templates**.</span></span>

4.  <span data-ttu-id="9b5ae-141">**Windows** 구성 요소 Microsoft Defender 바이러스 백신 서명 업데이트까지 트리를 확장한 다음 배터리 전원으로 실행 중일 때 보안 인텔리전스 업데이트 허용을  >    >  사용 **안 하도록 설정 합니다.** </span><span class="sxs-lookup"><span data-stu-id="9b5ae-141">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Signature Updates**, and then set **Allow security intelligence updates when running on battery power** to **Disabled**.</span></span> <span data-ttu-id="9b5ae-142">그런 다음 **확인** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9b5ae-142">Then select **OK**.</span></span> 

<span data-ttu-id="9b5ae-143">이 작업을 수행하면 PC가 배터리 전원에 있는 경우 보호 업데이트가 다운로드되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9b5ae-143">This action prevents protection updates from downloading when the PC is on battery power.</span></span>

## <a name="related-articles"></a><span data-ttu-id="9b5ae-144">관련 문서</span><span class="sxs-lookup"><span data-stu-id="9b5ae-144">Related articles</span></span>

- [<span data-ttu-id="9b5ae-145">Microsoft Defender 바이러스 백신 업데이트 관리 및 기준 적용</span><span class="sxs-lookup"><span data-stu-id="9b5ae-145">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>](manage-updates-baselines-microsoft-defender-antivirus.md)
- [<span data-ttu-id="9b5ae-146">Windows 10에서 Microsoft Defender 바이러스 백신 업데이트 및 관리</span><span class="sxs-lookup"><span data-stu-id="9b5ae-146">Update and manage Microsoft Defender Antivirus in Windows 10</span></span>](deploy-manage-report-microsoft-defender-antivirus.md)