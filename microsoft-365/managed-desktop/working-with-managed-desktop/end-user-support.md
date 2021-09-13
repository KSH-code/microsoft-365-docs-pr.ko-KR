---
title: 사용자 지원 Microsoft Managed Desktop
description: 사용자가 서비스 및 장치에 대한 도움말을 얻을 수 있는 방법
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: ad3b53a9936fb40c8d699f656f88bf5a3fff20b9
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59215185"
---
# <a name="getting-help-for-users"></a>사용자를 위한 도움말

Microsoft에 대한 상승된 장치 [](../service-description/user-support.md) 액세스 또는 에스컬레이터를 요청해야 하는 워크플로 지점에 도달한 경우 다음 단계를 수행합니다.
 
>[!NOTE]
>테스트 그룹의 디바이스에서는 이러한 지원 옵션을 사용할 수 없습니다.

## <a name="elevation-requests"></a>권한 상승 요청

장치에 대한 높은 액세스 권한을 요청하기 전에 가장 적합한 작업을 검토하는 것이 가장 좋은 것입니다.

- **일반적인 작업은** 이 프로세스가 의도한 작업으로, 장치와의 문제를 해결하는 동안 Microsoft Managed Desktop 수행됩니다. 예를 들면 다음과 같습니다.
    - 기본 제공 시스템 문제 해결사, 명령 프롬프트 또는 Windows PowerShell
    - 업무용 응용 프로그램 문제 해결
    - 해결 방법을 사용하여 디자인에 따라 작동해야 하는 기능 수정(예: BitLocker 정품 인증 또는 업데이트되지 않는 시스템 시간)
    - 업데이트 드라이버, 장치 제거 또는 새 변경 내용 검색과 같은 작업을 위해 장치 관리자 권한 상승

- **권장되지 않는 작업은** 다음과 같습니다.
    - 소프트웨어 또는 브라우저 설치
    - 주변 장치용 드라이버를 Windows 설정 외부에 드라이버 설치
    - 파일 .msi 또는 .exe 설치
    - Windows 기능 설치

- **지원되지 않는 작업은** 다음과 같습니다.
    - 보안 또는 관리 기능과 충돌하는 소프트웨어 또는 Microsoft Managed Desktop 기능 설치
    - BitLocker와 같은 Windows 필요한 Microsoft Managed Desktop 기능을 사용 하지 않습니다.
    - 관리되는 설정 수정

### <a name="to-request-elevation"></a>권한 상승을 요청하는 경우

1. 의 포털로 이동한 후 사용자 자격 증명으로 [https://aka.ms/mmdelevationrequest](https://aka.ms/mmdelevationrequest) Azure Active Directory 로그인합니다.
2. 새 **권한 상승 요청을 선택합니다.**
3. 다음 세부 정보를 제공합니다.
    - **자체 지원 티켓** 시스템에서 티켓 ID를 지원합니다.
    - **장치 이름:** 장치 일련 번호를 입력한 다음 메뉴에서 장치를 선택합니다.
    - **범주:** 문제와 가장 잘 맞는 범주를 선택합니다. 옵션이 닫히는 것 같은 경우 기타 를 **선택합니다.** 가능한 경우 범주를 선택하는 것이 가장 좋습니다.
    - **하위 목록**: 이슈에 가장 잘 맞는 하위 목록 선택 옵션이 닫히는 것 같은 경우 기타 를 **선택합니다.**
    - **제목:** 장치에서 문제의 간단한 설명을 제공합니다.
    - **작업 계획:** 권한 상승이 부여된 후 수행하기로 계획한 문제 해결 단계를 제공하세요. 
4. **전송** 을 선택합니다.


## <a name="escalation-requests"></a>에스컬레이터 요청


Microsoft로 [문제를 에스컬레이터해야](../service-description/user-support.md#escalation-portal) 하는 경우 다음 단계를 수행합니다.

1. 의 포털로 이동한 후 사용자 자격 증명으로 [https://aka.ms/mmdelevationrequest](https://aka.ms/mmdelevationrequest) Azure Active Directory 로그인합니다.
2. **에스컬ation 요청 을** 선택한 다음 새 **에스컬ation 요청을 선택합니다.**
3. 다음 세부 정보를 제공합니다.
    - **범주:** 문제와 가장 잘 맞는 범주를 선택합니다.
    - **제목:** 간단한 설명을 입력합니다.
    - **설명:** 팀에서 문제를 이해하는 데 도움이 될 수 있는 세부 정보를 추가합니다. 파일을 첨부해야 하는 경우 파일을 제출한 후 요청으로 돌아와서 첨부할 수 있습니다.
    - **기본 연락처 정보:** 팀과 함께 작업하는 주 담당자에게 연락하는 방법에 대한 정보를 제공합니다.
4. **전송** 을 선택합니다.
5. 팀과 상호 작용하기 위해 동일한 포털에서 티켓을 다시 검색합니다.

> [!NOTE]
> 이 경로를 통해 심각도 C 문제만 에스컬레이터할 수 있습니다. 다른 문제가 있는 경우 IT 관리자에게 문의하여 관리 포털을 통해 요청을 제출합니다.
