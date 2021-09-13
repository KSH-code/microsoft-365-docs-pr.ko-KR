---
title: Endpoint 라이브 응답 문제에 대한 Microsoft Defender 문제 해결
description: 끝점용 Microsoft Defender에서 라이브 응답을 사용할 때 발생할 수 있는 문제 해결
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
ms.openlocfilehash: a6be4282c2388f8a3aff3cd91bb8385f712bdea3
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59220215"
---
# <a name="troubleshoot-microsoft-defender-for-endpoint-live-response-issues"></a>Endpoint 라이브 응답 문제에 대한 Microsoft Defender 문제 해결

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Endpoint용 Defender를 경험하고 싶나요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-pullalerts-abovefoldlink)

이 페이지에서는 라이브 응답 문제를 해결하기 위한 자세한 단계를 제공합니다.

## <a name="file-cannot-be-accessed-during-live-response-sessions"></a>라이브 응답 세션 중에 파일에 액세스할 수 없습니다.

라이브 응답 세션 중에 작업을 수행하려고 할 때 파일에 액세스할 수 없다고 하는 오류 메시지가 표시될 경우 아래 단계를 사용하여 문제를 해결해야 합니다.

1. 다음 스크립트 코드 코드를 복사하여 PS1 파일로 저장합니다.

    ```powershell
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

2. 라이브 응답 라이브러리에 스크립트를 추가합니다.
3. 복사할 파일의 파일 경로인 매개 변수 하나를 사용하여 스크립트를 실행합니다.
4. TEMP 폴더로 이동합니다.
5. 복사한 파일에 대한 작업을 실행합니다.

## <a name="slow-live-response-sessions-or-delays-during-initial-connections"></a>초기 연결 중에 느린 라이브 응답 세션 또는 지연

라이브 응답은 WNS 서비스에 대한 끝점 센서 등록에 대한 Defender를 Windows. 라이브 응답에 연결 문제가 있는 경우 다음 세부 정보를 확인 합니다.

1. `notify.windows.com` 는 환경에서 차단되지 않습니다. 자세한 내용은 장치 프록시 및 인터넷 연결 설정 [구성을 참조하세요.](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)
2. WpnService(Windows 알림 시스템 서비스)를 사용할 수 없습니다.

WpnService 서비스 동작 및 요구 사항을 완전히 이해하기 위해 아래 문서를 참조하세요.

- [Windows WNS(푸시 Notification Services) 개요](/windows/uwp/design/shell/tiles-and-notifications/windows-push-notification-services--wns--overview)
- [Enterprise WNS 트래픽을 지원하기 위한 방화벽 및 프록시 구성](/windows/uwp/design/shell/tiles-and-notifications/firewall-allowlist-config)
- [Microsoft 푸시 알림 서비스(MPNS) 공용 IP 범위](https://www.microsoft.com/download/details.aspx?id=44535)
