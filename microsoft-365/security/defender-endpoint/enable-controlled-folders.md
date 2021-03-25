---
title: 제어된 폴더 액세스 사용
keywords: 제어된 폴더 액세스, windows 10, windows defender, 랜섬웨어, 보호, 파일, 폴더, 사용, 켜기, 사용
description: 제어된 폴더 액세스를 사용하도록 설정하여 중요한 파일을 보호하는 방법에 대해 자세히 알아보기
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: levinec
ms.author: ellevin
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 6d07e2a21bb01794990160cf02837fc524008098
ms.sourcegitcommit: 8685b0f7d53c99577fa65144ab60295dfa60f46f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/25/2021
ms.locfileid: "51218763"
---
# <a name="enable-controlled-folder-access"></a><span data-ttu-id="2f669-104">제어된 폴더 액세스 사용</span><span class="sxs-lookup"><span data-stu-id="2f669-104">Enable controlled folder access</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2f669-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="2f669-105">**Applies to:**</span></span>
- [<span data-ttu-id="2f669-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="2f669-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="2f669-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2f669-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="2f669-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="2f669-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="2f669-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="2f669-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="2f669-110">[제어된 폴더 액세스는](controlled-folders.md) 랜섬웨어와 같은 악성 앱 및 위협으로부터 중요한 데이터를 보호하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f669-110">[Controlled folder access](controlled-folders.md) helps you protect valuable data from malicious apps and threats, such as ransomware.</span></span> <span data-ttu-id="2f669-111">제어된 폴더 액세스는 Windows 10 및 Windows Server 2019에 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f669-111">Controlled folder access is included with Windows 10 and Windows Server 2019.</span></span>

<span data-ttu-id="2f669-112">다음 방법 중 한 가지를 사용하여 제어된 폴더 액세스를 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f669-112">You can enable controlled folder access by using any of these methods:</span></span>

* [<span data-ttu-id="2f669-113">Windows 보안 앱</span><span class="sxs-lookup"><span data-stu-id="2f669-113">Windows Security app</span></span>](#windows-security-app)
* [<span data-ttu-id="2f669-114">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="2f669-114">Microsoft Intune</span></span>](#intune)
* [<span data-ttu-id="2f669-115">MDM(모바일 장치 관리)</span><span class="sxs-lookup"><span data-stu-id="2f669-115">Mobile Device Management (MDM)</span></span>](#mobile-device-management-mdm)
* [<span data-ttu-id="2f669-116">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="2f669-116">Microsoft Endpoint Configuration Manager</span></span>](#microsoft-endpoint-configuration-manager)
* [<span data-ttu-id="2f669-117">그룹 정책</span><span class="sxs-lookup"><span data-stu-id="2f669-117">Group Policy</span></span>](#group-policy)
* [<span data-ttu-id="2f669-118">PowerShell</span><span class="sxs-lookup"><span data-stu-id="2f669-118">PowerShell</span></span>](#powershell)

<span data-ttu-id="2f669-119">[감사 모드를](evaluate-controlled-folder-access.md) 사용하면 장치의 일반적인 사용에 영향을 주지 않고 기능이 어떻게 작동하고 이벤트를 검토하는지 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f669-119">[Audit mode](evaluate-controlled-folder-access.md) allows you to test how the feature would work (and review events) without impacting the normal use of the device.</span></span>

<span data-ttu-id="2f669-120">로컬 관리자 목록의 선택을 해제하는 그룹 정책 설정은 제어된 폴더 액세스 설정을 다시 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2f669-120">Group Policy settings that disable local administrator list merging will override controlled folder access settings.</span></span> <span data-ttu-id="2f669-121">또한 제어된 폴더 액세스를 통해 로컬 관리자가 설정한 보호된 폴더 및 허용된 앱을 어버합니다.</span><span class="sxs-lookup"><span data-stu-id="2f669-121">They also override protected folders and allowed apps set by the local administrator through controlled folder access.</span></span> <span data-ttu-id="2f669-122">이러한 정책에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f669-122">These policies include:</span></span>

* <span data-ttu-id="2f669-123">Microsoft Defender 바이러스 백신 **목록에 대한 로컬 관리자 병합 동작 구성**</span><span class="sxs-lookup"><span data-stu-id="2f669-123">Microsoft Defender Antivirus **Configure local administrator merge behavior for lists**</span></span>
* <span data-ttu-id="2f669-124">System Center Endpoint Protection 사용자가 제외 및 오버라이드를 추가할 **수 있도록 허용**</span><span class="sxs-lookup"><span data-stu-id="2f669-124">System Center Endpoint Protection **Allow users to add exclusions and overrides**</span></span>

<span data-ttu-id="2f669-125">로컬 목록의 선택을 취소하는 데 대한 자세한 내용은 [사용자가 Microsoft Defender AV](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-local-policy-overrides-microsoft-defender-antivirus#configure-how-locally-and-globally-defined-threat-remediation-and-exclusions-lists-are-merged)정책 설정을 로컬로 수정하지 못하도록 허용을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2f669-125">For more information about disabling local list merging, see [Prevent or allow users to locally modify Microsoft Defender AV policy settings](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-local-policy-overrides-microsoft-defender-antivirus#configure-how-locally-and-globally-defined-threat-remediation-and-exclusions-lists-are-merged).</span></span>

## <a name="windows-security-app"></a><span data-ttu-id="2f669-126">Windows 보안 앱</span><span class="sxs-lookup"><span data-stu-id="2f669-126">Windows Security app</span></span>

1. <span data-ttu-id="2f669-127">작업 표시줄에서 방패 아이콘을 선택하여 Windows 보안 앱을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f669-127">Open the Windows Security app by selecting the shield icon in the task bar.</span></span> <span data-ttu-id="2f669-128">Defender의 시작 메뉴를 **검색할 수도 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="2f669-128">You can also search the start menu for **Defender**.</span></span>

2. <span data-ttu-id="2f669-129">바이러스 & **위협** 방지 타일(또는 왼쪽 메뉴 표시줄의 방패 아이콘)을 선택한 다음 랜섬웨어 보호 **를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="2f669-129">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar) and then select **Ransomware protection**.</span></span>

3. <span data-ttu-id="2f669-130">제어된 폴더 **액세스에 대한 스위치를** **켜기 로 설정**</span><span class="sxs-lookup"><span data-stu-id="2f669-130">Set the switch for **Controlled folder access** to **On**.</span></span>

> [!NOTE]
> <span data-ttu-id="2f669-131">그룹 정책, PowerShell 또는 MDM CSP를 사용하여 제어된 폴더 액세스가 구성된 경우 장치를 다시 시작한 후 Windows 보안 앱에서 상태가 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f669-131">If controlled folder access is configured with Group Policy, PowerShell, or MDM CSPs, the state will change in the Windows Security app after a restart of the device.</span></span>
> <span data-ttu-id="2f669-132">해당 도구를 사용하여  기능이 감사 모드로 설정되어 있는 경우 Windows 보안 앱은 상태를 해제로 **표시됩니다.**</span><span class="sxs-lookup"><span data-stu-id="2f669-132">If the feature is set to **Audit mode** with any of those tools, the Windows Security app will show the state as **Off**.</span></span>
> <span data-ttu-id="2f669-133">사용자 프로필 데이터를 보호하는 경우 사용자 프로필이 기본 Windows 설치 드라이브에 있는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="2f669-133">If you are protecting user profile data, we recommend that the user profile should be on the default Windows installation drive.</span></span>

## <a name="intune"></a><span data-ttu-id="2f669-134">Intune</span><span class="sxs-lookup"><span data-stu-id="2f669-134">Intune</span></span>

1. <span data-ttu-id="2f669-135">[Azure Portal에 로그인하고](https://portal.azure.com) Intune을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f669-135">Sign in to the [Azure portal](https://portal.azure.com) and open Intune.</span></span>

2. <span data-ttu-id="2f669-136">장치 구성 **프로필**  >  **프로필**  >  **만들기로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="2f669-136">Go to **Device configuration** > **Profiles** > **Create profile**.</span></span>

3. <span data-ttu-id="2f669-137">프로필 이름을 지정하고 **Windows 10 이상 및** 엔드포인트 보호 **를 선택하세요.**</span><span class="sxs-lookup"><span data-stu-id="2f669-137">Name the profile, choose **Windows 10 and later** and **Endpoint protection**.</span></span> <br/> <span data-ttu-id="2f669-138">![끝점 보호 프로필 만들기](/microsoft-365/security/defender-endpoint/images/create-endpoint-protection-profile)</span><span class="sxs-lookup"><span data-stu-id="2f669-138">![Create endpoint protection profile](/microsoft-365/security/defender-endpoint/images/create-endpoint-protection-profile)</span></span> <br/>

4. <span data-ttu-id="2f669-139">Configure   >  **Windows Defender Exploit Guard**  >  **Controlled folder access**  >  **Enable으로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="2f669-139">Go to **Configure** > **Windows Defender Exploit Guard** > **Controlled folder access** > **Enable**.</span></span>

5. <span data-ttu-id="2f669-140">보호된 폴더에 액세스할 수 있는 각 응용 프로그램의 경로와 보호가 필요한 추가 폴더의 경로를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="2f669-140">Type the path to each application that has access to protected folders and the path to any additional folder that needs protection.</span></span> <span data-ttu-id="2f669-141">**추가** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2f669-141">Select **Add**.</span></span><br/> <span data-ttu-id="2f669-142">![Intune에서 제어된 폴더 액세스 사용](/microsoft-365/security/defender-endpoint/images/enable-cfa-intune)</span><span class="sxs-lookup"><span data-stu-id="2f669-142">![Enable controlled folder access in Intune](/microsoft-365/security/defender-endpoint/images/enable-cfa-intune)</span></span><br/>

   > [!NOTE]
   > <span data-ttu-id="2f669-143">응용 프로그램에는 Wilcard가 지원되지만 폴더에는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2f669-143">Wilcard is supported for applications, but not for folders.</span></span> <span data-ttu-id="2f669-144">하위폴더는 보호되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2f669-144">Subfolders are not protected.</span></span> <span data-ttu-id="2f669-145">허용된 앱은 다시 시작할 때까지 이벤트를 계속 트리거합니다.</span><span class="sxs-lookup"><span data-stu-id="2f669-145">Allowed apps will continue to trigger events until they are restarted.</span></span>

6. <span data-ttu-id="2f669-146">확인을 **선택하여** 열려 있는 각 블레이드를 저장하고 **만들기 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="2f669-146">Select **OK** to save each open blade and **Create**.</span></span>

7. <span data-ttu-id="2f669-147">프로필 **할당을 선택하고** 모든 장치 및 & **할당합니다.** </span><span class="sxs-lookup"><span data-stu-id="2f669-147">Select the profile **Assignments**, assign to **All Users & All Devices**, and **Save**.</span></span>

## <a name="mobile-device-management-mdm"></a><span data-ttu-id="2f669-148">MDM(모바일 장치 관리)</span><span class="sxs-lookup"><span data-stu-id="2f669-148">Mobile Device Management (MDM)</span></span>

<span data-ttu-id="2f669-149">[./Vendor/MSFT/Policy/Config/ControlledFolderAccessProtectedFolders](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-controlledfolderaccessprotectedfolders) CSP(구성 서비스 공급자)를 사용하여 앱이 보호된 폴더를 변경할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f669-149">Use the [./Vendor/MSFT/Policy/Config/ControlledFolderAccessProtectedFolders](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-controlledfolderaccessprotectedfolders) configuration service provider (CSP) to allow apps to make changes to protected folders.</span></span>

## <a name="microsoft-endpoint-configuration-manager"></a><span data-ttu-id="2f669-150">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="2f669-150">Microsoft Endpoint Configuration Manager</span></span>

1. <span data-ttu-id="2f669-151">Microsoft Endpoint Configuration Manager에서 Exploit **Guard의** 자산 및 준수 끝점 보호  >    >  **Windows Defender 로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="2f669-151">In Microsoft Endpoint Configuration Manager, go to **Assets and Compliance** > **Endpoint Protection** > **Windows Defender Exploit Guard**.</span></span>

2. <span data-ttu-id="2f669-152">홈 **Exploit**  >  **Guard 정책 만들기 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="2f669-152">Select **Home** > **Create Exploit Guard Policy**.</span></span>

3. <span data-ttu-id="2f669-153">이름과 설명을 입력하고 제어된 **폴더 액세스** 를 선택하고 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="2f669-153">Enter a name and a description, select **Controlled folder access**, and select **Next**.</span></span>

4. <span data-ttu-id="2f669-154">변경 차단 또는 감사, 다른 앱 허용 또는 다른 폴더 추가 여부를 선택하고 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="2f669-154">Choose whether block or audit changes, allow other apps, or add other folders, and select **Next**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="2f669-155">응용 프로그램에는 Wilcard가 지원되지만 폴더에는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2f669-155">Wilcard is supported for applications, but not for folders.</span></span> <span data-ttu-id="2f669-156">하위폴더는 보호되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2f669-156">Subfolders are not protected.</span></span> <span data-ttu-id="2f669-157">허용된 앱은 다시 시작할 때까지 이벤트를 계속 트리거합니다.</span><span class="sxs-lookup"><span data-stu-id="2f669-157">Allowed apps will continue to trigger events until they are restarted.</span></span>

5. <span data-ttu-id="2f669-158">설정을 검토하고 **다음을** 선택하여 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f669-158">Review the settings and select **Next** to create the policy.</span></span>

6. <span data-ttu-id="2f669-159">정책을 만든 후 를 **닫습니다.**</span><span class="sxs-lookup"><span data-stu-id="2f669-159">After the policy is created, **Close**.</span></span>

## <a name="group-policy"></a><span data-ttu-id="2f669-160">그룹 정책</span><span class="sxs-lookup"><span data-stu-id="2f669-160">Group Policy</span></span>

1. <span data-ttu-id="2f669-161">그룹 정책 관리 장치에서 그룹 정책 관리 콘솔을 [열고](https://technet.microsoft.com/library/cc731212.aspx)구성할 그룹 정책 개체를 마우스 오른쪽 단추로 클릭하고 편집을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="2f669-161">On your Group Policy management device, open the [Group Policy Management Console](https://technet.microsoft.com/library/cc731212.aspx), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="2f669-162">그룹 **정책 관리 편집기에서** 컴퓨터 **구성으로 이동하여** 관리 **템플릿을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="2f669-162">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="2f669-163">Microsoft Defender 바이러스 백신 > 제어된 폴더 액세스를 > Windows Defender Windows 구성 **> 확장합니다.**</span><span class="sxs-lookup"><span data-stu-id="2f669-163">Expand the tree to **Windows components > Microsoft Defender Antivirus > Windows Defender Exploit Guard > Controlled folder access**.</span></span>

4. <span data-ttu-id="2f669-164">제어된 폴더 액세스 구성 설정을 **두** 번 클릭하고 옵션을 사용으로 **설정합니다.**</span><span class="sxs-lookup"><span data-stu-id="2f669-164">Double-click the **Configure Controlled folder access** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="2f669-165">옵션 섹션에서 다음 옵션 중 하나를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f669-165">In the options section you must specify one of the following options:</span></span>
    * <span data-ttu-id="2f669-166">**사용** - 악성 및 의심스러운 앱은 보호된 폴더의 파일을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2f669-166">**Enable** - Malicious and suspicious apps won't be allowed to make changes to files in protected folders.</span></span> <span data-ttu-id="2f669-167">알림이 Windows 이벤트 로그에 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f669-167">A notification will be provided in the Windows event log.</span></span>
    * <span data-ttu-id="2f669-168">**사용 안 하게(기본값)** - 제어된 폴더 액세스 기능이 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2f669-168">**Disable (Default)** - The Controlled folder access feature won't work.</span></span> <span data-ttu-id="2f669-169">모든 앱은 보호된 폴더의 파일을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f669-169">All apps can make changes to files in protected folders.</span></span>
    * <span data-ttu-id="2f669-170">**감사 모드** - 악의적 또는 의심스러운 앱이 보호된 폴더의 파일을 변경하려고 하면 변경이 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f669-170">**Audit Mode** - Changes will be allowed if a malicious or suspicious app attempts to make a change to a file in a protected folder.</span></span> <span data-ttu-id="2f669-171">그러나 조직에 미치는 영향을 평가할 수 있는 Windows 이벤트 로그에 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f669-171">However, it will be recorded in the Windows event log where you can assess the impact on your organization.</span></span>
    * <span data-ttu-id="2f669-172">**디스크 수정만 차단** - Windows 이벤트 로그에 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f669-172">**Block disk modification only** - Attempts by untrusted apps to write to disk sectors will be logged in Windows Event log.</span></span> <span data-ttu-id="2f669-173">이러한 로그 **>는** Microsoft > Windows > Windows Defender > ID 1123의 응용 프로그램 및 > 로그에서 > 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f669-173">These logs can be found in **Applications and Services Logs** > Microsoft > Windows > Windows Defender > Operational > ID 1123.</span></span>
    * <span data-ttu-id="2f669-174">**디스크 수정만** 감사 - 보호된 디스크 섹터에 쓰기 시도만 Windows 이벤트 로그에 기록됩니다(응용 프로그램 및 서비스 로그 Microsoft Windows Windows Defender  >    >    >    >  **작동**  >  **ID 1124).**</span><span class="sxs-lookup"><span data-stu-id="2f669-174">**Audit disk modification only** - Only attempts to write to protected disk sectors will be recorded in the Windows event log (under **Applications and Services Logs** > **Microsoft** > **Windows** > **Windows Defender** > **Operational** > **ID 1124**).</span></span> <span data-ttu-id="2f669-175">보호된 폴더의 파일 수정 또는 삭제 시도는 기록되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2f669-175">Attempts to modify or delete files in protected folders won't be recorded.</span></span>

      ![드롭다운에서 선택한 그룹 정책 옵션 사용 및 감사 모드 스크린샷](/microsoft-365/security/defender-endpoint/images/cfa-gp-enable)

> [!IMPORTANT]
> <span data-ttu-id="2f669-177">제어된 폴더 액세스를 완전히 사용하도록 설정하려면 그룹  정책 옵션을  사용으로 설정하고 옵션 드롭다운 메뉴에서 차단을 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f669-177">To fully enable controlled folder access, you must set the Group Policy option to **Enabled** and select **Block** in the options drop-down menu.</span></span>

## <a name="powershell"></a><span data-ttu-id="2f669-178">PowerShell</span><span class="sxs-lookup"><span data-stu-id="2f669-178">PowerShell</span></span>

1. <span data-ttu-id="2f669-179">시작 **메뉴에 powershell을** 입력하고 마우스 오른쪽 단추로 Windows PowerShell **관리자** 권한으로 **실행을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="2f669-179">Type **powershell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="2f669-180">다음 cmdlet을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="2f669-180">Enter the following cmdlet:</span></span>

    ```PowerShell
    Set-MpPreference -EnableControlledFolderAccess Enabled
    ```

<span data-ttu-id="2f669-181">대신 를 지정하여 감사 모드에서 이 기능을 사용하도록 설정할 `AuditMode` 수 `Enabled` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f669-181">You can enable the feature in audit mode by specifying `AuditMode` instead of `Enabled`.</span></span>

<span data-ttu-id="2f669-182">기능을 `Disabled` 끄는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f669-182">Use `Disabled` to turn off the feature.</span></span>

## <a name="see-also"></a><span data-ttu-id="2f669-183">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2f669-183">See also</span></span>

* [<span data-ttu-id="2f669-184">제어된 폴더 액세스로 중요한 폴더 보호</span><span class="sxs-lookup"><span data-stu-id="2f669-184">Protect important folders with controlled folder access</span></span>](controlled-folders.md)
* [<span data-ttu-id="2f669-185">제어된 폴더 액세스 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="2f669-185">Customize controlled folder access</span></span>](customize-controlled-folders.md)
* [<span data-ttu-id="2f669-186">끝점에 대한 Microsoft Defender 평가</span><span class="sxs-lookup"><span data-stu-id="2f669-186">Evaluate Microsoft Defender for Endpoint</span></span>](evaluate-mde.md)
