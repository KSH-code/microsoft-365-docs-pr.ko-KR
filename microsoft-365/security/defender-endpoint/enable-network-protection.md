---
title: 네트워크 보호 설정 켜기
description: 그룹 정책, PowerShell 또는 모바일 장치 관리 및 구성 관리자를 사용하여 네트워크 보호를 사용하도록 설정하세요.
keywords: ANetwork 보호, 악용, 악성 웹 사이트, ip, 도메인, 사용, 켜기
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: dansimp
ms.author: dansimp
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 5c7a2d943ec1813623065e70330b914a3911d1eb
ms.sourcegitcommit: 4acf613587128cae27e0fd470d1216b509775529
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/15/2021
ms.locfileid: "51769001"
---
# <a name="turn-on-network-protection"></a><span data-ttu-id="fae72-104">네트워크 보호 설정 켜기</span><span class="sxs-lookup"><span data-stu-id="fae72-104">Turn on network protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="fae72-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="fae72-105">**Applies to:**</span></span>
- <span data-ttu-id="fae72-106">[엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037) </span><span class="sxs-lookup"><span data-stu-id="fae72-106">[Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)</span></span>
- [<span data-ttu-id="fae72-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fae72-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> <span data-ttu-id="fae72-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="fae72-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="fae72-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="fae72-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="fae72-110">[네트워크 보호는](network-protection.md) 직원이 응용 프로그램을 사용하여 인터넷에서 피싱 사기, 악용 및 기타 악성 콘텐츠를 호스팅할 수 있는 위험한 도메인에 액세스하지 못하게 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fae72-110">[Network protection](network-protection.md) helps to prevent employees from using any application to access dangerous domains that may host phishing scams, exploits, and other malicious content on the internet.</span></span> <span data-ttu-id="fae72-111">테스트 [환경에서 네트워크](evaluate-network-protection.md) 보호를 감사하여 사용하도록 설정하기 전에 차단되는 앱을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fae72-111">You can [audit network protection](evaluate-network-protection.md) in a test environment to view which apps would be blocked before you enable it.</span></span>

[<span data-ttu-id="fae72-112">네트워크 필터링 구성 옵션에 대해 자세히 알아보시다</span><span class="sxs-lookup"><span data-stu-id="fae72-112">Learn more about network filtering configuration options</span></span>](/mem/intune/protect/endpoint-protection-windows-10#network-filtering)

## <a name="check-if-network-protection-is-enabled"></a><span data-ttu-id="fae72-113">네트워크 보호를 사용하도록 설정되어 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="fae72-113">Check if network protection is enabled</span></span>

<span data-ttu-id="fae72-114">레지스트리 편집기를 사용하여 로컬 장치에서 네트워크 보호가 활성화되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="fae72-114">Check if network protection has been enabled on a local device by using Registry editor.</span></span>

1. <span data-ttu-id="fae72-115">작업 **표시줄에서 시작** 단추를 선택하고 **regedit를** 입력하여 레지스트리 편집기 열기</span><span class="sxs-lookup"><span data-stu-id="fae72-115">Select the **Start** button in the task bar and type **regedit** to open Registry editor</span></span>

2. <span data-ttu-id="fae72-116">사이드 **HKEY_LOCAL_MACHINE** 선택</span><span class="sxs-lookup"><span data-stu-id="fae72-116">Choose **HKEY_LOCAL_MACHINE** from the side menu</span></span>

3. <span data-ttu-id="fae72-117">중첩된 메뉴를 탐색하여   >    >  **Exploit** Guard 네트워크  >    >    >   보호를 Windows Defender Windows Defender Windows Defender 정책</span><span class="sxs-lookup"><span data-stu-id="fae72-117">Navigate through the nested menus to **SOFTWARE** > **Policies** > **Microsoft** > **Windows Defender** > **Windows Defender Exploit Guard** > **Network Protection**</span></span>

4. <span data-ttu-id="fae72-118">**EnableNetworkProtection을** 선택하여 장치의 현재 네트워크 보호 상태를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="fae72-118">Select **EnableNetworkProtection** to see the current state of network protection on the device</span></span>

    * <span data-ttu-id="fae72-119">0 또는 **끄기**</span><span class="sxs-lookup"><span data-stu-id="fae72-119">0, or **Off**</span></span>
    * <span data-ttu-id="fae72-120">1 또는 </span><span class="sxs-lookup"><span data-stu-id="fae72-120">1, or **On**</span></span>
    * <span data-ttu-id="fae72-121">2 또는 **감사** 모드</span><span class="sxs-lookup"><span data-stu-id="fae72-121">2, or **Audit** mode</span></span>
    
    ![networkprotection](https://user-images.githubusercontent.com/3296790/95341270-b738b280-08d3-11eb-84a0-16abb140c9fd.PNG)

## <a name="enable-network-protection"></a><span data-ttu-id="fae72-123">네트워크 보호 사용</span><span class="sxs-lookup"><span data-stu-id="fae72-123">Enable network protection</span></span>

<span data-ttu-id="fae72-124">다음 방법을 사용하여 네트워크 보호를 사용하도록 설정하십시오.</span><span class="sxs-lookup"><span data-stu-id="fae72-124">Enable network protection by using any of these methods:</span></span>

* [<span data-ttu-id="fae72-125">PowerShell</span><span class="sxs-lookup"><span data-stu-id="fae72-125">PowerShell</span></span>](#powershell)
* [<span data-ttu-id="fae72-126">MDM(모바일 장치 관리)</span><span class="sxs-lookup"><span data-stu-id="fae72-126">Mobile Device Management (MDM)</span></span>](#mobile-device-management-mdm)
* [<span data-ttu-id="fae72-127">Microsoft Endpoint Manager /Intune</span><span class="sxs-lookup"><span data-stu-id="fae72-127">Microsoft Endpoint Manager / Intune</span></span>](#microsoft-endpoint-manager-formerly-intune)
* [<span data-ttu-id="fae72-128">그룹 정책</span><span class="sxs-lookup"><span data-stu-id="fae72-128">Group Policy</span></span>](#group-policy)

### <a name="powershell"></a><span data-ttu-id="fae72-129">PowerShell</span><span class="sxs-lookup"><span data-stu-id="fae72-129">PowerShell</span></span>

1. <span data-ttu-id="fae72-130">시작 **메뉴에 powershell을** 입력하고 마우스 오른쪽 단추로 Windows PowerShell **관리자** 권한으로 **실행을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="fae72-130">Type **powershell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**</span></span>
2. <span data-ttu-id="fae72-131">다음 cmdlet을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="fae72-131">Enter the following cmdlet:</span></span>

    ```PowerShell
    Set-MpPreference -EnableNetworkProtection Enabled
    ```

3. <span data-ttu-id="fae72-132">선택 사항: 다음 cmdlet을 사용하여 감사 모드에서 기능을 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="fae72-132">Optional: Enable the feature in audit mode using the following cmdlet:</span></span>

    ```PowerShell
    Set-MpPreference -EnableNetworkProtection AuditMode
    ```

    <span data-ttu-id="fae72-133">대신 `Disabled` 또는 `AuditMode` 기능을 `Enabled` 끄는 데 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fae72-133">Use `Disabled` instead of `AuditMode` or `Enabled` to turn off the feature.</span></span>

### <a name="mobile-device-management-mdm"></a><span data-ttu-id="fae72-134">MDM(모바일 장치 관리)</span><span class="sxs-lookup"><span data-stu-id="fae72-134">Mobile device management (MDM)</span></span>

<span data-ttu-id="fae72-135">[./Vendor/MSFT/Policy/Config/Defender/EnableNetworkProtection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-enablenetworkprotection) CSP(구성 서비스 공급자)를 사용하여 네트워크 보호를 사용하도록 설정하거나 감사 모드를 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fae72-135">Use the [./Vendor/MSFT/Policy/Config/Defender/EnableNetworkProtection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-enablenetworkprotection) configuration service provider (CSP) to enable or disable network protection or enable audit mode.</span></span>

### <a name="microsoft-endpoint-manager-formerly-intune"></a><span data-ttu-id="fae72-136">Microsoft Endpoint Manager(이전의 Intune)</span><span class="sxs-lookup"><span data-stu-id="fae72-136">Microsoft Endpoint Manager (formerly Intune)</span></span>

1. <span data-ttu-id="fae72-137">Microsoft Endpoint Manager 관리 센터에 로그인합니다.https://endpoint.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="fae72-137">Sign into the Microsoft Endpoint Manager admin center (https://endpoint.microsoft.com)</span></span>

2. <span data-ttu-id="fae72-138">끝점 보호 구성 프로필 [만들기 또는 편집](/mem/intune/protect/endpoint-protection-configure)</span><span class="sxs-lookup"><span data-stu-id="fae72-138">Create or edit an [endpoint protection configuration profile](/mem/intune/protect/endpoint-protection-configure)</span></span>

3. <span data-ttu-id="fae72-139">프로필 **흐름의** 구성 설정에서 **Microsoft Defender Exploit Guard** 네트워크 필터링 네트워크 보호 사용 또는  >    >    >   **감사로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="fae72-139">Under **Configuration Settings** in the profile flow, go to **Microsoft Defender Exploit Guard** > **Network filtering** > **Network protection** > **Enable** or **Audit only**</span></span>

### <a name="group-policy"></a><span data-ttu-id="fae72-140">그룹 정책</span><span class="sxs-lookup"><span data-stu-id="fae72-140">Group Policy</span></span>

<span data-ttu-id="fae72-141">다음 절차에 따라 도메인에 가입된 컴퓨터 또는 독립 실행형 컴퓨터에서 네트워크 보호를 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fae72-141">Use the following procedure to enable network protection on domain-joined computers or on a standalone computer.</span></span>

1. <span data-ttu-id="fae72-142">독립 실행형 컴퓨터에서 시작으로  이동한 다음 그룹 정책 편집을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="fae72-142">On a standalone computer, go to **Start** and then type and select **Edit group policy**.</span></span>

    <span data-ttu-id="fae72-143">*-Or-*</span><span class="sxs-lookup"><span data-stu-id="fae72-143">*-Or-*</span></span>

    <span data-ttu-id="fae72-144">도메인에 가입된 그룹 정책 관리 컴퓨터에서 [](https://technet.microsoft.com/library/cc731212.aspx)그룹 정책 관리 콘솔을 열고 구성할 그룹 정책 개체를 마우스 오른쪽 단추로 클릭하고 편집을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="fae72-144">On a domain-joined Group Policy management computer, open the [Group Policy Management Console](https://technet.microsoft.com/library/cc731212.aspx), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="fae72-145">그룹 **정책 관리 편집기에서** 컴퓨터 **구성으로 이동하여** 관리 **템플릿을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="fae72-145">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="fae72-146">**Windows** 구성 요소 Microsoft Defender 바이러스 백신 및 Exploit Guard 네트워크 Windows Defender  >    >    >  **확장합니다.**</span><span class="sxs-lookup"><span data-stu-id="fae72-146">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Windows Defender Exploit Guard** > **Network protection**.</span></span>

> [!NOTE]
> <span data-ttu-id="fae72-147">이전 버전의 Windows에서 그룹 정책 경로는 "Microsoft Defender 바이러스 백신" Windows Defender "바이러스 백신"으로 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fae72-147">On older versions of Windows, the group policy path may say "Windows Defender Antivirus" instead of "Microsoft Defender Antivirus."</span></span>

4. <span data-ttu-id="fae72-148">사용자 및  앱이 위험한 웹 사이트에 액세스하지 못하게 방지 설정을 두 번 클릭하고 옵션을 사용으로 **설정합니다.**</span><span class="sxs-lookup"><span data-stu-id="fae72-148">Double-click the **Prevent users and apps from accessing dangerous websites** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="fae72-149">옵션 섹션에서 다음 옵션 중 하나를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fae72-149">In the options section, you must specify one of the following options:</span></span>
    * <span data-ttu-id="fae72-150">**차단** - 사용자가 악성 IP 주소 및 도메인에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fae72-150">**Block** - Users can't access malicious IP addresses and domains</span></span>
    * <span data-ttu-id="fae72-151">**사용 안 하게(기본값)** - 네트워크 보호 기능이 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fae72-151">**Disable (Default)** - The Network protection feature won't work.</span></span> <span data-ttu-id="fae72-152">사용자가 악의적인 도메인에 액세스하지 못하게 차단되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fae72-152">Users won't be blocked from accessing malicious domains</span></span>
    * <span data-ttu-id="fae72-153">**감사 모드** - 사용자가 악성 IP 주소 또는 도메인을 방문하면 이벤트가 Windows 이벤트 로그에 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="fae72-153">**Audit Mode** - If a user visits a malicious IP address or domain, an event will be recorded in the Windows event log.</span></span> <span data-ttu-id="fae72-154">그러나 사용자가 주소를 방문하지 못하도록 차단되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fae72-154">However, the user won't be blocked from visiting the address.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fae72-155">네트워크 보호를 완전히 사용하도록 설정하려면 그룹  정책 옵션을  사용으로 설정하고 옵션 드롭다운 메뉴에서 차단을 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fae72-155">To fully enable network protection, you must set the Group Policy option to **Enabled** and also select **Block** in the options drop-down menu.</span></span>

<span data-ttu-id="fae72-156">레지스트리 편집기를 사용하여 로컬 컴퓨터에서 네트워크 보호가 사용하도록 설정되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="fae72-156">Confirm network protection is enabled on a local computer by using Registry editor:</span></span>

1. <span data-ttu-id="fae72-157">시작을 **선택하고** **regedit를** 입력하여 **레지스트리 편집기를 열 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="fae72-157">Select **Start** and type **regedit** to open **Registry Editor**.</span></span>

2. <span data-ttu-id="fae72-158">사이트 **HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender\Policy Manager\EnableNetworkProtection**</span><span class="sxs-lookup"><span data-stu-id="fae72-158">Navigate to **HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender\Policy Manager\EnableNetworkProtection**</span></span>

3. <span data-ttu-id="fae72-159">**EnableNetworkProtection을 선택하고** 값을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="fae72-159">Select **EnableNetworkProtection** and confirm the value:</span></span>
   * <span data-ttu-id="fae72-160">0=해제</span><span class="sxs-lookup"><span data-stu-id="fae72-160">0=Off</span></span>
   * <span data-ttu-id="fae72-161">1=켜기</span><span class="sxs-lookup"><span data-stu-id="fae72-161">1=On</span></span>
   * <span data-ttu-id="fae72-162">2=감사</span><span class="sxs-lookup"><span data-stu-id="fae72-162">2=Audit</span></span>

## <a name="see-also"></a><span data-ttu-id="fae72-163">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fae72-163">See also</span></span>

* [<span data-ttu-id="fae72-164">네트워크 보호</span><span class="sxs-lookup"><span data-stu-id="fae72-164">Network protection</span></span>](network-protection.md)
* [<span data-ttu-id="fae72-165">네트워크 보호 평가</span><span class="sxs-lookup"><span data-stu-id="fae72-165">Evaluate network protection</span></span>](evaluate-network-protection.md)
* [<span data-ttu-id="fae72-166">네트워크 보호 문제 해결</span><span class="sxs-lookup"><span data-stu-id="fae72-166">Troubleshoot network protection</span></span>](troubleshoot-np.md)
