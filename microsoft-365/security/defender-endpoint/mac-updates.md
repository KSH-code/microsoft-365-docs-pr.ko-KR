---
title: Mac용 Microsoft Defender ATP에 대한 업데이트 배포
description: 엔터프라이즈 환경에서 Mac용 Microsoft Defender ATP에 대한 업데이트를 제어합니다.
keywords: microsoft, defender, atp, mac, 업데이트, 배포
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 99f507ad381ee21ba91753716439180fafe37c24
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51074343"
---
# <a name="deploy-updates-for-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="67179-104">Mac용 끝점용 Microsoft Defender 업데이트 배포</span><span class="sxs-lookup"><span data-stu-id="67179-104">Deploy updates for Microsoft Defender for Endpoint for Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="67179-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="67179-105">**Applies to:**</span></span>

- [<span data-ttu-id="67179-106">Mac용 끝점용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="67179-106">Microsoft Defender for Endpoint for Mac</span></span>](microsoft-defender-endpoint-mac.md)
- [<span data-ttu-id="67179-107">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="67179-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="67179-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="67179-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="67179-109">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="67179-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="67179-110">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="67179-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="67179-111">Microsoft는 성능, 보안을 개선하고 새로운 기능을 제공하기 위해 소프트웨어 업데이트를 정기적으로 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="67179-111">Microsoft regularly publishes software updates to improve performance, security, and to deliver new features.</span></span>

<span data-ttu-id="67179-112">Mac용 끝점용 Microsoft Defender를 업데이트하기 위해 MAU(Microsoft 자동 업데이트)라는 프로그램이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="67179-112">To update Microsoft Defender for Endpoint for Mac, a program named Microsoft AutoUpdate (MAU) is used.</span></span> <span data-ttu-id="67179-113">기본적으로 MAU는 매일 업데이트를 자동으로 확인하지만 매주, 월별 또는 수동으로 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67179-113">By default, MAU automatically checks for updates daily, but you can change that to weekly, monthly, or manually.</span></span>

![MAU 스크린샷](images/MDATP-34-MAU.png)

<span data-ttu-id="67179-115">소프트웨어 배포 도구를 사용하여 업데이트를 배포하기로 결정한 경우 소프트웨어 업데이트를 수동으로 확인하도록 MAU를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="67179-115">If you decide to deploy updates by using your software distribution tools, you should configure MAU to manually check for software updates.</span></span> <span data-ttu-id="67179-116">기본 설정을 배포하여 MAU가 조직의 Mac에 대한 업데이트를 검사하는 방법과 경우를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67179-116">You can deploy preferences to configure how and when MAU checks for updates for the Macs in your organization.</span></span>

## <a name="use-msupdate"></a><span data-ttu-id="67179-117">Msupdate 사용</span><span class="sxs-lookup"><span data-stu-id="67179-117">Use msupdate</span></span>

<span data-ttu-id="67179-118">MAU에는 업데이트가 적용되는 경우를 보다 정확하게 제어할 수 있도록 IT 관리자를 위해 설계된 *msupdate라는* 명령줄 도구가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67179-118">MAU includes a command-line tool, called *msupdate*, that is designed for IT administrators so that they have more precise control over when updates are applied.</span></span> <span data-ttu-id="67179-119">이 도구를 사용하는 방법에 대한 지침은 [msupdate를 사용하여 Mac용 Office 업데이트에서 찾을 수 있습니다.](https://docs.microsoft.com/deployoffice/mac/update-office-for-mac-using-msupdate)</span><span class="sxs-lookup"><span data-stu-id="67179-119">Instructions for how to use this tool can be found in [Update Office for Mac by using msupdate](https://docs.microsoft.com/deployoffice/mac/update-office-for-mac-using-msupdate).</span></span>

<span data-ttu-id="67179-120">MAU에서 Mac용 끝점용 Microsoft Defender의 응용 프로그램 식별자는 *WDAV00입니다.*</span><span class="sxs-lookup"><span data-stu-id="67179-120">In MAU, the application identifier for Microsoft Defender for Endpoint for Mac is *WDAV00*.</span></span> <span data-ttu-id="67179-121">Mac용 끝점용 Microsoft Defender의 최신 업데이트를 다운로드하고 설치하려면 터미널 창에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="67179-121">To download and install the latest updates for Microsoft Defender for Endpoint for Mac, execute the following command from a Terminal window:</span></span>

```
./msupdate --install --apps wdav00
```

## <a name="set-preferences-for-microsoft-autoupdate"></a><span data-ttu-id="67179-122">Microsoft 자동 업데이트 기본 설정 설정</span><span class="sxs-lookup"><span data-stu-id="67179-122">Set preferences for Microsoft AutoUpdate</span></span>

<span data-ttu-id="67179-123">이 섹션에서는 MAU를 구성하는 데 사용할 수 있는 가장 일반적인 기본 설정에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="67179-123">This section describes the most common preferences that can be used to configure MAU.</span></span> <span data-ttu-id="67179-124">이러한 설정은 엔터프라이즈에서 사용하는 관리 콘솔을 통해 구성 프로필로 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67179-124">These settings can be deployed as a configuration profile through the management console that your enterprise is using.</span></span> <span data-ttu-id="67179-125">구성 프로필의 예는 다음 섹션에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67179-125">An example of a configuration profile is shown in the following sections.</span></span>

### <a name="set-the-channel-name"></a><span data-ttu-id="67179-126">채널 이름 설정</span><span class="sxs-lookup"><span data-stu-id="67179-126">Set the channel name</span></span>

<span data-ttu-id="67179-127">채널은 MAU를 통해 제공되는 업데이트의 유형과 빈도를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="67179-127">The channel determines the type and frequency of updates that are offered through MAU.</span></span> <span data-ttu-id="67179-128">의 `Beta` 장치는 및 의 장치 앞에 새로운 기능을 시도할 수 `Preview` `Current` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67179-128">Devices in `Beta` can try out new features before devices in `Preview` and `Current`.</span></span> 

<span data-ttu-id="67179-129">채널에는 `Current` 제품의 가장 안정적인 버전이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67179-129">The `Current` channel contains the most stable version of the product.</span></span>

>[!IMPORTANT]
> <span data-ttu-id="67179-130">Microsoft 자동 업데이트 버전 4.29 이전의 채널 이름은 서로 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="67179-130">Prior to Microsoft AutoUpdate version 4.29, channels had different names:</span></span> 
> 
> - <span data-ttu-id="67179-131">`Beta` 이름이 `InsiderFast` 지정됩니다(Insider Fast).</span><span class="sxs-lookup"><span data-stu-id="67179-131">`Beta` was named `InsiderFast` (Insider Fast)</span></span>
> - <span data-ttu-id="67179-132">`Preview` 이름이 `External` 지정(Insider Slow)</span><span class="sxs-lookup"><span data-stu-id="67179-132">`Preview` was named `External` (Insider Slow)</span></span>
> - <span data-ttu-id="67179-133">`Current` 명명 `Production`</span><span class="sxs-lookup"><span data-stu-id="67179-133">`Current` was named `Production`</span></span>

>[!TIP]
><span data-ttu-id="67179-134">새 기능을 미리 보고 초기 피드백을 제공하기 위해서는 엔터프라이즈의 일부 장치를 또는 로 구성하는 것이 `Beta` `Preview` 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="67179-134">In order to preview new features and provide early feedback, it is recommended that you configure some devices in your enterprise to `Beta` or `Preview`.</span></span>

|||
|:--|:--|
| <span data-ttu-id="67179-135">**도메인**</span><span class="sxs-lookup"><span data-stu-id="67179-135">**Domain**</span></span> | <span data-ttu-id="67179-136">com.microsoft.autoupdate2</span><span class="sxs-lookup"><span data-stu-id="67179-136">com.microsoft.autoupdate2</span></span> |
| <span data-ttu-id="67179-137">**키**</span><span class="sxs-lookup"><span data-stu-id="67179-137">**Key**</span></span> | <span data-ttu-id="67179-138">ChannelName</span><span class="sxs-lookup"><span data-stu-id="67179-138">ChannelName</span></span> |
| <span data-ttu-id="67179-139">**Data type**</span><span class="sxs-lookup"><span data-stu-id="67179-139">**Data type**</span></span> | <span data-ttu-id="67179-140">String</span><span class="sxs-lookup"><span data-stu-id="67179-140">String</span></span> |
| <span data-ttu-id="67179-141">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="67179-141">**Possible values**</span></span> | <span data-ttu-id="67179-142">Beta</span><span class="sxs-lookup"><span data-stu-id="67179-142">Beta</span></span> <br/> <span data-ttu-id="67179-143">Preview</span><span class="sxs-lookup"><span data-stu-id="67179-143">Preview</span></span> <br/> <span data-ttu-id="67179-144">Current</span><span class="sxs-lookup"><span data-stu-id="67179-144">Current</span></span> |
|||

>[!WARNING]
><span data-ttu-id="67179-145">이 설정은 Microsoft 자동 업데이트를 통해 업데이트되는 모든 응용 프로그램의 채널을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="67179-145">This setting changes the channel for all applications that are updated through Microsoft AutoUpdate.</span></span> <span data-ttu-id="67179-146">Mac용 끝점용 Microsoft Defender에 대한 채널만 변경하기 위해 원하는 채널로 교체한 후 다음 명령을 `[channel-name]` 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="67179-146">To change the channel only for Microsoft Defender for Endpoint for Mac, execute the following command after replacing `[channel-name]` with the desired channel:</span></span>
> ```bash
> defaults write com.microsoft.autoupdate2 Applications -dict-add "/Applications/Microsoft Defender ATP.app" " { 'Application ID' = 'WDAV00' ; 'App Domain' = 'com.microsoft.wdav' ; LCID = 1033 ; ChannelName = '[channel-name]' ; }"
> ```

### <a name="set-update-check-frequency"></a><span data-ttu-id="67179-147">업데이트 확인 빈도 설정</span><span class="sxs-lookup"><span data-stu-id="67179-147">Set update check frequency</span></span>

<span data-ttu-id="67179-148">MAU가 업데이트를 검색하는 자주 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="67179-148">Change how often MAU searches for updates.</span></span>

|||
|:--|:--|
| <span data-ttu-id="67179-149">**도메인**</span><span class="sxs-lookup"><span data-stu-id="67179-149">**Domain**</span></span> | <span data-ttu-id="67179-150">com.microsoft.autoupdate2</span><span class="sxs-lookup"><span data-stu-id="67179-150">com.microsoft.autoupdate2</span></span> |
| <span data-ttu-id="67179-151">**키**</span><span class="sxs-lookup"><span data-stu-id="67179-151">**Key**</span></span> | <span data-ttu-id="67179-152">UpdateCheckFrequency</span><span class="sxs-lookup"><span data-stu-id="67179-152">UpdateCheckFrequency</span></span> |
| <span data-ttu-id="67179-153">**Data type**</span><span class="sxs-lookup"><span data-stu-id="67179-153">**Data type**</span></span> | <span data-ttu-id="67179-154">정수</span><span class="sxs-lookup"><span data-stu-id="67179-154">Integer</span></span> |
| <span data-ttu-id="67179-155">**기본값**.</span><span class="sxs-lookup"><span data-stu-id="67179-155">**Default value**</span></span> | <span data-ttu-id="67179-156">720(분)</span><span class="sxs-lookup"><span data-stu-id="67179-156">720 (minutes)</span></span> |
| <span data-ttu-id="67179-157">**설명**</span><span class="sxs-lookup"><span data-stu-id="67179-157">**Comment**</span></span> | <span data-ttu-id="67179-158">이 값은 분으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="67179-158">This value is set in minutes.</span></span> |
|||

### <a name="change-how-mau-interacts-with-updates"></a><span data-ttu-id="67179-159">MAU가 업데이트와 상호 작용하는 방식 변경</span><span class="sxs-lookup"><span data-stu-id="67179-159">Change how MAU interacts with updates</span></span>

<span data-ttu-id="67179-160">MAU에서 업데이트를 검색하는 방법을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="67179-160">Change how MAU searches for updates.</span></span>

|||
|:--|:--|
| <span data-ttu-id="67179-161">**도메인**</span><span class="sxs-lookup"><span data-stu-id="67179-161">**Domain**</span></span> | <span data-ttu-id="67179-162">com.microsoft.autoupdate2</span><span class="sxs-lookup"><span data-stu-id="67179-162">com.microsoft.autoupdate2</span></span> |
| <span data-ttu-id="67179-163">**키**</span><span class="sxs-lookup"><span data-stu-id="67179-163">**Key**</span></span> | <span data-ttu-id="67179-164">HowToCheck</span><span class="sxs-lookup"><span data-stu-id="67179-164">HowToCheck</span></span> |
| <span data-ttu-id="67179-165">**Data type**</span><span class="sxs-lookup"><span data-stu-id="67179-165">**Data type**</span></span> | <span data-ttu-id="67179-166">String</span><span class="sxs-lookup"><span data-stu-id="67179-166">String</span></span> |
| <span data-ttu-id="67179-167">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="67179-167">**Possible values**</span></span> | <span data-ttu-id="67179-168">수동</span><span class="sxs-lookup"><span data-stu-id="67179-168">Manual</span></span> <br/> <span data-ttu-id="67179-169">AutomaticCheck</span><span class="sxs-lookup"><span data-stu-id="67179-169">AutomaticCheck</span></span> <br/> <span data-ttu-id="67179-170">AutomaticDownload</span><span class="sxs-lookup"><span data-stu-id="67179-170">AutomaticDownload</span></span> |
| <span data-ttu-id="67179-171">**설명**</span><span class="sxs-lookup"><span data-stu-id="67179-171">**Comment**</span></span> |  <span data-ttu-id="67179-172">AutomaticDownload는 다운로드를 수행하고 가능한 경우 자동으로 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="67179-172">Note that AutomaticDownload will do a download and install silently if possible.</span></span> |
|||

### <a name="change-whether-the-check-for-updates-button-is-enabled"></a><span data-ttu-id="67179-173">"업데이트 확인" 단추를 사용할 수 있는지 여부 변경</span><span class="sxs-lookup"><span data-stu-id="67179-173">Change whether the "Check for Updates" button is enabled</span></span>

<span data-ttu-id="67179-174">로컬 사용자가 Microsoft 자동 업데이트 사용자 인터페이스에서 "업데이트 확인" 옵션을 클릭할 수 있는지 여부를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="67179-174">Change whether local users will be able to click the "Check for Updates" option in the Microsoft AutoUpdate user interface.</span></span>

|||
|:--|:--|
| <span data-ttu-id="67179-175">**도메인**</span><span class="sxs-lookup"><span data-stu-id="67179-175">**Domain**</span></span> | <span data-ttu-id="67179-176">com.microsoft.autoupdate2</span><span class="sxs-lookup"><span data-stu-id="67179-176">com.microsoft.autoupdate2</span></span> |
| <span data-ttu-id="67179-177">**키**</span><span class="sxs-lookup"><span data-stu-id="67179-177">**Key**</span></span> | <span data-ttu-id="67179-178">EnableCheckForUpdatesButton</span><span class="sxs-lookup"><span data-stu-id="67179-178">EnableCheckForUpdatesButton</span></span> |
| <span data-ttu-id="67179-179">**Data type**</span><span class="sxs-lookup"><span data-stu-id="67179-179">**Data type**</span></span> | <span data-ttu-id="67179-180">부울</span><span class="sxs-lookup"><span data-stu-id="67179-180">Boolean</span></span> |
| <span data-ttu-id="67179-181">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="67179-181">**Possible values**</span></span> | <span data-ttu-id="67179-182">True(기본값)</span><span class="sxs-lookup"><span data-stu-id="67179-182">True (default)</span></span> <br/> <span data-ttu-id="67179-183">False</span><span class="sxs-lookup"><span data-stu-id="67179-183">False</span></span> |
|||

### <a name="disable-insider-checkbox"></a><span data-ttu-id="67179-184">내부자 사용 안함 확인란</span><span class="sxs-lookup"><span data-stu-id="67179-184">Disable Insider checkbox</span></span>

<span data-ttu-id="67179-185">true로 설정하여 "Office Insider Program에 참여..."로 설정 사용자에게 확인란을 사용할 수 없음/회색으로 나타났습니다.</span><span class="sxs-lookup"><span data-stu-id="67179-185">Set to true to make the "Join the Office Insider Program..." checkbox unavailable / greyed out to users.</span></span>

|||
|:--|:--|
| <span data-ttu-id="67179-186">**도메인**</span><span class="sxs-lookup"><span data-stu-id="67179-186">**Domain**</span></span> | <span data-ttu-id="67179-187">com.microsoft.autoupdate2</span><span class="sxs-lookup"><span data-stu-id="67179-187">com.microsoft.autoupdate2</span></span> |
| <span data-ttu-id="67179-188">**키**</span><span class="sxs-lookup"><span data-stu-id="67179-188">**Key**</span></span> | <span data-ttu-id="67179-189">DisableInsiderCheckbox</span><span class="sxs-lookup"><span data-stu-id="67179-189">DisableInsiderCheckbox</span></span> |
| <span data-ttu-id="67179-190">**Data type**</span><span class="sxs-lookup"><span data-stu-id="67179-190">**Data type**</span></span> | <span data-ttu-id="67179-191">부울</span><span class="sxs-lookup"><span data-stu-id="67179-191">Boolean</span></span> |
| <span data-ttu-id="67179-192">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="67179-192">**Possible values**</span></span> | <span data-ttu-id="67179-193">False(기본값)</span><span class="sxs-lookup"><span data-stu-id="67179-193">False (default)</span></span> <br/> <span data-ttu-id="67179-194">True</span><span class="sxs-lookup"><span data-stu-id="67179-194">True</span></span> |
|||

### <a name="limit-the-telemetry-that-is-sent-from-mau"></a><span data-ttu-id="67179-195">MAU에서 전송된 원격 분석 제한</span><span class="sxs-lookup"><span data-stu-id="67179-195">Limit the telemetry that is sent from MAU</span></span>

<span data-ttu-id="67179-196">false로 설정하여 최소 하트비트 데이터, 응용 프로그램 사용 현황 및 환경 세부 정보를 보내지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="67179-196">Set to false to send minimal heartbeat data, no application usage, and no environment details.</span></span>

|||
|:--|:--|
| <span data-ttu-id="67179-197">**도메인**</span><span class="sxs-lookup"><span data-stu-id="67179-197">**Domain**</span></span> | <span data-ttu-id="67179-198">com.microsoft.autoupdate2</span><span class="sxs-lookup"><span data-stu-id="67179-198">com.microsoft.autoupdate2</span></span> |
| <span data-ttu-id="67179-199">**키**</span><span class="sxs-lookup"><span data-stu-id="67179-199">**Key**</span></span> | <span data-ttu-id="67179-200">SendAllTelemetryEnabled</span><span class="sxs-lookup"><span data-stu-id="67179-200">SendAllTelemetryEnabled</span></span> |
| <span data-ttu-id="67179-201">**Data type**</span><span class="sxs-lookup"><span data-stu-id="67179-201">**Data type**</span></span> | <span data-ttu-id="67179-202">부울</span><span class="sxs-lookup"><span data-stu-id="67179-202">Boolean</span></span> |
| <span data-ttu-id="67179-203">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="67179-203">**Possible values**</span></span> | <span data-ttu-id="67179-204">True(기본값)</span><span class="sxs-lookup"><span data-stu-id="67179-204">True (default)</span></span> <br/> <span data-ttu-id="67179-205">False</span><span class="sxs-lookup"><span data-stu-id="67179-205">False</span></span> |
|||

## <a name="example-configuration-profile"></a><span data-ttu-id="67179-206">구성 프로필 예제</span><span class="sxs-lookup"><span data-stu-id="67179-206">Example configuration profile</span></span>

<span data-ttu-id="67179-207">다음 구성 프로필은 다음과 같은 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="67179-207">The following configuration profile is used to:</span></span>
- <span data-ttu-id="67179-208">디바이스를 베타 채널에 추가</span><span class="sxs-lookup"><span data-stu-id="67179-208">Place the device in the Beta channel</span></span>
- <span data-ttu-id="67179-209">업데이트를 자동으로 다운로드 및 설치</span><span class="sxs-lookup"><span data-stu-id="67179-209">Automatically download and install updates</span></span>
- <span data-ttu-id="67179-210">사용자 인터페이스에서 "업데이트 확인" 단추를 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="67179-210">Enable the "Check for updates" button in the user interface</span></span>
- <span data-ttu-id="67179-211">장치의 사용자가 Insider 채널에 등록할 수 있도록 허용</span><span class="sxs-lookup"><span data-stu-id="67179-211">Allow users on the device to enroll into the Insider channels</span></span>

### <a name="jamf"></a><span data-ttu-id="67179-212">JAMF</span><span class="sxs-lookup"><span data-stu-id="67179-212">JAMF</span></span>

```XML
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
    <key>ChannelName</key>
    <string>Beta</string>
    <key>HowToCheck</key>
    <string>AutomaticDownload</string>
    <key>EnableCheckForUpdatesButton</key>
    <true/>
    <key>DisableInsiderCheckbox</key>
    <false/>
    <key>SendAllTelemetryEnabled</key>
    <true/>
</dict>
</plist>
```

### <a name="intune"></a><span data-ttu-id="67179-213">Intune</span><span class="sxs-lookup"><span data-stu-id="67179-213">Intune</span></span>

```XML
<?xml version="1.0" encoding="utf-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1">
    <dict>
        <key>PayloadUUID</key>
        <string>B762FF60-6ACB-4A72-9E72-459D00C936F3</string>
        <key>PayloadType</key>
        <string>Configuration</string>
        <key>PayloadOrganization</key>
        <string>Microsoft</string>
        <key>PayloadIdentifier</key>
        <string>com.microsoft.autoupdate2</string>
        <key>PayloadDisplayName</key>
        <string>Microsoft AutoUpdate settings</string>
        <key>PayloadDescription</key>
        <string>Microsoft AutoUpdate configuration settings</string>
        <key>PayloadVersion</key>
        <integer>1</integer>
        <key>PayloadEnabled</key>
        <true/>
        <key>PayloadRemovalDisallowed</key>
        <true/>
        <key>PayloadScope</key>
        <string>System</string>
        <key>PayloadContent</key>
        <array>
            <dict>
            <key>PayloadUUID</key>
            <string>5A6F350A-CC2C-440B-A074-68E3F34EBAE9</string>
            <key>PayloadType</key>
            <string>com.microsoft.autoupdate2</string>
            <key>PayloadOrganization</key>
            <string>Microsoft</string>
            <key>PayloadIdentifier</key>
            <string>com.microsoft.autoupdate2</string>
            <key>PayloadDisplayName</key>
            <string>Microsoft AutoUpdate configuration settings</string>
            <key>PayloadDescription</key>
            <string/>
            <key>PayloadVersion</key>
            <integer>1</integer>
            <key>PayloadEnabled</key>
            <true/>
            <key>ChannelName</key>
            <string>Beta</string>
            <key>HowToCheck</key>
            <string>AutomaticDownload</string>
            <key>EnableCheckForUpdatesButton</key>
            <true/>
            <key>DisableInsiderCheckbox</key>
            <false/>
            <key>SendAllTelemetryEnabled</key>
            <true/>
            </dict>
        </array>
    </dict>
</plist>
```

<span data-ttu-id="67179-214">MAU를 구성하려면 엔터프라이즈에서 사용하는 관리 도구에서 이 구성 프로필을 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67179-214">To configure MAU, you can deploy this configuration profile from the management tool that your enterprise is using:</span></span>
- <span data-ttu-id="67179-215">JAMF에서 이 구성 프로필을 업로드하고 기본 설정 도메인을 *com.microsoft.autoupdate2로 설정합니다.*</span><span class="sxs-lookup"><span data-stu-id="67179-215">From JAMF, upload this configuration profile and set the Preference Domain to *com.microsoft.autoupdate2*.</span></span>
- <span data-ttu-id="67179-216">Intune에서 이 구성 프로필을 업로드하고 사용자 지정 구성 프로필 이름을 *com.microsoft.autoupdate2로 설정하십시오.*</span><span class="sxs-lookup"><span data-stu-id="67179-216">From Intune, upload this configuration profile and set the custom configuration profile name to *com.microsoft.autoupdate2*.</span></span>

## <a name="resources"></a><span data-ttu-id="67179-217">리소스</span><span class="sxs-lookup"><span data-stu-id="67179-217">Resources</span></span>

- [<span data-ttu-id="67179-218">msupdate 참조</span><span class="sxs-lookup"><span data-stu-id="67179-218">msupdate reference</span></span>](https://docs.microsoft.com/deployoffice/mac/update-office-for-mac-using-msupdate)
