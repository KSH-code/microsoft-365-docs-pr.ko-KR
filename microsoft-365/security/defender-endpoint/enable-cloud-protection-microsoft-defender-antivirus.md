---
title: Microsoft Defender 바이러스 백신 클라우드 로 배달된 보호 기능 켜기
description: 빠르고 고급 보호 기능을 통해 클라우드로 제공되는 보호 기능을 켭니다.
keywords: Microsoft Defender 바이러스 백신, 맬웨어 방지, 보안, 클라우드, 첫눈에 차단
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.date: 05/18/2021
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 8c45fb4b60e3c20c2001cc0008ecc8154e854273
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572060"
---
# <a name="turn-on-cloud-delivered-protection"></a><span data-ttu-id="bf1c5-104">클라우드 제공 보호 켜기</span><span class="sxs-lookup"><span data-stu-id="bf1c5-104">Turn on cloud-delivered protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="bf1c5-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="bf1c5-105">**Applies to:**</span></span>

- [<span data-ttu-id="bf1c5-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="bf1c5-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

> [!NOTE]
> <span data-ttu-id="bf1c5-107">Microsoft Defender 바이러스 백신 클라우드 서비스는 네트워크 및 끝점에 업데이트된 보호를 제공하는 메커니즘입니다.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-107">The Microsoft Defender Antivirus cloud service is a mechanism for delivering updated protection to your network and endpoints.</span></span> <span data-ttu-id="bf1c5-108">클라우드 서비스라고 하지만 클라우드에 저장된 파일을 보호하는 것은 아닙니다. 오히려 분산 리소스와 머신 러닝을 사용하여 기존 보안 인텔리전스 업데이트보다 훨씬 빠른 속도로 엔드포인트에 대한 보호를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-108">Although it is called a cloud service, it is not simply protection for files stored in the cloud; rather, it uses distributed resources and machine learning to deliver protection to your endpoints at a rate that is far faster than traditional Security intelligence updates.</span></span>

<span data-ttu-id="bf1c5-109">Microsoft Defender 바이러스 백신 여러 탐지 및 예방 기술을 사용하여 정확하고 실시간으로 지능형 보호를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-109">Microsoft Defender Antivirus uses multiple detection and prevention technologies to deliver accurate, real-time, and intelligent protection.</span></span> <span data-ttu-id="bf1c5-110">[엔드포인트 차세대 보호를 위한 Microsoft Defender의 핵심에 있는 첨단 기술을 알아보십시오.](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/)</span><span class="sxs-lookup"><span data-stu-id="bf1c5-110">[Get to know the advanced technologies at the core of Microsoft Defender for Endpoint next-generation protection](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/).</span></span>

<span data-ttu-id="bf1c5-111">다음과 같은 여러 가지 방법으로 클라우드로 제공되는 보호 기능을 켜거나 끌 Microsoft Defender 바이러스 백신 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-111">You can turn Microsoft Defender Antivirus cloud-delivered protection on or off in several ways:</span></span>

- <span data-ttu-id="bf1c5-112">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="bf1c5-112">Microsoft Intune</span></span>
- <span data-ttu-id="bf1c5-113">Microsoft Endpoint Manager </span><span class="sxs-lookup"><span data-stu-id="bf1c5-113">Microsoft Endpoint Manager</span></span>
- <span data-ttu-id="bf1c5-114">그룹 정책</span><span class="sxs-lookup"><span data-stu-id="bf1c5-114">Group Policy</span></span>
- <span data-ttu-id="bf1c5-115">파워쉘 cmdlets.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-115">PowerShell cmdlets.</span></span>

 <span data-ttu-id="bf1c5-116">또한 Windows 보안 앱을 통해 개별 클라이언트에서 켜거나 끌 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-116">You can also turn it on or off in individual clients with the Windows Security app.</span></span>

<span data-ttu-id="bf1c5-117">클라우드로 제공되는 보호 에 대한 개요는 [microsoft 클라우드에서 제공하는 보호 사용을](cloud-protection-microsoft-defender-antivirus.md) 참조Microsoft Defender 바이러스 백신</span><span class="sxs-lookup"><span data-stu-id="bf1c5-117">See [Use Microsoft cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) for an overview of Microsoft Defender Antivirus cloud-delivered protection.</span></span>

<span data-ttu-id="bf1c5-118">엔드포인트가 클라우드 제공 보호 서비스에 연결할 수 있도록 특정 네트워크 연결 요구 사항에 대한 자세한 내용은 [네트워크 연결 구성 및 유효성을 검사합니다.](configure-network-connections-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="bf1c5-118">For more information about the specific network-connectivity requirements to ensure your endpoints can connect to the cloud-delivered protection service, see [Configure and validate network connections](configure-network-connections-microsoft-defender-antivirus.md).</span></span>

> [!NOTE]
> <span data-ttu-id="bf1c5-119">Windows 10 이 항목에 설명된 **기본** 및 **고급** 보고 옵션 간에는 차이가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-119">In Windows 10, there is no difference between the **Basic** and **Advanced** reporting options described in this topic.</span></span> <span data-ttu-id="bf1c5-120">이는 레거시 구분이며 두 설정을 선택하면 동일한 수준의 클라우드 전달 보호가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-120">This is a legacy distinction and choosing either setting will result in the same level of cloud-delivered protection.</span></span> <span data-ttu-id="bf1c5-121">공유되는 정보의 유형이나 양에는 차이가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-121">There is no difference in the type or amount of information that is shared.</span></span> <span data-ttu-id="bf1c5-122">당사가 수집하는 내용에 대한 자세한 내용은 [Microsoft 개인 정보 보호 정책을](https://go.microsoft.com/fwlink/?linkid=521839)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-122">For more information on what we collect, see the [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=521839).</span></span>

## <a name="use-intune-to-turn-on-cloud-delivered-protection"></a><span data-ttu-id="bf1c5-123">Intune을 사용하여 클라우드 로 배달된 보호 기능을 켭니다.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-123">Use Intune to turn on cloud-delivered protection</span></span>

1. <span data-ttu-id="bf1c5-124">Microsoft Endpoint Manager 관리 [https://endpoint.microsoft.com](https://endpoint.microsoft.com) 센터()로 이동하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-124">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and log in.</span></span>

2. <span data-ttu-id="bf1c5-125">**홈** 창에서 **프로파일을 > 장치 구성을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="bf1c5-125">On the **Home** pane, select **Device configuration > Profiles**.</span></span>

3. <span data-ttu-id="bf1c5-126">구성할 **장치 제한** 프로필 유형을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-126">Select the **Device restrictions** profile type you want to configure.</span></span> <span data-ttu-id="bf1c5-127">새 **장치 제한** 프로필 유형을 만들어야 하는 경우 Microsoft Intune 장치 제한 [설정 구성을](/intune/device-restrictions-configure)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-127">If you need to create a new **Device restrictions** profile type, see [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure).</span></span>

4. <span data-ttu-id="bf1c5-128">**속성**  >  **구성 설정 선택:**  >  Microsoft Defender 바이러스 백신 편집할 수 **있습니다.**</span><span class="sxs-lookup"><span data-stu-id="bf1c5-128">Select **Properties** > **Configuration settings: Edit** > **Microsoft Defender Antivirus**.</span></span>

5. <span data-ttu-id="bf1c5-129">**클라우드제공 보호** 스위치에서 **사용 가능을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="bf1c5-129">On the **Cloud-delivered protection** switch, select **Enable**.</span></span>

6. <span data-ttu-id="bf1c5-130">샘플 제출 드롭다운 **전에 프롬프트 사용자에서** **모든 데이터 보내기를 자동으로 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="bf1c5-130">In the **Prompt users before sample submission** dropdown, select **Send all data automatically**.</span></span>

<span data-ttu-id="bf1c5-131">설정을 만들고 구성하는 방법을 포함하여 Intune 장치 프로필에 대한 자세한 내용은 [장치 프로필에 Microsoft Intune 무엇입니까?](/intune/device-profiles)</span><span class="sxs-lookup"><span data-stu-id="bf1c5-131">For more information about Intune device profiles, including how to create and configure their settings, see [What are Microsoft Intune device profiles?](/intune/device-profiles)</span></span>

## <a name="use-microsoft-endpoint-manager-to-turn-on-cloud-delivered-protection"></a><span data-ttu-id="bf1c5-132">Microsoft Endpoint Manager 사용하여 클라우드 로 배달된 보호 기능을 켭니다.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-132">Use Microsoft Endpoint Manager to turn on cloud-delivered protection</span></span>

1. <span data-ttu-id="bf1c5-133">Microsoft Endpoint Manager 관리 [https://endpoint.microsoft.com](https://endpoint.microsoft.com) 센터()로 이동하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-133">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and log in.</span></span>

2. <span data-ttu-id="bf1c5-134">**엔드포인트 보안**  >  **바이러스 백신을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="bf1c5-134">Choose **Endpoint security** > **Antivirus**.</span></span>

3. <span data-ttu-id="bf1c5-135">바이러스 백신 프로파일을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-135">Select an antivirus profile.</span></span> <span data-ttu-id="bf1c5-136">아직 프로필이 없거나 새 프로필을 만들려는 경우 [Microsoft Intune 장치 제한 설정 구성을](/intune/device-restrictions-configure)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-136">(If you don't have one yet, or if you want to create a new profile, see [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure).</span></span>

4. <span data-ttu-id="bf1c5-137">**속성을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="bf1c5-137">Select **Properties**.</span></span> <span data-ttu-id="bf1c5-138">그런 다음 **구성 설정** 옆에 **편집을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="bf1c5-138">Then, next to **Configuration settings**, choose **Edit**.</span></span>

5. <span data-ttu-id="bf1c5-139">**클라우드 보호를** 확장한 다음 **클라우드에서 제공하는 보호 수준** 목록에서 다음 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-139">Expand **Cloud protection**, and then in the **Cloud-delivered protection level** list, select one of the following:</span></span>
   - <span data-ttu-id="bf1c5-140">**높음**: 강력한 수준의 감지를 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-140">**High**: Applies a strong level of detection.</span></span>
   - <span data-ttu-id="bf1c5-141">**높음 :** **높은** 수준을 사용하고 추가 보호 조치를 적용합니다(고객 성능에 영향을 미칠 수 있음).</span><span class="sxs-lookup"><span data-stu-id="bf1c5-141">**High plus**: Uses the **High** level and applies additional protection measures (may impact client performance).</span></span>
   - <span data-ttu-id="bf1c5-142">**무관용**: 알 수 없는 모든 실행판을 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-142">**Zero tolerance**: Blocks all unknown executables.</span></span>

6. <span data-ttu-id="bf1c5-143">**검토 + 저장을** 선택한 다음 **저장을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="bf1c5-143">Select **Review + save**, then choose **Save**.</span></span>

<span data-ttu-id="bf1c5-144">Microsoft Endpoint Configuration Manager 구성에 대한 자세한 내용은 [맬웨어 방지 정책을 만들고 배포하는 방법: 클라우드 보호 서비스 입니다.](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)</span><span class="sxs-lookup"><span data-stu-id="bf1c5-144">For more information about configuring Microsoft Endpoint Configuration Manager, see [How to create and deploy antimalware policies: Cloud-protection service](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service).</span></span>

## <a name="use-group-policy-to-turn-on-cloud-delivered-protection"></a><span data-ttu-id="bf1c5-145">그룹 정책을 사용하여 클라우드 로 배달된 보호 기능을 켭니다.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-145">Use Group Policy to turn on cloud-delivered protection</span></span>

1. <span data-ttu-id="bf1c5-146">그룹 정책 관리 장치에서 [그룹 정책 관리 콘솔을](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))열고 구성하려는 그룹 정책 개체를 마우스 오른쪽 단추로 클릭하고 **편집을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="bf1c5-146">On your Group Policy management device, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="bf1c5-147">그룹 **정책 관리 편집기에서** **컴퓨터 구성으로** 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-147">In the **Group Policy Management Editor**, go to **Computer configuration**.</span></span>

3. <span data-ttu-id="bf1c5-148">**관리 템플릿을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="bf1c5-148">Select **Administrative templates**.</span></span>

4. <span data-ttu-id="bf1c5-149">트리를 **맵> Microsoft Defender 바이러스 백신 > Windows 구성 요소로** 확장</span><span class="sxs-lookup"><span data-stu-id="bf1c5-149">Expand the tree to **Windows components > Microsoft Defender Antivirus > MAPS**</span></span>

5. <span data-ttu-id="bf1c5-150">두 번 클릭 **마이크로 소프트 맵가입**.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-150">Double-click **Join Microsoft MAPS**.</span></span> <span data-ttu-id="bf1c5-151">옵션이 켜져 있는지 확인하고 기본 MAPS 또는 고급 **지도로** **설정합니다.**</span><span class="sxs-lookup"><span data-stu-id="bf1c5-151">Ensure the option is turned on and set to **Basic MAPS** or **Advanced MAPS**.</span></span> <span data-ttu-id="bf1c5-152">**확인** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-152">Select **OK**.</span></span>

6. <span data-ttu-id="bf1c5-153">**추가 분석이 필요한 경우 파일 샘플 보내기를** 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-153">Double-click **Send file samples when further analysis is required**.</span></span> <span data-ttu-id="bf1c5-154">첫 번째 옵션이 **활성화로** 설정되어 있고 다른 옵션이 중 하나에 설정되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-154">Ensure that the first option is set to **Enabled** and that the other options are set to either:</span></span>

    1. <span data-ttu-id="bf1c5-155">**안전한 샘플 보내기** (1)</span><span class="sxs-lookup"><span data-stu-id="bf1c5-155">**Send safe samples** (1)</span></span>
    2. <span data-ttu-id="bf1c5-156">**모든 샘플 보내기** (3)</span><span class="sxs-lookup"><span data-stu-id="bf1c5-156">**Send all samples** (3)</span></span>

        >[!NOTE]
        > <span data-ttu-id="bf1c5-157">**안전한 샘플 보내기(1)** 옵션은 대부분의 샘플이 자동으로 전송된다는 것을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-157">The **Send safe samples** (1) option means that most samples will be sent automatically.</span></span> <span data-ttu-id="bf1c5-158">개인 정보가 포함될 가능성이 있는 파일은 여전히 프롬프트되고 추가 확인이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-158">Files that are likely to contain personal information will still prompt and require additional confirmation.</span></span>
        > <span data-ttu-id="bf1c5-159">**항상 프롬프트(0)로** 옵션을 설정하면 장치의 보호 상태가 낮아집니다.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-159">Setting the option to **Always Prompt** (0) will lower the protection state of the device.</span></span> <span data-ttu-id="bf1c5-160">**절대 보내지 마십시오** (2)로 설정하면 엔드포인트에 대한 Microsoft Defender의 [첫눈에 블록](configure-block-at-first-sight-microsoft-defender-antivirus.md) 기능이 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-160">Setting it to **Never send** (2) means that the [Block at First Sight](configure-block-at-first-sight-microsoft-defender-antivirus.md) feature of Microsoft Defender for Endpoint won't work.</span></span>

7. <span data-ttu-id="bf1c5-161">**확인** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-161">Select **OK**.</span></span>

## <a name="use-powershell-cmdlets-to-turn-on-cloud-delivered-protection"></a><span data-ttu-id="bf1c5-162">PowerShell cmdlet을 사용하여 클라우드 로 전달된 보호 기능을 켭니다.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-162">Use PowerShell cmdlets to turn on cloud-delivered protection</span></span>

<span data-ttu-id="bf1c5-163">다음 cmdlets는 클라우드 로 배달된 보호를 켤 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-163">The following cmdlets can turn on cloud-delivered protection:</span></span>

```PowerShell
Set-MpPreference -MAPSReporting Advanced
Set-MpPreference -SubmitSamplesConsent SendAllSamples
```

<span data-ttu-id="bf1c5-164">Microsoft Defender 바이러스 백신 PowerShell을 사용하는 방법에 대한 자세한 내용은 [powerShell cmdlet을 사용하여 Microsoft Defender 바이러스 백신 및 수비수 cmdlet을 구성하고](use-powershell-cmdlets-microsoft-defender-antivirus.md) [실행하십시오.](/powershell/module/defender/)</span><span class="sxs-lookup"><span data-stu-id="bf1c5-164">For more information on how to use PowerShell with Microsoft Defender Antivirus, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span> <span data-ttu-id="bf1c5-165">[정책 CSP - Defender는](/windows/client-management/mdm/policy-csp-defender) [-submitSamples동의에](/windows/client-management/mdm/policy-csp-defender#defender-submitsamplesconsent)대한 자세한 정보도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-165">[Policy CSP - Defender](/windows/client-management/mdm/policy-csp-defender) also has more information specifically on [-SubmitSamplesConsent](/windows/client-management/mdm/policy-csp-defender#defender-submitsamplesconsent).</span></span>

>[!NOTE]
> <span data-ttu-id="bf1c5-166">**-SubmitSamples동의(기본** 설정) 또는 .를 설정할 수도 `SendSafeSamples` `NeverSend` `AlwaysPrompt` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-166">You can also set **-SubmitSamplesConsent** to `SendSafeSamples` (the default setting), `NeverSend`, or `AlwaysPrompt`.</span></span> <span data-ttu-id="bf1c5-167">`SendSafeSamples`설정은 대부분의 샘플이 자동으로 전송된다는 것을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-167">The `SendSafeSamples` setting means that most samples will be sent automatically.</span></span> <span data-ttu-id="bf1c5-168">개인 정보가 포함될 가능성이 있는 파일은 여전히 프롬프트되고 추가 확인이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-168">Files that are likely to contain personal information will still prompt and require additional confirmation.</span></span>

>[!WARNING]
> <span data-ttu-id="bf1c5-169">설정 **-제출견본에동의하거나** `NeverSend` 장치의 보호 수준을 낮출 `AlwaysPrompt` 것입니다.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-169">Setting **-SubmitSamplesConsent** to `NeverSend` or `AlwaysPrompt` will lower the protection level of the device.</span></span> <span data-ttu-id="bf1c5-170">또한 `NeverSend` 엔드포인트용 Microsoft Defender의 [첫눈에 블록](configure-block-at-first-sight-microsoft-defender-antivirus.md) 기능이 작동하지 않는다는 의미로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-170">In addition, setting it to `NeverSend` means that the [Block at First Sight](configure-block-at-first-sight-microsoft-defender-antivirus.md) feature of Microsoft Defender for Endpoint won't work.</span></span>

## <a name="use-windows-management-instruction-wmi-to-turn-on-cloud-delivered-protection"></a><span data-ttu-id="bf1c5-171">wMI(Windows 관리 지침)를 사용하여 클라우드 로 배달된 보호 기능을 켭니다.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-171">Use Windows Management Instruction (WMI) to turn on cloud-delivered protection</span></span>

<span data-ttu-id="bf1c5-172">다음 속성에 [ **MSFT_MpPreference** 클래스의 **설정** 방법을](/previous-versions/windows/desktop/defender/set-msft-mppreference) 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-172">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/defender/set-msft-mppreference) class for the following properties:</span></span>

```WMI
MAPSReporting
SubmitSamplesConsent
```

<span data-ttu-id="bf1c5-173">허용된 매개 변수에 대한 자세한 내용은 [Windows Defender WMIv2 API를 참조하십시오.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="bf1c5-173">For more information about allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span></span>

## <a name="turn-on-cloud-delivered-protection-on-individual-clients-with-the-windows-security-app"></a><span data-ttu-id="bf1c5-174">Windows 보안 앱을 통해 개별 클라이언트에 클라우드로 제공되는 보호 기능 설정</span><span class="sxs-lookup"><span data-stu-id="bf1c5-174">Turn on cloud-delivered protection on individual clients with the Windows Security app</span></span>

> [!NOTE]
> <span data-ttu-id="bf1c5-175">Microsoft MAPS 그룹 정책 **설정을 보고하기 위한 로컬 설정 구성이** **비활성화된** 것으로 설정된 경우 Windows 설정 **클라우드 기반 보호** 설정이 회색으로 지정되고 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-175">If the **Configure local setting override for reporting Microsoft MAPS** Group Policy setting is set to **Disabled**, then the **Cloud-based protection** setting in Windows Settings will be greyed-out and unavailable.</span></span> <span data-ttu-id="bf1c5-176">설정이 Windows 설정에서 업데이트되기 전에 먼저 그룹 정책 개체를 통해 수행한 변경을 개별 엔드포인트에 배포해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-176">Changes made through a Group Policy Object must first be deployed to individual endpoints before the setting will be updated in Windows Settings.</span></span>

1. <span data-ttu-id="bf1c5-177">작업 표시줄에서 쉴드 아이콘을 선택하거나 Defender의 시작 메뉴를 검색하여 Windows 보안 앱을 **엽니다.**</span><span class="sxs-lookup"><span data-stu-id="bf1c5-177">Open the Windows Security app by selecting the shield icon in the task bar, or by searching the start menu for **Defender**.</span></span>

2. <span data-ttu-id="bf1c5-178">바이러스 **& 위협 보호** 타일(또는 왼쪽 메뉴 표시줄의 쉴드 아이콘)을 선택한 다음 **바이러스 & 위협 보호 설정** 레이블을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-178">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar) and then the **Virus & threat protection settings** label:</span></span>

    ![Windows 보안 앱의 바이러스 및 위협 방지 설정 레이블 스크린샷](images/defender/wdav-protection-settings-wdsc.png)

3. <span data-ttu-id="bf1c5-180">클라우드 **기반 보호** 및 **자동 샘플 제출이** On으로 전환되어 있는지 **확인합니다.**</span><span class="sxs-lookup"><span data-stu-id="bf1c5-180">Confirm that **Cloud-based Protection** and **Automatic sample submission** are switched to **On**.</span></span>

> [!NOTE]
> <span data-ttu-id="bf1c5-181">자동 샘플 제출이 그룹 정책으로 구성된 경우 설정이 회색으로 지정되고 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-181">If automatic sample submission has been configured with Group Policy then the setting will be greyed-out and unavailable.</span></span>

## <a name="related-articles"></a><span data-ttu-id="bf1c5-182">관련 문서</span><span class="sxs-lookup"><span data-stu-id="bf1c5-182">Related articles</span></span>

- [<span data-ttu-id="bf1c5-183">클라우드 차단 제한 시간 구성</span><span class="sxs-lookup"><span data-stu-id="bf1c5-183">Configure the cloud block timeout period</span></span>](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md)
- [<span data-ttu-id="bf1c5-184">첫눈에 블록 구성</span><span class="sxs-lookup"><span data-stu-id="bf1c5-184">Configure block at first sight</span></span>](configure-block-at-first-sight-microsoft-defender-antivirus.md)
- [<span data-ttu-id="bf1c5-185">PowerShell cmdlet을 사용하여 Microsoft Defender 바이러스 백신 관리</span><span class="sxs-lookup"><span data-stu-id="bf1c5-185">Use PowerShell cmdlets to manage Microsoft Defender Antivirus</span></span>](use-powershell-cmdlets-microsoft-defender-antivirus.md)
- <span data-ttu-id="bf1c5-186">[Microsoft Intune Endpoint Protection Windows PC를 보호하는 데 도움이 됩니다.](/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)</span><span class="sxs-lookup"><span data-stu-id="bf1c5-186">[Help secure Windows PCs with Endpoint Protection for Microsoft Intune](/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)]</span></span>
- [<span data-ttu-id="bf1c5-187">수비수 cmdlets</span><span class="sxs-lookup"><span data-stu-id="bf1c5-187">Defender cmdlets</span></span>](/powershell/module/defender/)
- [<span data-ttu-id="bf1c5-188">microsoft 클라우드 제공 보호 Microsoft Defender 바이러스 백신 사용</span><span class="sxs-lookup"><span data-stu-id="bf1c5-188">Use Microsoft cloud-delivered protection in Microsoft Defender Antivirus</span></span>](cloud-protection-microsoft-defender-antivirus.md)
- [<span data-ttu-id="bf1c5-189">맬웨어 방지 정책을 만들고 배포하는 방법: 클라우드 보호 서비스</span><span class="sxs-lookup"><span data-stu-id="bf1c5-189">How to create and deploy antimalware policies: Cloud-protection service</span></span>](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)
- [<span data-ttu-id="bf1c5-190">Windows 10의 Microsoft Defender 바이러스 백신</span><span class="sxs-lookup"><span data-stu-id="bf1c5-190">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
