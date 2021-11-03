---
title: 업데이트 준수 및 업데이트 관리에 대한 진단 Microsoft Defender 바이러스 백신
description: 도구를 사용하여 데이터 수집을 통해 Microsoft Defender 바이러스 백신 추가 기능을 사용할 때 준수 업데이트 문제를 해결합니다.
keywords: 문제 해결, 오류, 수정, 업데이트 준수, oms, 모니터링, 보고서, Microsoft Defender AV
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.collection: M365-security-compliance
ms.openlocfilehash: b8a0c196373cf0d6ef03b2eccb171d125917a993
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/02/2021
ms.locfileid: "60665804"
---
# <a name="collect-update-compliance-diagnostic-data-for-microsoft-defender-antivirus-assessment"></a>테스트 평가를 위한 업데이트 Microsoft Defender 바이러스 백신 데이터 수집


**적용 대상:**

- [엔드포인트용 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

이 문서에서는 업데이트 준수 추가 기능의 Microsoft Defender 바이러스 백신 평가 섹션을 사용할 때 발생할 수 있는 문제를 해결하기 위해 Microsoft 지원 및 엔지니어링 팀에서 사용할 수 있는 진단 데이터를 수집하는 방법에 대해 설명합니다.

이 프로세스를 시도하기 전에 Troubleshoot [troubleshoot Microsoft Defender 바이러스 백신 reporting](troubleshoot-reporting.md), met all require prerequisites을 충족하고 다른 제안된 문제 해결 단계를 수행해야 합니다.

업데이트 준수에 보고하거나 표시하지 않는 두 개 이상의 장치에서 다음 단계를 수행하여 .cab 진단 파일을 얻게 됩니다.

1. 다음과 같이 관리자 수준 명령 프롬프트 버전을 열 수 있습니다.

    a. 시작 **메뉴를** 열 수 있습니다.

    b. **cmd 를 입력합니다.** 명령 프롬프트를 **마우스 오른쪽 단추로 클릭한** 다음 **관리자 권한으로 실행을 선택합니다.**

    c. 관리자 자격 증명을 지정하거나 프롬프트를 승인합니다.

2. 사용자 디렉터리로 Windows Defender 이동합니다. 기본적으로 는 `C:\Program Files\Windows Defender` 입니다.

3. 다음 명령을 입력한 다음 **Enter를 누르기**

    ```Dos
    mpcmdrun -getfiles
    ```

4. 다양한 .cab 로그가 포함된 파일도 생성됩니다. 파일 위치는 명령 프롬프트의 출력에 지정됩니다. 기본적으로 위치는 `C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab` 입니다.

5. 이러한 .cab 파일을 Microsoft 지원에서 액세스할 수 있는 위치에 복사합니다. 예를 들어 사용자와 공유할 수 있는 암호로 OneDrive 폴더를 예로 들 수 있습니다.

6. 업데이트 준수 지원 <a href="mailto:ucsupport@microsoft.com?subject=MDAV assessment issue&body=I%20am%20encountering%20the%20following%20issue%20when%20using%20Windows%20Defender%20AV%20in%20Update%20Compliance%3a%20%0d%0aI%20have%20provided%20at%20least%202%20support%20.cab%20files%20at%20the%20following%20location%3a%20%3Caccessible%20share%2c%20including%20access%20details%20such%20as%20password%3E%0d%0aMy%20OMS%20workspace%20ID%20is%3a%20%0d%0aPlease%20contact%20me%20at%3a"></a>전자 메일 서식 파일을 사용하여 전자 메일을 보내고 다음 정보를 사용하여 서식 파일을 작성합니다.

    ```text
    I am encountering the following issue when using Microsoft Defender Antivirus in Update Compliance:

    I have provided at least 2 support .cab files at the following location: <accessible share, including access details such as password>

    My OMS workspace ID is:

    Please contact me at:
    ```

## <a name="see-also"></a>참고 항목

- [보고 Microsoft Defender 바이러스 백신 문제 해결](troubleshoot-reporting.md)
