---
title: 끝점용 Microsoft Defender에서 파일에 대한 응답 작업 수행
description: 파일을 중지 및 차단하거나 파일을 차단하고 활동 세부 정보를 확인하여 파일 관련 경고에 대한 대응 조치를 취합니다.
keywords: 응답, 중지 및 검사, 파일 차단, 심층 분석
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
ms.openlocfilehash: 1f189956d65e6d08d8e00272ba0d8db3ba59f6d4
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844083"
---
# <a name="take-response-actions-on-a-file"></a><span data-ttu-id="54e55-104">파일에 대해 대응 조치 실행</span><span class="sxs-lookup"><span data-stu-id="54e55-104">Take response actions on a file</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="54e55-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="54e55-105">**Applies to:**</span></span>
- [<span data-ttu-id="54e55-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="54e55-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

[!include[Prerelease information](../../includes/prerelease.md)]

> <span data-ttu-id="54e55-107">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="54e55-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="54e55-108">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-responddile-abovefoldlink)

<span data-ttu-id="54e55-109">파일을 중지 및 차단하거나 파일을 차단하여 감지된 공격에 신속하게 대응합니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-109">Quickly respond to detected attacks by stopping and quarantining files or blocking a file.</span></span> <span data-ttu-id="54e55-110">파일에 대한 작업을 수행한 후 작업 센터에서 활동 세부 정보를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-110">After taking action on files, you can check activity details in the Action center.</span></span>

<span data-ttu-id="54e55-111">응답 작업은 파일의 자세한 프로필 페이지에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-111">Response actions are available on a file's detailed profile page.</span></span> <span data-ttu-id="54e55-112">이 페이지에서는 새 파일 페이지를 전환하여 새 페이지 레이아웃과 이전 페이지 레이아웃 간에 **전환할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="54e55-112">Once on this page, you can switch between the new and old page layouts by toggling **new File page**.</span></span> <span data-ttu-id="54e55-113">이 문서의 나머지에서는 새로운 페이지 레이아웃에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-113">The rest of this article describes the newer page layout.</span></span>

<span data-ttu-id="54e55-114">응답 작업은 파일 페이지 위쪽을 따라 실행하고 다음을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-114">Response actions run along the top of the file page, and include:</span></span>

- <span data-ttu-id="54e55-115">파일 중지 및 Quarantine</span><span class="sxs-lookup"><span data-stu-id="54e55-115">Stop and Quarantine File</span></span>
- <span data-ttu-id="54e55-116">표시기 추가</span><span class="sxs-lookup"><span data-stu-id="54e55-116">Add Indicator</span></span>
- <span data-ttu-id="54e55-117">파일 다운로드</span><span class="sxs-lookup"><span data-stu-id="54e55-117">Download file</span></span>
- <span data-ttu-id="54e55-118">위협 전문가에게 문의</span><span class="sxs-lookup"><span data-stu-id="54e55-118">Consult a threat expert</span></span>
- <span data-ttu-id="54e55-119">작업 센터</span><span class="sxs-lookup"><span data-stu-id="54e55-119">Action center</span></span>

<span data-ttu-id="54e55-120">또한 심층 분석을 위해 파일을 제출하여 안전한 클라우드 샌드박스에서 파일을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-120">You can also submit files for deep analysis, to run the file in a secure cloud sandbox.</span></span> <span data-ttu-id="54e55-121">분석이 완료되면 파일의 동작에 대한 정보를 제공하는 자세한 보고서가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-121">When the analysis is complete, you'll get a detailed report that provides information about the behavior of the file.</span></span> <span data-ttu-id="54e55-122">심층 분석을 위해 파일을 제출하고 심층 분석 탭을 선택하여 지난 보고서를 읽을 **수** 있습니다. 파일 정보 카드 아래에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-122">You can submit files for deep analysis and read past reports by selecting the **Deep analysis** tab. It's located below the file information cards.</span></span>

<span data-ttu-id="54e55-123">일부 작업을 수행하려면 특정 사용 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-123">Some actions require certain permissions.</span></span> <span data-ttu-id="54e55-124">다음 표에서는 PE(이식 가능한 실행 파일) 및 PE가 아닌 파일에 대해 특정 사용 권한이 취할 수 있는 작업을 설명하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-124">The following table describes what action certain permissions can take on portable executable (PE) and non-PE files:</span></span>

| <span data-ttu-id="54e55-125">사용 권한</span><span class="sxs-lookup"><span data-stu-id="54e55-125">Permission</span></span>             | <span data-ttu-id="54e55-126">PE 파일</span><span class="sxs-lookup"><span data-stu-id="54e55-126">PE files</span></span> | <span data-ttu-id="54e55-127">PE가 아닌 파일</span><span class="sxs-lookup"><span data-stu-id="54e55-127">Non-PE files</span></span> |
| :--------------------- | :------: | :----------: |
| <span data-ttu-id="54e55-128">데이터 보기</span><span class="sxs-lookup"><span data-stu-id="54e55-128">View data</span></span>              |     <span data-ttu-id="54e55-129">X</span><span class="sxs-lookup"><span data-stu-id="54e55-129">X</span></span>    |       <span data-ttu-id="54e55-130">X 키</span><span class="sxs-lookup"><span data-stu-id="54e55-130">X</span></span>      |
| <span data-ttu-id="54e55-131">경고 조사</span><span class="sxs-lookup"><span data-stu-id="54e55-131">Alerts investigation</span></span>   | <span data-ttu-id="54e55-132">&#x2611;</span><span class="sxs-lookup"><span data-stu-id="54e55-132">&#x2611;</span></span> |       <span data-ttu-id="54e55-133">X 키</span><span class="sxs-lookup"><span data-stu-id="54e55-133">X</span></span>      |
| <span data-ttu-id="54e55-134">실시간 응답 기본</span><span class="sxs-lookup"><span data-stu-id="54e55-134">Live response basic</span></span>    |     <span data-ttu-id="54e55-135">X</span><span class="sxs-lookup"><span data-stu-id="54e55-135">X</span></span>    |       <span data-ttu-id="54e55-136">X 키</span><span class="sxs-lookup"><span data-stu-id="54e55-136">X</span></span>      |
| <span data-ttu-id="54e55-137">실시간 응답 고급</span><span class="sxs-lookup"><span data-stu-id="54e55-137">Live response advanced</span></span> | <span data-ttu-id="54e55-138">&#x2611;</span><span class="sxs-lookup"><span data-stu-id="54e55-138">&#x2611;</span></span> |   <span data-ttu-id="54e55-139">&#x2611;</span><span class="sxs-lookup"><span data-stu-id="54e55-139">&#x2611;</span></span>   |

<span data-ttu-id="54e55-140">역할에 대한 자세한 내용은 역할 기반 액세스 제어에 대한 역할 [만들기 및 관리를 참조하세요.](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="54e55-140">For more information on roles, see [Create and manage roles for role-based access control](user-roles.md).</span></span>

## <a name="stop-and-quarantine-files-in-your-network"></a><span data-ttu-id="54e55-141">네트워크에서 파일 중지 및 격리</span><span class="sxs-lookup"><span data-stu-id="54e55-141">Stop and quarantine files in your network</span></span>

<span data-ttu-id="54e55-142">악의적인 프로세스를 중지하고 파일이 관찰된 파일을 대리하여 조직에서 공격을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-142">You can contain an attack in your organization by stopping the malicious process and quarantining the file where it was observed.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="54e55-143">이 작업은 다음의 경우만 취할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-143">You can only take this action if:</span></span>
>
> - <span data-ttu-id="54e55-144">작업을 수행 중인 장치가 버전 1703 이상에서 Windows 10 실행 중입니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-144">The device you're taking the action on is running Windows 10, version 1703 or later</span></span>
> - <span data-ttu-id="54e55-145">파일이 신뢰할 수 있는 타사 게시자에 속하지 않는 경우 또는 Microsoft에서 서명하지 않은 경우</span><span class="sxs-lookup"><span data-stu-id="54e55-145">The file does not belong to trusted third-party publishers or not signed by Microsoft</span></span>
> - <span data-ttu-id="54e55-146">Microsoft Defender 바이러스 백신 수동 모드에서 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-146">Microsoft Defender Antivirus must at least be running on Passive mode.</span></span> <span data-ttu-id="54e55-147">자세한 내용은 호환성 [Microsoft Defender 바이러스 백신 참조하세요.](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)</span><span class="sxs-lookup"><span data-stu-id="54e55-147">For more information, see [Microsoft Defender Antivirus compatibility](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility).</span></span>

<span data-ttu-id="54e55-148">파일 중지 및 **Quarantine 작업으로는** 실행 중인 프로세스를 중지하고, 파일을 검지하고, 레지스트리 키와 같은 영구 데이터를 삭제하는 작업이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-148">The **Stop and Quarantine File** action includes stopping running processes, quarantining the files, and deleting persistent data such as registry keys.</span></span>

<span data-ttu-id="54e55-149">이 작업은 지난 30일 동안 Windows 10 버전 1703 이상이 있는 장치에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-149">This action takes effect on devices with Windows 10, version 1703 or later, where the file was observed in the last 30 days.</span></span>

> [!NOTE]
> <span data-ttu-id="54e55-150">파일을 무단으로 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-150">You’ll be able to restore the file from quarantine at any time.</span></span>

### <a name="stop-and-quarantine-files"></a><span data-ttu-id="54e55-151">파일 중지 및 검지</span><span class="sxs-lookup"><span data-stu-id="54e55-151">Stop and quarantine files</span></span>

1. <span data-ttu-id="54e55-152">중지하고 검사할 파일을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-152">Select the file you want to stop and quarantine.</span></span> <span data-ttu-id="54e55-153">다음 보기에서 파일을 선택하거나 검색 상자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-153">You can select a file from any of the following views or use the Search box:</span></span>

   - <span data-ttu-id="54e55-154">**경고** - 아티팩트 타임라인의 설명 또는 세부 정보에서 해당 링크를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-154">**Alerts** - click the corresponding links from the Description or Details in the Artifact timeline</span></span>
   - <span data-ttu-id="54e55-155">**검색 상자** - **드롭다운** 메뉴에서 파일을 선택하고 파일 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-155">**Search box** - select **File** from the drop–down menu and enter the file name</span></span>

   > [!NOTE]
   > <span data-ttu-id="54e55-156">파일 중지 및 검지 작업은 최대 1,000개 장치로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-156">The stop and quarantine file action is limited to a maximum of 1000 devices.</span></span> <span data-ttu-id="54e55-157">더 많은 수의 장치에서 파일을 중지하기 위해 표시기 추가를 참조하여 파일을 [차단하거나 허용합니다.](#add-indicator-to-block-or-allow-a-file)</span><span class="sxs-lookup"><span data-stu-id="54e55-157">To stop a file on a larger number of devices, see [Add indicator to block or allow file](#add-indicator-to-block-or-allow-a-file).</span></span>

2. <span data-ttu-id="54e55-158">위쪽 표시줄로 이동하여 파일 중지 **및 Quarantine 을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="54e55-158">Go to the top bar and select **Stop and Quarantine File**.</span></span>

   ![파일 중지 및 검지 작업의 이미지](images/atp-stop-quarantine-file.png)

3. <span data-ttu-id="54e55-160">이유를 지정한 다음 확인 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="54e55-160">Specify a reason, then select **Confirm**.</span></span>

   ![파일 모달 창 중지 및 검지 이미지](images/atp-stop-quarantine.png)

   <span data-ttu-id="54e55-162">Action Center에는 제출 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-162">The Action center shows the submission information:</span></span>
   
   ![파일 중지 및 검지 작업 센터 이미지](images/atp-stopnquarantine-file.png)

   - <span data-ttu-id="54e55-164">**제출 시간** - 작업이 제출된 시간을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-164">**Submission time** - Shows when the action was submitted.</span></span>
   - <span data-ttu-id="54e55-165">**Success** - 파일이 중지 및 대리된 장치 수를 보여 주며,</span><span class="sxs-lookup"><span data-stu-id="54e55-165">**Success** - Shows the number of devices where the file has been stopped and quarantined.</span></span>
   - <span data-ttu-id="54e55-166">**Failed** - 작업이 실패한 장치 수와 실패에 대한 세부 정보를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-166">**Failed** - Shows the number of devices where the action failed and details about the failure.</span></span>
   - <span data-ttu-id="54e55-167">**보류** 중 - 파일이 아직 중지 및 중단되지 않은 장치 수를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-167">**Pending** - Shows the number of devices where the file is yet to be stopped and quarantined from.</span></span> <span data-ttu-id="54e55-168">디바이스가 오프라인 상태이거나 네트워크에 연결되지 않은 경우 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-168">This can take time for cases when the device is offline or not connected to the network.</span></span>

4. <span data-ttu-id="54e55-169">상태에 대한 자세한 정보를 확인하려면 상태 표시기를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-169">Select any of the status indicators to view more information about the action.</span></span> <span data-ttu-id="54e55-170">예를 들어 **실패를** 선택하여 작업이 실패한 위치를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-170">For example, select **Failed** to see where the action failed.</span></span>

<span data-ttu-id="54e55-171">**장치 사용자에 대한 알림**:</span><span class="sxs-lookup"><span data-stu-id="54e55-171">**Notification on device user**:</span></span></br>
<span data-ttu-id="54e55-172">장치에서 파일을 제거하면 다음 알림이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-172">When the file is being removed from a device, the following notification is shown:</span></span>

![장치 사용자에 대한 알림 이미지](images/atp-notification-file.png)

<span data-ttu-id="54e55-174">장치 타임라인에서 파일이 중지 및 중단된 각 장치에 대해 새 이벤트가 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-174">In the device timeline, a new event is added for each device where a file was stopped and quarantined.</span></span>

<span data-ttu-id="54e55-175">조직 전체에서 널리 사용되는 파일에 대한 작업을 구현하기 전에 경고가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-175">A warning is shown before the action is implemented for files widely used throughout an organization.</span></span> <span data-ttu-id="54e55-176">작업이 의도된지 유효성을 검사하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-176">It's to validate that the operation is intended.</span></span>

## <a name="restore-file-from-quarantine"></a><span data-ttu-id="54e55-177">격리로부터 파일 복원</span><span class="sxs-lookup"><span data-stu-id="54e55-177">Restore file from quarantine</span></span>

<span data-ttu-id="54e55-178">조사 후에 파일이 정리된 것으로 판단되면 파일을 롤백하고 검지에서 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-178">You can roll back and remove a file from quarantine if you’ve determined that it’s clean after an investigation.</span></span> <span data-ttu-id="54e55-179">파일이 중단된 각 디바이스에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-179">Run the following command on each device where the file was quarantined.</span></span>

1. <span data-ttu-id="54e55-180">디바이스에서 상승된 명령줄 프롬프트를 니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-180">Open an elevated command–line prompt on the device:</span></span>

   1. <span data-ttu-id="54e55-181">**시작**(으)로 이동하고 _cmd_ 를 입력하십시오.</span><span class="sxs-lookup"><span data-stu-id="54e55-181">Go to **Start** and type _cmd_.</span></span>

   1. <span data-ttu-id="54e55-182">명령 **프롬프트를 마우스 오른쪽 단추로 클릭하고** **관리자 권한으로 실행을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="54e55-182">Right–click **Command prompt** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="54e55-183">다음 명령을 입력하고 **Enter를 누를 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="54e55-183">Enter the following command, and press **Enter**:</span></span>

   ```powershell
   “%ProgramFiles%\Windows Defender\MpCmdRun.exe” –Restore –Name EUS:Win32/CustomEnterpriseBlock –All
   ```

> [!NOTE]
> <span data-ttu-id="54e55-184">일부 시나리오에서는 **ThreatName이** EUS:Win32/CustomEnterpriseBlock!cl과 같은 것으로 나타날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-184">In some scenarios, the **ThreatName** may appear as: EUS:Win32/CustomEnterpriseBlock!cl.</span></span>
>
> <span data-ttu-id="54e55-185">Endpoint용 Defender는 지난 30일 동안 이 장치에서 차단된 모든 사용자 지정 차단 파일을 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-185">Defender for Endpoint will restore all custom blocked files that were quarantined on this device in the last 30 days.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="54e55-186">잠재적인 네트워크 위협으로 고지된 파일은 복구할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-186">A file that was quarantined as a potential network threat might not be recoverable.</span></span> <span data-ttu-id="54e55-187">사용자가 파일을 검지 후에 복원하려고 시도하면 해당 파일에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-187">If a user attempts to restore the file after quarantine, that file might not be accessible.</span></span> <span data-ttu-id="54e55-188">시스템에 파일에 액세스하기 위한 네트워크 자격 증명이 더 이상 필요하기 때문일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-188">This can be due to the system no longer having network credentials to access the file.</span></span> <span data-ttu-id="54e55-189">일반적으로 시스템 또는 공유 폴더에 일시적으로 로그온하고 액세스 토큰이 만료된 결과입니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-189">Typically, this is a result of a temporary log on to a system or shared folder and the access tokens expired.</span></span>

## <a name="download-or-collect-file"></a><span data-ttu-id="54e55-190">파일 다운로드 또는 수집</span><span class="sxs-lookup"><span data-stu-id="54e55-190">Download or collect file</span></span>

<span data-ttu-id="54e55-191">응답 **작업에서** 파일 다운로드를 선택하면 파일이 포함된 로컬 암호로 보호된 .zip 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-191">Selecting **Download file** from the response actions allows you to download a local, password-protected .zip archive containing your file.</span></span> <span data-ttu-id="54e55-192">파일을 다운로드하는 이유를 기록하고 암호를 설정할 수 있는 플라이아웃이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-192">A flyout will appear where you can record a reason for downloading the file, and set a password.</span></span>

<span data-ttu-id="54e55-193">기본적으로는 검지된 파일을 다운로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-193">By default, you will not be able to download files that are in quarantine.</span></span>

![파일 다운로드 작업의 이미지](images/atp-download-file-action.png)

### <a name="collect-files"></a><span data-ttu-id="54e55-195">파일 수집</span><span class="sxs-lookup"><span data-stu-id="54e55-195">Collect files</span></span>

<span data-ttu-id="54e55-196">파일이 끝점용 Microsoft Defender에 아직 저장되어 있지 않은 경우 다운로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-196">If a file is not already stored by Microsoft Defender for Endpoint, you can't download it.</span></span> <span data-ttu-id="54e55-197">대신 동일한 위치에 파일  수집 단추가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-197">Instead, you'll see a **Collect file** button in the same location.</span></span> <span data-ttu-id="54e55-198">지난 30일 동안 조직에 파일이 없는 경우 파일  수집을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-198">If a file hasn't been seen in the organization in the past 30 days, **Collect file** will be disabled.</span></span>
> [!Important]
> <span data-ttu-id="54e55-199">잠재적인 네트워크 위협으로 고지된 파일은 복구할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-199">A file that was quarantined as a potential network threat might not be recoverable.</span></span> <span data-ttu-id="54e55-200">사용자가 파일을 검지 후에 복원하려고 시도하면 해당 파일에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-200">If a user attempts to restore the file after quarantine, that file might not be accessible.</span></span> <span data-ttu-id="54e55-201">시스템에 파일에 액세스하기 위한 네트워크 자격 증명이 더 이상 필요하기 때문일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-201">This can be due to the system no longer having network credentials to access the file.</span></span> <span data-ttu-id="54e55-202">일반적으로 시스템 또는 공유 폴더에 일시적으로 로그온하고 액세스 토큰이 만료된 결과입니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-202">Typically, this is a result of a temporary log on to a system or shared folder and the access tokens expired.</span></span>

## <a name="add-indicator-to-block-or-allow-a-file"></a><span data-ttu-id="54e55-203">파일을 차단하거나 허용하는 표시기 추가</span><span class="sxs-lookup"><span data-stu-id="54e55-203">Add indicator to block or allow a file</span></span>

<span data-ttu-id="54e55-204">잠재적으로 악의적인 파일 또는 의심되는 맬웨어를 금지하여 조직에서 공격이 추가로 전파되는 것을 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-204">Prevent further propagation of an attack in your organization by banning potentially malicious files or suspected malware.</span></span> <span data-ttu-id="54e55-205">잠재적으로 악의적인 PE(이식 가능한 실행 파일) 파일을 알고 있는 경우 해당 파일을 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-205">If you know a potentially malicious portable executable (PE) file, you can block it.</span></span> <span data-ttu-id="54e55-206">이 작업을 수행하면 조직의 장치에서 읽고 쓰거나 실행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-206">This operation will prevent it from being read, written, or executed on devices in your organization.</span></span>

> [!IMPORTANT]
>
> - <span data-ttu-id="54e55-207">조직에서 클라우드 제공 보호를 사용하도록 설정하고 Microsoft Defender 바이러스 백신 기능을 사용하는 경우 이 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-207">This feature is available if your organization uses Microsoft Defender Antivirus and Cloud–delivered protection is enabled.</span></span> <span data-ttu-id="54e55-208">자세한 내용은 클라우드 제공 [보호 관리를 참조하세요.](/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus)</span><span class="sxs-lookup"><span data-stu-id="54e55-208">For more information, see [Manage cloud–delivered protection](/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus).</span></span>
>
> - <span data-ttu-id="54e55-209">맬웨어 방지 클라이언트 버전은 4.18.1901.x 이상입니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-209">The Antimalware client version must be 4.18.1901.x or later.</span></span>
> - <span data-ttu-id="54e55-210">이 기능은 의심되는 맬웨어(또는 악성 파일)가 웹에서 다운로드되지 않도록 디자인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-210">This feature is designed to prevent suspected malware (or potentially malicious files) from being downloaded from the web.</span></span> <span data-ttu-id="54e55-211">현재 이식 가능한 PE(이식 가능한 실행 파일) 파일을.exe _.dll_ _있습니다._</span><span class="sxs-lookup"><span data-stu-id="54e55-211">It currently supports portable executable (PE) files, including _.exe_ and _.dll_ files.</span></span> <span data-ttu-id="54e55-212">적용 범위는 시간이 지날 때 연장됩니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-212">The coverage will be extended over time.</span></span>
> - <span data-ttu-id="54e55-213">이 응답 작업은 버전 1703 Windows 10 장치에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-213">This response action is available for devices on Windows 10, version 1703 or later.</span></span>
> - <span data-ttu-id="54e55-214">허용 또는 차단 작업 전에 파일의 분류가 디바이스 캐시에 있는 경우 파일에서 허용 또는 차단 기능을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-214">The allow or block function cannot be done on files if the file's classification exists on the device's cache prior to the allow or block action.</span></span>

> [!NOTE]
> <span data-ttu-id="54e55-215">이 작업을 수행하려면 PE 파일이 장치 타임라인에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-215">The PE file needs to be in the device timeline for you to be able to take this action.</span></span>
>
> <span data-ttu-id="54e55-216">작업을 수행한 시간과 차단되는 실제 파일 사이에 몇 분의 대기 시간이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-216">There may be a couple of minutes of latency between the time the action is taken and the actual file being blocked.</span></span>

### <a name="enable-the-block-file-feature"></a><span data-ttu-id="54e55-217">파일 차단 기능 사용</span><span class="sxs-lookup"><span data-stu-id="54e55-217">Enable the block file feature</span></span>

<span data-ttu-id="54e55-218">파일 차단을 시작하려면 먼저 [  ](advanced-features.md) 차단 또는 허용 기능을 설정해야 설정.</span><span class="sxs-lookup"><span data-stu-id="54e55-218">To start blocking files, you first need to [turn the **Block or allow** feature on](advanced-features.md) in Settings.</span></span>
### <a name="allow-or-block-file"></a><span data-ttu-id="54e55-219">파일 허용 또는 차단</span><span class="sxs-lookup"><span data-stu-id="54e55-219">Allow or block file</span></span>

<span data-ttu-id="54e55-220">파일에 대한 표시기 해시를 추가할 때 조직의 장치가 파일을 실행하려고 할 때마다 경고를 발생하고 파일을 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-220">When you add an indicator hash for a file, you can choose to raise an alert and block the file whenever a device in your organization attempts to run it.</span></span>

<span data-ttu-id="54e55-221">표시기에서 자동으로 차단되는 파일은 파일의 알림 센터에 표시되지 않지만 경고 큐에 계속 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-221">Files automatically blocked by an indicator won't show up in the file's Action center, but the alerts will still be visible in the Alerts queue.</span></span>

<span data-ttu-id="54e55-222">파일에 [대한](manage-indicators.md) 경고 차단 및 발생에 대한 자세한 내용은 표시기 관리를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-222">See [manage indicators](manage-indicators.md) for more details on blocking and raising alerts on files.</span></span>

<span data-ttu-id="54e55-223">파일 차단을 중지하려면 표시기를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-223">To stop blocking a file, remove the indicator.</span></span> <span data-ttu-id="54e55-224">파일의 프로필 페이지에서  표시기 편집 작업을 통해 이 작업을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-224">You can do so via the **Edit Indicator** action on the file's profile page.</span></span> <span data-ttu-id="54e55-225">이 작업은 표시기를 추가하기 전에  지표 추가 작업과 동일한 위치에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-225">This action will be visible in the same position as the **Add Indicator** action, before you added the indicator.</span></span>

<span data-ttu-id="54e55-226">규칙 표시기 **의** 설정 **표시기를**  >  **편집할 수도 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="54e55-226">You can also edit indicators from  the **Settings** page, under **Rules** > **Indicators**.</span></span> <span data-ttu-id="54e55-227">표시기는 파일의 해시에 의해 이 영역에 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-227">Indicators are listed in this area by their file's hash.</span></span>

## <a name="consult-a-threat-expert"></a><span data-ttu-id="54e55-228">위협 전문가에게 문의</span><span class="sxs-lookup"><span data-stu-id="54e55-228">Consult a threat expert</span></span>

<span data-ttu-id="54e55-229">잠재적으로 손상된 장치 또는 이미 손상된 장치에 대한 자세한 내용은 Microsoft 위협 전문가에게 문의하세요.</span><span class="sxs-lookup"><span data-stu-id="54e55-229">Consult a Microsoft threat expert for more insights on a potentially compromised device, or already compromised devices.</span></span> <span data-ttu-id="54e55-230">Microsoft 위협 전문가 정확한 응답을 위해 Microsoft Defender 보안 센터 내에서 직접 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-230">Microsoft Threat Experts are engaged directly from within the Microsoft Defender Security Center for timely and accurate response.</span></span> <span data-ttu-id="54e55-231">전문가는 잠재적으로 손상된 장치에 대한 인사이트를 제공하고 복잡한 위협 및 대상 공격 알림을 이해하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-231">Experts provide insights on a potentially compromised device and help you understand complex threats and targeted attack notifications.</span></span> <span data-ttu-id="54e55-232">또한 포털 대시보드에서 경고 또는 위협 인텔리전스 컨텍스트에 대한 정보를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-232">They can also provide information about the alerts or a threat intelligence context that you see on your portal dashboard.</span></span>

<span data-ttu-id="54e55-233">자세한 [내용은 Microsoft Threat Expert를](/microsoft-365/security/defender-endpoint/configure-microsoft-threat-experts#consult-a-microsoft-threat-expert-about-suspicious-cybersecurity-activities-in-your-organization) 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-233">See [Consult a Microsoft Threat Expert](/microsoft-365/security/defender-endpoint/configure-microsoft-threat-experts#consult-a-microsoft-threat-expert-about-suspicious-cybersecurity-activities-in-your-organization) for details.</span></span>

## <a name="check-activity-details-in-action-center"></a><span data-ttu-id="54e55-234">알림 센터에서 활동 세부 정보 확인</span><span class="sxs-lookup"><span data-stu-id="54e55-234">Check activity details in Action center</span></span>

<span data-ttu-id="54e55-235">관리 **센터는** 장치 또는 파일에서 수행된 작업에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-235">The **Action center** provides information on actions that were taken on a device or file.</span></span> <span data-ttu-id="54e55-236">다음 세부 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-236">You can view the following details:</span></span>

- <span data-ttu-id="54e55-237">조사 패키지 컬렉션</span><span class="sxs-lookup"><span data-stu-id="54e55-237">Investigation package collection</span></span>
- <span data-ttu-id="54e55-238">바이러스 백신 검사</span><span class="sxs-lookup"><span data-stu-id="54e55-238">Antivirus scan</span></span>
- <span data-ttu-id="54e55-239">앱 제한</span><span class="sxs-lookup"><span data-stu-id="54e55-239">App restriction</span></span>
- <span data-ttu-id="54e55-240">장치 고리</span><span class="sxs-lookup"><span data-stu-id="54e55-240">Device isolation</span></span>

<span data-ttu-id="54e55-241">제출 날짜/시간, 사용자 제출, 작업 성공 또는 실패와 같은 기타 모든 관련 세부 정보도 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-241">All other related details are also shown, such as submission date/time, submitting user, and if the action succeeded or failed.</span></span>

![정보가 있는 센터 이미지](images/action-center-details.png)

## <a name="deep-analysis"></a><span data-ttu-id="54e55-243">심층 분석</span><span class="sxs-lookup"><span data-stu-id="54e55-243">Deep analysis</span></span>

<span data-ttu-id="54e55-244">사이버 보안 조사는 일반적으로 경고에 의해 트리거됩니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-244">Cyber security investigations are typically triggered by an alert.</span></span> <span data-ttu-id="54e55-245">경고는 종종 신규 또는 알 수 없는 관찰된 하나 이상의 파일과 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-245">Alerts are related to one or more observed files that are often new or unknown.</span></span> <span data-ttu-id="54e55-246">파일을 선택하면 파일의 메타데이터를 볼 수 있는 파일 보기로 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-246">Selecting a file takes you to the file view where you can see the file's metadata.</span></span> <span data-ttu-id="54e55-247">파일과 관련된 데이터를 보강하기 위해 심층 분석을 위해 파일을 제출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-247">To enrich the data related to the file, you can submit the file for deep analysis.</span></span>

<span data-ttu-id="54e55-248">심층 분석 기능은 완전하게 계측된 안전한 클라우드 환경에서 파일을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-248">The Deep analysis feature executes a file in a secure, fully instrumented cloud environment.</span></span> <span data-ttu-id="54e55-249">심층 분석 결과에는 파일의 활동, 관찰된 동작 및 연결된 아티팩트(예: 삭제된 파일, 레지스트리 수정, IP와의 통신)가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-249">Deep analysis results show the file's activities, observed behaviors, and associated artifacts, such as dropped files, registry modifications, and communication with IPs.</span></span>
<span data-ttu-id="54e55-250">현재 심층 분석은 PE(이식 가능한 실행 파일) 파일(파일 및 파일 _포함)에_ 대한 광범위한.exe _.dll_ 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-250">Deep analysis currently supports extensive analysis of portable executable (PE) files (including _.exe_ and _.dll_ files).</span></span>

<span data-ttu-id="54e55-251">파일을 심층 분석하는 데 몇 분 정도 걸립니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-251">Deep analysis of a file takes several minutes.</span></span> <span data-ttu-id="54e55-252">파일 분석이 완료되면 심층 분석 탭이 업데이트되어 사용 가능한 최신 결과의 요약과 날짜 및 시간이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-252">Once the file analysis is complete, the Deep Analysis tab will update to display a summary and the date and time of the latest available results.</span></span>

<span data-ttu-id="54e55-253">심층 분석 요약에는 관찰된 동작 목록이 포함되어 있으며, 그 중 일부는 악의적인 활동 및 관찰 가능 항목(디스크에 만들어진 연락처된 IP 및 파일 포함)을 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-253">The deep analysis summary includes a list of observed *behaviors*, some of which can indicate malicious activity, and *observables*, including contacted IPs and files created on the disk.</span></span> <span data-ttu-id="54e55-254">아무 것도 발견하지 못하면 이러한 섹션에 간단한 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-254">If nothing was found, these sections will display a brief message.</span></span>

<span data-ttu-id="54e55-255">심층 분석 결과는 위협 인텔리전스와 일치하며 일치하면 적절한 경고가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-255">Results of deep analysis are matched against threat intelligence and any matches will generate appropriate alerts.</span></span>

<span data-ttu-id="54e55-256">심층 분석 기능을 사용하여 일반적으로 경고 조사 중에 또는 악의적인 동작이 의심되는 다른 이유로 파일의 세부 정보를 조사합니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-256">Use the deep analysis feature to investigate the details of any file, usually during an investigation of an alert or for any other reason where you suspect malicious behavior.</span></span> <span data-ttu-id="54e55-257">이 기능은 파일의  프로필 페이지에서 심층 분석 탭에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-257">This feature is available within the **Deep analysis** tab, on the file's profile page.</span></span><br/>
<br/>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4aAYy?rel=0]

<span data-ttu-id="54e55-258"> 파일을 Endpoint 백 엔드용 Defender 샘플 컬렉션에서 사용할 수 있는 경우 또는 심층 분석 제출을 지원하는 Windows 10 장치에서 파일을 관찰한 경우 심층 분석을 위한 제출을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-258">**Submit for deep analysis** is enabled when the file is available in the Defender for Endpoint backend sample collection, or if it was observed on a Windows 10 device that supports submitting to deep analysis.</span></span>

> [!NOTE]
> <span data-ttu-id="54e55-259">모든 파일의 Windows 10 자동으로 수집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-259">Only files from Windows 10 can be automatically collected.</span></span>

<span data-ttu-id="54e55-260">파일에서 파일이 관찰되지 않은 경우 [Microsoft](https://www.microsoft.com/security/portal/submission/submit.aspx) 보안 센터 포털을 통해 샘플을 제출할 Windows 10  심층 분석 단추가 제공될 때까지 기다릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-260">You can also submit a sample through the [Microsoft Security Center Portal](https://www.microsoft.com/security/portal/submission/submit.aspx) if the file wasn't observed on a Windows 10 device, and wait for **Submit for deep analysis** button to become available.</span></span>

> [!NOTE]
> <span data-ttu-id="54e55-261">Microsoft 보안 센터 포털의 백 엔드 처리 흐름으로 인해 파일 전송과 Endpoint용 Defender의 심층 분석 기능 가용성 사이에 최대 10분이 지연될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-261">Due to backend processing flows in the Microsoft Security Center Portal, there could be up to 10 minutes of latency between file submission and availability of the deep analysis feature in Defender for Endpoint.</span></span>

<span data-ttu-id="54e55-262">샘플이 수집될 때 Defender for Endpoint는 안전한 환경에서 파일을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-262">When the sample is collected, Defender for Endpoint runs the file in a secure environment.</span></span> <span data-ttu-id="54e55-263">그런 다음 관찰된 동작 및 관련 아티팩트(예: 장치에 삭제된 파일, IP와의 통신 및 레지스트리 수정)에 대한 자세한 보고서를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-263">It then creates a detailed report of observed behaviors and associated artifacts, such as files dropped on devices, communication to IPs, and registry modifications.</span></span>

### <a name="submit-files-for-deep-analysis"></a><span data-ttu-id="54e55-264">심층 분석을 위한 파일 제출</span><span class="sxs-lookup"><span data-stu-id="54e55-264">Submit files for deep analysis</span></span>

1. <span data-ttu-id="54e55-265">심층 분석을 위해 제출할 파일을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-265">Select the file that you want to submit for deep analysis.</span></span> <span data-ttu-id="54e55-266">다음 보기에서 파일을 선택하거나 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-266">You can select or search a file from any of the following views:</span></span>

    - <span data-ttu-id="54e55-267">경고 - 아티팩트 타임라인의 **설명** 또는 **세부 정보에서** 파일 링크 선택</span><span class="sxs-lookup"><span data-stu-id="54e55-267">Alerts - select the file links from the **Description** or **Details** in the Artifact timeline</span></span>
    - <span data-ttu-id="54e55-268">**장치 목록** - 조직 내  장치 섹션의 설명 또는 세부 정보 섹션에서 **파일** 링크 **선택**</span><span class="sxs-lookup"><span data-stu-id="54e55-268">**Devices list** - select the file links from the **Description** or **Details** in the **Device in organization** section</span></span>
    - <span data-ttu-id="54e55-269">검색 상자 - **드롭다운** 메뉴에서 파일을 선택하고 파일 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-269">Search box - select **File** from the drop–down menu and enter the file name</span></span>

2. <span data-ttu-id="54e55-270">파일 **보기의** 심층 분석 탭에서 제출을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="54e55-270">In the **Deep analysis** tab of the file view, select **Submit**.</span></span>

   ![파일 세부 정보 섹션에서만 PE 파일을 제출할 수 있습니다.](images/submit-file.png)

   > [!NOTE]
   > <span data-ttu-id="54e55-272">PE 파일만 _지원됩니다(파일_ 및.exe _.dll_ 포함).</span><span class="sxs-lookup"><span data-stu-id="54e55-272">Only PE files are supported, including _.exe_ and _.dll_ files.</span></span>

<span data-ttu-id="54e55-273">진행률 표시줄이 표시되고 다양한 분석 단계에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-273">A progress bar is displayed and provides information on the different stages of the analysis.</span></span> <span data-ttu-id="54e55-274">그런 다음 분석이 완료되면 보고서를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-274">You can then view the report when the analysis is done.</span></span>

> [!NOTE]
> <span data-ttu-id="54e55-275">디바이스 가용성에 따라 샘플 수집 시간이 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-275">Depending on device availability, sample collection time can vary.</span></span> <span data-ttu-id="54e55-276">샘플 수집에는 3시간의 시간 제한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-276">There is a 3–hour timeout for sample collection.</span></span> <span data-ttu-id="54e55-277">이때 장치 보고를 위해 온라인 Windows 10 컬렉션이 실패하고 작업이 다시 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-277">The collection will fail and the operation will abort if there is no online Windows 10 device reporting at that time.</span></span> <span data-ttu-id="54e55-278">심층 분석을 위해 파일을 다시 제출하여 파일에 대한 새 데이터를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-278">You can re–submit files for deep analysis to get fresh data on the file.</span></span>

### <a name="view-deep-analysis-reports"></a><span data-ttu-id="54e55-279">심층 분석 보고서 보기</span><span class="sxs-lookup"><span data-stu-id="54e55-279">View deep analysis reports</span></span>

<span data-ttu-id="54e55-280">제공된 심층 분석 보고서를 보고 제출한 파일에 대한 자세한 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-280">View the provided deep analysis report to see more in-depth insights on the file you submitted.</span></span> <span data-ttu-id="54e55-281">이 기능은 파일 보기 컨텍스트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-281">This feature is available in the file view context.</span></span>

<span data-ttu-id="54e55-282">다음 섹션에 대한 세부 정보를 제공하는 포괄적인 보고서를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-282">You can view the comprehensive report that provides details on the following sections:</span></span>

- <span data-ttu-id="54e55-283">동작</span><span class="sxs-lookup"><span data-stu-id="54e55-283">Behaviors</span></span>
- <span data-ttu-id="54e55-284">관찰용</span><span class="sxs-lookup"><span data-stu-id="54e55-284">Observables</span></span>

<span data-ttu-id="54e55-285">제공된 세부 정보는 잠재적인 공격의 표시가 있는 경우 조사하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-285">The details provided can help you investigate if there are indications of a potential attack.</span></span>

1. <span data-ttu-id="54e55-286">심층 분석을 위해 제출한 파일을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-286">Select the file you submitted for deep analysis.</span></span>
2. <span data-ttu-id="54e55-287">심층 **분석 탭을** 선택합니다. 이전 보고서가 있는 경우 보고서 요약이 이 탭에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-287">Select the **Deep analysis** tab. If there are any previous reports, the report summary will appear in this tab.</span></span>

    ![심층 분석 보고서에는 여러 범주의 세부 정보가 표시되어 있습니다.](images/analysis-results-nothing500.png)

#### <a name="troubleshoot-deep-analysis"></a><span data-ttu-id="54e55-289">심층 분석 문제 해결</span><span class="sxs-lookup"><span data-stu-id="54e55-289">Troubleshoot deep analysis</span></span>

<span data-ttu-id="54e55-290">파일을 제출할 때 문제가 발생하면 다음 문제 해결 단계를 각각 시도해 하세요.</span><span class="sxs-lookup"><span data-stu-id="54e55-290">If you come across a problem when trying to submit a file, try each of the following troubleshooting steps.</span></span>

1. <span data-ttu-id="54e55-291">해당 파일이 PE 파일인지 확인</span><span class="sxs-lookup"><span data-stu-id="54e55-291">Ensure that the file in question is a PE file.</span></span> <span data-ttu-id="54e55-292">PE 파일에는 일반적으로 _.exe_ 또는.dll확장명(실행 프로그램 또는 응용 프로그램)이 있습니다. </span><span class="sxs-lookup"><span data-stu-id="54e55-292">PE files typically have _.exe_ or _.dll_ extensions (executable programs or applications).</span></span>
2. <span data-ttu-id="54e55-293">서비스에 파일에 대한 액세스 권한이 있으며, 파일이 여전히 존재하며, 손상되거나 수정되지 않은지 확인</span><span class="sxs-lookup"><span data-stu-id="54e55-293">Ensure the service has access to the file, that it still exists, and hasn't been corrupted or modified.</span></span>
3. <span data-ttu-id="54e55-294">잠시 기다렸다가 파일을 다시 제출합니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-294">Wait a short while and try to submit the file again.</span></span> <span data-ttu-id="54e55-295">큐가 가득 차거나 일시적인 연결 또는 통신 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-295">The queue may be full, or there was a temporary connection or communication error.</span></span>
4. <span data-ttu-id="54e55-296">샘플 수집 정책이 구성되지 않은 경우 기본 동작은 샘플 수집을 허용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-296">If the sample collection policy isn't configured, then the default behavior is to allow sample collection.</span></span> <span data-ttu-id="54e55-297">구성된 경우 파일을 다시 제출하기 전에 정책 설정에서 샘플 수집을 허용하는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-297">If it's configured, then verify the policy setting allows sample collection before submitting the file again.</span></span> <span data-ttu-id="54e55-298">샘플 컬렉션이 구성되면 다음 레지스트리 값을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-298">When sample collection is configured, then check the following registry value:</span></span>

    ```powershell
    Path: HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection
    Name: AllowSampleCollection
    Type: DWORD
    Hexadecimal value :
      Value = 0 – block sample collection
      Value = 1 – allow sample collection
    ```

1. <span data-ttu-id="54e55-299">그룹 정책을 통해 조직 구성 단위를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="54e55-299">Change the organizational unit through the Group Policy.</span></span> <span data-ttu-id="54e55-300">자세한 내용은 [그룹 정책으로 구성을 참조하세요.](configure-endpoints-gp.md)</span><span class="sxs-lookup"><span data-stu-id="54e55-300">For more information, see [Configure with Group Policy](configure-endpoints-gp.md).</span></span>
1. <span data-ttu-id="54e55-301">이러한 단계로 문제가 해결되지 않으면 에 [winatp@microsoft.com.](mailto:winatp@microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="54e55-301">If these steps do not resolve the issue, contact [winatp@microsoft.com](mailto:winatp@microsoft.com).</span></span>

## <a name="related-topics"></a><span data-ttu-id="54e55-302">관련 항목</span><span class="sxs-lookup"><span data-stu-id="54e55-302">Related topics</span></span>

- [<span data-ttu-id="54e55-303">장치에 대해 대응 조치 실행</span><span class="sxs-lookup"><span data-stu-id="54e55-303">Take response actions on a device</span></span>](respond-machine-alerts.md)
- [<span data-ttu-id="54e55-304">파일 조사</span><span class="sxs-lookup"><span data-stu-id="54e55-304">Investigate files</span></span>](investigate-files.md)
