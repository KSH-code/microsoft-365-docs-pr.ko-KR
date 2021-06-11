---
title: 제어된 폴더 액세스 사용자 지정
description: 제어된 폴더 액세스로 보호해야 하는 다른 폴더를 추가하거나 중요한 파일의 변경 내용을 잘못 차단하는 앱을 허용합니다.
keywords: 제어된 폴더 액세스, windows 10, windows defender, 랜섬웨어, 보호, 파일, 폴더, 사용자 지정, 폴더 추가, 앱 추가, 허용, 실행 파일 추가
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: jcedola, dbodorin, vladiso, nixanm, anvascon
manager: dansimp
ms.date: 05/10/2021
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: e12368b6241a2c79eead66ed77b30b7864af3955
ms.sourcegitcommit: 68383240ef7a673d5f28e2ecfab9f105bf1d8c8f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2021
ms.locfileid: "52326533"
---
# <a name="customize-controlled-folder-access"></a><span data-ttu-id="8f9d7-104">제어된 폴더 액세스 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="8f9d7-104">Customize controlled folder access</span></span>

<span data-ttu-id="8f9d7-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="8f9d7-105">**Applies to:**</span></span>
- [<span data-ttu-id="8f9d7-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="8f9d7-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="8f9d7-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8f9d7-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> <span data-ttu-id="8f9d7-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="8f9d7-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="8f9d7-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="8f9d7-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="8f9d7-110">제어된 폴더 액세스는 랜섬웨어와 같은 악성 앱 및 위협으로부터 중요한 데이터를 보호하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f9d7-110">Controlled folder access helps you protect valuable data from malicious apps and threats, such as ransomware.</span></span> <span data-ttu-id="8f9d7-111">제어된 폴더 액세스는 Windows Server 2019 및 Windows 10 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f9d7-111">Controlled folder access is supported on Windows Server 2019 and Windows 10 clients.</span></span> <span data-ttu-id="8f9d7-112">이 문서에서는 제어된 폴더 액세스 기능을 사용자 지정하는 방법을 설명하고 다음 섹션을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="8f9d7-112">This article describes how to customize controlled folder access capabilities, and includes the following sections:</span></span>

- [<span data-ttu-id="8f9d7-113">추가 폴더 보호</span><span class="sxs-lookup"><span data-stu-id="8f9d7-113">Protect additional folders</span></span>](#protect-additional-folders)
- [<span data-ttu-id="8f9d7-114">보호된 폴더에 액세스할 수 있도록 허용해야 하는 앱 추가</span><span class="sxs-lookup"><span data-stu-id="8f9d7-114">Add apps that should be allowed to access protected folders</span></span>](#allow-specific-apps-to-make-changes-to-controlled-folders)
- [<span data-ttu-id="8f9d7-115">서명된 실행 파일이 보호된 폴더에 액세스하도록 허용</span><span class="sxs-lookup"><span data-stu-id="8f9d7-115">Allow signed executable files to access protected folders</span></span>](#allow-signed-executable-files-to-access-protected-folders)
- [<span data-ttu-id="8f9d7-116">알림 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="8f9d7-116">Customize the notification</span></span>](#customize-the-notification)

> [!IMPORTANT]
> <span data-ttu-id="8f9d7-117">제어된 폴더 액세스는 악성으로 감지된 활동이 앱을 모니터링합니다.</span><span class="sxs-lookup"><span data-stu-id="8f9d7-117">Controlled folder access monitors apps for activities that are detected as malicious.</span></span> <span data-ttu-id="8f9d7-118">경우에 따라 합법적인 앱이 파일을 변경하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8f9d7-118">Sometimes, legitimate apps are blocked from making changes to your files.</span></span> <span data-ttu-id="8f9d7-119">제어된 폴더 액세스가 조직의 생산성에 영향을 미치는 경우 감사 [](audit-windows-defender.md) 모드에서 이 기능을 실행하여 영향을 완전히 평가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f9d7-119">If controlled folder access impacts your organization's productivity, you might consider running this feature in [audit mode](audit-windows-defender.md) to fully assess the impact.</span></span>

## <a name="protect-additional-folders"></a><span data-ttu-id="8f9d7-120">추가 폴더 보호</span><span class="sxs-lookup"><span data-stu-id="8f9d7-120">Protect additional folders</span></span>

<span data-ttu-id="8f9d7-121">제어된 폴더 액세스는 문서, 사진, 영화 등의 폴더를 비롯한 여러 시스템 폴더 및 기본 위치에 **적용됩니다.**</span><span class="sxs-lookup"><span data-stu-id="8f9d7-121">Controlled folder access applies to many system folders and default locations, including folders such as **Documents**, **Pictures**, and **Movies**.</span></span> <span data-ttu-id="8f9d7-122">보호할 다른 폴더를 추가할 수 있지만 기본 목록에서 기본 폴더를 제거할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8f9d7-122">You can add other folders to be protected, but you cannot remove the default folders in the default list.</span></span>

<span data-ttu-id="8f9d7-123">제어된 폴더 액세스에 다른 폴더를 추가하면 기본 Windows 라이브러리에 파일을 저장하지 않는 경우나 라이브러리의 기본 위치를 변경한 경우에 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f9d7-123">Adding other folders to controlled folder access can be helpful for cases when you don't store files in the default Windows libraries, or you've changed the default location of your libraries.</span></span>

<span data-ttu-id="8f9d7-124">네트워크 공유 및 매핑된 드라이브를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f9d7-124">You can also specify network shares and mapped drives.</span></span> <span data-ttu-id="8f9d7-125">환경 변수 및 와일드카드가 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f9d7-125">Environment variables and wildcards are supported.</span></span> <span data-ttu-id="8f9d7-126">와일드카드 사용에 대한 자세한 내용은 파일 이름 및 폴더 경로 또는 확장명 제외 목록에 와일드카드 사용을 [참조하세요.](configure-extension-file-exclusions-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="8f9d7-126">For information about using wildcards, see [Use wildcards in the file name and folder path or extension exclusion lists](configure-extension-file-exclusions-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="8f9d7-127">Windows 보안, 그룹 정책, PowerShell cmdlet 또는 모바일 장치 관리 구성 서비스 공급자를 사용하여 보호된 폴더를 추가 및 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f9d7-127">You can use the Windows Security app, Group Policy, PowerShell cmdlets, or mobile device management configuration service providers to add and remove protected folders.</span></span>

### <a name="use-the-windows-security-app-to-protect-additional-folders"></a><span data-ttu-id="8f9d7-128">앱 Windows 보안 사용하여 추가 폴더 보호</span><span class="sxs-lookup"><span data-stu-id="8f9d7-128">Use the Windows Security app to protect additional folders</span></span>

1. <span data-ttu-id="8f9d7-129">작업 Windows 보안 방패 아이콘을 선택하거나 시작 메뉴에서 보안을 검색하여  앱 앱을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f9d7-129">Open the Windows Security app by selecting the shield icon in the task bar, or by searching for *security* in the Start menu.</span></span>

2. <span data-ttu-id="8f9d7-130">바이러스 **& 보호를** 선택한 다음 **아래로 스크롤하여 랜섬웨어 보호 섹션으로 스크롤합니다.**</span><span class="sxs-lookup"><span data-stu-id="8f9d7-130">Select **Virus & threat protection**, and then scroll down to the **Ransomware protection** section.</span></span>

3. <span data-ttu-id="8f9d7-131">**랜섬웨어 보호 관리를** 선택하여 **랜섬웨어** 보호 창을 여는 방법을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8f9d7-131">Select **Manage ransomware protection** to open the **Ransomware protection** pane.</span></span>

4. <span data-ttu-id="8f9d7-132">제어된 **폴더 액세스 섹션에서** 보호된 폴더 **를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="8f9d7-132">Under the **Controlled folder access** section, select **Protected folders**.</span></span>

5. <span data-ttu-id="8f9d7-133">사용자 **액세스** 제어 프롬프트에서 **예를** 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f9d7-133">Choose **Yes** on the **User Access Control** prompt.</span></span> <span data-ttu-id="8f9d7-134">보호된 **폴더 창이** 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f9d7-134">The **Protected folders** pane displays.</span></span>

6. <span data-ttu-id="8f9d7-135">보호된 **폴더 추가를 선택하고** 프롬프트에 따라 폴더를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8f9d7-135">Select **Add a protected folder** and follow the prompts to add folders.</span></span>

### <a name="use-group-policy-to-protect-additional-folders"></a><span data-ttu-id="8f9d7-136">그룹 정책을 사용하여 추가 폴더 보호</span><span class="sxs-lookup"><span data-stu-id="8f9d7-136">Use Group Policy to protect additional folders</span></span>

1. <span data-ttu-id="8f9d7-137">그룹 정책 관리 컴퓨터에서 [그룹 정책 관리 콘솔](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true)을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="8f9d7-137">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true).</span></span> 

2. <span data-ttu-id="8f9d7-138">구성할 그룹 정책 개체를 마우스 오른쪽 단추로 클릭한 다음 편집 **을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="8f9d7-138">Right-click the Group Policy Object you want to configure, and then select **Edit**.</span></span>

3. <span data-ttu-id="8f9d7-139">그룹 정책 **관리 편집기에서** 컴퓨터 **구성** 정책 관리  >    >  **템플릿으로 이동하십시오.**</span><span class="sxs-lookup"><span data-stu-id="8f9d7-139">In your **Group Policy Management Editor**, go to **Computer configuration** > **Policies** > **Administrative templates**.</span></span>

4. <span data-ttu-id="8f9d7-140">Exploit Guard **제어된 폴더 Windows Microsoft Defender 바이러스 백신** Windows Defender 구성 요소를  >    >    >  **확장합니다.**</span><span class="sxs-lookup"><span data-stu-id="8f9d7-140">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Windows Defender Exploit Guard** > **Controlled folder access**.</span></span> <br/><span data-ttu-id="8f9d7-141">**참고:** 이전 버전의 Windows 에 를 표시하지 않고 Windows Defender 바이러스 백신 수 **Microsoft Defender 바이러스 백신.** </span><span class="sxs-lookup"><span data-stu-id="8f9d7-141">**NOTE**: On older versions of Windows, you might see **Windows Defender Antivirus** instead of **Microsoft Defender Antivirus**.</span></span>

5. <span data-ttu-id="8f9d7-142">보호된 폴더 구성을 두 번 **클릭한** 다음 옵션을 사용으로 **설정합니다.**</span><span class="sxs-lookup"><span data-stu-id="8f9d7-142">Double-click **Configured protected folders**, and then set the option to **Enabled**.</span></span> <span data-ttu-id="8f9d7-143">**표시를** 선택하고 보호할 각 폴더를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8f9d7-143">Select **Show**, and specify each folder that you want to protect.</span></span>

6. <span data-ttu-id="8f9d7-144">일반적으로 그룹 정책 개체를 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="8f9d7-144">Deploy your Group Policy Object as you usually do.</span></span>

### <a name="use-powershell-to-protect-additional-folders"></a><span data-ttu-id="8f9d7-145">PowerShell을 사용하여 추가 폴더 보호</span><span class="sxs-lookup"><span data-stu-id="8f9d7-145">Use PowerShell to protect additional folders</span></span>

1. <span data-ttu-id="8f9d7-146">시작 **메뉴에 PowerShell을** 입력하고 마우스 오른쪽 단추로 Windows PowerShell **관리자** 권한으로 **실행을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="8f9d7-146">Type **PowerShell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**</span></span>

2. <span data-ttu-id="8f9d7-147">다음 PowerShell cmdlet을 입력하고 폴더의 경로(예: )로 `<the folder to be protected>` `"c:\apps\"` 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="8f9d7-147">Type the following PowerShell cmdlet, replacing `<the folder to be protected>` with the folder's path (such as `"c:\apps\"`):</span></span>

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessProtectedFolders "<the folder to be protected>"
    ```
3. <span data-ttu-id="8f9d7-148">보호할 각 폴더에 대해 2단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="8f9d7-148">Repeat step 2 for each folder that you want to protect.</span></span> <span data-ttu-id="8f9d7-149">보호된 폴더는 앱의 Windows 보안 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f9d7-149">Folders that are protected are visible in the Windows Security app.</span></span>

   :::image type="content" source="images/cfa-allow-folder-ps.png" alt-text="cmdlet이 표시된 PowerShell 창":::

> [!IMPORTANT]
> <span data-ttu-id="8f9d7-151">를 사용하지 말고 목록에 `Add-MpPreference` 앱을 추가하거나 추가하는 데 사용하세요. `Set-MpPreference`</span><span class="sxs-lookup"><span data-stu-id="8f9d7-151">Use `Add-MpPreference` to append or add apps to the list and not `Set-MpPreference`.</span></span> <span data-ttu-id="8f9d7-152">`Set-MpPreference`cmdlet을 사용하여 기존 목록을 덮어 습니다.</span><span class="sxs-lookup"><span data-stu-id="8f9d7-152">Using the `Set-MpPreference` cmdlet will overwrite the existing list.</span></span>

### <a name="use-mdm-csps-to-protect-additional-folders"></a><span data-ttu-id="8f9d7-153">MDM CSP를 사용하여 추가 폴더 보호</span><span class="sxs-lookup"><span data-stu-id="8f9d7-153">Use MDM CSPs to protect additional folders</span></span>

<span data-ttu-id="8f9d7-154">[./Vendor/MSFT/Policy/Config/Defender/GuardedFoldersList](/windows/client-management/mdm/policy-csp-defender#defender-guardedfolderslist) CSP(구성 서비스 공급자)를 사용하여 앱이 보호된 폴더를 변경할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f9d7-154">Use the [./Vendor/MSFT/Policy/Config/Defender/GuardedFoldersList](/windows/client-management/mdm/policy-csp-defender#defender-guardedfolderslist) configuration service provider (CSP) to allow apps to make changes to protected folders.</span></span>

## <a name="allow-specific-apps-to-make-changes-to-controlled-folders"></a><span data-ttu-id="8f9d7-155">특정 앱이 제어된 폴더를 변경할 수 있도록 허용</span><span class="sxs-lookup"><span data-stu-id="8f9d7-155">Allow specific apps to make changes to controlled folders</span></span>

<span data-ttu-id="8f9d7-156">특정 앱이 항상 안전한 것으로 간주되는지 지정하고 보호된 폴더의 파일에 대한 쓰기 권한을 부여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f9d7-156">You can specify if certain apps are always considered safe and give write access to files in protected folders.</span></span> <span data-ttu-id="8f9d7-157">앱 허용은 사용자가 알고 신뢰하는 특정 앱이 제어된 폴더 액세스 기능으로 차단되는 경우 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f9d7-157">Allowing apps can be useful if a particular app you know and trust is being blocked by the controlled folder access feature.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8f9d7-158">기본적으로 Windows 목록에 친숙한 것으로 간주되는 앱을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8f9d7-158">By default, Windows adds apps that are considered friendly to the allowed list.</span></span> <span data-ttu-id="8f9d7-159">자동으로 추가되는 이러한 앱은 Windows 보안 또는 연결된 PowerShell cmdlet을 사용하여 기록되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8f9d7-159">Such apps that are added automatically are not recorded in the list shown in the Windows Security app or by using the associated PowerShell cmdlets.</span></span> <span data-ttu-id="8f9d7-160">대부분의 앱을 추가할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8f9d7-160">You shouldn't need to add most apps.</span></span> <span data-ttu-id="8f9d7-161">앱이 차단되고 있으며 신뢰할 수 있는지 확인할 수 있는 앱만 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8f9d7-161">Only add apps if they are being blocked and you can verify their trustworthiness.</span></span>

<span data-ttu-id="8f9d7-162">앱을 추가할 때 앱의 위치를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f9d7-162">When you add an app, you have to specify the app's location.</span></span> <span data-ttu-id="8f9d7-163">해당 위치에 있는 앱만 보호된 폴더에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f9d7-163">Only the app in that location will be permitted access to the protected folders.</span></span> <span data-ttu-id="8f9d7-164">이름이 같은 앱이 다른 위치에 있는 경우 앱이 허용 목록에 추가되지 않습니다. 제어된 폴더 액세스로 차단될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f9d7-164">If the app (with the same name) is in a different location, it will not be added to the allowlist and may be blocked by controlled folder access.</span></span>

<span data-ttu-id="8f9d7-165">허용된 응용 프로그램 또는 서비스는 시작된 후에만 제어된 폴더에 대한 쓰기 권한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f9d7-165">An allowed application or service only has write access to a controlled folder after it starts.</span></span> <span data-ttu-id="8f9d7-166">예를 들어 업데이트 서비스는 중지했다가 다시 시작할 때까지 허용된 후에도 이벤트를 계속 트리거합니다.</span><span class="sxs-lookup"><span data-stu-id="8f9d7-166">For example, an update service will continue to trigger events after it's allowed until it is stopped and restarted.</span></span>

### <a name="use-the-windows-defender-security-app-to-allow-specific-apps"></a><span data-ttu-id="8f9d7-167">보안 Windows Defender 사용하여 특정 앱 허용</span><span class="sxs-lookup"><span data-stu-id="8f9d7-167">Use the Windows Defender Security app to allow specific apps</span></span>

1. <span data-ttu-id="8f9d7-168">보안의 시작 Windows 보안 검색하여 앱 앱을 열 **수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="8f9d7-168">Open the Windows Security app by searching the start menu for **Security**.</span></span>

2. <span data-ttu-id="8f9d7-169">바이러스 & **위협** 방지 타일(또는 왼쪽 메뉴 표시줄의 방패 아이콘)을 선택한 다음 **랜섬웨어** 보호 관리를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8f9d7-169">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar) and then select **Manage ransomware protection**.</span></span>

3. <span data-ttu-id="8f9d7-170">제어된 **폴더 액세스 섹션에서** 제어된 폴더 액세스를 **통해 앱 허용을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="8f9d7-170">Under the **Controlled folder access** section, select **Allow an app through Controlled folder access**</span></span>

4. <span data-ttu-id="8f9d7-171">허용된 **앱 추가를 선택하고** 프롬프트에 따라 앱을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8f9d7-171">Select **Add an allowed app** and follow the prompts to add apps.</span></span>

   :::image type="content" source="images/cfa-allow-app.png" alt-text="허용된 앱 단추 추가":::

### <a name="use-group-policy-to-allow-specific-apps"></a><span data-ttu-id="8f9d7-173">그룹 정책을 사용하여 특정 앱 허용</span><span class="sxs-lookup"><span data-stu-id="8f9d7-173">Use Group Policy to allow specific apps</span></span>

1. <span data-ttu-id="8f9d7-174">그룹 정책 관리 장치에서 그룹 정책 관리 콘솔을 [열고](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true)구성할 그룹 정책 개체를 마우스 오른쪽 단추로 클릭하고 편집을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="8f9d7-174">On your Group Policy management device, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="8f9d7-175">**그룹 정책 관리 편집기** 에서 **컴퓨터 구성** 으로 이동하여 **관리 템플릿** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8f9d7-175">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="8f9d7-176">Exploit Guard **제어된 폴더 Windows Microsoft Defender 바이러스 백신** Windows Defender 구성 요소를  >    >    >  **확장합니다.**</span><span class="sxs-lookup"><span data-stu-id="8f9d7-176">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Windows Defender Exploit Guard** > **Controlled folder access**.</span></span>

4. <span data-ttu-id="8f9d7-177">허용되는 응용 프로그램 **구성 설정을 두** 번 클릭하고 옵션을 사용으로 **설정합니다.**</span><span class="sxs-lookup"><span data-stu-id="8f9d7-177">Double-click the **Configure allowed applications** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="8f9d7-178">표시를 **선택하고** 각 앱을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="8f9d7-178">Select **Show** and enter each app.</span></span>

### <a name="use-powershell-to-allow-specific-apps"></a><span data-ttu-id="8f9d7-179">PowerShell을 사용하여 특정 앱 허용</span><span class="sxs-lookup"><span data-stu-id="8f9d7-179">Use PowerShell to allow specific apps</span></span>

1. <span data-ttu-id="8f9d7-180">시작 **메뉴에 PowerShell을** 입력하고 마우스 오른쪽 단추로 Windows PowerShell **관리자** 권한으로 **실행을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="8f9d7-180">Type **PowerShell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**</span></span>
2. <span data-ttu-id="8f9d7-181">다음 cmdlet을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="8f9d7-181">Enter the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessAllowedApplications "<the app that should be allowed, including the path>"
    ```

    <span data-ttu-id="8f9d7-182">예를 들어 *C:\apps* test.exe있는 실행 파일을 추가하는 경우 cmdlet은 다음과 같습니다. </span><span class="sxs-lookup"><span data-stu-id="8f9d7-182">For example, to add the executable *test.exe* located in the folder *C:\apps*, the cmdlet would be as follows:</span></span>

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessAllowedApplications "c:\apps\test.exe"
    ```

   <span data-ttu-id="8f9d7-183">계속 사용하여 목록에 앱을 `Add-MpPreference -ControlledFolderAccessAllowedApplications` 더 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8f9d7-183">Continue to use `Add-MpPreference -ControlledFolderAccessAllowedApplications` to add more apps to the list.</span></span> <span data-ttu-id="8f9d7-184">이 cmdlet을 사용하여 추가된 앱은 앱의 Windows 보안 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f9d7-184">Apps added using this cmdlet will appear in the Windows Security app.</span></span>

   :::image type="content" source="images/cfa-allow-app-ps.png" alt-text="앱을 허용하는 PowerShell cmdlet":::

> [!IMPORTANT]
> <span data-ttu-id="8f9d7-186">목록에 `Add-MpPreference` 앱을 추가하거나 추가하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f9d7-186">Use `Add-MpPreference` to append or add apps to the list.</span></span> <span data-ttu-id="8f9d7-187">`Set-MpPreference`cmdlet을 사용하여 기존 목록을 덮어 습니다.</span><span class="sxs-lookup"><span data-stu-id="8f9d7-187">Using the `Set-MpPreference` cmdlet will overwrite the existing list.</span></span>

### <a name="use-mdm-csps-to-allow-specific-apps"></a><span data-ttu-id="8f9d7-188">MDM CSP를 사용하여 특정 앱 허용</span><span class="sxs-lookup"><span data-stu-id="8f9d7-188">Use MDM CSPs to allow specific apps</span></span>

<span data-ttu-id="8f9d7-189">[./Vendor/MSFT/Policy/Config/Defender/GuardedFoldersAllowedApplications](/windows/client-management/mdm/policy-csp-defender#defender-guardedfoldersallowedapplications) CSP(구성 서비스 공급자)를 사용하여 앱이 보호된 폴더를 변경할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f9d7-189">Use the [./Vendor/MSFT/Policy/Config/Defender/GuardedFoldersAllowedApplications](/windows/client-management/mdm/policy-csp-defender#defender-guardedfoldersallowedapplications) configuration service provider (CSP) to allow apps to make changes to protected folders.</span></span>

## <a name="allow-signed-executable-files-to-access-protected-folders"></a><span data-ttu-id="8f9d7-190">서명된 실행 파일이 보호된 폴더에 액세스하도록 허용</span><span class="sxs-lookup"><span data-stu-id="8f9d7-190">Allow signed executable files to access protected folders</span></span>

<span data-ttu-id="8f9d7-191">Microsoft Defender for Endpoint 인증서 및 파일 표시기는 서명된 실행 파일이 보호된 폴더에 액세스할 수 있도록 허용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f9d7-191">Microsoft Defender for Endpoint certificate and file indicators can allow signed executable files to access protected folders.</span></span> <span data-ttu-id="8f9d7-192">구현에 대한 자세한 내용은 [인증서를 기반으로 지표 만들기를 참조합니다.](indicator-certificates.md)</span><span class="sxs-lookup"><span data-stu-id="8f9d7-192">For implementation details, see [Create indicators based on certificates](indicator-certificates.md).</span></span>

> [!Note]
> <span data-ttu-id="8f9d7-193">Powershell을 포함한 스크립팅 엔진에는 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8f9d7-193">This does no apply to scripting engines, including Powershell</span></span>

## <a name="customize-the-notification"></a><span data-ttu-id="8f9d7-194">알림 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="8f9d7-194">Customize the notification</span></span>

<span data-ttu-id="8f9d7-195">규칙이 트리거된 후 앱 또는 파일을 차단할 때 알림을 사용자 지정하는 데 대한 자세한 내용은 [Configure alert notifications in Microsoft Defender for Endpoint을 참조하세요.](configure-email-notifications.md)</span><span class="sxs-lookup"><span data-stu-id="8f9d7-195">For more information about customizing the notification when a rule is triggered and blocks an app or file, see [Configure alert notifications in Microsoft Defender for Endpoint](configure-email-notifications.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="8f9d7-196">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8f9d7-196">See also</span></span>

- [<span data-ttu-id="8f9d7-197">제어된 폴더 액세스로 중요한 폴더 보호</span><span class="sxs-lookup"><span data-stu-id="8f9d7-197">Protect important folders with controlled folder access</span></span>](controlled-folders.md)
- [<span data-ttu-id="8f9d7-198">제어된 폴더 액세스 사용</span><span class="sxs-lookup"><span data-stu-id="8f9d7-198">Enable controlled folder access</span></span>](enable-controlled-folders.md)
- [<span data-ttu-id="8f9d7-199">공격 표면 감소 규칙 평가</span><span class="sxs-lookup"><span data-stu-id="8f9d7-199">Evaluate attack surface reduction rules</span></span>](evaluate-attack-surface-reduction.md)
