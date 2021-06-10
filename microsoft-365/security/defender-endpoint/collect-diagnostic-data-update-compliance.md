---
title: 업데이트 준수 및 업데이트 관리에 대한 진단 Windows Defender Microsoft Defender 바이러스 백신
description: 도구를 사용하여 데이터 수집을 통해 Microsoft Defender 바이러스 백신 추가 기능 사용 시 준수 업데이트 문제를 해결
keywords: 문제 해결, 오류, 수정, 업데이트 준수, oms, 모니터링, 보고서, Microsoft Defender AV
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 2aaf3d1c650713a7f6cfb7b9abb9f2232013d6db
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274799"
---
# <a name="collect-update-compliance-diagnostic-data-for-microsoft-defender-av-assessment"></a><span data-ttu-id="82cca-104">Microsoft Defender AV 평가에 대한 업데이트 준수 진단 데이터 수집</span><span class="sxs-lookup"><span data-stu-id="82cca-104">Collect Update Compliance diagnostic data for Microsoft Defender AV Assessment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="82cca-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="82cca-105">**Applies to:**</span></span>

- [<span data-ttu-id="82cca-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="82cca-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="82cca-107">이 문서에서는 업데이트 준수 추가 기능의 Microsoft Defender AV 평가 섹션을 사용할 때 발생할 수 있는 문제를 해결하기 위해 Microsoft 지원 및 엔지니어링 팀에서 사용할 수 있는 진단 데이터를 수집하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="82cca-107">This article describes how to collect diagnostic data that can be used by Microsoft support and engineering teams to help troubleshoot issues you may encounter when using the Microsoft Defender AV Assessment section in the Update Compliance add-in.</span></span>

<span data-ttu-id="82cca-108">이 프로세스를 시도하기 전에 Troubleshoot [troubleshoot Microsoft Defender 바이러스 백신 reporting](troubleshoot-reporting.md), met all require prerequisites을 충족하고 다른 제안된 문제 해결 단계를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="82cca-108">Before attempting this process, ensure you have read [Troubleshoot Microsoft Defender Antivirus reporting](troubleshoot-reporting.md), met all require prerequisites, and taken any other suggested troubleshooting steps.</span></span>

<span data-ttu-id="82cca-109">업데이트 준수에 보고하거나 표시하지 않는 두 개 이상의 장치에서 다음 단계를 수행하여 .cab 진단 파일을 얻게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="82cca-109">On at least two devices that are not reporting or showing up in Update Compliance, obtain the .cab diagnostic file by taking the following steps:</span></span>

1. <span data-ttu-id="82cca-110">다음과 같이 관리자 수준 명령 프롬프트 버전을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82cca-110">Open an administrator-level version of the command prompt as follows:</span></span>
        
    <span data-ttu-id="82cca-111">a.</span><span class="sxs-lookup"><span data-stu-id="82cca-111">a.</span></span> <span data-ttu-id="82cca-112">시작 **메뉴를** 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82cca-112">Open the **Start** menu.</span></span>

    <span data-ttu-id="82cca-113">b.</span><span class="sxs-lookup"><span data-stu-id="82cca-113">b.</span></span> <span data-ttu-id="82cca-114">**cmd 를 입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="82cca-114">Type **cmd**.</span></span> <span data-ttu-id="82cca-115">명령 프롬프트를 **마우스 오른쪽 단추로 클릭하고** **관리자 권한으로 실행을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="82cca-115">Right-click on **Command Prompt** and click **Run as administrator**.</span></span>

    <span data-ttu-id="82cca-116">c.</span><span class="sxs-lookup"><span data-stu-id="82cca-116">c.</span></span> <span data-ttu-id="82cca-117">관리자 자격 증명을 입력하거나 프롬프트를 승인합니다.</span><span class="sxs-lookup"><span data-stu-id="82cca-117">Enter administrator credentials or approve the prompt.</span></span>
        
2. <span data-ttu-id="82cca-118">사용자 디렉터리로 Windows Defender 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="82cca-118">Navigate to the Windows Defender directory.</span></span> <span data-ttu-id="82cca-119">기본적으로 는 `C:\Program Files\Windows Defender` 입니다.</span><span class="sxs-lookup"><span data-stu-id="82cca-119">By default, this is `C:\Program Files\Windows Defender`.</span></span>

3. <span data-ttu-id="82cca-120">다음 명령을 입력한 다음 **Enter를 누르기**</span><span class="sxs-lookup"><span data-stu-id="82cca-120">Type the following command, and then press **Enter**</span></span>
        
    ```Dos
    mpcmdrun -getfiles
    ```
    
4. <span data-ttu-id="82cca-121">다양한 .cab 로그가 포함된 파일도 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="82cca-121">A .cab file will be generated that contains various diagnostic logs.</span></span> <span data-ttu-id="82cca-122">파일 위치는 명령 프롬프트의 출력에 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="82cca-122">The location of the file will be specified in the output in the command prompt.</span></span> <span data-ttu-id="82cca-123">기본적으로 위치는 `C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab` 입니다.</span><span class="sxs-lookup"><span data-stu-id="82cca-123">By default, the location is `C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab`.</span></span>

5. <span data-ttu-id="82cca-124">이러한 .cab 파일을 Microsoft 지원에서 액세스할 수 있는 위치에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="82cca-124">Copy these .cab files to a location that can be accessed by Microsoft support.</span></span> <span data-ttu-id="82cca-125">예를 들어 사용자와 공유할 수 있는 암호로 OneDrive 폴더를 예로 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82cca-125">An example could be a password-protected OneDrive folder that you can share with us.</span></span>

6. <span data-ttu-id="82cca-126">업데이트 준수 지원 <a href="mailto:ucsupport@microsoft.com?subject=WDAV assessment issue&body=I%20am%20encountering%20the%20following%20issue%20when%20using%20Windows%20Defender%20AV%20in%20Update%20Compliance%3a%20%0d%0aI%20have%20provided%20at%20least%202%20support%20.cab%20files%20at%20the%20following%20location%3a%20%3Caccessible%20share%2c%20including%20access%20details%20such%20as%20password%3E%0d%0aMy%20OMS%20workspace%20ID%20is%3a%20%0d%0aPlease%20contact%20me%20at%3a"></a>전자 메일 서식 파일을 사용하여 전자 메일을 보내고 다음 정보를 사용하여 서식 파일을 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="82cca-126">Send an email using the <a href="mailto:ucsupport@microsoft.com?subject=WDAV assessment issue&body=I%20am%20encountering%20the%20following%20issue%20when%20using%20Windows%20Defender%20AV%20in%20Update%20Compliance%3a%20%0d%0aI%20have%20provided%20at%20least%202%20support%20.cab%20files%20at%20the%20following%20location%3a%20%3Caccessible%20share%2c%20including%20access%20details%20such%20as%20password%3E%0d%0aMy%20OMS%20workspace%20ID%20is%3a%20%0d%0aPlease%20contact%20me%20at%3a">Update Compliance support email template</a>, and fill out the template with the following information:</span></span>
  
    ```
    I am encountering the following issue when using Microsoft Defender Antivirus in Update Compliance:
    
    I have provided at least 2 support .cab files at the following location: <accessible share, including access details such as password>

    My OMS workspace ID is:

    Please contact me at:
    ```

## <a name="see-also"></a><span data-ttu-id="82cca-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="82cca-127">See also</span></span>

- [<span data-ttu-id="82cca-128">보고 Windows Defender Microsoft Defender 바이러스 백신 문제 해결</span><span class="sxs-lookup"><span data-stu-id="82cca-128">Troubleshoot Windows Defender Microsoft Defender Antivirus reporting</span></span>](troubleshoot-reporting.md)