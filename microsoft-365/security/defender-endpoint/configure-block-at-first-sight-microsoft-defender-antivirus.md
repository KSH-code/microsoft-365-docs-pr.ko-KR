---
title: 즉시 차단을 사용하여 몇 초 만에 맬웨어 감지
description: 몇 초 이내에 맬웨어를 감지하고 차단하는 모든 시 차단 기능을 켜세요.
keywords: 검사, BAFS, 맬웨어, 최초, 최초, 클라우드, defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: high
author: denisebmsft
ms.author: deniseb
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.date: 10/22/2020
ms.technology: mde
ms.openlocfilehash: 837b7899368e69b274323125c97169bbe4f823b7
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51691565"
---
# <a name="turn-on-block-at-first-sight"></a><span data-ttu-id="7c9a1-104">첫 번째 차단 켜기</span><span class="sxs-lookup"><span data-stu-id="7c9a1-104">Turn on block at first sight</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="7c9a1-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="7c9a1-105">**Applies to:**</span></span>

- <span data-ttu-id="7c9a1-106">[엔드포인트용 Microsoft Defender](/microsoft-365/security/defender-endpoint/) </span><span class="sxs-lookup"><span data-stu-id="7c9a1-106">[Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)</span></span>

<span data-ttu-id="7c9a1-107">차단은 몇 초 이내에 새 맬웨어를 검색하고 차단하는 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7c9a1-107">Block at first sight provides a way to detect and block new malware within seconds.</span></span> <span data-ttu-id="7c9a1-108">이 보호는 특정 선행 조건 설정을 사용할 때 기본적으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c9a1-108">This protection is enabled by default when certain prerequisite settings are enabled.</span></span> <span data-ttu-id="7c9a1-109">이러한 설정에는 클라우드 제공 보호, 지정된 샘플 제출 시간 제한(예: 50초) 및 높은 파일 차단 수준이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c9a1-109">These settings include cloud-delivered protection, a specified sample submission timeout (such as 50 seconds), and a file-blocking level of high.</span></span> <span data-ttu-id="7c9a1-110">대부분의 엔터프라이즈 조직에서 이러한 설정은 기본적으로 Microsoft Defender 바이러스 백신 배포에서 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c9a1-110">In most enterprise organizations, these settings are enabled by default with Microsoft Defender Antivirus deployments.</span></span> 

<span data-ttu-id="7c9a1-111">클라우드 기반 [보호](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md) 서비스가 파일을 분석하는 동안 파일 실행을 차단할 기간을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c9a1-111">You can [specify how long a file should be prevented from running](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md) while the cloud-based protection service analyzes the file.</span></span> <span data-ttu-id="7c9a1-112">또한 파일이 [차단될](/windows/security/threat-protection//windows-defender-security-center/wdsc-customize-contact-information.md) 때 사용자의 데스크톱에 표시되는 메시지를 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c9a1-112">And, you can [customize the message displayed on users' desktops](/windows/security/threat-protection//windows-defender-security-center/wdsc-customize-contact-information.md) when a file is blocked.</span></span> <span data-ttu-id="7c9a1-113">회사 이름, 연락처 정보 및 메시지 URL을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c9a1-113">You can change the company name, contact information, and message URL.</span></span>

>[!TIP]
><span data-ttu-id="7c9a1-114">Microsoft Defender for Endpoint 데모 웹 [사이트(demo.wd.microsoft.com)를](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) 방문하여 기능이 작동하고 작동 방법을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="7c9a1-114">Visit the Microsoft Defender for Endpoint demo website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the features are working and see how they work.</span></span>

## <a name="how-it-works"></a><span data-ttu-id="7c9a1-115">작동 방식</span><span class="sxs-lookup"><span data-stu-id="7c9a1-115">How it works</span></span>

<span data-ttu-id="7c9a1-116">Microsoft Defender 바이러스 백신이 의심스러우지만 검색되지는 않지만 파일을 발견하면 클라우드 보호 백엔드를 쿼리합니다.</span><span class="sxs-lookup"><span data-stu-id="7c9a1-116">When Microsoft Defender Antivirus encounters a suspicious but undetected file, it queries our cloud protection backend.</span></span> <span data-ttu-id="7c9a1-117">클라우드 백end는 파일에 대한 지론, 기계 학습 및 자동화된 분석을 적용하여 파일이 악성인지 아니면 위협이 아닌지 판단합니다.</span><span class="sxs-lookup"><span data-stu-id="7c9a1-117">The cloud backend applies heuristics, machine learning, and automated analysis of the file to determine whether the files are malicious or not a threat.</span></span>

<span data-ttu-id="7c9a1-118">Microsoft Defender 바이러스 백신은 여러 감지 및 방지 기술을 사용하여 정확하고 지능적인 실시간 보호를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7c9a1-118">Microsoft Defender Antivirus uses multiple detection and prevention technologies to deliver accurate, intelligent, and real-time protection.</span></span> <span data-ttu-id="7c9a1-119">자세한 내용은 다음 블로그를 참조하세요. Endpoint 차세대 보호를 위한 Microsoft Defender의 핵심에 있는 고급 기술에 [대해 알아보세요.](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/)</span><span class="sxs-lookup"><span data-stu-id="7c9a1-119">To learn more, see this blog: [Get to know the advanced technologies at the core of Microsoft Defender for Endpoint next-generation protection](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/).</span></span>
<span data-ttu-id="7c9a1-120">![Microsoft Defender AV 엔진 목록](images/microsoft-defender-atp-next-generation-protection-engines.png)</span><span class="sxs-lookup"><span data-stu-id="7c9a1-120">![List of Microsoft Defender AV engines](images/microsoft-defender-atp-next-generation-protection-engines.png)</span></span>  

<span data-ttu-id="7c9a1-121">Windows 10 버전 1803 이상에서 즉석에서 차단은 이식할 수 없는 실행 파일(예: JS, VBS 또는 매크로)과 실행 파일을 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c9a1-121">In Windows 10, version 1803 or later, block at first sight can block non-portable executable files (such as JS, VBS, or macros) as well as executable files.</span></span>

<span data-ttu-id="7c9a1-122">즉 차단은 인터넷에서 다운로드되거나 인터넷 영역에서 시작된 실행 파일 및 이식할 수 없는 실행 파일에만 클라우드 보호 백드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c9a1-122">Block at first sight only uses the cloud protection backend for executable files and non-portable executable files that are downloaded from the Internet, or that originate from the Internet zone.</span></span> <span data-ttu-id="7c9a1-123">.exe 파일의 해시 값은 클라우드 백엔드를 통해 확인하여 파일이 이전에는 확인되지 않았다는 파일을 확인하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7c9a1-123">A hash value of the .exe file is checked via the cloud backend to determine if the file is a previously undetected file.</span></span>

<span data-ttu-id="7c9a1-124">클라우드 백디드에서 판단할 수 없는 경우 Microsoft Defender 바이러스 백신은 파일을 잠그고 클라우드에 복사본을 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="7c9a1-124">If the cloud backend is unable to make a determination, Microsoft Defender Antivirus locks the file and uploads a copy to the cloud.</span></span> <span data-ttu-id="7c9a1-125">클라우드는 추가 분석을 수행하여 파일이 악의적인지 안전한지 여부에 따라 향후 발생할 모든 발생 시 파일을 실행하거나 차단하기 전에 결정에 도달합니다.</span><span class="sxs-lookup"><span data-stu-id="7c9a1-125">The cloud performs additional analysis to reach a determination before it either allows the file to run or blocks it in all future encounters, depending on whether it determines the file to be malicious or safe.</span></span>

<span data-ttu-id="7c9a1-126">대부분의 경우 이 프로세스는 새 맬웨어에 대한 응답 시간을 시간에서 초로 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c9a1-126">In many cases, this process can reduce the response time for new malware from hours to seconds.</span></span>

## <a name="turn-on-block-at-first-sight-with-microsoft-intune"></a><span data-ttu-id="7c9a1-127">Microsoft Intune을 통해 즉시 차단 켜기</span><span class="sxs-lookup"><span data-stu-id="7c9a1-127">Turn on block at first sight with Microsoft Intune</span></span>

> [!TIP]
> <span data-ttu-id="7c9a1-128">Microsoft Intune은 이제 Microsoft Endpoint Manager의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="7c9a1-128">Microsoft Intune is now part of Microsoft Endpoint Manager.</span></span>

1. <span data-ttu-id="7c9a1-129">Microsoft Endpoint Manager 관리 [https://endpoint.microsoft.com](https://endpoint.microsoft.com) 센터()에서 장치 구성   >  **프로필로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="7c9a1-129">In the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)), navigate to **Devices** > **Configuration profiles**.</span></span>

2. <span data-ttu-id="7c9a1-130">장치 제한 프로필 유형을 사용하여 **프로필을 선택하거나** 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c9a1-130">Select or create a profile using the **Device restrictions** profile type.</span></span>

3. <span data-ttu-id="7c9a1-131">장치 제한 **프로필의** 구성 설정에서 Microsoft Defender 바이러스 백신에서 다음 설정을 **설정하거나 확인합니다.**</span><span class="sxs-lookup"><span data-stu-id="7c9a1-131">In the **Configuration settings** for the Device restrictions profile, set or confirm the following settings under **Microsoft Defender Antivirus**:</span></span>

   - <span data-ttu-id="7c9a1-132">**클라우드 제공 보호**: 사용</span><span class="sxs-lookup"><span data-stu-id="7c9a1-132">**Cloud-delivered protection**: Enabled</span></span>
   - <span data-ttu-id="7c9a1-133">**파일 차단 수준**: 높음</span><span class="sxs-lookup"><span data-stu-id="7c9a1-133">**File Blocking Level**: High</span></span>
   - <span data-ttu-id="7c9a1-134">**클라우드에서 파일 검색을 위한 시간 확장명:** 50</span><span class="sxs-lookup"><span data-stu-id="7c9a1-134">**Time extension for file scanning by the cloud**: 50</span></span>
   - <span data-ttu-id="7c9a1-135">**샘플 제출 전에** 사용자에게 확인 : 메시지를 표시하지 않고 모든 데이터 보내기</span><span class="sxs-lookup"><span data-stu-id="7c9a1-135">**Prompt users before sample submission**: Send all data without prompting</span></span>

   ![Intune 구성](images/defender/intune-block-at-first-sight.png)

4. <span data-ttu-id="7c9a1-137">설정을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="7c9a1-137">Save your settings.</span></span>

> [!TIP]
> - <span data-ttu-id="7c9a1-138">파일 차단 수준을 **높음으로** 설정하면 강력한 검색 수준이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c9a1-138">Setting the file blocking level to **High** applies a strong level of detection.</span></span> <span data-ttu-id="7c9a1-139">파일 차단으로 인해 합법적인 파일이 가의 긍정 검색을 발생하게 하는 가능성은 낮지만, 검지된 파일을 복원할 [수 있습니다.](./restore-quarantined-files-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="7c9a1-139">In the unlikely event that file blocking causes a false positive detection of legitimate files, you can [restore quarantined files](./restore-quarantined-files-microsoft-defender-antivirus.md).</span></span>
> - <span data-ttu-id="7c9a1-140">Intune에서 Microsoft Defender 바이러스 백신 장치 제한을 구성하는 데 대한 자세한 내용은 Microsoft Intune에서 장치 제한 설정 [구성을 참조하세요.](/intune/device-restrictions-configure)</span><span class="sxs-lookup"><span data-stu-id="7c9a1-140">For more information about configuring Microsoft Defender Antivirus device restrictions in Intune, see [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure).</span></span>
> - <span data-ttu-id="7c9a1-141">Intune의 Microsoft Defender 바이러스 백신 장치 제한 목록은 [Intune의 Windows 10](/intune/device-restrictions-windows-10#microsoft-defender-antivirus)및 최신 설정에 대한 장치 제한을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7c9a1-141">For a list of Microsoft Defender Antivirus device restrictions in Intune, see [Device restriction for Windows 10 (and newer) settings in Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus).</span></span>

## <a name="turn-on-block-at-first-sight-with-microsoft-endpoint-manager"></a><span data-ttu-id="7c9a1-142">Microsoft Endpoint Manager를 통해 첫 번째 차단 켜기</span><span class="sxs-lookup"><span data-stu-id="7c9a1-142">Turn on block at first sight with Microsoft Endpoint Manager</span></span>

> [!TIP]
> <span data-ttu-id="7c9a1-143">Microsoft Endpoint Configuration Manager를 찾고 있는 경우 이제 Microsoft Endpoint Manager의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="7c9a1-143">If you're looking for Microsoft Endpoint Configuration Manager, it's now part of Microsoft Endpoint Manager.</span></span>

1. <span data-ttu-id="7c9a1-144">Microsoft Endpoint Manager( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) 에서 **Endpoint 보안 바이러스 백신으로**  >  **이동 합니다.**</span><span class="sxs-lookup"><span data-stu-id="7c9a1-144">In Microsoft Endpoint Manager ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)), go to **Endpoint security** > **Antivirus**.</span></span>

2. <span data-ttu-id="7c9a1-145">기존 정책을 선택하거나 **Microsoft Defender 바이러스** 백신 프로필 유형을 사용하여 새 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c9a1-145">Select an existing policy, or create a new policy using the **Microsoft Defender Antivirus** profile type.</span></span>

3. <span data-ttu-id="7c9a1-146">다음 구성 설정을 설정하거나 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="7c9a1-146">Set or confirm the following configuration settings:</span></span>

   - <span data-ttu-id="7c9a1-147">**클라우드 제공 보호 켜기**: 예</span><span class="sxs-lookup"><span data-stu-id="7c9a1-147">**Turn on cloud-delivered protection**: Yes</span></span>
   - <span data-ttu-id="7c9a1-148">**클라우드 제공 보호 수준:** 높음</span><span class="sxs-lookup"><span data-stu-id="7c9a1-148">**Cloud-delivered protection level**: High</span></span>
   - <span data-ttu-id="7c9a1-149">**Defender 클라우드 확장 시간 제한(초)**: 50</span><span class="sxs-lookup"><span data-stu-id="7c9a1-149">**Defender Cloud Extended Timeout in Seconds**: 50</span></span>

   :::image type="content" source="images/endpointmgr-antivirus-cloudprotection.png" alt-text="엔드포인트 관리자에서 즉시 설정 차단":::

4. <span data-ttu-id="7c9a1-151">모든 사용자, 모든 장치 또는 모든 사용자 및 장치와 같은 그룹에 Microsoft Defender 바이러스 백신 **프로필을 적용합니다.**</span><span class="sxs-lookup"><span data-stu-id="7c9a1-151">Apply the Microsoft Defender Antivirus profile to a group, such as **All users**, **All devices**, or **All users and devices**.</span></span>

## <a name="turn-on-block-at-first-sight-with-group-policy"></a><span data-ttu-id="7c9a1-152">그룹 정책을 통해 첫 번째 차단 켜기</span><span class="sxs-lookup"><span data-stu-id="7c9a1-152">Turn on block at first sight with Group Policy</span></span>

> [!NOTE]
> <span data-ttu-id="7c9a1-153">Intune 또는 Microsoft Endpoint Manager를 사용하여 즉시 차단을 켜는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="7c9a1-153">We recommend using Intune or Microsoft Endpoint Manager to turn on block at first sight.</span></span> 

1. <span data-ttu-id="7c9a1-154">그룹 정책 관리 컴퓨터에서 그룹 정책 관리 콘솔을 [열고](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))구성할 그룹 정책 개체를 마우스 오른쪽 단추로 클릭하고 편집을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="7c9a1-154">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and select **Edit**.</span></span> 

2. <span data-ttu-id="7c9a1-155">그룹 정책 **관리 편집기를 사용하여** **컴퓨터** 구성 관리 템플릿 Windows 구성 요소  >    >    >  **Microsoft Defender 바이러스 백신** MAPS 로  >  **이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="7c9a1-155">Using the **Group Policy Management Editor** go to **Computer configuration** > **Administrative templates** > **Windows Components** > **Microsoft Defender Antivirus** > **MAPS**.</span></span> 

3. <span data-ttu-id="7c9a1-156">MAPS 섹션에서 '즉각적 **차단'** 기능 구성을 두 번 클릭하고 사용으로 **설정한** 다음 확인 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="7c9a1-156">In the MAPS section, double-click **Configure the 'Block at First Sight' feature**, and set it to **Enabled**, and then select **OK**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="7c9a1-157">항상 **메시지 표시(0)로** 설정하면 장치의 보호 상태가 낮아지게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c9a1-157">Setting to **Always prompt (0)** will lower the protection state of the device.</span></span> <span data-ttu-id="7c9a1-158">보내지 **않습니다(2)로** 설정하면 즉시 차단이 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7c9a1-158">Setting to **Never send (2)** means block at first sight will not function.</span></span>

4. <span data-ttu-id="7c9a1-159">MAPS 섹션에서 추가 분석이 필요한 경우 파일 샘플 보내기 를 두 번 클릭하고 사용으로 **설정합니다.** </span><span class="sxs-lookup"><span data-stu-id="7c9a1-159">In the MAPS section, double-click **Send file samples when further analysis is required**, and set it to **Enabled**.</span></span> <span data-ttu-id="7c9a1-160">추가 **분석이 필요한** 경우 파일 샘플 보내기에서 모든 샘플 보내기 **를** 선택하고 확인을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="7c9a1-160">Under **Send file samples when further analysis is required**, select **Send all samples**, and then click **OK**.</span></span>

5. <span data-ttu-id="7c9a1-161">설정을 변경한 경우 네트워크 전체에 그룹 정책 개체를 다시 재배포하여 모든 끝점이 적용되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c9a1-161">If you changed any settings, redeploy the Group Policy Object across your network to ensure all endpoints are covered.</span></span>

## <a name="confirm-block-at-first-sight-is-enabled-on-individual-clients"></a><span data-ttu-id="7c9a1-162">개별 클라이언트에서 최초 차단이 사용하도록 설정되어 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="7c9a1-162">Confirm block at first sight is enabled on individual clients</span></span>

<span data-ttu-id="7c9a1-163">Windows 보안 설정을 사용하여 개별 클라이언트에서 즉시 차단이 사용하도록 설정되어 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c9a1-163">You can confirm that block at first sight is enabled on individual clients using Windows security settings.</span></span>

<span data-ttu-id="7c9a1-164">클라우드 제공 보호 및 자동  샘플 제출이 모두 켜져 있는 한, 모든 시야 **차단이** 자동으로 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c9a1-164">Block at first sight is automatically enabled as long as **Cloud-delivered protection** and **Automatic sample submission** are both turned on.</span></span>

1. <span data-ttu-id="7c9a1-165">Windows 보안 앱을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c9a1-165">Open the Windows Security app.</span></span>

2. <span data-ttu-id="7c9a1-166">바이러스 **& 위협** 방지를 선택한 다음 바이러스 & **보호** 설정에서 설정 **관리를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="7c9a1-166">Select **Virus & threat protection**, and then, under **Virus & threat protection settings**, select **Manage Settings**.</span></span>

   ![Windows 보안 앱의 바이러스 & 보호 설정 레이블 스크린샷](images/defender/wdav-protection-settings-wdsc.png)

3. <span data-ttu-id="7c9a1-168">클라우드 제공 **보호 및** 자동 샘플 제출이 **모두** 켜져 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="7c9a1-168">Confirm that **Cloud-delivered protection** and **Automatic sample submission** are both turned on.</span></span>

> [!NOTE]
> - <span data-ttu-id="7c9a1-169">그룹 정책을 사용하여 선행 구성 설정이 구성 및 배포된 경우 이 섹션에 설명된 설정은 회색으로 표시됩니다. 개별 끝점에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7c9a1-169">If the prerequisite settings are configured and deployed using Group Policy, the settings described in this section will be greyed-out and unavailable for use on individual endpoints.</span></span> 
> - <span data-ttu-id="7c9a1-170">그룹 정책 개체를 통해 변경한 내용은 먼저 개별 끝점에 배포해야 설정이 Windows 설정에서 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c9a1-170">Changes made through a Group Policy Object must first be deployed to individual endpoints before the setting will be updated in Windows Settings.</span></span>

## <a name="validate-block-at-first-sight-is-working"></a><span data-ttu-id="7c9a1-171">모든 시 차단이 작동하고 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="7c9a1-171">Validate block at first sight is working</span></span>

<span data-ttu-id="7c9a1-172">기능이 작동하고 있는지 확인을 위해 네트워크와 클라우드 간의 연결 유효성 검사의 지침을 [따르하세요.](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud)</span><span class="sxs-lookup"><span data-stu-id="7c9a1-172">To validate that the feature is working, follow the guidance in [Validate connections between your network and the cloud](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud).</span></span>

## <a name="turn-off-block-at-first-sight"></a><span data-ttu-id="7c9a1-173">첫 번째 차단 끄기</span><span class="sxs-lookup"><span data-stu-id="7c9a1-173">Turn off block at first sight</span></span>

> [!CAUTION]
> <span data-ttu-id="7c9a1-174">차단을 끄면 디바이스와 네트워크의 보호 상태가 낮아집니다.</span><span class="sxs-lookup"><span data-stu-id="7c9a1-174">Turning off block at first sight will lower the protection state of your device(s) and your network.</span></span>

<span data-ttu-id="7c9a1-175">실제로 차단을 사용하지 않고 선행 설정을 유지하려는 경우 모든 시 차단을 사용하지 않도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c9a1-175">You might choose to disable block at first sight if you want to retain the prerequisite settings without actually using block at first sight protection.</span></span> <span data-ttu-id="7c9a1-176">대기 시간 문제가 발생하거나 기능이 네트워크에 미치는 영향을 테스트하려는 경우 일시적으로 차단을 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c9a1-176">You might do temporarily turn block at first sight off if you are experiencing latency issues or you want to test the feature's impact on your network.</span></span> <span data-ttu-id="7c9a1-177">그러나 최초 보호를 영구적으로 차단하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="7c9a1-177">However, we do not recommend disabling block at first sight protection permanently.</span></span>

### <a name="turn-off-block-at-first-sight-with-microsoft-endpoint-manager"></a><span data-ttu-id="7c9a1-178">Microsoft Endpoint Manager를 통해 중단 시 차단 끄기</span><span class="sxs-lookup"><span data-stu-id="7c9a1-178">Turn off block at first sight with Microsoft Endpoint Manager</span></span>

1. <span data-ttu-id="7c9a1-179">Microsoft Endpoint Manager 관리 센터()로 이동하여 [https://endpoint.microsoft.com](https://endpoint.microsoft.com) 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="7c9a1-179">Go to Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and sign in.</span></span>

2. <span data-ttu-id="7c9a1-180">끝점 보안 **바이러스 백신으로**  >  **이동한** 다음 Microsoft Defender 바이러스 백신 정책을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7c9a1-180">Go to **Endpoint security** > **Antivirus**, and then select your Microsoft Defender Antivirus policy.</span></span>

3. <span data-ttu-id="7c9a1-181">관리에서 속성을 **선택 합니다.** </span><span class="sxs-lookup"><span data-stu-id="7c9a1-181">Under **Manage**, choose **Properties**.</span></span>

4. <span data-ttu-id="7c9a1-182">구성 설정 **옆에 있는** 편집 **을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="7c9a1-182">Next to **Configuration settings**, choose **Edit**.</span></span>

5. <span data-ttu-id="7c9a1-183">다음 설정 중 하나 이상을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="7c9a1-183">Change one or more of the following settings:</span></span>

   - <span data-ttu-id="7c9a1-184">클라우드 **제공 보호 켜기 를** **구성** 안 되거나 **구성되지 않습니다.로 설정**</span><span class="sxs-lookup"><span data-stu-id="7c9a1-184">Set **Turn on cloud-delivered protection** to **No** or **Not configured**.</span></span>
   - <span data-ttu-id="7c9a1-185">클라우드 **제공 보호 수준을 구성되지** 않은 **으로 설정**</span><span class="sxs-lookup"><span data-stu-id="7c9a1-185">Set **Cloud-delivered protection level** to **Not configured**.</span></span>
   - <span data-ttu-id="7c9a1-186">**Defender 클라우드 확장 시간 제한(초) 상자의 선택을 취소합니다.**</span><span class="sxs-lookup"><span data-stu-id="7c9a1-186">Clear the **Defender Cloud Extended Timeout In Seconds** box.</span></span>

6. <span data-ttu-id="7c9a1-187">설정을 검토하고 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="7c9a1-187">Review and save your settings.</span></span>

### <a name="turn-off-block-at-first-sight-with-group-policy"></a><span data-ttu-id="7c9a1-188">그룹 정책을 통해 한시 차단 끄기</span><span class="sxs-lookup"><span data-stu-id="7c9a1-188">Turn off block at first sight with Group Policy</span></span>

1. <span data-ttu-id="7c9a1-189">그룹 정책 관리 컴퓨터에서 그룹 [](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))정책 관리 콘솔을 열고 구성할 그룹 정책 개체를 마우스 오른쪽 단추로 클릭한 다음 편집을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="7c9a1-189">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure, and then click **Edit**.</span></span>

2. <span data-ttu-id="7c9a1-190">그룹 정책 **관리 편집기를 사용하여** **컴퓨터 구성으로 이동하여** 관리 템플릿 **을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="7c9a1-190">Using the **Group Policy Management Editor** go to **Computer configuration** and click **Administrative templates**.</span></span>

3. <span data-ttu-id="7c9a1-191">Windows 구성 요소 **Microsoft** Defender 바이러스 백신  >  **MAPS를 통해 트리를**  >  **확장합니다.**</span><span class="sxs-lookup"><span data-stu-id="7c9a1-191">Expand the tree through **Windows components** > **Microsoft Defender Antivirus** > **MAPS**.</span></span>

4. <span data-ttu-id="7c9a1-192">**'최초 차단'** 기능 구성을 두 번 클릭하고 옵션을 사용 안 **하도록 설정 합니다.**</span><span class="sxs-lookup"><span data-stu-id="7c9a1-192">Double-click **Configure the 'Block at First Sight' feature** and set the option to **Disabled**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="7c9a1-193">차단을 최초로 사용하지 않도록 설정하면 선행 그룹 정책이 비활성화되거나 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7c9a1-193">Disabling block at first sight does not disable or alter the prerequisite group policies.</span></span>

## <a name="see-also"></a><span data-ttu-id="7c9a1-194">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7c9a1-194">See also</span></span>

- [<span data-ttu-id="7c9a1-195">Windows 10의 Microsoft Defender 바이러스 백신</span><span class="sxs-lookup"><span data-stu-id="7c9a1-195">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)

- [<span data-ttu-id="7c9a1-196">클라우드 제공 보호 사용</span><span class="sxs-lookup"><span data-stu-id="7c9a1-196">Enable cloud-delivered protection</span></span>](enable-cloud-protection-microsoft-defender-antivirus.md)