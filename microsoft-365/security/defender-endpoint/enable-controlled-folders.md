---
title: 제어된 폴더 액세스 사용
keywords: 제어된 폴더 액세스, windows 10, windows defender, 랜섬웨어, 보호, 파일, 폴더, 사용, 켜기, 사용
description: 제어된 폴더 액세스를 사용하도록 설정하여 중요한 파일을 보호하는 방법에 대해 자세히 알아보기
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.topic: article
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: dansimp
ms.author: dansimp
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 5a90a12457597fa38c648fd44bf194d2322a26af
ms.sourcegitcommit: 3e971b31435d17ceeaa9871c01e88e25ead560fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2021
ms.locfileid: "52861226"
---
# <a name="enable-controlled-folder-access"></a><span data-ttu-id="68e7b-104">제어된 폴더 액세스 사용</span><span class="sxs-lookup"><span data-stu-id="68e7b-104">Enable controlled folder access</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="68e7b-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="68e7b-105">**Applies to:**</span></span>
- [<span data-ttu-id="68e7b-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="68e7b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="68e7b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="68e7b-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="68e7b-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="68e7b-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="68e7b-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="68e7b-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="68e7b-110">[제어된 폴더 액세스는](controlled-folders.md) 랜섬웨어와 같은 악성 앱 및 위협으로부터 중요한 데이터를 보호하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="68e7b-110">[Controlled folder access](controlled-folders.md) helps you protect valuable data from malicious apps and threats, such as ransomware.</span></span> <span data-ttu-id="68e7b-111">제어된 폴더 액세스는 Windows 10 Server 2019에 Windows 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68e7b-111">Controlled folder access is included with Windows 10 and Windows Server 2019.</span></span>

<span data-ttu-id="68e7b-112">다음 방법 중 한 가지를 사용하여 제어된 폴더 액세스를 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68e7b-112">You can enable controlled folder access by using any of these methods:</span></span>

* [<span data-ttu-id="68e7b-113">Windows 보안 앱</span><span class="sxs-lookup"><span data-stu-id="68e7b-113">Windows Security app</span></span>](#windows-security-app)
* [<span data-ttu-id="68e7b-114">Microsoft Endpoint Manager </span><span class="sxs-lookup"><span data-stu-id="68e7b-114">Microsoft Endpoint Manager</span></span>](#endpoint-manager)
* [<span data-ttu-id="68e7b-115">MDM(모바일 장치 관리)</span><span class="sxs-lookup"><span data-stu-id="68e7b-115">Mobile Device Management (MDM)</span></span>](#mobile-device-management-mdm)
* [<span data-ttu-id="68e7b-116">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="68e7b-116">Microsoft Endpoint Configuration Manager</span></span>](#microsoft-endpoint-configuration-manager)
* [<span data-ttu-id="68e7b-117">그룹 정책</span><span class="sxs-lookup"><span data-stu-id="68e7b-117">Group Policy</span></span>](#group-policy)
* [<span data-ttu-id="68e7b-118">PowerShell</span><span class="sxs-lookup"><span data-stu-id="68e7b-118">PowerShell</span></span>](#powershell)

<span data-ttu-id="68e7b-119">[감사 모드를](evaluate-controlled-folder-access.md) 사용하면 장치의 일반적인 사용에 영향을 주지 않고 기능이 어떻게 작동하고 이벤트를 검토하는지 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68e7b-119">[Audit mode](evaluate-controlled-folder-access.md) allows you to test how the feature would work (and review events) without impacting the normal use of the device.</span></span>

<span data-ttu-id="68e7b-120">로컬 관리자 목록의 선택을 해제하는 그룹 정책 설정은 제어된 폴더 액세스 설정을 다시 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="68e7b-120">Group Policy settings that disable local administrator list merging will override controlled folder access settings.</span></span> <span data-ttu-id="68e7b-121">또한 제어된 폴더 액세스를 통해 로컬 관리자가 설정한 보호된 폴더 및 허용된 앱을 어버합니다.</span><span class="sxs-lookup"><span data-stu-id="68e7b-121">They also override protected folders and allowed apps set by the local administrator through controlled folder access.</span></span> <span data-ttu-id="68e7b-122">이러한 정책에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="68e7b-122">These policies include:</span></span>

* <span data-ttu-id="68e7b-123">Microsoft Defender 바이러스 백신 목록에 **대한 로컬 관리자 병합 동작 구성**</span><span class="sxs-lookup"><span data-stu-id="68e7b-123">Microsoft Defender Antivirus **Configure local administrator merge behavior for lists**</span></span>
* <span data-ttu-id="68e7b-124">System Center Endpoint Protection 사용자가 제외 및 오버라이드를 추가할 **수 있도록 허용**</span><span class="sxs-lookup"><span data-stu-id="68e7b-124">System Center Endpoint Protection **Allow users to add exclusions and overrides**</span></span>

<span data-ttu-id="68e7b-125">로컬 목록의 선택을 취소하는 데 대한 자세한 내용은 [사용자가 Microsoft Defender AV](/windows/security/threat-protection/microsoft-defender-antivirus/configure-local-policy-overrides-microsoft-defender-antivirus#configure-how-locally-and-globally-defined-threat-remediation-and-exclusions-lists-are-merged)정책 설정을 로컬로 수정하지 못하도록 허용을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="68e7b-125">For more information about disabling local list merging, see [Prevent or allow users to locally modify Microsoft Defender AV policy settings](/windows/security/threat-protection/microsoft-defender-antivirus/configure-local-policy-overrides-microsoft-defender-antivirus#configure-how-locally-and-globally-defined-threat-remediation-and-exclusions-lists-are-merged).</span></span>

## <a name="windows-security-app"></a><span data-ttu-id="68e7b-126">Windows 보안 앱</span><span class="sxs-lookup"><span data-stu-id="68e7b-126">Windows Security app</span></span>

1. <span data-ttu-id="68e7b-127">작업 Windows 보안 방패 아이콘을 선택하여 앱 앱을 니다.</span><span class="sxs-lookup"><span data-stu-id="68e7b-127">Open the Windows Security app by selecting the shield icon in the task bar.</span></span> <span data-ttu-id="68e7b-128">Defender의 시작 메뉴를 **검색할 수도 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="68e7b-128">You can also search the start menu for **Defender**.</span></span>

2. <span data-ttu-id="68e7b-129">바이러스 & **위협** 방지 타일(또는 왼쪽 메뉴 표시줄의 방패 아이콘)을 선택한 다음 랜섬웨어 보호 **를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="68e7b-129">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar) and then select **Ransomware protection**.</span></span>

3. <span data-ttu-id="68e7b-130">제어된 폴더 **액세스에 대한 스위치를** **켜기 로 설정**</span><span class="sxs-lookup"><span data-stu-id="68e7b-130">Set the switch for **Controlled folder access** to **On**.</span></span>

> [!NOTE]
> <span data-ttu-id="68e7b-131">제어된 폴더 액세스가 그룹 정책, PowerShell 또는 MDM CSP로 구성된 경우 디바이스를 다시 시작한 후 Windows 보안 앱에서 상태가 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="68e7b-131">If controlled folder access is configured with Group Policy, PowerShell, or MDM CSPs, the state will change in the Windows Security app after a restart of the device.</span></span>
> <span data-ttu-id="68e7b-132">해당 도구를 사용하여  기능이 감사 모드로 설정되어 있는 경우 Windows 보안 앱이 상태를 끄기로 **표시됩니다.**</span><span class="sxs-lookup"><span data-stu-id="68e7b-132">If the feature is set to **Audit mode** with any of those tools, the Windows Security app will show the state as **Off**.</span></span>
> <span data-ttu-id="68e7b-133">사용자 프로필 데이터를 보호하는 경우 사용자 프로필이 설치 드라이브의 기본 Windows 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="68e7b-133">If you are protecting user profile data, we recommend that the user profile should be on the default Windows installation drive.</span></span>

## <a name="endpoint-manager"></a><span data-ttu-id="68e7b-134">Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="68e7b-134">Endpoint Manager</span></span>

1. <span data-ttu-id="68e7b-135">끝점 보안 [Endpoint Manager](https://endpoint.microsoft.com) **로그인하고 을 를 습니다.**</span><span class="sxs-lookup"><span data-stu-id="68e7b-135">Sign in to the [Endpoint Manager](https://endpoint.microsoft.com) and open **Endpoint Security**.</span></span>

2. <span data-ttu-id="68e7b-136">공격 표면 **감소 정책으로**  >  **이동 합니다.**</span><span class="sxs-lookup"><span data-stu-id="68e7b-136">Go to **Attack Surface Reduction** > **Policy**.</span></span>

3. <span data-ttu-id="68e7b-137">플랫폼을 **선택하고** Windows 10 **이상을** 선택하고 프로필 공격 표면 감소 규칙 만들기 **를**  >  **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="68e7b-137">Select **Platform**, choose **Windows 10 and later**, and select the profile **Attack Surface Reduction rules** > **Create**.</span></span>

4.  <span data-ttu-id="68e7b-138">정책 이름을 지정하고 설명을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="68e7b-138">Name the policy and add a description.</span></span> <span data-ttu-id="68e7b-139">**다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="68e7b-139">Select **Next**.</span></span>

5.  <span data-ttu-id="68e7b-140">아래로 스크롤하여 폴더 보호  사용 드롭다운을 선택하고 사용 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="68e7b-140">Scroll down to the bottom, select the **Enable Folder Protection** drop-down, and choose **Enable**.</span></span>

6.  <span data-ttu-id="68e7b-141">**보호해야** 하는 추가 폴더 목록을 선택하고 보호해야 하는 폴더를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="68e7b-141">Select **List of additional folders that need to be protected** and add the folders that need to be protected.</span></span>

7.  <span data-ttu-id="68e7b-142">보호된 **폴더에 액세스할** 수 있는 앱 목록을 선택하고 보호된 폴더에 액세스할 수 있는 앱을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="68e7b-142">Select **List of apps that have access to protected folders** and add the apps that have access to protected folders.</span></span>

8.  <span data-ttu-id="68e7b-143">공격 **표면 축소** 규칙에서 파일 및 경로 제외를 선택하고 공격 표면 축소 규칙에서 제외해야 하는 파일 및 경로를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="68e7b-143">Select **Exclude files and paths from attack surface reduction rules** and add the files and paths that need to be excluded from attack surface reduction rules.</span></span>

9.  <span data-ttu-id="68e7b-144">프로필 할당 **을 선택하고** 모든 사용자 및 모든 & **할당하고** 저장을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="68e7b-144">Select the profile **Assignments**, assign to **All Users & All Devices**, and select **Save**.</span></span>

10.  <span data-ttu-id="68e7b-145">다음을 **선택하여** 열려 있는 각 블레이드를 저장한 다음 **만들기를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="68e7b-145">Select **Next** to save each open blade and then **Create**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="68e7b-146">와일드카드는 응용 프로그램에 지원되지만 폴더에는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="68e7b-146">Wildcards are supported for applications, but not for folders.</span></span> <span data-ttu-id="68e7b-147">하위폴더는 보호되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="68e7b-147">Subfolders are not protected.</span></span> <span data-ttu-id="68e7b-148">허용된 앱은 다시 시작할 때까지 이벤트를 계속 트리거합니다.</span><span class="sxs-lookup"><span data-stu-id="68e7b-148">Allowed apps will continue to trigger events until they are restarted.</span></span>

## <a name="mobile-device-management-mdm"></a><span data-ttu-id="68e7b-149">MDM(모바일 장치 관리)</span><span class="sxs-lookup"><span data-stu-id="68e7b-149">Mobile Device Management (MDM)</span></span>

<span data-ttu-id="68e7b-150">[./Vendor/MSFT/Policy/Config/ControlledFolderAccessProtectedFolders](/windows/client-management/mdm/policy-csp-defender#defender-controlledfolderaccessprotectedfolders) CSP(구성 서비스 공급자)를 사용하여 앱이 보호된 폴더를 변경할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="68e7b-150">Use the [./Vendor/MSFT/Policy/Config/ControlledFolderAccessProtectedFolders](/windows/client-management/mdm/policy-csp-defender#defender-controlledfolderaccessprotectedfolders) configuration service provider (CSP) to allow apps to make changes to protected folders.</span></span>

## <a name="microsoft-endpoint-configuration-manager"></a><span data-ttu-id="68e7b-151">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="68e7b-151">Microsoft Endpoint Configuration Manager</span></span>

1. <span data-ttu-id="68e7b-152">이 Microsoft Endpoint Configuration Manager Exploit **Guard에서** 자산 및 규정 준수 Endpoint Protection  >    >  **Windows Defender 로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="68e7b-152">In Microsoft Endpoint Configuration Manager, go to **Assets and Compliance** > **Endpoint Protection** > **Windows Defender Exploit Guard**.</span></span>

2. <span data-ttu-id="68e7b-153">홈 **Exploit**  >  **Guard 정책 만들기 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="68e7b-153">Select **Home** > **Create Exploit Guard Policy**.</span></span>

3. <span data-ttu-id="68e7b-154">이름과 설명을 입력하고 제어된 **폴더 액세스** 를 선택하고 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="68e7b-154">Enter a name and a description, select **Controlled folder access**, and select **Next**.</span></span>

4. <span data-ttu-id="68e7b-155">변경 차단 또는 감사, 다른 앱 허용 또는 다른 폴더 추가 여부를 선택하고 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="68e7b-155">Choose whether block or audit changes, allow other apps, or add other folders, and select **Next**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="68e7b-156">응용 프로그램에는 Wilcard가 지원되지만 폴더에는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="68e7b-156">Wilcard is supported for applications, but not for folders.</span></span> <span data-ttu-id="68e7b-157">하위폴더는 보호되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="68e7b-157">Subfolders are not protected.</span></span> <span data-ttu-id="68e7b-158">허용된 앱은 다시 시작할 때까지 이벤트를 계속 트리거합니다.</span><span class="sxs-lookup"><span data-stu-id="68e7b-158">Allowed apps will continue to trigger events until they are restarted.</span></span>

5. <span data-ttu-id="68e7b-159">설정을 검토하고 **다음을** 선택하여 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68e7b-159">Review the settings and select **Next** to create the policy.</span></span>

6. <span data-ttu-id="68e7b-160">정책을 만든 후 를 **닫습니다.**</span><span class="sxs-lookup"><span data-stu-id="68e7b-160">After the policy is created, **Close**.</span></span>

## <a name="group-policy"></a><span data-ttu-id="68e7b-161">그룹 정책</span><span class="sxs-lookup"><span data-stu-id="68e7b-161">Group Policy</span></span>

1. <span data-ttu-id="68e7b-162">그룹 정책 관리 장치에서 그룹 정책 관리 콘솔을 [열고](https://technet.microsoft.com/library/cc731212.aspx)구성할 그룹 정책 개체를 마우스 오른쪽 단추로 클릭하고 편집을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="68e7b-162">On your Group Policy management device, open the [Group Policy Management Console](https://technet.microsoft.com/library/cc731212.aspx), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="68e7b-163">**그룹 정책 관리 편집기** 에서 **컴퓨터 구성** 으로 이동하여 **관리 템플릿** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="68e7b-163">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="68e7b-164">제어된 **폴더 액세스 Windows Exploit Guard > Microsoft Defender 바이러스 백신 > Windows Defender 구성 > 확장합니다.**</span><span class="sxs-lookup"><span data-stu-id="68e7b-164">Expand the tree to **Windows components > Microsoft Defender Antivirus > Windows Defender Exploit Guard > Controlled folder access**.</span></span>

4. <span data-ttu-id="68e7b-165">제어된 폴더 액세스 구성 설정을 **두** 번 클릭하고 옵션을 사용으로 **설정합니다.**</span><span class="sxs-lookup"><span data-stu-id="68e7b-165">Double-click the **Configure Controlled folder access** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="68e7b-166">옵션 섹션에서 다음 옵션 중 하나를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="68e7b-166">In the options section you must specify one of the following options:</span></span>
    * <span data-ttu-id="68e7b-167">**사용** - 악성 및 의심스러운 앱은 보호된 폴더의 파일을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="68e7b-167">**Enable** - Malicious and suspicious apps won't be allowed to make changes to files in protected folders.</span></span> <span data-ttu-id="68e7b-168">알림은 이벤트 로그의 Windows 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="68e7b-168">A notification will be provided in the Windows event log.</span></span>
    * <span data-ttu-id="68e7b-169">**사용 안 하게(기본값)** - 제어된 폴더 액세스 기능이 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="68e7b-169">**Disable (Default)** - The Controlled folder access feature won't work.</span></span> <span data-ttu-id="68e7b-170">모든 앱은 보호된 폴더의 파일을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68e7b-170">All apps can make changes to files in protected folders.</span></span>
    * <span data-ttu-id="68e7b-171">**감사 모드** - 악의적 또는 의심스러운 앱이 보호된 폴더의 파일을 변경하려고 하면 변경이 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="68e7b-171">**Audit Mode** - Changes will be allowed if a malicious or suspicious app attempts to make a change to a file in a protected folder.</span></span> <span data-ttu-id="68e7b-172">그러나 조직에 미치는 영향을 평가할 수 있는 Windows 로그에 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="68e7b-172">However, it will be recorded in the Windows event log where you can assess the impact on your organization.</span></span>
    * <span data-ttu-id="68e7b-173">**디스크 수정만 차단** - 디스크 섹터에 쓰는 것으로 확인되지 않은 앱에서 디스크 섹터에 쓰는 시도는 이벤트 로그에 Windows 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="68e7b-173">**Block disk modification only** - Attempts by untrusted apps to write to disk sectors will be logged in Windows Event log.</span></span> <span data-ttu-id="68e7b-174">이러한 로그는 Microsoft  > 작업 ID 1123의 응용 프로그램 > Windows > Windows Defender > 서비스 > 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68e7b-174">These logs can be found in **Applications and Services Logs** > Microsoft > Windows > Windows Defender > Operational > ID 1123.</span></span>
    * <span data-ttu-id="68e7b-175">**디스크** 수정만 감사 - 보호된 디스크 섹터에 쓰기 시도만 Windows 이벤트 로그에 기록됩니다(응용 프로그램 및 서비스 로그 Microsoft Windows Windows Defender  >    >    >    >  **작동**  >  **ID 1124).**</span><span class="sxs-lookup"><span data-stu-id="68e7b-175">**Audit disk modification only** - Only attempts to write to protected disk sectors will be recorded in the Windows event log (under **Applications and Services Logs** > **Microsoft** > **Windows** > **Windows Defender** > **Operational** > **ID 1124**).</span></span> <span data-ttu-id="68e7b-176">보호된 폴더의 파일 수정 또는 삭제 시도는 기록되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="68e7b-176">Attempts to modify or delete files in protected folders won't be recorded.</span></span>

      ![드롭다운에서 선택한 그룹 정책 옵션 사용 및 감사 모드 스크린샷](/microsoft-365/security/defender-endpoint/images/cfa-gp-enable)

> [!IMPORTANT]
> <span data-ttu-id="68e7b-178">제어된 폴더 액세스를 완전히 사용하도록 설정하려면 그룹  정책 옵션을  사용으로 설정하고 옵션 드롭다운 메뉴에서 차단을 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="68e7b-178">To fully enable controlled folder access, you must set the Group Policy option to **Enabled** and select **Block** in the options drop-down menu.</span></span>

## <a name="powershell"></a><span data-ttu-id="68e7b-179">PowerShell</span><span class="sxs-lookup"><span data-stu-id="68e7b-179">PowerShell</span></span>

1. <span data-ttu-id="68e7b-180">시작 **메뉴에 powershell을** 입력하고 마우스 오른쪽 단추로 Windows PowerShell **관리자** 권한으로 **실행을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="68e7b-180">Type **powershell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="68e7b-181">다음 cmdlet을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="68e7b-181">Enter the following cmdlet:</span></span>

    ```PowerShell
    Set-MpPreference -EnableControlledFolderAccess Enabled
    ```

<span data-ttu-id="68e7b-182">대신 를 지정하여 감사 모드에서 이 기능을 사용하도록 설정할 `AuditMode` 수 `Enabled` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68e7b-182">You can enable the feature in audit mode by specifying `AuditMode` instead of `Enabled`.</span></span>

<span data-ttu-id="68e7b-183">기능을 `Disabled` 끄는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68e7b-183">Use `Disabled` to turn off the feature.</span></span>

## <a name="see-also"></a><span data-ttu-id="68e7b-184">참고 항목</span><span class="sxs-lookup"><span data-stu-id="68e7b-184">See also</span></span>

* [<span data-ttu-id="68e7b-185">제어된 폴더 액세스로 중요한 폴더 보호</span><span class="sxs-lookup"><span data-stu-id="68e7b-185">Protect important folders with controlled folder access</span></span>](controlled-folders.md)
* [<span data-ttu-id="68e7b-186">제어된 폴더 액세스 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="68e7b-186">Customize controlled folder access</span></span>](customize-controlled-folders.md)
* [<span data-ttu-id="68e7b-187">엔드포인트용 Microsoft Defender 평가</span><span class="sxs-lookup"><span data-stu-id="68e7b-187">Evaluate Microsoft Defender for Endpoint</span></span>](evaluate-mde.md)
