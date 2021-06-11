---
title: 끝점용 Microsoft Defender에서 라이브 응답을 사용하여 장치의 엔터티 조사
description: 보안 원격 셸 연결을 사용하여 장치에 액세스하여 조사 작업을 수행하고 실시간으로 디바이스에서 즉각적인 응답 작업을 수행할 수 있습니다.
keywords: 원격, 셸, 연결, 라이브, 응답, 실시간, 명령, 스크립트, 재구성, 헌트, 내보내기, 로그, 놓기, 다운로드, 파일,
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: d5e48f1e4f6bc2cfaa836d90e24f2ce8ba3f2114
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845333"
---
# <a name="investigate-entities-on-devices-using-live-response"></a><span data-ttu-id="a1b49-104">라이브 응답을 사용하여 디바이스에서 엔터티 조사</span><span class="sxs-lookup"><span data-stu-id="a1b49-104">Investigate entities on devices using live response</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a1b49-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="a1b49-105">**Applies to:**</span></span>
- [<span data-ttu-id="a1b49-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="a1b49-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="a1b49-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a1b49-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="a1b49-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="a1b49-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="a1b49-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="a1b49-110">실시간 응답은 보안 운영 팀이 원격 셸 연결을 사용하여 장치(컴퓨터라고도도 지칭)에 즉시 액세스할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-110">Live response gives security operations teams instantaneous access to a device (also referred to as a machine) using a remote shell connection.</span></span> <span data-ttu-id="a1b49-111">이를 통해 실시간으로 심층 조사 작업을 수행하고 즉각적인 대응 조치를 취하여 식별된 위협을 즉시 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-111">This gives you the power to do in-depth investigative work and take immediate response actions to promptly contain identified threats—in real time.</span></span> 

<span data-ttu-id="a1b49-112">실시간 대응은 보안 운영 팀이 법의적 데이터를 수집하고, 스크립트를 실행하고, 분석을 위해 의심스러운 엔터티를 보내고, 위협을 수정하고, 새로운 위협을 사전 대응할 수 있도록 하여 조사를 향상시킵니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-112">Live response is designed to enhance investigations by enabling your security operations team to collect forensic data, run scripts, send suspicious entities for analysis, remediate threats, and proactively hunt for emerging threats.</span></span><br/><br/>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4qLUW]

<span data-ttu-id="a1b49-113">실시간 응답을 통해 분석가가 다음 작업을 모두 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-113">With live response, analysts can do all of the following tasks:</span></span>
- <span data-ttu-id="a1b49-114">기본 및 고급 명령을 실행하여 장치에서 조사 작업을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-114">Run basic and advanced commands to do investigative work on a device.</span></span>
- <span data-ttu-id="a1b49-115">PowerShell 스크립트의 맬웨어 샘플 및 결과와 같은 파일을 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-115">Download files such as malware samples and outcomes of PowerShell scripts.</span></span>
- <span data-ttu-id="a1b49-116">백그라운드에서 파일을 다운로드합니다(new!).</span><span class="sxs-lookup"><span data-stu-id="a1b49-116">Download files in the background (new!).</span></span>
- <span data-ttu-id="a1b49-117">업로드 PowerShell 스크립트 또는 실행을 라이브러리에 추가하고 테넌트 수준에서 디바이스에서 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-117">Upload a PowerShell script or executable to the library and run it on a device from a tenant level.</span></span>
- <span data-ttu-id="a1b49-118">수정 작업을 수행하거나 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-118">Take or undo remediation actions.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="a1b49-119">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="a1b49-119">Before you begin</span></span>

<span data-ttu-id="a1b49-120">장치에서 세션을 시작하려면 먼저 다음 요구 사항을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-120">Before you can initiate a session on a device, make sure you fulfill the following requirements:</span></span>

- <span data-ttu-id="a1b49-121">지원되는 버전의 를 실행 **중인지 Windows.**</span><span class="sxs-lookup"><span data-stu-id="a1b49-121">**Verify that you're running a supported version of Windows**.</span></span> <br/>
<span data-ttu-id="a1b49-122">장치에서 다음 버전의 디바이스 중 하나를 실행해야 Windows</span><span class="sxs-lookup"><span data-stu-id="a1b49-122">Devices must be running one of the following versions of Windows</span></span>

  - <span data-ttu-id="a1b49-123">**Windows 10**</span><span class="sxs-lookup"><span data-stu-id="a1b49-123">**Windows 10**</span></span>
    - <span data-ttu-id="a1b49-124">[버전 1909](/windows/whats-new/whats-new-windows-10-version-1909) 이상</span><span class="sxs-lookup"><span data-stu-id="a1b49-124">[Version 1909](/windows/whats-new/whats-new-windows-10-version-1909) or later</span></span>  
    - <span data-ttu-id="a1b49-125">[버전 1903(KB4515384)](https://support.microsoft.com/en-us/help/4515384/windows-10-update-kb4515384) [](/windows/whats-new/whats-new-windows-10-version-1903)</span><span class="sxs-lookup"><span data-stu-id="a1b49-125">[Version 1903](/windows/whats-new/whats-new-windows-10-version-1903) with [KB4515384](https://support.microsoft.com/en-us/help/4515384/windows-10-update-kb4515384)</span></span>
    - <span data-ttu-id="a1b49-126">[KB4537818이](https://support.microsoft.com/help/4537818/windows-10-update-kb4537818) 있는 버전 [1809(RS 5)](/windows/whats-new/whats-new-windows-10-version-1809)</span><span class="sxs-lookup"><span data-stu-id="a1b49-126">[Version 1809 (RS 5)](/windows/whats-new/whats-new-windows-10-version-1809) with [with KB4537818](https://support.microsoft.com/help/4537818/windows-10-update-kb4537818)</span></span>
    - <span data-ttu-id="a1b49-127">[KB4537795가](https://support.microsoft.com/help/4537795/windows-10-update-kb4537795) 있는 버전 [1803(RS 4)](/windows/whats-new/whats-new-windows-10-version-1803)</span><span class="sxs-lookup"><span data-stu-id="a1b49-127">[Version 1803 (RS 4)](/windows/whats-new/whats-new-windows-10-version-1803) with [KB4537795](https://support.microsoft.com/help/4537795/windows-10-update-kb4537795)</span></span>
    - <span data-ttu-id="a1b49-128">[KB4537816이](https://support.microsoft.com/help/4537816/windows-10-update-kb4537816) 있는 버전 [1709(RS 3)](/windows/whats-new/whats-new-windows-10-version-1709)</span><span class="sxs-lookup"><span data-stu-id="a1b49-128">[Version 1709 (RS 3)](/windows/whats-new/whats-new-windows-10-version-1709) with [KB4537816](https://support.microsoft.com/help/4537816/windows-10-update-kb4537816)</span></span>
  
  - <span data-ttu-id="a1b49-129">**Windows Server 2019 - 공개 미리 보기에만 해당**</span><span class="sxs-lookup"><span data-stu-id="a1b49-129">**Windows Server 2019 - Only applicable for Public preview**</span></span>
    - <span data-ttu-id="a1b49-130">버전 1903 또는 이후 [버전(KB4515384](https://support.microsoft.com/en-us/help/4515384/windows-10-update-kb4515384)사용)</span><span class="sxs-lookup"><span data-stu-id="a1b49-130">Version 1903 or (with [KB4515384](https://support.microsoft.com/en-us/help/4515384/windows-10-update-kb4515384)) later</span></span> 
    - <span data-ttu-id="a1b49-131">버전 [1809(KB4537818)](https://support.microsoft.com/en-us/help/4537818/windows-10-update-kb4537818)</span><span class="sxs-lookup"><span data-stu-id="a1b49-131">Version 1809 (with [KB4537818](https://support.microsoft.com/en-us/help/4537818/windows-10-update-kb4537818))</span></span>

- <span data-ttu-id="a1b49-132">**고급 설정 페이지에서 라이브 응답을 사용하도록 설정합니다.**</span><span class="sxs-lookup"><span data-stu-id="a1b49-132">**Enable live response from the advanced settings page**.</span></span><br>
<span data-ttu-id="a1b49-133">고급 기능 설정 페이지에서 라이브 응답 기능을 [사용하도록 설정해야](advanced-features.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-133">You'll need to enable the live response capability in the [Advanced features settings](advanced-features.md) page.</span></span>

    >[!NOTE]
    ><span data-ttu-id="a1b49-134">보안 또는 전역 관리자 역할이 있는 사용자만 이러한 설정을 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-134">Only users with manage security or global admin roles can edit these settings.</span></span>

- <span data-ttu-id="a1b49-135">고급 설정 페이지에서 서버에 대한 **실시간 응답을 사용하도록** 설정하세요(권장).</span><span class="sxs-lookup"><span data-stu-id="a1b49-135">**Enable live response for servers from the advanced settings page** (recommended).</span></span><br>

    >[!NOTE]
    ><span data-ttu-id="a1b49-136">보안 또는 전역 관리자 역할이 있는 사용자만 이러한 설정을 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-136">Only users with manage security or global admin roles can edit these settings.</span></span>
    
- <span data-ttu-id="a1b49-137">디바이스에 자동화 수정 수준이 **할당되어 있는지 확인합니다.**</span><span class="sxs-lookup"><span data-stu-id="a1b49-137">**Ensure that the device has an Automation Remediation level assigned to it**.</span></span><br>
<span data-ttu-id="a1b49-138">적어도 특정 디바이스 그룹에 대해 최소 재구성 수준을 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-138">You'll need to enable, at least, the minimum Remediation Level for a given Device Group.</span></span> <span data-ttu-id="a1b49-139">그렇지 않으면 해당 그룹의 구성원에게 라이브 응답 세션을 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-139">Otherwise you won't be able to establish a Live Response session to a member of that group.</span></span>

    <span data-ttu-id="a1b49-140">다음 오류가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-140">You'll receive the following error:</span></span>

    ![오류 메시지의 이미지](images/live-response-error.png)

- <span data-ttu-id="a1b49-142">**라이브 응답 부호 없는** 스크립트 실행을 사용하도록 설정(선택 사항).</span><span class="sxs-lookup"><span data-stu-id="a1b49-142">**Enable live response unsigned script execution** (optional).</span></span> <br>

    >[!WARNING]
    ><span data-ttu-id="a1b49-143">부호 없는 스크립트를 사용할 수 있도록 허용하면 위협에 대한 노출이 증가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-143">Allowing the use of unsigned scripts may increase your exposure to threats.</span></span>
 
  <span data-ttu-id="a1b49-144">위협에 대한 노출을 늘리기 위해 부호 없는 스크립트를 실행하는 것은 권장되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-144">Running unsigned scripts is not recommended as it can increase your exposure to threats.</span></span> <span data-ttu-id="a1b49-145">그러나 이 설정을 사용하려면 고급 기능 설정 페이지에서 설정을 [사용하도록 설정해야](advanced-features.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-145">If you must use them however, you'll need to enable the setting in the [Advanced features settings](advanced-features.md) page.</span></span>
    
- <span data-ttu-id="a1b49-146">**적절한 사용 권한이 있는지 확인**</span><span class="sxs-lookup"><span data-stu-id="a1b49-146">**Ensure that you have the appropriate permissions**.</span></span><br>
    <span data-ttu-id="a1b49-147">적절한 사용 권한으로 프로비전된 사용자만 세션을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-147">Only users who have been provisioned with the appropriate permissions can initiate a session.</span></span> <span data-ttu-id="a1b49-148">역할 할당에 대한 자세한 내용은 역할 만들기 [및 관리를 참조하세요.](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="a1b49-148">For more information on role assignments, see [Create and manage roles](user-roles.md).</span></span> 

    > [!IMPORTANT]
    > <span data-ttu-id="a1b49-149">라이브러리에 파일을 업로드하는 옵션은 적절한 RBAC 권한이 있는 사용자만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-149">The option to upload a file to the library is only available to those with the appropriate RBAC permissions.</span></span> <span data-ttu-id="a1b49-150">이 단추는 위임된 사용 권한만 있는 사용자에 대해 회색으로 표시되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-150">The button is greyed out for users with only delegated permissions.</span></span>

    <span data-ttu-id="a1b49-151">부여된 역할에 따라 기본 또는 고급 라이브 응답 명령을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-151">Depending on the role that's been granted to you, you can run basic or advanced live response commands.</span></span> <span data-ttu-id="a1b49-152">사용자 권한은 RBAC 사용자 지정 역할에 의해 제어됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-152">Users permissions are controlled by RBAC custom role.</span></span> 

## <a name="live-response-dashboard-overview"></a><span data-ttu-id="a1b49-153">실시간 응답 대시보드 개요</span><span class="sxs-lookup"><span data-stu-id="a1b49-153">Live response dashboard overview</span></span>
<span data-ttu-id="a1b49-154">디바이스에서 라이브 응답 세션을 시작하면 대시보드가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-154">When you initiate a live response session on a device, a dashboard opens.</span></span> <span data-ttu-id="a1b49-155">대시보드에서는 다음과 같은 세션에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-155">The dashboard provides information about the session such as the following:</span></span> 

- <span data-ttu-id="a1b49-156">Who 세션을 만들지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-156">Who created the session</span></span>
- <span data-ttu-id="a1b49-157">세션이 시작된 시간</span><span class="sxs-lookup"><span data-stu-id="a1b49-157">When the session started</span></span>
- <span data-ttu-id="a1b49-158">세션 기간</span><span class="sxs-lookup"><span data-stu-id="a1b49-158">The duration of the session</span></span>

<span data-ttu-id="a1b49-159">대시보드를 통해 다음에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-159">The dashboard also gives you access to:</span></span>
- <span data-ttu-id="a1b49-160">세션 연결 끊기</span><span class="sxs-lookup"><span data-stu-id="a1b49-160">Disconnect session</span></span>
- <span data-ttu-id="a1b49-161">업로드 파일을 라이브러리에 저장</span><span class="sxs-lookup"><span data-stu-id="a1b49-161">Upload files to the library</span></span> 
- <span data-ttu-id="a1b49-162">명령 콘솔</span><span class="sxs-lookup"><span data-stu-id="a1b49-162">Command console</span></span>
- <span data-ttu-id="a1b49-163">명령 로그</span><span class="sxs-lookup"><span data-stu-id="a1b49-163">Command log</span></span>


## <a name="initiate-a-live-response-session-on-a-device"></a><span data-ttu-id="a1b49-164">장치에서 라이브 응답 세션 시작</span><span class="sxs-lookup"><span data-stu-id="a1b49-164">Initiate a live response session on a device</span></span> 

1. <span data-ttu-id="a1b49-165">로그인하여 Microsoft Defender 보안 센터.</span><span class="sxs-lookup"><span data-stu-id="a1b49-165">Sign in to Microsoft Defender Security Center.</span></span>

2. <span data-ttu-id="a1b49-166">장치 목록 페이지로 이동하여 조사할 장치를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-166">Navigate to the devices list page and select a device to investigate.</span></span> <span data-ttu-id="a1b49-167">장치 페이지가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-167">The devices page opens.</span></span>

3. <span data-ttu-id="a1b49-168">라이브 응답 세션 시작을 선택하여 **라이브 응답 세션을 실행합니다.**</span><span class="sxs-lookup"><span data-stu-id="a1b49-168">Launch the live response session by selecting **Initiate live response session**.</span></span> <span data-ttu-id="a1b49-169">명령 콘솔이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-169">A command console is displayed.</span></span> <span data-ttu-id="a1b49-170">세션이 장치에 연결되는 동안 기다릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-170">Wait while the session connects to the device.</span></span>

4. <span data-ttu-id="a1b49-171">기본 제공 명령을 사용하여 조사 작업을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-171">Use the built-in commands to do investigative work.</span></span> <span data-ttu-id="a1b49-172">자세한 내용은 라이브 응답 [명령을 참조하세요.](#live-response-commands)</span><span class="sxs-lookup"><span data-stu-id="a1b49-172">For more information, see [Live response commands](#live-response-commands).</span></span>

5. <span data-ttu-id="a1b49-173">조사를 완료한 후 세션 연결 **끊기를** 선택한 다음 확인 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="a1b49-173">After completing your investigation, select **Disconnect session**, then select **Confirm**.</span></span>

## <a name="live-response-commands"></a><span data-ttu-id="a1b49-174">라이브 응답 명령</span><span class="sxs-lookup"><span data-stu-id="a1b49-174">Live response commands</span></span>

<span data-ttu-id="a1b49-175">부여된 역할에 따라 기본 또는 고급 라이브 응답 명령을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-175">Depending on the role that's been granted to you, you can run basic or advanced live response commands.</span></span> <span data-ttu-id="a1b49-176">사용자 권한은 RBAC 사용자 지정 역할에 의해 제어됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-176">User permissions are controlled by RBAC custom roles.</span></span> <span data-ttu-id="a1b49-177">역할 할당에 대한 자세한 내용은 역할 만들기 [및 관리를 참조하세요.](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="a1b49-177">For more information on role assignments, see [Create and manage roles](user-roles.md).</span></span> 


>[!NOTE]
><span data-ttu-id="a1b49-178">라이브 응답은 클라우드 기반 대화형 셸로, 최종 사용자와 대상 장치 간의 시스템 부하 및 네트워크 품질에 따라 응답 시간이 달라질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-178">Live response is a cloud-based interactive shell, as such, specific command experience may vary in response time depending on network quality and system load between the end user and the target device.</span></span>

### <a name="basic-commands"></a><span data-ttu-id="a1b49-179">기본 명령</span><span class="sxs-lookup"><span data-stu-id="a1b49-179">Basic commands</span></span>

<span data-ttu-id="a1b49-180">기본 라이브 응답 명령을 실행할 수 있는 권한이 부여된  사용자 역할에 대해 다음 명령을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-180">The following commands are available for user roles that are granted the ability to run **basic** live response commands.</span></span> <span data-ttu-id="a1b49-181">역할 할당에 대한 자세한 내용은 역할 만들기 [및 관리를 참조하세요.](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="a1b49-181">For more information on role assignments, see [Create and manage roles](user-roles.md).</span></span> 

| <span data-ttu-id="a1b49-182">명령</span><span class="sxs-lookup"><span data-stu-id="a1b49-182">Command</span></span> | <span data-ttu-id="a1b49-183">설명</span><span class="sxs-lookup"><span data-stu-id="a1b49-183">Description</span></span> |
|---|---|--- |
|`cd` | <span data-ttu-id="a1b49-184">현재 디렉터리를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-184">Changes the current directory.</span></span> | 
|`cls` | <span data-ttu-id="a1b49-185">콘솔 화면을 지우습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-185">Clears the console screen.</span></span>  |
|`connect` | <span data-ttu-id="a1b49-186">디바이스에 대한 라이브 응답 세션을 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-186">Initiates a live response session to the device.</span></span> |
|`connections` | <span data-ttu-id="a1b49-187">모든 활성 연결을 보여 주며,</span><span class="sxs-lookup"><span data-stu-id="a1b49-187">Shows all the active connections.</span></span> |
|`dir` | <span data-ttu-id="a1b49-188">디렉터리의 파일 및 하위 디렉터리 목록을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-188">Shows a list of files and subdirectories in a directory.</span></span> |
|`drivers` |  <span data-ttu-id="a1b49-189">장치에 설치된 모든 드라이버를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-189">Shows all drivers installed on the device.</span></span> |
|`fg <command ID>` | <span data-ttu-id="a1b49-190">지정한 작업을 포그라운드의 포그라운드에 두어 현재 작업으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-190">Place the specified job in the foreground in the foreground, making it the current job.</span></span> <br> <span data-ttu-id="a1b49-191">참고: fg는 PID가 아니라 작업에서 사용할 수 있는 "명령 ID"를 취합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-191">NOTE: fg takes a “command ID” available from jobs, not a PID</span></span> |
|`fileinfo` | <span data-ttu-id="a1b49-192">파일에 대한 정보를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-192">Get information about a file.</span></span> |
|`findfile` | <span data-ttu-id="a1b49-193">디바이스에서 지정한 이름으로 파일을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-193">Locates files by a given name on the device.</span></span> |
|`getfile <file_path>` | <span data-ttu-id="a1b49-194">파일을 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-194">Downloads a file.</span></span> |
|`help` | <span data-ttu-id="a1b49-195">라이브 응답 명령에 대한 도움말 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-195">Provides help information for live response commands.</span></span> |
|`jobs` | <span data-ttu-id="a1b49-196">현재 실행 중인 작업, ID 및 상태를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-196">Shows currently running jobs, their ID and status.</span></span> |
|`persistence` | <span data-ttu-id="a1b49-197">디바이스에서 알려진 모든 지속성 메서드를 보여 주며,</span><span class="sxs-lookup"><span data-stu-id="a1b49-197">Shows all known persistence methods on the device.</span></span> |
|`processes` | <span data-ttu-id="a1b49-198">디바이스에서 실행 중인 모든 프로세스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-198">Shows all processes running on the device.</span></span> |
|`registry` | <span data-ttu-id="a1b49-199">레지스트리 값을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-199">Shows registry values.</span></span> |
|`scheduledtasks` | <span data-ttu-id="a1b49-200">디바이스의 모든 예약된 작업을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-200">Shows all scheduled tasks on the device.</span></span> |
|`services` | <span data-ttu-id="a1b49-201">디바이스의 모든 서비스를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-201">Shows all services on the device.</span></span> |
|`trace` | <span data-ttu-id="a1b49-202">터미널의 로깅 모드를 디버그로 설정</span><span class="sxs-lookup"><span data-stu-id="a1b49-202">Sets the terminal's logging mode to debug.</span></span> |

### <a name="advanced-commands"></a><span data-ttu-id="a1b49-203">고급 명령</span><span class="sxs-lookup"><span data-stu-id="a1b49-203">Advanced commands</span></span>
<span data-ttu-id="a1b49-204">고급 라이브 응답 명령을 실행할 수 있는 권한이 부여된 사용자 역할에 대해 다음 **명령을** 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-204">The following commands are available for user roles that are granted the ability to run **advanced** live response commands.</span></span> <span data-ttu-id="a1b49-205">역할 할당에 대한 자세한 내용은 역할 만들기 [및 관리를 참조하세요.](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="a1b49-205">For more information on role assignments, see [Create and manage roles](user-roles.md).</span></span> 

| <span data-ttu-id="a1b49-206">명령</span><span class="sxs-lookup"><span data-stu-id="a1b49-206">Command</span></span> | <span data-ttu-id="a1b49-207">설명</span><span class="sxs-lookup"><span data-stu-id="a1b49-207">Description</span></span> |
|---|---|
| `analyze` | <span data-ttu-id="a1b49-208">다양한 판별 엔진을 통해 엔터티를 분석하여 판정에 도달합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-208">Analyses the entity with various incrimination engines to reach a verdict.</span></span> |
| `run` | <span data-ttu-id="a1b49-209">장치의 라이브러리에서 PowerShell 스크립트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-209">Runs a PowerShell script from the library on the device.</span></span> |
| `library` | <span data-ttu-id="a1b49-210">라이브 응답 라이브러리에 업로드된 파일을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-210">Lists files that were uploaded to the live response library.</span></span> |
| `putfile` | <span data-ttu-id="a1b49-211">라이브러리에서 장치로 파일을 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-211">Puts a file from the library to the device.</span></span> <span data-ttu-id="a1b49-212">파일은 작업 폴더에 저장되고 장치가 기본적으로 다시 시작될 때 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-212">Files are saved in a working folder and are deleted when the device restarts by default.</span></span> |
| `remediate` | <span data-ttu-id="a1b49-213">장치에서 엔터티를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-213">Remediates an entity on the device.</span></span> <span data-ttu-id="a1b49-214">수정 작업은 엔터티 유형에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-214">The remediation action will vary depending on the entity type:</span></span><br><span data-ttu-id="a1b49-215">- 파일: 삭제</span><span class="sxs-lookup"><span data-stu-id="a1b49-215">- File: delete</span></span><br><span data-ttu-id="a1b49-216">- 프로세스: 이미지 파일 중지, 삭제</span><span class="sxs-lookup"><span data-stu-id="a1b49-216">- Process: stop, delete image file</span></span><br><span data-ttu-id="a1b49-217">- 서비스: 이미지 파일 중지, 삭제</span><span class="sxs-lookup"><span data-stu-id="a1b49-217">- Service: stop, delete image file</span></span><br><span data-ttu-id="a1b49-218">- 레지스트리 항목: delete</span><span class="sxs-lookup"><span data-stu-id="a1b49-218">- Registry entry: delete</span></span><br><span data-ttu-id="a1b49-219">- 예약된 작업: remove</span><span class="sxs-lookup"><span data-stu-id="a1b49-219">- Scheduled task: remove</span></span><br><span data-ttu-id="a1b49-220">- 시작 폴더 항목: 파일 삭제</span><span class="sxs-lookup"><span data-stu-id="a1b49-220">- Startup folder item: delete file</span></span> <br> <span data-ttu-id="a1b49-221">참고: 이 명령에는 선행 명령이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-221">NOTE: This command has a prerequisite command.</span></span> <span data-ttu-id="a1b49-222">명령을 함께 사용하여 자동으로 선행 명령을 실행할 `-auto` `remediate` 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-222">You can use the `-auto` command in conjunction with `remediate` to automatically run the prerequisite command.</span></span> 
|`undo` | <span data-ttu-id="a1b49-223">수정된 엔터티를 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-223">Restores an entity that was remediated.</span></span> |


## <a name="use-live-response-commands"></a><span data-ttu-id="a1b49-224">라이브 응답 명령 사용</span><span class="sxs-lookup"><span data-stu-id="a1b49-224">Use live response commands</span></span>

<span data-ttu-id="a1b49-225">콘솔에서 사용할 수 있는 명령은 명령과 [Windows 합니다.](/windows-server/administration/windows-commands/windows-commands#BKMK_c)</span><span class="sxs-lookup"><span data-stu-id="a1b49-225">The commands that you can use in the console follow similar principles as [Windows Commands](/windows-server/administration/windows-commands/windows-commands#BKMK_c).</span></span>

<span data-ttu-id="a1b49-226">고급 명령은 파일 다운로드 및 업로드, 장치에서 스크립트 실행, 엔터티에 대한 수정 작업 등의 보다 강력한 작업을 수행할 수 있는 보다 강력한 작업 집합을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-226">The advanced commands offer a more robust set of actions that allow you to take more powerful actions such as download and upload a file, run scripts on the device, and take remediation actions on an entity.</span></span>

### <a name="get-a-file-from-the-device"></a><span data-ttu-id="a1b49-227">장치에서 파일 다운로드</span><span class="sxs-lookup"><span data-stu-id="a1b49-227">Get a file from the device</span></span>

<span data-ttu-id="a1b49-228">조사하고 있는 장치에서 파일을 다운로드하는 시나리오의 경우 명령을 사용할 수 `getfile` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-228">For scenarios when you'd like get a file from a device you're investigating, you can use the `getfile` command.</span></span> <span data-ttu-id="a1b49-229">이렇게 하면 추가 조사를 위해 장치에서 파일을 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-229">This allows you to save the file from the device for further investigation.</span></span>

>[!NOTE]
><span data-ttu-id="a1b49-230">다음 파일 크기 제한이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-230">The following file size limits apply:</span></span>
>- <span data-ttu-id="a1b49-231">`getfile` 제한: 3GB</span><span class="sxs-lookup"><span data-stu-id="a1b49-231">`getfile` limit: 3 GB</span></span>
>- <span data-ttu-id="a1b49-232">`fileinfo` 제한: 10GB</span><span class="sxs-lookup"><span data-stu-id="a1b49-232">`fileinfo` limit: 10 GB</span></span>
>- <span data-ttu-id="a1b49-233">`library` 제한: 250MB</span><span class="sxs-lookup"><span data-stu-id="a1b49-233">`library` limit: 250 MB</span></span>

### <a name="download-a-file-in-the-background"></a><span data-ttu-id="a1b49-234">백그라운드에서 파일 다운로드</span><span class="sxs-lookup"><span data-stu-id="a1b49-234">Download a file in the background</span></span>

<span data-ttu-id="a1b49-235">보안 운영 팀이 영향을 미치는 장치 조사를 계속할 수 있도록 파일을 백그라운드에서 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-235">To enable your security operations team to continue investigating an impacted device, files can now be downloaded in the background.</span></span>

- <span data-ttu-id="a1b49-236">백그라운드에서 파일을 다운로드하려면 라이브 응답 명령 콘솔에 를 `download <file_path> &` 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-236">To download a file in the background, in the live response command console, type `download <file_path> &`.</span></span>
- <span data-ttu-id="a1b49-237">파일이 다운로드될 때까지 기다리는 경우 Ctrl + Z를 사용하여 백그라운드로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-237">If you are waiting for a file to be downloaded, you can move it to the background by using Ctrl + Z.</span></span>
- <span data-ttu-id="a1b49-238">파일 다운로드를 포그라운드로 가져오기 위해 라이브 응답 명령 콘솔에 를 `fg <command_id>` 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-238">To bring a file download to the foreground, in the live response command console, type `fg <command_id>`.</span></span>

<span data-ttu-id="a1b49-239">다음은 몇 가지 예입니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-239">Here are some examples:</span></span>


|<span data-ttu-id="a1b49-240">명령</span><span class="sxs-lookup"><span data-stu-id="a1b49-240">Command</span></span>  |<span data-ttu-id="a1b49-241">속성 기능</span><span class="sxs-lookup"><span data-stu-id="a1b49-241">What it does</span></span>  |
|---------|---------|
|`getfile "C:\windows\some_file.exe" &`     |<span data-ttu-id="a1b49-242">백그라운드에서 이름이some_file.exe *다운로드를* 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-242">Starts downloading a file named *some_file.exe* in the background.</span></span>         |
|`fg 1234`     |<span data-ttu-id="a1b49-243">명령 ID가 *1234인* 다운로드를 포그라운드로 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-243">Returns a download with command ID *1234* to the foreground.</span></span>         |


### <a name="put-a-file-in-the-library"></a><span data-ttu-id="a1b49-244">라이브러리에 파일 저장</span><span class="sxs-lookup"><span data-stu-id="a1b49-244">Put a file in the library</span></span>

<span data-ttu-id="a1b49-245">라이브 응답에는 파일을 넣을 수 있는 라이브러리가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-245">Live response has a library where you can put files into.</span></span> <span data-ttu-id="a1b49-246">라이브러리에는 테넌트 수준에서 라이브 응답 세션에서 실행할 수 있는 파일(예: 스크립트)이 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-246">The library stores files (such as scripts) that can be run in a live response session at the tenant level.</span></span>

<span data-ttu-id="a1b49-247">실시간 응답을 통해 PowerShell 스크립트를 실행할 수 있습니다. 그러나 먼저 파일을 라이브러리에 저장해야 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-247">Live response allows PowerShell scripts to run, however you must first put the files into the library before you can run them.</span></span> 

<span data-ttu-id="a1b49-248">라이브 응답 세션을 시작하는 디바이스에서 실행할 수 있는 PowerShell 스크립트 컬렉션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-248">You can have a collection of PowerShell scripts that can run on devices that you initiate live response sessions with.</span></span> 

#### <a name="to-upload-a-file-in-the-library"></a><span data-ttu-id="a1b49-249">라이브러리에서 파일을 업로드하려면</span><span class="sxs-lookup"><span data-stu-id="a1b49-249">To upload a file in the library</span></span>

1. <span data-ttu-id="a1b49-250">라이브러리에 **업로드 파일을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="a1b49-250">Click **Upload file to library**.</span></span> 

2. <span data-ttu-id="a1b49-251">**찾아보기를** 클릭하고 파일을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-251">Click **Browse** and select the file.</span></span>

3. <span data-ttu-id="a1b49-252">간단한 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-252">Provide a brief description.</span></span>

4. <span data-ttu-id="a1b49-253">같은 이름의 파일을 덮어 사용할지 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-253">Specify if you'd like to overwrite a file with the same name.</span></span>

5. <span data-ttu-id="a1b49-254">원하는 경우 스크립트에 필요한 매개 변수를 알고자 하는 경우 스크립트 매개 변수 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-254">If you'd like to be,  know what parameters are needed for the script, select the script parameters check box.</span></span> <span data-ttu-id="a1b49-255">텍스트 필드에 예제와 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-255">In the text field, enter an example and a description.</span></span>

6. <span data-ttu-id="a1b49-256">확인을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="a1b49-256">Click **Confirm**.</span></span> 

7. <span data-ttu-id="a1b49-257">(선택 사항) 파일이 라이브러리에 업로드 됐는지 확인하려면 명령을 `library` 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-257">(Optional) To verify that the file was uploaded to the library, run the `library` command.</span></span>


### <a name="cancel-a-command"></a><span data-ttu-id="a1b49-258">명령 취소</span><span class="sxs-lookup"><span data-stu-id="a1b49-258">Cancel a command</span></span>
<span data-ttu-id="a1b49-259">세션 중에 언제든지 Ctrl + C를 눌러 명령을 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-259">Anytime during a session, you can cancel a command by pressing CTRL + C.</span></span>  

>[!WARNING]
><span data-ttu-id="a1b49-260">이 바로 가기를 사용하면 에이전트 쪽의 명령이 중지되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-260">Using this shortcut will not stop the command in the agent side.</span></span> <span data-ttu-id="a1b49-261">포털에서 명령만 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-261">It will only cancel the command in the portal.</span></span> <span data-ttu-id="a1b49-262">따라서 명령이 취소된 동안 "재구성" 등의 변경 작업이 계속될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-262">So, changing operations such as "remediate" may continue, while the command is canceled.</span></span> 

## <a name="run-a-powershell-script"></a><span data-ttu-id="a1b49-263">PowerShell 스크립트 실행</span><span class="sxs-lookup"><span data-stu-id="a1b49-263">Run a PowerShell script</span></span> 

<span data-ttu-id="a1b49-264">PowerShell 스크립트를 실행하려면 먼저 라이브러리에 업로드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-264">Before you can run a PowerShell script, you must first upload it to the library.</span></span> 

<span data-ttu-id="a1b49-265">스크립트를 라이브러리에 업로드한 후 명령을 사용하여 `run` 스크립트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-265">After uploading the script to the library, use the `run` command to run the script.</span></span>

<span data-ttu-id="a1b49-266">세션에서 부호 없는 스크립트를 사용하려면 고급 기능 설정 페이지에서 설정을 사용하도록 [설정해야](advanced-features.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-266">If you plan to use an unsigned script in the session, you'll need to enable the setting in the [Advanced features settings](advanced-features.md) page.</span></span>

>[!WARNING]
><span data-ttu-id="a1b49-267">부호 없는 스크립트를 사용할 수 있도록 허용하면 위협에 대한 노출이 증가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-267">Allowing the use of unsigned scripts may increase your exposure to threats.</span></span>

## <a name="apply-command-parameters"></a><span data-ttu-id="a1b49-268">명령 매개 변수 적용</span><span class="sxs-lookup"><span data-stu-id="a1b49-268">Apply command parameters</span></span>

- <span data-ttu-id="a1b49-269">콘솔 도움말을 보고 명령 매개 변수에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-269">View the console help to learn about command parameters.</span></span> <span data-ttu-id="a1b49-270">개별 명령에 대해 알아보고 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-270">To learn about an individual command, run:</span></span>
 
    `help <command name>`

- <span data-ttu-id="a1b49-271">명령에 매개 변수를 적용할 때 매개 변수는 고정된 순서에 따라 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-271">When applying parameters to commands, note that parameters are handled based on a fixed order:</span></span>
 
    `<command name> param1 param2` 

- <span data-ttu-id="a1b49-272">고정 순서 외부에 매개 변수를 지정할 때 값을 제공하기 전에 하이픈으로 매개 변수의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-272">When specifying parameters outside of the fixed order, specify the name of the parameter with a hyphen before providing the value:</span></span>
 
    `<command name> -param2_name param2`

- <span data-ttu-id="a1b49-273">선행 명령이 있는 명령을 사용하는 경우 플래그를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-273">When using commands that have prerequisite commands, you can use flags:</span></span>

    <span data-ttu-id="a1b49-274">`<command name> -type file -id <file path> - auto` 또는 `remediate file <file path> - auto` .</span><span class="sxs-lookup"><span data-stu-id="a1b49-274">`<command name> -type file -id <file path> - auto` or `remediate file <file path> - auto`.</span></span>

## <a name="supported-output-types"></a><span data-ttu-id="a1b49-275">지원되는 출력 형식</span><span class="sxs-lookup"><span data-stu-id="a1b49-275">Supported output types</span></span>

<span data-ttu-id="a1b49-276">라이브 응답은 테이블 및 JSON 형식 출력 형식을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-276">Live response supports table and JSON format output types.</span></span> <span data-ttu-id="a1b49-277">각 명령에 대해 기본 출력 동작이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-277">For each command, there's a default output behavior.</span></span> <span data-ttu-id="a1b49-278">다음 명령을 사용하여 원하는 출력 형식의 출력을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-278">You can modify the output in your preferred output format using the following commands:</span></span>

- `-output json`
- `-output table`

>[!NOTE]
><span data-ttu-id="a1b49-279">제한된 공간으로 인해 테이블 형식으로 표시되는 필드 수가 적습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-279">Fewer fields are shown in table format due to the limited space.</span></span> <span data-ttu-id="a1b49-280">출력에서 더 많은 세부 정보를 표시하기 위해 JSON 출력 명령을 사용하여 더 많은 세부 정보를 표시하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-280">To see more details in the output, you can use the JSON output command so that more details are shown.</span></span>

## <a name="supported-output-pipes"></a><span data-ttu-id="a1b49-281">지원되는 출력 파이프</span><span class="sxs-lookup"><span data-stu-id="a1b49-281">Supported output pipes</span></span>

<span data-ttu-id="a1b49-282">실시간 응답은 CLI 및 파일에 대한 출력 파이핑을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-282">Live response supports output piping to CLI and file.</span></span> <span data-ttu-id="a1b49-283">CLI는 기본 출력 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-283">CLI is the default output behavior.</span></span> <span data-ttu-id="a1b49-284">[command] > [filename]을 사용하여 출력을 파일에 파이프할 수 .txt.</span><span class="sxs-lookup"><span data-stu-id="a1b49-284">You can pipe the output to a file using the following command: [command] > [filename].txt.</span></span>  

<span data-ttu-id="a1b49-285">예제:</span><span class="sxs-lookup"><span data-stu-id="a1b49-285">Example:</span></span>

```console
processes > output.txt
```

## <a name="view-the-command-log"></a><span data-ttu-id="a1b49-286">명령 로그 보기</span><span class="sxs-lookup"><span data-stu-id="a1b49-286">View the command log</span></span>

<span data-ttu-id="a1b49-287">세션 **중에** 디바이스에서 사용되는 명령을 확인하려면 명령 로그 탭을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-287">Select the **Command log** tab to see the commands used on the device during a session.</span></span> <span data-ttu-id="a1b49-288">각 명령은 전체 세부 정보(예: )를 사용하여 추적됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-288">Each command is tracked with full details such as:</span></span>
- <span data-ttu-id="a1b49-289">ID</span><span class="sxs-lookup"><span data-stu-id="a1b49-289">ID</span></span>
- <span data-ttu-id="a1b49-290">명령줄</span><span class="sxs-lookup"><span data-stu-id="a1b49-290">Command line</span></span>
- <span data-ttu-id="a1b49-291">기간</span><span class="sxs-lookup"><span data-stu-id="a1b49-291">Duration</span></span>
- <span data-ttu-id="a1b49-292">상태 및 입력 또는 출력 사이드바</span><span class="sxs-lookup"><span data-stu-id="a1b49-292">Status and input or output side bar</span></span>

## <a name="limitations"></a><span data-ttu-id="a1b49-293">제한 사항</span><span class="sxs-lookup"><span data-stu-id="a1b49-293">Limitations</span></span>

- <span data-ttu-id="a1b49-294">라이브 응답 세션은 한 때 25개 라이브 응답 세션으로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-294">Live response sessions are limited to 25 live response sessions at a time.</span></span>
- <span data-ttu-id="a1b49-295">라이브 응답 세션 비활성 시간 제한 값은 30분입니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-295">Live response session inactive timeout value is 30 minutes.</span></span> 
- <span data-ttu-id="a1b49-296">사용자는 최대 10개까지 동시 세션을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-296">A user can initiate up to 10 concurrent sessions.</span></span>
- <span data-ttu-id="a1b49-297">디바이스는 한 번의 세션에만 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-297">A device can only be in one session at a time.</span></span>
- <span data-ttu-id="a1b49-298">다음 파일 크기 제한이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1b49-298">The following file size limits apply:</span></span>
   - <span data-ttu-id="a1b49-299">`getfile` 제한: 3GB</span><span class="sxs-lookup"><span data-stu-id="a1b49-299">`getfile` limit: 3 GB</span></span>
   - <span data-ttu-id="a1b49-300">`fileinfo` 제한: 10GB</span><span class="sxs-lookup"><span data-stu-id="a1b49-300">`fileinfo` limit: 10 GB</span></span>
   - <span data-ttu-id="a1b49-301">`library` 제한: 250MB</span><span class="sxs-lookup"><span data-stu-id="a1b49-301">`library` limit: 250 MB</span></span>

## <a name="related-article"></a><span data-ttu-id="a1b49-302">관련 문서</span><span class="sxs-lookup"><span data-stu-id="a1b49-302">Related article</span></span>
- [<span data-ttu-id="a1b49-303">실시간 대응 명령 예제</span><span class="sxs-lookup"><span data-stu-id="a1b49-303">Live response command examples</span></span>](live-response-command-examples.md)
