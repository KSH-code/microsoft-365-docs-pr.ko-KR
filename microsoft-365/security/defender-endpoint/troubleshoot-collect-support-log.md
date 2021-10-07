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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: troubleshooting
ms.technology: mde
ms.openlocfilehash: 333fb1c1ea9dbe3c3105ce160a55a1e7ba5f3bc1
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60196816"
---
# <a name="collect-support-logs-in-microsoft-defender-for-endpoint-using-live-response"></a>라이브 응답을 사용하여 끝점용 Microsoft Defender에서 지원 로그 수집


**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Endpoint용 Defender를 경험하고 싶나요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-pullalerts-abovefoldlink)


지원에 문의할 때 끝점용 Microsoft Defender 클라이언트 분석기 도구의 출력 패키지를 제공해야 할 수 있습니다.

이 항목에서는 Live Response를 통해 도구를 실행하는 방법에 대한 지침을 제공합니다.

1. 적절한 스크립트 다운로드
   - 끝점용 Microsoft Defender 클라이언트 센서 로그만:LiveAnalyzer.ps1 [스크립트.](https://aka.ms/MDELiveAnalyzer)
      - 결과 패키지 대략적인 크기: ~100Kb
   - Microsoft Defender for Endpoint 클라이언트 센서 및 바이러스 백신 로그: [LiveAnalyzer+MDAV.ps1 스크립트입니다.](https://aka.ms/MDELiveAnalyzerAV)
       - 결과 패키지 대략적인 크기: ~10Mb

2. 조사해야 [하는](live-response.md#initiate-a-live-response-session-on-a-device) 컴퓨터의 실시간 응답 세션을 시작합니다.

3. 라이브러리에 **업로드 파일을 선택합니다.**

    ![업로드 파일의 이미지입니다.](images/upload-file.png)

4. 파일 **선택 을 선택합니다.**

    ![파일 선택 단추1의 이미지입니다.](images/choose-file.png)

5. 이름이 MDELiveAnalyzer.ps1 파일을 선택한 다음 확인을 **클릭합니다.**

   ![파일 단추 2 선택 이미지입니다.](images/analyzer-file.png)

6. LiveResponse 세션에서 여전히 아래 명령을 사용하여 분석기를 실행하고 결과 파일을 수집합니다.

    ```console
    Run MDELiveAnalyzer.ps1
    GetFile "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\MDEClientAnalyzerResult.zip"
    ```

    [![명령의 이미지입니다.](images/analyzer-commands.png)](images/analyzer-commands.png#lightbox)

> [!NOTE]
>
> - MDEClientAnalyzer의 최신 미리 보기 버전은 에서 다운로드할 수 [https://aka.ms/Betamdeanalyzer](https://aka.ms/Betamdeanalyzer) 있습니다. .
>
> - LiveAnalyzer 스크립트는 다음에서 대상 컴퓨터의 문제 해결 패키지를 https://mdatpclientanalyzer.blob.core.windows.net 다운로드합니다.
>
>   컴퓨터의 위 URL에 도달하도록 허용할 수 없는 경우 LiveAnalyzer 스크립트를 실행하기 전에 MDEClientAnalyzerPreview.zip 파일을 라이브러리에 업로드합니다.
>
>   ```console
>   PutFile MDEClientAnalyzerPreview.zip -overwrite
>   Run MDELiveAnalyzer.ps1
>   GetFile "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\MDEClientAnalyzerResult.zip"
>   ```
>
> - 컴퓨터의 끝점 클라우드 서비스용 Microsoft Defender와 통신하지 않는 경우 또는 끝점용 Microsoft Defender 포털에 예상대로 나타나지 않는 경우 컴퓨터의 데이터를 로컬로 수집하는 데 대한 자세한 내용은 끝점 서비스 [URL에 대한 Microsoft Defender에](configure-proxy-internet.md#verify-client-connectivity-to-microsoft-defender-for-endpoint-service-urls)대한 클라이언트 연결 확인을 참조하세요.
> 
> - 라이브 응답 [](live-response-command-examples.md)명령 예제에 설명된 바와 같이 명령 끝에 '&' 기호를 사용하여 로그를 백그라운드 작업으로 수집할 수 있습니다.
>   ```console
>   Run MDELiveAnalyzer.ps1&
>   ```


## <a name="see-also"></a>참고 항목
- [클라이언트 분석기 개요](overview-client-analyzer.md)
- [클라이언트 분석기 다운로드 및 실행](download-client-analyzer.md)
- [Windows에서 클라이언트 분석기 실행](run-analyzer-windows.md)
- [macOS 또는 Linux에서 클라이언트 분석기 실행](run-analyzer-macos-linux.md)
- [Windows에서 고급 문제 해결을 위한 데이터 수집](data-collection-analyzer.md)
- [분석기 HTML 보고서 이해](analyzer-report.md)

