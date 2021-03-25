---
title: Microsoft Defender ATP 라이브 응답 문제 해결
description: Microsoft Defender ATP에서 라이브 응답을 사용할 때 발생할 수 있는 문제 해결
keywords: 라이브 응답, 라이브, 응답, 잠긴, 파일 문제 해결
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
ms.openlocfilehash: 27f2c7eb01a857ec38b11797c0703710c02ac1bc
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51076799"
---
# <a name="troubleshoot-microsoft-defender-for-endpoint-live-response-issues"></a><span data-ttu-id="2c1df-104">Endpoint 라이브 응답 문제에 대한 Microsoft Defender 문제 해결</span><span class="sxs-lookup"><span data-stu-id="2c1df-104">Troubleshoot Microsoft Defender for Endpoint live response issues</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2c1df-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="2c1df-105">**Applies to:**</span></span>
- [<span data-ttu-id="2c1df-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="2c1df-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="2c1df-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2c1df-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="2c1df-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="2c1df-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="2c1df-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="2c1df-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 

<span data-ttu-id="2c1df-110">이 페이지에서는 라이브 응답 문제를 해결하기 위한 자세한 단계를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2c1df-110">This page provides detailed steps to troubleshoot live response issues.</span></span>

## <a name="file-cannot-be-accessed-during-live-response-sessions"></a><span data-ttu-id="2c1df-111">라이브 응답 세션 중에 파일에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2c1df-111">File cannot be accessed during live response sessions</span></span>
<span data-ttu-id="2c1df-112">라이브 응답 세션 중에 작업을 수행하려고 할 때 파일에 액세스할 수 없다고 하는 오류 메시지가 표시될 경우 아래 단계를 사용하여 문제를 해결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c1df-112">If while trying to take an action during a live response session, you encounter an error message stating that the file can't be accessed, you'll need to use the steps below to address the issue.</span></span>

1. <span data-ttu-id="2c1df-113">다음 스크립트 코드 코드를 복사하여 PS1 파일로 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="2c1df-113">Copy the following script code snippet and save it as a PS1 file:</span></span>

    ```
    $copied_file_path=$args[0] 
    $action=Copy-Item $copied_file_path -Destination $env:TEMP -PassThru -ErrorAction silentlyContinue
        
    if ($action){
         Write-Host "You copied the file specified in $copied_file_path to $env:TEMP Succesfully"
    }
    
    else{
        Write-Output "Error occoured while trying to copy a file, details:"
        Write-Output  $error[0].exception.message
 
    }
    ```


2. <span data-ttu-id="2c1df-114">라이브 응답 라이브러리에 스크립트를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2c1df-114">Add the script to the live response library.</span></span>
3. <span data-ttu-id="2c1df-115">복사할 파일의 파일 경로인 매개 변수 하나를 사용하여 스크립트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2c1df-115">Run the script with one parameter: the file path of the file to be copied.</span></span>
4. <span data-ttu-id="2c1df-116">TEMP 폴더로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="2c1df-116">Navigate to your TEMP folder.</span></span>
5. <span data-ttu-id="2c1df-117">복사한 파일에 대한 작업을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2c1df-117">Run the action you wanted to take on the copied file.</span></span>

## <a name="slow-live-response-sessions-or-delays-during-initial-connections"></a><span data-ttu-id="2c1df-118">초기 연결 중에 느린 라이브 응답 세션 또는 지연</span><span class="sxs-lookup"><span data-stu-id="2c1df-118">Slow live response sessions or delays during initial connections</span></span>
<span data-ttu-id="2c1df-119">실시간 응답은 Windows에서 WNS 서비스를 통해 Endpoint 센서 등록에 Defender를 활용합니다.</span><span class="sxs-lookup"><span data-stu-id="2c1df-119">Live response leverages Defender for Endpoint sensor registration with WNS service in Windows.</span></span> <span data-ttu-id="2c1df-120">라이브 응답에 연결 문제가 있는 경우 다음 세부 정보를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c1df-120">If you are having connectivity issues with live response, confirm the following details:</span></span>
1. <span data-ttu-id="2c1df-121">`notify.windows.com` 는 환경에서 차단되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2c1df-121">`notify.windows.com` is not blocked in your environment.</span></span> <span data-ttu-id="2c1df-122">자세한 내용은 장치 프록시 및 인터넷 연결 설정 [구성을 참조하세요.](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)</span><span class="sxs-lookup"><span data-stu-id="2c1df-122">For more information, see, [Configure device proxy and Internet connectivity settings](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server).</span></span>
2. <span data-ttu-id="2c1df-123">WpnService(Windows 푸시 알림 시스템 서비스)를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2c1df-123">WpnService (Windows Push Notifications System Service) is not disabled.</span></span>

<span data-ttu-id="2c1df-124">WpnService 서비스 동작 및 요구 사항을 완전히 이해하기 위해 아래 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2c1df-124">Refer to the articles below to fully understand the WpnService service behavior and requirements:</span></span>
- [<span data-ttu-id="2c1df-125">WNS(Windows 푸시 Notification Services) 개요</span><span class="sxs-lookup"><span data-stu-id="2c1df-125">Windows Push Notification Services (WNS) overview</span></span>](https://docs.microsoft.com/windows/uwp/design/shell/tiles-and-notifications/windows-push-notification-services--wns--overview)
- [<span data-ttu-id="2c1df-126">WNS 트래픽을 지원하기 위한 엔터프라이즈 방화벽 및 프록시 구성</span><span class="sxs-lookup"><span data-stu-id="2c1df-126">Enterprise Firewall and Proxy Configurations to Support WNS Traffic</span></span>](https://docs.microsoft.com/windows/uwp/design/shell/tiles-and-notifications/firewall-allowlist-config)
- [<span data-ttu-id="2c1df-127">Microsoft 푸시 알림 서비스(MPNS) 공용 IP 범위</span><span class="sxs-lookup"><span data-stu-id="2c1df-127">Microsoft Push Notifications Service (MPNS) Public IP ranges</span></span>](https://www.microsoft.com/en-us/download/details.aspx?id=44535)

