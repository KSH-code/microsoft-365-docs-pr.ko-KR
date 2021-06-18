---
title: 즉각적 차단 기능을 사용하여 몇 초 안에 맬웨어 검색
description: 즉각적 차단 기능을 켜면 몇 초 내에 맬웨어를 검색하고 차단합니다.
keywords: 검사, 즉각적 차단, 맬웨어, 즉각적, 클라우드, defender, 바이러스 백신
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Priority
author: denisebmsft
ms.author: deniseb
ms.reviewer: marcmcc
manager: dansimp
ms.custom: nextgen
ms.date: 06/17/2021
ms.technology: mde
ms.topic: article
ms.openlocfilehash: a6bcc023571e544819ae7f276e6c3af5c1fc1335
ms.sourcegitcommit: bbad1938b6661d4a6bca99f235c44e521b1fb662
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/18/2021
ms.locfileid: "53007404"
---
# <a name="turn-on-block-at-first-sight"></a><span data-ttu-id="55409-104">즉각적 차단 켜기</span><span class="sxs-lookup"><span data-stu-id="55409-104">Turn on block at first sight</span></span>

<span data-ttu-id="55409-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="55409-105">**Applies to:**</span></span>

- [<span data-ttu-id="55409-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="55409-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="55409-107">이 문서에서는 "즉각적 차단"으로 불리우는 바이러스 백신/맬웨어 방지 기능을 설명하고 조직에 대해 즉각적 차단을 사용하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="55409-107">This article describes an antivirus/antimalware feature known as "block at first sight", and describes how to enable block at first sight for your organization.</span></span> 

> [!TIP]
> <span data-ttu-id="55409-108">이 문서는 조직의 보안 설정을 관리하는 엔터프라이즈 관리자 및 IT 전문가를 대상으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="55409-108">This article is intended for enterprise admins and IT Pros who manage security settings for organizations.</span></span> <span data-ttu-id="55409-109">엔터프라이즈 관리자나 IT 전문가는 아니지만 즉각적 차단에 관한 질문이 있다면 [엔터프라이즈 관리자 또는 IT 전문가가 아니세요?](#not-an-enterprise-admin-or-it-pro) 구역을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="55409-109">If you are not an enteprise admin or IT Pro but you have questions about block at first sight, see the [Not an enterprise admin or IT Pro?](#not-an-enterprise-admin-or-it-pro) section.</span></span>

## <a name="what-is-block-at-first-sight"></a><span data-ttu-id="55409-110">“즉각적 차단”이란 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="55409-110">What is "block at first sight"?</span></span>

<span data-ttu-id="55409-111">즉각적 차단은 몇 초 내에 새로운 맬웨어를 검색하고 차단하는 차세대 보호의 위협 방지 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="55409-111">Block at first sight is a threat protection feature of next-generation protection that detects new malware and blocks it within seconds.</span></span> <span data-ttu-id="55409-112">특정 보안 설정을 사용하면 즉각적 차단이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="55409-112">Block at first sight is enabled when certain security settings are enabled.</span></span> <span data-ttu-id="55409-113">이러한 설정은 다음을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="55409-113">These settings include:</span></span>

- <span data-ttu-id="55409-114">클라우드 제공 보호;</span><span class="sxs-lookup"><span data-stu-id="55409-114">Cloud-delivered protection;</span></span> 
- <span data-ttu-id="55409-115">지정된 샘플 제출 시간 제한(예: 50초); 및</span><span class="sxs-lookup"><span data-stu-id="55409-115">A specified sample submission timeout (such as 50 seconds); and</span></span> 
- <span data-ttu-id="55409-116">높은 파일 차단 수준.</span><span class="sxs-lookup"><span data-stu-id="55409-116">A file-blocking level of high.</span></span> 

<span data-ttu-id="55409-117">대부분의 엔터프라이즈 조직에서 즉각적 차단 사용에 필요한 설정은 Microsoft Defender 바이러스 백신 배포로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="55409-117">In most enterprise organizations, the settings needed to enable block at first sight are configured with Microsoft Defender Antivirus deployments.</span></span> 

## <a name="how-it-works"></a><span data-ttu-id="55409-118">작동 방법</span><span class="sxs-lookup"><span data-stu-id="55409-118">How it works</span></span>

<span data-ttu-id="55409-119">Microsoft Defender 바이러스 백신은 의심스러우나 검색되지 않은 파일을 발견하면 클라우드 보호 백 엔드를 쿼리합니다.</span><span class="sxs-lookup"><span data-stu-id="55409-119">When Microsoft Defender Antivirus encounters a suspicious but undetected file, it queries our cloud protection backend.</span></span> <span data-ttu-id="55409-120">클라우드 백 엔드는 파일에 대한 추론, 기계 학습, 자동화된 분석을 적용하여 파일이 악성인지 위협이 아닌지 여부를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="55409-120">The cloud backend applies heuristics, machine learning, and automated analysis of the file to determine whether the files are malicious or not a threat.</span></span>

<span data-ttu-id="55409-121">Microsoft Defender 바이러스 백신은 여러 검색 및 방지 기술을 사용하여 정확하고 지능적인 실시간 보호를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="55409-121">Microsoft Defender Antivirus uses multiple detection and prevention technologies to deliver accurate, intelligent, and real-time protection.</span></span> 

![Microsoft Defender AV 엔진 목록](images/microsoft-defender-atp-next-generation-protection-engines.png)  

> [!TIP]
> <span data-ttu-id="55409-123">자세한 내용은 [(블로그) 차세대 보호 엔드포인트용 Microsoft Defender의 핵심 고급 기술 알아보기](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="55409-123">To learn more, see [(Blog) Get to know the advanced technologies at the core of Microsoft Defender for Endpoint next-generation protection](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/).</span></span>

## <a name="a-few-things-to-know-about-block-at-first-sight"></a><span data-ttu-id="55409-124">즉각적 차단에 대해 알아야 할 몇 가지</span><span class="sxs-lookup"><span data-stu-id="55409-124">A few things to know about block at first sight</span></span>

- <span data-ttu-id="55409-125">Windows 10 버전 1803 이상에서는 즉각적 차단을 통해 이식 불가능한 실행 파일(예: JS, VBS 또는 매크로) 및 실행 파일을 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55409-125">In Windows 10, version 1803 or later, block at first sight can block non-portable executable files (such as JS, VBS, or macros) and executable files.</span></span>

- <span data-ttu-id="55409-126">즉각적 차단은 인터넷에서 다운로드하거나 인터넷 영역에서 발생하는 실행 파일 및 이식 불가능한 실행 파일에 대해서만 클라우드 보호 백 엔드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="55409-126">Block at first sight only uses the cloud protection backend for executable files and non-portable executable files that are downloaded from the Internet, or that originate from the Internet zone.</span></span> <span data-ttu-id="55409-127">이전에 검색되지 않은 파일인지 확인하기 위해 클라우드 백 엔드를 통해 .exe 파일의 해시 값을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="55409-127">A hash value of the .exe file is checked via the cloud backend to determine if the file is a previously undetected file.</span></span>

- <span data-ttu-id="55409-128">클라우드 백 엔드에서 결정을 할 수 없는 경우 Microsoft Defender 바이러스 백신에서 파일을 잠그고 클라우드에 복사본을 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="55409-128">If the cloud backend is unable to make a determination, Microsoft Defender Antivirus locks the file and uploads a copy to the cloud.</span></span> <span data-ttu-id="55409-129">클라우드는 추가 분석을 수행하여 파일이 악성인지 위협이 아닌지 여부에 따라 앞으로 발생하는 모든 경우에 대해 파일을 실행하거나 차단하도록 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="55409-129">The cloud performs more analysis to reach a determination before it either allows the file to run or blocks it in all future encounters, depending on whether it determines the file to be malicious or not a threat.</span></span>

- <span data-ttu-id="55409-130">대부분의 경우 이 프로세스를 통해 새 맬웨어에 대한 응답 시간을 초 단위로 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55409-130">In many cases, this process can reduce the response time for new malware from hours to seconds.</span></span>

- <span data-ttu-id="55409-131">클라우드 기반 보호 서비스가 파일을 분석하는 동안 [파일 실행을 금지할 시간을 지정](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55409-131">You can [specify how long a file should be prevented from running](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md) while the cloud-based protection service analyzes the file.</span></span> <span data-ttu-id="55409-132">또한 파일이 차단될 때 [사용자의 데스크톱에 표시되는 메시지를 사용자 지정](/windows/security/threat-protection//windows-defender-security-center/wdsc-customize-contact-information.md)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55409-132">And, you can [customize the message displayed on users' desktops](/windows/security/threat-protection//windows-defender-security-center/wdsc-customize-contact-information.md) when a file is blocked.</span></span> <span data-ttu-id="55409-133">회사 이름, 연락처 정보 및 메시지 URL을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55409-133">You can change the company name, contact information, and message URL.</span></span>

## <a name="turn-on-block-at-first-sight-with-microsoft-intune"></a><span data-ttu-id="55409-134">Microsoft Intune으로 즉각적 차단 켜기</span><span class="sxs-lookup"><span data-stu-id="55409-134">Turn on block at first sight with Microsoft Intune</span></span>

> [!TIP]
> <span data-ttu-id="55409-135">Microsoft Intune은 이제 Microsoft Endpoint Manager의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="55409-135">Microsoft Intune is now part of Microsoft Endpoint Manager.</span></span>

1. <span data-ttu-id="55409-136">Microsoft Endpoint Manager 관리 센터([https://endpoint.microsoft.com](https://endpoint.microsoft.com))에서 **장치** > **구성 프로필** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="55409-136">In the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)), navigate to **Devices** > **Configuration profiles**.</span></span>

2. <span data-ttu-id="55409-137">**장치 제한** 프로필 유형을 사용하여 프로필을 선택하거나 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="55409-137">Select or create a profile using the **Device restrictions** profile type.</span></span>

3. <span data-ttu-id="55409-138">장치 제한 프로필의 **구성 설정** 에서 **Microsoft Defender 바이러스 백신** 에 있는 다음 설정을 수행하거나 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="55409-138">In the **Configuration settings** for the Device restrictions profile, set or confirm the following settings under **Microsoft Defender Antivirus**:</span></span>

   - <span data-ttu-id="55409-139">**클라우드 제공 보호**: 사용</span><span class="sxs-lookup"><span data-stu-id="55409-139">**Cloud-delivered protection**: Enabled</span></span>
   - <span data-ttu-id="55409-140">**파일 차단 수준**: 높음</span><span class="sxs-lookup"><span data-stu-id="55409-140">**File Blocking Level**: High</span></span>
   - <span data-ttu-id="55409-141">**클라우드에서 파일을 검사하는 시간 확장**: 50</span><span class="sxs-lookup"><span data-stu-id="55409-141">**Time extension for file scanning by the cloud**: 50</span></span>
   - <span data-ttu-id="55409-142">**샘플 제출 전 사용자에게 메시지 표시**: 묻지 않고 모든 데이터 보내기</span><span class="sxs-lookup"><span data-stu-id="55409-142">**Prompt users before sample submission**: Send all data without prompting</span></span>

   :::image type="content" source="../../media/intune-block-at-first-sight.png" alt-text="즉각적 Intune 구성 블록":::

4. <span data-ttu-id="55409-144">설정을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="55409-144">Save your settings.</span></span>

> [!TIP]
> - <span data-ttu-id="55409-145">파일 차단 수준을 **높음** 으로 설정하면 강력한 검색 수준이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="55409-145">Setting the file blocking level to **High** applies a strong level of detection.</span></span> <span data-ttu-id="55409-146">파일 차단으로 인해 적법한 파일이 가양성 검색으로 드물게 오인되는 경우, 보안 운영 팀에서 [격리된 파일을 복원](./restore-quarantined-files-microsoft-defender-antivirus.md)하는 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55409-146">In the unlikely event that file blocking causes a false positive detection of legitimate files, your security operations team can [restore quarantined files](./restore-quarantined-files-microsoft-defender-antivirus.md).</span></span>
> - <span data-ttu-id="55409-147">Intune에서 Microsoft Defender 바이러스 백신 장치 제한을 구성하는 방법에 대한 자세한 내용은 [Microsoft Intune에서 장치 제한 설정 구성](/intune/device-restrictions-configure)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="55409-147">For more information about configuring Microsoft Defender Antivirus device restrictions in Intune, see [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure).</span></span>
> - <span data-ttu-id="55409-148">Intune의 Microsoft Defender 바이러스 백신 장치 제한 목록은 [Intune에서 Windows 10(및 최신 버전) 설정에 대한 장치 제한](/intune/device-restrictions-windows-10#microsoft-defender-antivirus)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="55409-148">For a list of Microsoft Defender Antivirus device restrictions in Intune, see [Device restriction for Windows 10 (and newer) settings in Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus).</span></span>

## <a name="turn-on-block-at-first-sight-with-microsoft-endpoint-manager"></a><span data-ttu-id="55409-149">Microsoft Endpoint Manager를 사용하여 즉각적 차단 켜기</span><span class="sxs-lookup"><span data-stu-id="55409-149">Turn on block at first sight with Microsoft Endpoint Manager</span></span>

> [!TIP]
> <span data-ttu-id="55409-150">Microsoft Endpoint Configuration Manager는 이제 Microsoft Endpoint Manager의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="55409-150">If you're looking for Microsoft Endpoint Configuration Manager, it's now part of Microsoft Endpoint Manager.</span></span>

1. <span data-ttu-id="55409-151">Microsoft Endpoint Manager([https://endpoint.microsoft.com](https://endpoint.microsoft.com))에서 **엔드포인트 보안** > **바이러스 백신** 으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="55409-151">In Microsoft Endpoint Manager ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)), go to **Endpoint security** > **Antivirus**.</span></span>

2. <span data-ttu-id="55409-152">기존 정책을 선택하거나 **Microsoft Defender 바이러스 백신** 프로필 유형을 사용하여 새 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="55409-152">Select an existing policy, or create a new policy using the **Microsoft Defender Antivirus** profile type.</span></span>

3. <span data-ttu-id="55409-153">다음 구성 설정을 수행하거나 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="55409-153">Set or confirm the following configuration settings:</span></span>

   - <span data-ttu-id="55409-154">**클라우드 제공 보호 켜기**: 예</span><span class="sxs-lookup"><span data-stu-id="55409-154">**Turn on cloud-delivered protection**: Yes</span></span>
   - <span data-ttu-id="55409-155">**클라우드 제공 보호 수준**: 높음</span><span class="sxs-lookup"><span data-stu-id="55409-155">**Cloud-delivered protection level**: High</span></span>
   - <span data-ttu-id="55409-156">**Defender Cloud 확장 시간 초과(초)**: 50</span><span class="sxs-lookup"><span data-stu-id="55409-156">**Defender Cloud Extended Timeout in Seconds**: 50</span></span>

   :::image type="content" source="images/endpointmgr-antivirus-cloudprotection.png" alt-text="Endpoint Manager에서 즉각적 차단 설정":::

4. <span data-ttu-id="55409-158">Microsoft Defender 바이러스 백신 프로필을 **모든 사용자**, **모든 장치** 또는 **모든 사용자 및 장치** 와 같은 그룹에 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="55409-158">Apply the Microsoft Defender Antivirus profile to a group, such as **All users**, **All devices**, or **All users and devices**.</span></span>

## <a name="turn-on-block-at-first-sight-with-group-policy"></a><span data-ttu-id="55409-159">그룹 정책으로 즉각적 차단 켜기</span><span class="sxs-lookup"><span data-stu-id="55409-159">Turn on block at first sight with Group Policy</span></span>

> [!NOTE]
> <span data-ttu-id="55409-160">Intune 또는 Microsoft Endpoint Manager를 사용하여 즉각적 차단을 켜는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="55409-160">We recommend using Intune or Microsoft Endpoint Manager to turn on block at first sight.</span></span> 

1. <span data-ttu-id="55409-161">그룹 정책 관리 컴퓨터에서 [그룹 정책 관리 콘솔](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))을 열고 구성하려는 그룹 정책 개체를 마우스 오른쪽 단추로 클릭한 다음 **편집** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="55409-161">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and select **Edit**.</span></span> 

2. <span data-ttu-id="55409-162">**그룹 정책 관리 편집기** 를 사용하여 **컴퓨터 구성** > **관리 템플릿** > **Windows 구성 요소** > **Microsoft Defender 바이러스 백신** > **MAPS** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="55409-162">Using the **Group Policy Management Editor** go to **Computer configuration** > **Administrative templates** > **Windows Components** > **Microsoft Defender Antivirus** > **MAPS**.</span></span> 

3. <span data-ttu-id="55409-163">MAPS 섹션에서 **'즉각적 차단' 기능 구성** 을 두 번 클릭하여 **사용함** 으로 설정한 다음 **확인** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="55409-163">In the MAPS section, double-click **Configure the 'Block at First Sight' feature**, and set it to **Enabled**, and then select **OK**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="55409-164">**항상 확인(0)** 으로 설정하면 장치의 보호 상태가 낮아집니다.</span><span class="sxs-lookup"><span data-stu-id="55409-164">Setting to **Always prompt (0)** will lower the protection state of the device.</span></span> <span data-ttu-id="55409-165">**보내지 않음(2)** 으로 설정하면 즉각적 차단 기능이 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="55409-165">Setting to **Never send (2)** means block at first sight will not function.</span></span>

4. <span data-ttu-id="55409-166">MAPS 섹션에서 **추가 분석 필요시 파일 샘플 보내기** 를 두 번 클릭하여 **사용함** 으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="55409-166">In the MAPS section, double-click **Send file samples when further analysis is required**, and set it to **Enabled**.</span></span> <span data-ttu-id="55409-167">**추가 분석이 필요할 때 파일 샘플 보내기** 에서 **모든 샘플 보내기** 를 선택한 다음 **확인** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="55409-167">Under **Send file samples when further analysis is required**, select **Send all samples**, and then select **OK**.</span></span>

5. <span data-ttu-id="55409-168">평소와 같이 네트워크에서 그룹 정책 개체를 다시 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="55409-168">Redeploy your Group Policy Object across your network as you usually do.</span></span>

## <a name="confirm-block-at-first-sight-is-enabled-on-individual-client-devices"></a><span data-ttu-id="55409-169">개별 클라이언트 장치에서 즉각적 차단을 사용하는지 확인</span><span class="sxs-lookup"><span data-stu-id="55409-169">Confirm block at first sight is enabled on individual client devices</span></span>

<span data-ttu-id="55409-170">Windows 보안 앱을 사용하는 개별 클라이언트 장치에 즉각적 차단 기능이 설정되어 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55409-170">You can confirm that block at first sight is enabled on individual client devices using the Windows Security app.</span></span> <span data-ttu-id="55409-171">**클라우드 제공 보호** 와 **자동 샘플 제출** 이 모두 켜져 있는 한 즉각적 차단이 자동으로 사용 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="55409-171">Block at first sight is automatically enabled as long as **Cloud-delivered protection** and **Automatic sample submission** are both turned on.</span></span>

1. <span data-ttu-id="55409-172">Windows 보안 앱을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="55409-172">Open the Windows Security app.</span></span>

2. <span data-ttu-id="55409-173">**바이러스 및 위협 방지** 를 선택한 다음 **바이러스 및 위협 방지 설정** 에서 **설정 관리** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="55409-173">Select **Virus & threat protection**, and then, under **Virus & threat protection settings**, select **Manage Settings**.</span></span>

   :::image type="content" source="../../media/wdav-protection-settings-wdsc.png" alt-text="Windows 보안 앱의 바이러스 및 위협 방지 설정 레이블 스크린샷":::

3. <span data-ttu-id="55409-175">**클라우드 제공 보호** 및 **자동 샘플 제출** 이 모두 켜져있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="55409-175">Confirm that **Cloud-delivered protection** and **Automatic sample submission** are both turned on.</span></span>

> [!NOTE]
> - <span data-ttu-id="55409-176">그룹 정책을 사용하여 필수 구성 요소 설정을 구성하고 배포하는 경우 이 섹션에 설명된 설정은 회색으로 표시되어 개별 엔드포인트에서 사용할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="55409-176">If the prerequisite settings are configured and deployed using Group Policy, the settings described in this section will be greyed-out and unavailable for use on individual endpoints.</span></span> 
> - <span data-ttu-id="55409-177">설정이 Windows 설정에서 업데이트되기 전에 먼저 그룹 정책 개체를 통해 수행한 변경을 개별 엔드포인트에 배포해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="55409-177">Changes made through a Group Policy Object must first be deployed to individual endpoints before the setting will be updated in Windows Settings.</span></span>

## <a name="validate-block-at-first-sight-is-working"></a><span data-ttu-id="55409-178">즉각적 차단이 작동 중인지 확인</span><span class="sxs-lookup"><span data-stu-id="55409-178">Validate block at first sight is working</span></span>

<span data-ttu-id="55409-179">기능이 제대로 작동하는지 확인하려면 [즉각적 차단 샘플 파일](https://demo.wd.microsoft.com/Page/BAFS)을 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="55409-179">To validate that the feature is working, download the [Block at first sight sample file](https://demo.wd.microsoft.com/Page/BAFS).</span></span> <span data-ttu-id="55409-180">파일을 다운로드하려면 보안 관리자 또는 전역 관리자 역할이 할당된 Azure Active Directory 계정이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="55409-180">To download the file, you will need an account in Azure AD that has either the Security Administrator or Global Administrator role assigned.</span></span>

<span data-ttu-id="55409-181">클라우드 지원 보호가 제대로 작동하는지 확인하려면 [네트워크와 클라우드 간 연결 확인](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud) 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="55409-181">To validate that cloud-enabled protection is working, follow the guidance in [Validate connections between your network and the cloud](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud).</span></span> 

## <a name="turn-off-block-at-first-sight"></a><span data-ttu-id="55409-182">즉각적 차단 끄기</span><span class="sxs-lookup"><span data-stu-id="55409-182">Turn off block at first sight</span></span>

> [!CAUTION]
> <span data-ttu-id="55409-183">즉각적 차단을 끄면 장치와 네트워크의 보호 상태가 낮아집니다.</span><span class="sxs-lookup"><span data-stu-id="55409-183">Turning off block at first sight will lower the protection state of your device(s) and your network.</span></span>

<span data-ttu-id="55409-184">실제로 즉각적 차단 보호를 사용하지 않고 필수 구성 요소 설정을 유지하려는 경우 즉각적 차단을 사용하지 않도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55409-184">You might choose to disable block at first sight if you want to retain the prerequisite settings without actually using block at first sight protection.</span></span> <span data-ttu-id="55409-185">이 기능이 네트워크에 어떤 영향을 주는지 확인하기 위해 일시적으로 즉각적 차단을 끌 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55409-185">You might temporarily turn block at first sight off to see how this feature affects your network.</span></span> <span data-ttu-id="55409-186">그러나 즉각적 차단 보호를 영구적으로 사용 중지하는 것은 권장되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="55409-186">However, we do not recommend disabling block at first sight protection permanently.</span></span>

### <a name="turn-off-block-at-first-sight-with-microsoft-endpoint-manager"></a><span data-ttu-id="55409-187">Microsoft Endpoint Manager를 사용하여 즉각적 차단 끄기</span><span class="sxs-lookup"><span data-stu-id="55409-187">Turn off block at first sight with Microsoft Endpoint Manager</span></span>

1. <span data-ttu-id="55409-188">Microsoft Endpoint Manager 관리 센터([https://endpoint.microsoft.com](https://endpoint.microsoft.com))로 이동하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="55409-188">Go to Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and sign in.</span></span>

2. <span data-ttu-id="55409-189">**엔드포인트 보안** > **바이러스 백신** 으로 이동한 다음 Microsoft Defender 바이러스 백신 정책을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="55409-189">Go to **Endpoint security** > **Antivirus**, and then select your Microsoft Defender Antivirus policy.</span></span>

3. <span data-ttu-id="55409-190">**관리** 에서 **속성** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="55409-190">Under **Manage**, choose **Properties**.</span></span>

4. <span data-ttu-id="55409-191">**구성 설정** 옆의 **편집** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="55409-191">Next to **Configuration settings**, choose **Edit**.</span></span>

5. <span data-ttu-id="55409-192">다음 설정 중 하나 이상을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="55409-192">Change one or more of the following settings:</span></span>

   - <span data-ttu-id="55409-193">**클라우드 제공 보호 켜기** 를 **아니요** 또는 **구성되지 않음** 으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="55409-193">Set **Turn on cloud-delivered protection** to **No** or **Not configured**.</span></span>
   - <span data-ttu-id="55409-194">**클라우드 제공 보호 켜기** 를 **구성되지 않음** 으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="55409-194">Set **Cloud-delivered protection level** to **Not configured**.</span></span>
   - <span data-ttu-id="55409-195">**Defender Cloud 확장 시간 초과(초)** 확인란을 선택 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="55409-195">Clear the check box for **Defender Cloud Extended Timeout In Seconds**.</span></span>

6. <span data-ttu-id="55409-196">설정을 검토한 후 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="55409-196">Review and save your settings.</span></span>

### <a name="turn-off-block-at-first-sight-with-group-policy"></a><span data-ttu-id="55409-197">그룹 정책을 사용하여 즉각적 차단 끄기</span><span class="sxs-lookup"><span data-stu-id="55409-197">Turn off block at first sight with Group Policy</span></span>

1. <span data-ttu-id="55409-198">그룹 정책 관리 컴퓨터에서 [그룹 정책 관리 콘솔](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))을 열고 구성하려는 그룹 정책 개체를 마우스 오른쪽 단추로 클릭한 다음 **편집** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="55409-198">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure, and then select **Edit**.</span></span>

2. <span data-ttu-id="55409-199">**그룹 정책 관리 편집기** 를 사용해서 **컴퓨터 구성** 으로 이동하여 **관리 템플릿** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="55409-199">Using the **Group Policy Management Editor** go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="55409-200">**Windows 구성 요소** > **Microsoft Defender 바이러스 백신** > **MAPS** 를 통해 트리를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="55409-200">Expand the tree through **Windows components** > **Microsoft Defender Antivirus** > **MAPS**.</span></span>

4. <span data-ttu-id="55409-201">**'즉각적 차단' 기능 구성** 을 두 번 클릭하고 옵션을 **사용 안 함** 으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="55409-201">Double-click **Configure the 'Block at First Sight' feature** and set the option to **Disabled**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="55409-202">즉각적 차단을 사용하지 않아도 필수 구성 요소 그룹 정책이 사용 중지되거나 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="55409-202">Disabling block at first sight does not disable or alter the prerequisite group policies.</span></span>

## <a name="not-an-enterprise-admin-or-it-pro"></a><span data-ttu-id="55409-203">엔터프라이즈 관리자나 IT 전문가가 아니세요?</span><span class="sxs-lookup"><span data-stu-id="55409-203">Not an enterprise admin or IT Pro?</span></span>

<span data-ttu-id="55409-204">엔터프라이즈 관리자 또는 IT 전문가는 아니지만 즉각적 차단에 대한 질문이 있는 경우 이 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="55409-204">If you are not an enterprise admin or IT Pro, but you have questions about block at first sight, this section is for you.</span></span> <span data-ttu-id="55409-205">즉각적 차단은 맬웨어를 몇 초 내에 검색하고 차단하는 위협 방지 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="55409-205">Block at first sight is a threat protection feature that detects and blocks malware within seconds.</span></span> <span data-ttu-id="55409-206">"즉각적 차단"이라 불리우는 특정 설정이 있는 것은 아니지만 장치에 특정 설정이 구성되면 이 기능이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="55409-206">Although there isn't a specific setting called "Block at first sight," the feature is enabled when certain settings are configured on your device.</span></span>

### <a name="how-to-manage-block-at-first-sight-on-or-off-on-your-own-device"></a><span data-ttu-id="55409-207">자신의 장치에서 즉각적 차단을 켜거나 끄는 것을 관리하는 방법</span><span class="sxs-lookup"><span data-stu-id="55409-207">How to manage block at first sight on or off on your own device</span></span>

<span data-ttu-id="55409-208">조직에서 관리하지 않는 개인 장치가 있는 경우 즉각적 차단을 켜거나 끄는 방법에 대해 궁금할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55409-208">If you have a personal device that is not managed by an organization, you might be wondering how to turn block at first sight on or off.</span></span> <span data-ttu-id="55409-209">Windows 보안 앱을 사용하여 즉각적 차단을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55409-209">You can use the Windows Security app to manage block at first sight.</span></span>

1. <span data-ttu-id="55409-210">Windows 10 컴퓨터에서 Windows 보안 앱을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="55409-210">On your Windows 10 computer, open the Windows Security app.</span></span>

2. <span data-ttu-id="55409-211">**바이러스 및 위협 방지** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="55409-211">Select **Virus & threat protection**.</span></span>

3. <span data-ttu-id="55409-212">**바이러스 및 위협 방지 설정** 에서 **설정 관리** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="55409-212">Under **Virus & threat protection settings**, select **Manage settings**.</span></span>

4. <span data-ttu-id="55409-213">다음 단계 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="55409-213">Take one of the following steps:</span></span>

   - <span data-ttu-id="55409-214">즉각적 차단을 사용하려면 **클라우드 제공 보호** 와 **자동 샘플 제출** 이 모두 켜져 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="55409-214">To enable block at first sight, make sure that both **Cloud-delivered protection** and **Automatic sample submission** are both turned on.</span></span>

   - <span data-ttu-id="55409-215">즉각적 차단을 사용하지 않으려면 **클라우드 제공 보호** 또는 **자동 샘플 제출** 을 끕니다.</span><span class="sxs-lookup"><span data-stu-id="55409-215">To disable block at first sight, turn off **Cloud-delivered protection** or **Automatic sample submission**.</span></span> <br/>
    
     > [!CAUTION]
     > <span data-ttu-id="55409-216">즉각적 차단을 끄면 장치의 보호 수준이 낮아집니다.</span><span class="sxs-lookup"><span data-stu-id="55409-216">Turning off block at first sight lowers the level of protection for your device.</span></span> <span data-ttu-id="55409-217">즉각적 차단을 영구적으로 사용 중지하는 것은 권장되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="55409-217">We do not recommend permanently disabling block at first sight.</span></span> 


## <a name="see-also"></a><span data-ttu-id="55409-218">참고 항목</span><span class="sxs-lookup"><span data-stu-id="55409-218">See also</span></span>

- [<span data-ttu-id="55409-219">Windows 10의 Microsoft Defender 바이러스 백신</span><span class="sxs-lookup"><span data-stu-id="55409-219">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="55409-220">클라우드 제공 보호 사용</span><span class="sxs-lookup"><span data-stu-id="55409-220">Enable cloud-delivered protection</span></span>](enable-cloud-protection-microsoft-defender-antivirus.md)
- [<span data-ttu-id="55409-221">Windows 보안으로 보호 유지</span><span class="sxs-lookup"><span data-stu-id="55409-221">Stay protected with Windows Security</span></span>](https://support.microsoft.com/windows/stay-protected-with-windows-security-2ae0363d-0ada-c064-8b56-6a39afb6a963)
