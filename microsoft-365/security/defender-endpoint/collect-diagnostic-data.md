---
title: 진단 데이터의 Microsoft Defender 바이러스 백신
description: 도구를 사용하여 데이터 수집을 통해 문제 해결을 Microsoft Defender 바이러스 백신
keywords: 문제 해결, 오류, 수정, 업데이트 준수, oms, 모니터링, 보고, Microsoft Defender av, 그룹 정책 개체, 설정, 진단 데이터
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/29/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: ccf6da0e1bc91a29865868305b5333f7ef9c47cc
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274787"
---
# <a name="collect-microsoft-defender-av-diagnostic-data"></a><span data-ttu-id="c3e58-104">Microsoft Defender AV 진단 데이터 수집</span><span class="sxs-lookup"><span data-stu-id="c3e58-104">Collect Microsoft Defender AV diagnostic data</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="c3e58-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="c3e58-105">**Applies to:**</span></span>

- [<span data-ttu-id="c3e58-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="c3e58-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="c3e58-107">이 문서에서는 Microsoft 지원 및 엔지니어링 팀에서 Microsoft Defender AV를 사용할 때 발생할 수 있는 문제를 해결하는 데 사용할 수 있는 진단 데이터를 수집하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c3e58-107">This article describes how to collect diagnostic data that can be used by Microsoft support and engineering teams to help troubleshoot issues you might encounter when using the Microsoft Defender AV.</span></span>

> [!NOTE]
> <span data-ttu-id="c3e58-108">조사 또는 응답 프로세스의 일부로 장치에서 조사 패키지를 수집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3e58-108">As part of the investigation or response process, you can collect an investigation package from a device.</span></span> <span data-ttu-id="c3e58-109">방법: 장치에서 [조사 패키지를 수집합니다.](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#collect-investigation-package-from-devices)</span><span class="sxs-lookup"><span data-stu-id="c3e58-109">Here's how: [Collect investigation package from devices](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#collect-investigation-package-from-devices).</span></span>

<span data-ttu-id="c3e58-110">동일한 문제가 발생하는 두 개 이상의 장치에서 다음 단계를 수행하여 .cab 진단 파일을 얻게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c3e58-110">On at least two devices that are experiencing the same issue, obtain the .cab diagnostic file by taking the following steps:</span></span>

1. <span data-ttu-id="c3e58-111">다음과 같이 관리자 수준 명령 프롬프트 버전을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3e58-111">Open an administrator-level version of the command prompt as follows:</span></span>

    <span data-ttu-id="c3e58-112">a.</span><span class="sxs-lookup"><span data-stu-id="c3e58-112">a.</span></span> <span data-ttu-id="c3e58-113">시작 **메뉴를** 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3e58-113">Open the **Start** menu.</span></span>

    <span data-ttu-id="c3e58-114">b.</span><span class="sxs-lookup"><span data-stu-id="c3e58-114">b.</span></span> <span data-ttu-id="c3e58-115">**cmd 를 입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="c3e58-115">Type **cmd**.</span></span> <span data-ttu-id="c3e58-116">명령 프롬프트를 **마우스 오른쪽 단추로 클릭하고** **관리자 권한으로 실행을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="c3e58-116">Right-click on **Command Prompt** and click **Run as administrator**.</span></span>

    <span data-ttu-id="c3e58-117">c.</span><span class="sxs-lookup"><span data-stu-id="c3e58-117">c.</span></span> <span data-ttu-id="c3e58-118">관리자 자격 증명을 입력하거나 프롬프트를 승인합니다.</span><span class="sxs-lookup"><span data-stu-id="c3e58-118">Enter administrator credentials or approve the prompt.</span></span>

2. <span data-ttu-id="c3e58-119">Microsoft Defender 디렉터리로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="c3e58-119">Navigate to the Microsoft Defender directory.</span></span> <span data-ttu-id="c3e58-120">기본적으로 는 `C:\Program Files\Windows Defender` 입니다.</span><span class="sxs-lookup"><span data-stu-id="c3e58-120">By default, this is `C:\Program Files\Windows Defender`.</span></span>

> [!NOTE]
> <span data-ttu-id="c3e58-121">업데이트된 [Microsoft Defender 플랫폼](https://support.microsoft.com/help/4052623/update-for-microsoft-defender-antimalware-platform)버전을 실행 중인 경우 다음 위치에서 `MpCmdRun` `C:\ProgramData\Microsoft\Windows Defender\Platform\<version>` 실행하세요. .</span><span class="sxs-lookup"><span data-stu-id="c3e58-121">If you're running an [updated Microsoft Defender Platform version](https://support.microsoft.com/help/4052623/update-for-microsoft-defender-antimalware-platform), please run `MpCmdRun` from the following location: `C:\ProgramData\Microsoft\Windows Defender\Platform\<version>`.</span></span>

3. <span data-ttu-id="c3e58-122">다음 명령을 입력한 다음 **Enter를 누르기**</span><span class="sxs-lookup"><span data-stu-id="c3e58-122">Type the following command, and then press **Enter**</span></span>  

    ```Dos
    mpcmdrun.exe -GetFiles
    ```
  
4. <span data-ttu-id="c3e58-123">다양한 .cab 로그가 포함된 파일도 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="c3e58-123">A .cab file will be generated that contains various diagnostic logs.</span></span> <span data-ttu-id="c3e58-124">파일 위치는 명령 프롬프트의 출력에 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="c3e58-124">The location of the file will be specified in the output in the command prompt.</span></span> <span data-ttu-id="c3e58-125">기본적으로 위치는 `C:\ProgramData\Microsoft\Microsoft Defender\Support\MpSupportFiles.cab` 입니다.</span><span class="sxs-lookup"><span data-stu-id="c3e58-125">By default, the location is `C:\ProgramData\Microsoft\Microsoft Defender\Support\MpSupportFiles.cab`.</span></span>

> [!NOTE]
> <span data-ttu-id="c3e58-126">cab 파일을 다른 경로 또는 UNC 공유로 리디렉션하기 위해 다음 명령을 사용 합니다. `mpcmdrun.exe -GetFiles -SupportLogLocation <path>`</span><span class="sxs-lookup"><span data-stu-id="c3e58-126">To redirect the cab file to a a different path or UNC share, use the following command: `mpcmdrun.exe -GetFiles -SupportLogLocation <path>`</span></span>  <br/><span data-ttu-id="c3e58-127">자세한 내용은 진단 데이터를 [UNC 공유로 리디렉션을 참조하세요.](#redirect-diagnostic-data-to-a-unc-share)</span><span class="sxs-lookup"><span data-stu-id="c3e58-127">For more information, see [Redirect diagnostic data to a UNC share](#redirect-diagnostic-data-to-a-unc-share).</span></span>

5. <span data-ttu-id="c3e58-128">이러한 .cab 파일을 Microsoft 지원에서 액세스할 수 있는 위치에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="c3e58-128">Copy these .cab files to a location that can be accessed by Microsoft support.</span></span> <span data-ttu-id="c3e58-129">예를 들어 사용자와 공유할 수 있는 암호로 OneDrive 폴더를 예로 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3e58-129">An example could be a password-protected OneDrive folder that you can share with us.</span></span>

> [!NOTE]
><span data-ttu-id="c3e58-130">업데이트 준수에 문제가 있는 경우 업데이트 준수 <a href="mailto:ucsupport@microsoft.com?subject=WDAV assessment issue&body=I%20am%20encountering%20the%20following%20issue%20when%20using%20Windows%20Defender%20AV%20in%20Update%20Compliance%3a%20%0d%0aI%20have%20provided%20at%20least%202%20support%20.cab%20files%20at%20the%20following%20location%3a%20%3Caccessible%20share%2c%20including%20access%20details%20such%20as%20password%3E%0d%0aMy%20OMS%20workspace%20ID%20is%3a%20%0d%0aPlease%20contact%20me%20at%3a"></a>지원 전자 메일 서식 파일을 사용하여 전자 메일을 보내고 다음 정보를 사용하여 서식 파일을 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="c3e58-130">If you have a problem with Update compliance, send an email using the <a href="mailto:ucsupport@microsoft.com?subject=WDAV assessment issue&body=I%20am%20encountering%20the%20following%20issue%20when%20using%20Windows%20Defender%20AV%20in%20Update%20Compliance%3a%20%0d%0aI%20have%20provided%20at%20least%202%20support%20.cab%20files%20at%20the%20following%20location%3a%20%3Caccessible%20share%2c%20including%20access%20details%20such%20as%20password%3E%0d%0aMy%20OMS%20workspace%20ID%20is%3a%20%0d%0aPlease%20contact%20me%20at%3a">Update Compliance support email template</a>, and fill out the template with the following information:</span></span>
>```
> I am encountering the following issue when using Microsoft Defender Antivirus in Update Compliance:
> I have provided at least 2 support .cab files at the following location:  
> <accessible share, including access details such as password>
>
>    My OMS workspace ID is:
>
>    Please contact me at:

## <a name="redirect-diagnostic-data-to-a-unc-share"></a><span data-ttu-id="c3e58-131">진단 데이터를 UNC 공유로 리디렉션</span><span class="sxs-lookup"><span data-stu-id="c3e58-131">Redirect diagnostic data to a UNC share</span></span>
<span data-ttu-id="c3e58-132">중앙 리포지토리에서 진단 데이터를 수집하기 위해 SupportLogLocation 매개 변수를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3e58-132">To collect diagnostic data on a central repository, you can specify the SupportLogLocation parameter.</span></span>

```Dos
mpcmdrun.exe -GetFiles -SupportLogLocation <path>
```

<span data-ttu-id="c3e58-133">진단 데이터를 지정된 경로에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="c3e58-133">Copies the diagnostic data to the specified path.</span></span> <span data-ttu-id="c3e58-134">경로를 지정하지 않으면 진단 데이터가 지원 로그 위치 구성에 지정된 위치에 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="c3e58-134">If the path is not specified, the diagnostic data will be copied to the location specified in the Support Log Location Configuration.</span></span>

<span data-ttu-id="c3e58-135">SupportLogLocation 매개 변수를 사용하면 다음과 같은 폴더 구조가 대상 경로에 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="c3e58-135">When the SupportLogLocation parameter is used, a folder structure like as follows will be created in the destination path:</span></span>

```Dos
<path>\<MMDD>\MpSupport-<hostname>-<HHMM>.cab
```

| <span data-ttu-id="c3e58-136">필드</span><span class="sxs-lookup"><span data-stu-id="c3e58-136">field</span></span>  | <span data-ttu-id="c3e58-137">설명</span><span class="sxs-lookup"><span data-stu-id="c3e58-137">Description</span></span>   |
|:----|:----|
| <span data-ttu-id="c3e58-138">path</span><span class="sxs-lookup"><span data-stu-id="c3e58-138">path</span></span> | <span data-ttu-id="c3e58-139">명령줄에 지정된 경로 또는 구성에서 검색된 경로</span><span class="sxs-lookup"><span data-stu-id="c3e58-139">The path as specified on the command line or retrieved from configuration</span></span>
| <span data-ttu-id="c3e58-140">MMDD</span><span class="sxs-lookup"><span data-stu-id="c3e58-140">MMDD</span></span> | <span data-ttu-id="c3e58-141">진단 데이터가 수집된 월 및 일(예: 0530)</span><span class="sxs-lookup"><span data-stu-id="c3e58-141">Month and day when the diagnostic data was collected (for example, 0530)</span></span>
| <span data-ttu-id="c3e58-142">hostname</span><span class="sxs-lookup"><span data-stu-id="c3e58-142">hostname</span></span> | <span data-ttu-id="c3e58-143">진단 데이터가 수집된 장치의 호스트 이름</span><span class="sxs-lookup"><span data-stu-id="c3e58-143">The hostname of the device on which the diagnostic data was collected</span></span>
| <span data-ttu-id="c3e58-144">HHMM</span><span class="sxs-lookup"><span data-stu-id="c3e58-144">HHMM</span></span> | <span data-ttu-id="c3e58-145">진단 데이터가 수집된 시간 및 분(예: 1422)</span><span class="sxs-lookup"><span data-stu-id="c3e58-145">Hours and minutes when the diagnostic data was collected (for example, 1422)</span></span>

> [!NOTE]
> <span data-ttu-id="c3e58-146">파일 공유를 사용할 때 진단 패키지를 수집하는 데 사용되는 계정에 공유에 대한 쓰기 권한이 있는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="c3e58-146">When using a file share please make sure that account used to collect the diagnostic package has write access to the share.</span></span>  

## <a name="specify-location-where-diagnostic-data-is-created"></a><span data-ttu-id="c3e58-147">진단 데이터를 만들 위치 지정</span><span class="sxs-lookup"><span data-stu-id="c3e58-147">Specify location where diagnostic data is created</span></span>

<span data-ttu-id="c3e58-148">GPO(그룹 정책 개체).cab 진단 파일을 만들 위치를 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3e58-148">You can also specify where the diagnostic .cab file will be created using a Group Policy Object (GPO).</span></span> 

1. <span data-ttu-id="c3e58-149">로컬 그룹 정책 편집기를 열고 다음에서 SupportLogLocation GPO를 찾을 수 있습니다. `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender\SupportLogLocation`</span><span class="sxs-lookup"><span data-stu-id="c3e58-149">Open the Local Group Policy Editor and find the SupportLogLocation GPO at: `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender\SupportLogLocation`</span></span>
   
1. <span data-ttu-id="c3e58-150">지원 로그 파일을 복사하려면 디렉터리 경로 **정의 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="c3e58-150">Select **Define the directory path to copy support log files**.</span></span>

    ![로컬 그룹 정책 편집기 스크린샷](images/GPO1-SupportLogLocationDefender.png)  
        
     ![로그 파일 경로 정의 설정 스크린샷](images/GPO2-SupportLogLocationGPPage.png)  
3. <span data-ttu-id="c3e58-153">정책 편집기 내에서 사용 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="c3e58-153">Inside the policy editor, select **Enabled**.</span></span>
       
4. <span data-ttu-id="c3e58-154">옵션 필드에서 지원 로그 파일을 복사할 디렉터리 경로를 **지정합니다.**</span><span class="sxs-lookup"><span data-stu-id="c3e58-154">Specify the directory path where you want to copy the support log files in the **Options** field.</span></span>
     <span data-ttu-id="c3e58-155">![사용 디렉터리 경로 사용자 지정 설정 스크린샷](images/GPO3-SupportLogLocationGPPageEnabledExample.png)</span><span class="sxs-lookup"><span data-stu-id="c3e58-155">![Screenshot of Enabled directory path custom setting](images/GPO3-SupportLogLocationGPPageEnabledExample.png)</span></span> 
5. <span data-ttu-id="c3e58-156">**확인 또는 적용을** **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="c3e58-156">Select **OK** or **Apply**.</span></span>

## <a name="see-also"></a><span data-ttu-id="c3e58-157">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c3e58-157">See also</span></span>

- [<span data-ttu-id="c3e58-158">보고 Microsoft Defender 바이러스 백신 문제 해결</span><span class="sxs-lookup"><span data-stu-id="c3e58-158">Troubleshoot Microsoft Defender Antivirus reporting</span></span>](troubleshoot-reporting.md)