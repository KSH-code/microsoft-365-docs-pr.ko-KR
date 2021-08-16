---
title: macOS 또는 Linux에서 클라이언트 분석기 실행
description: macOS 또는 Linux에서 끝점 클라이언트 분석기용 Microsoft Defender를 실행하는 방법에 대해 자세히 알아보기
keywords: 클라이언트 분석기, 센서 문제 해결, 분석기, mdeanalyzer, macos, linux, mdeanalyzer
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 6008e59abadc179f8e6580d56007ea88b9415ab5
ms.sourcegitcommit: a0185d6b0dd091db6e1e1bfae2f68ab0e3cf05e5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/13/2021
ms.locfileid: "58254846"
---
#  <a name="run-the-client-analyzer-on-macos-and-linux"></a>macOS 및 Linux에서 클라이언트 분석기 실행

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2146631)


## <a name="running-the-analyzer-through-gui-scenario"></a>GUI 시나리오를 통해 분석기 실행

1.  [XMDE 클라이언트 분석기](https://aka.ms/XMDEClientAnalyzer) 도구를 조사해야 하는 macOS 또는 Linux 컴퓨터로 다운로드합니다.
> [!NOTE]  
> 위의 링크에서 다운로드한 'XMDEClientAnalyzer.zip'의 현재 SHA256 해시는 '029296D437BA97B5563D0C75DD874F8F51C563B2B5AC16745619F4DB2E064C85'입니다.

2.  컴퓨터의 콘텐츠 XMDEClientAnalyzer.zip 추출합니다.

3.  터미널 세션을 열고 디렉터리를 추출된 위치로 변경한 후 다음을 실행합니다.

`./mde_support_tool.sh -d`

! 참고  
Linux에서 스크립트 실행 권한이 없는 경우 먼저 실행해야 합니다.  
*chmod a+x mde_support_tool.sh*

## <a name="running-the-analyzer-using-a-terminal-or-ssh-scenario"></a>터미널 또는 SSH 시나리오를 사용하여 분석기 실행

1.  관련 컴퓨터로 터미널 또는 SSH를 넣습니다.

2.  실행 `wget --quiet -O XMDEClientAnalyzer.zip*
    <http://aka.ms/XMDEClientAnalyzer> *&& unzip -q XMDEClientAnalyzer.zip && cd
    XMDEClientAnalyzer && chmod +x mde_support_tool.sh"`

3.  를 ` ./mde_support_tool.sh -d ` 실행하여 결과 보관 파일을 생성합니다.

> [!NOTE]  
> Linux의 경우 분석기에서 결과 출력을 생성하려면 'lxml'이 필요합니다. 설치되지 않은 경우 분석기는 아래 python 패키지에 대한 공식 리포지토리에서 이를 페치하려고 시도합니다.  
https://files.pythonhosted.org/packages/\*/lxml \* .whl

예제:  


![명령줄 예제의 이미지](images/4ca188f6c457e335abe3c9ad3eddda26.png)

  
  
추가 구문 도움말:

**-h** \# 도움말  
\# 도움말 메시지 표시

**-p** \# 성능  
\# 아직 구현되지 않은 계획된 매개 변수입니다.  
\# 요구 시 재현할 수 있는 성능 문제를 분석하기 위한 광범위한 추적을 수집합니다.

**-o** \# 출력  
\# 결과 파일의 대상 경로 지정

**-nz** \# No-Zip  
\# 설정된 경우 결과 보관 파일 대신 디렉터리가 만들어집니다.

**-f** \# Force  
\# 대상 경로에 출력이 이미 있는 경우 덮어써야 합니다.

## <a name="result-package-contents-on-macos-and-linux"></a>macOS 및 Linux의 결과 패키지 콘텐츠

-   report.html <br> 설명: 분석기 스크립트가 컴퓨터로 실행될 수 있는 결과 및 지침을 포함할 기본 HTML 출력 파일입니다.

-   mde_diagnostic.zip <br> 설명: [macOS](/windows/security/threat-protection/microsoft-defender-atp/mac-resources#collecting-diagnostic-information) 또는 [Linux에서](/windows/security/threat-protection/microsoft-defender-atp/linux-resources#collect-diagnostic-information) *mdatp* 진단 만들기를 실행하면 생성되는 동일한 진단 출력

-   mde.xml <br> 설명: 실행 중 생성되고 html 보고서 파일을 작성하는 데 사용되는 XML 출력입니다.

-   Processes_information.txt <br> 설명: 시스템에서 끝점 관련 프로세스에 대해 실행 중인 Microsoft Defender의 세부 정보를 제공합니다.

-   Log.txt <br> 설명: 데이터 수집 중에 화면에 작성된 동일한 로그 메시지를 포함

-   Health.txt <br> 설명: *mdatp* 상태 명령을 실행하면 표시되는 기본 상태 출력과 동일합니다.

-   Events.xml <br> 설명: HTML 보고서를 구축할 때 분석기에서 사용하는 추가 XML 파일입니다.

-   Auditd_info.txt <br> 설명: Linux OS에 대한 감사된 서비스 및 관련 구성 [요소에](/windows/security/threat-protection/microsoft-defender-atp/linux-support-events) 대한 세부 정보
