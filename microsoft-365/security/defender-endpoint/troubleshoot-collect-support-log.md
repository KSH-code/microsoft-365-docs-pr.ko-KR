---
title: 라이브 응답을 사용하여 끝점용 Microsoft Defender에서 지원 로그 수집
description: 실시간 응답을 사용하여 끝점에 대한 Microsoft Defender 문제 해결을 사용하여 로그를 수집하는 방법에 대해 자세히 알아보기
keywords: 지원, 로그, 수집, 문제 해결, 라이브 응답, liveanalyzer, 분석기, 라이브, 응답
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
ms.topic: troubleshooting
ms.technology: mde
ms.openlocfilehash: 07593fac6ed9a3fbc00d904718380b386f31dba3
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893416"
---
# <a name="collect-support-logs-in-microsoft-defender-for-endpoint-using-live-response"></a><span data-ttu-id="ce6cb-104">라이브 응답을 사용하여 끝점용 Microsoft Defender에서 지원 로그 수집</span><span class="sxs-lookup"><span data-stu-id="ce6cb-104">Collect support logs in Microsoft Defender for Endpoint using live response</span></span> 


<span data-ttu-id="ce6cb-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="ce6cb-105">**Applies to:**</span></span>
- [<span data-ttu-id="ce6cb-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="ce6cb-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="ce6cb-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ce6cb-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="ce6cb-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="ce6cb-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="ce6cb-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="ce6cb-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


<span data-ttu-id="ce6cb-110">지원에 문의할 때 끝점용 Microsoft Defender 클라이언트 분석기 도구의 출력 패키지를 제공해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce6cb-110">When contacting support, you may be asked to provide the output package of the Microsoft Defender for Endpoint Client Analyzer tool.</span></span>

<span data-ttu-id="ce6cb-111">이 항목에서는 Live Response를 통해 도구를 실행하는 방법에 대한 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ce6cb-111">This topic provides instructions on how to run the tool via Live Response.</span></span>

1. <span data-ttu-id="ce6cb-112">적절한 스크립트 다운로드</span><span class="sxs-lookup"><span data-stu-id="ce6cb-112">Download the appropriate script</span></span>
    * <span data-ttu-id="ce6cb-113">끝점용 Microsoft Defender 클라이언트 센서 로그만:LiveAnalyzer.ps1 [스크립트.](https://aka.ms/MDELiveAnalyzer)</span><span class="sxs-lookup"><span data-stu-id="ce6cb-113">Microsoft Defender for Endpoint client sensor logs only: [LiveAnalyzer.ps1 script](https://aka.ms/MDELiveAnalyzer).</span></span>
      - <span data-ttu-id="ce6cb-114">결과 패키지 대략적인 크기: ~100Kb</span><span class="sxs-lookup"><span data-stu-id="ce6cb-114">Result package approximate size: ~100Kb</span></span> 
    *  <span data-ttu-id="ce6cb-115">Microsoft Defender for Endpoint 클라이언트 센서 및 바이러스 백신 로그: [LiveAnalyzer+MDAV.ps1 스크립트입니다.](https://aka.ms/MDELiveAnalyzerAV)</span><span class="sxs-lookup"><span data-stu-id="ce6cb-115">Microsoft Defender for Endpoint client sensor and Antivirus logs: [LiveAnalyzer+MDAV.ps1 script](https://aka.ms/MDELiveAnalyzerAV).</span></span>
       - <span data-ttu-id="ce6cb-116">결과 패키지 대략적인 크기: ~10Mb</span><span class="sxs-lookup"><span data-stu-id="ce6cb-116">Result package approximate size: ~10Mb</span></span> 
 
2.  <span data-ttu-id="ce6cb-117">조사해야 [하는](live-response.md#initiate-a-live-response-session-on-a-device) 컴퓨터의 실시간 응답 세션을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="ce6cb-117">Initiate a [Live Response session](live-response.md#initiate-a-live-response-session-on-a-device) on the machine you need to investigate.</span></span>

3.  <span data-ttu-id="ce6cb-118">라이브러리에 **업로드 파일을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="ce6cb-118">Select **Upload file to library**.</span></span>

    ![업로드 파일의 이미지](images/upload-file.png)

4. <span data-ttu-id="ce6cb-120">파일 **선택 을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="ce6cb-120">Select **Choose file**.</span></span>

    ![파일 선택 단추의 이미지1](images/choose-file.png)

5. <span data-ttu-id="ce6cb-122">이름이 MDELiveAnalyzer.ps1 파일을 선택한 다음 확인을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="ce6cb-122">Select the downloaded file named MDELiveAnalyzer.ps1 and then click on **Confirm**</span></span>


   ![파일 선택 단추 2의 이미지](images/analyzer-file.png)


6. <span data-ttu-id="ce6cb-124">LiveResponse 세션에서 여전히 아래 명령을 사용하여 분석기를 실행하고 결과 파일을 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="ce6cb-124">While still in the LiveResponse session, use the commands below to run the analyzer and collect the result file:</span></span>

    ```console
    Run MDELiveAnalyzer.ps1
    GetFile "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\MDEClientAnalyzerResult.zip" -auto
    ```

    <span data-ttu-id="ce6cb-125">[![명령 이미지 ](images/analyzer-commands.png)](images/analyzer-commands.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="ce6cb-125">[ ![Image of commands](images/analyzer-commands.png) ](images/analyzer-commands.png#lightbox)</span></span>


>[!NOTE]
> - <span data-ttu-id="ce6cb-126">MDEClientAnalyzer의 최신 미리 보기 버전은 에서 다운로드할 수 [https://aka.ms/Betamdeanalyzer](https://aka.ms/Betamdeanalyzer) 있습니다. .</span><span class="sxs-lookup"><span data-stu-id="ce6cb-126">The latest preview version of MDEClientAnalyzer can be downloaded here: [https://aka.ms/Betamdeanalyzer](https://aka.ms/Betamdeanalyzer).</span></span>
> 
> - <span data-ttu-id="ce6cb-127">LiveAnalyzer 스크립트는 다음에서 대상 컴퓨터의 문제 해결 패키지를 https://mdatpclientanalyzer.blob.core.windows.net 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="ce6cb-127">The LiveAnalyzer script downloads the troubleshooting package on the destination machine from: https://mdatpclientanalyzer.blob.core.windows.net.</span></span>
> 
>   <span data-ttu-id="ce6cb-128">컴퓨터의 위 URL에 도달하도록 허용할 수 없는 경우 LiveAnalyzer 스크립트를 실행하기 전에 MDEClientAnalyzerPreview.zip 파일을 라이브러리에 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="ce6cb-128">If you cannot allow the machine to reach the above URL, then upload MDEClientAnalyzerPreview.zip file to the library before running the LiveAnalyzer script:</span></span>
>
>   ```console
>   PutFile MDEClientAnalyzerPreview.zip -overwrite
>   Run MDELiveAnalyzer.ps1
>   GetFile "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\MDEClientAnalyzerResult.zip" -auto
>   ```
> 
> - <span data-ttu-id="ce6cb-129">컴퓨터의 끝점 클라우드 서비스용 Microsoft Defender와 통신하지 않는 경우 또는 끝점용 Microsoft Defender 포털에 예상대로 나타나지 않는 경우 컴퓨터의 데이터를 로컬로 수집하는 데 대한 자세한 내용은 끝점 서비스 [URL에 대한 Microsoft Defender에](configure-proxy-internet.md#verify-client-connectivity-to-microsoft-defender-for-endpoint-service-urls)대한 클라이언트 연결 확인을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ce6cb-129">For more information on gathering data locally on a machine in case the machine isn't communicating with Microsoft Defender for Endpoint cloud services, or does not appear in Microsoft Defender for Endpoint portal as expected, see [Verify client connectivity to Microsoft Defender for Endpoint service URLs](configure-proxy-internet.md#verify-client-connectivity-to-microsoft-defender-for-endpoint-service-urls).</span></span>
