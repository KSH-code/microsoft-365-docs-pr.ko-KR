---
title: 자동화 된 조사에 대 한 세부 정보 및 결과
description: '자동화 조사가 진행 되는 동한 혹은 진행 완료된 후 주요 사항 및 결과를 확인할 수 있습니다. '
keywords: 자동화, 조사, 결과, 분속, 세부정보, 재구성, 오토에어
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.date: 09/16/2020
ms.openlocfilehash: 62d33c57606aad81607164b1f068c6f6d91063c2
ms.sourcegitcommit: 7c0873d2a804f17697844fb13f1a100fabce86c4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/18/2020
ms.locfileid: "47962302"
---
# <a name="details-and-results-of-an-automated-investigation"></a>자동화 된 조사에 대 한 세부 정보 및 결과

**적용 대상:**
- Microsoft Threat Protection

Microsoft Threat Protection에서 자동 조사가 발생 하는 경우, 해당 조사에 대한 세부 정보는 자동화 검사 프로세스 중에 확인할 수 있습니다. [필수 권한이](mtp-action-center.md#required-permissions-for-action-center-tasks)있는 경우 조사 세부 정보 보기에서 해당 정보를 확인할 수 있습니다.  조사 세부정부 보기에서 최신 상태를 확인하거나 보류중인 작업을 승인할 수 있습니다. 

![조사 세부정보](../../media/mtp-air-investdetails.png)

## <a name="open-the-investigation-details-view"></a>조사 세부정보 보기 열기 

다음 방법 중 하나를 사용 하여 조사 세부정보 보기를 열 수 있습니다.
- [작업 센터에서 항목 선택](#select-an-item-in-the-action-center)
- [문제 세부정보 페이지에서 조사 선택](#open-an-investigation-from-an-incident-details-page)

### <a name="select-an-item-in-the-action-center"></a>작업 센터에서 항목 선택

작업 센터를 사용하여 승인이 보류 중이거나 (**보류 중인** 탭에서) 기승인 된 (**기록** 탭에서) 작업을 볼 수 있습니다. 

1. [https://security.microsoft.com](https://security.microsoft.com)으로 이동하여 로그인합니다. 

2. 탐색 창에서 **작업 센터**를 선택합니다. 

3. **보류 중인** 또는 **기록** 탭에서 항목을 선택 합니다. [필수 권한이](mtp-action-center.md#required-permissions-for-action-center-tasks)있는 경우 보류 중인 작업을 승인(또는 거부) 할 수 있습니다.

### <a name="open-an-investigation-from-an-incident-details-page"></a>문제 세부정보 페이지에서 조사 오픈 

세부정보 페이지를 통해 알람 원인 장치, 사용자, 사서함 등 사건에 대한 세부 정보를 확인할 수 있습니다. 

1. [https://security.microsoft.com](https://security.microsoft.com)으로 이동하여 로그인합니다. 

2. 탐색 창에서 **사건**을 선택합니다. 

3. 목록에서 항목을 선택 하여 사건 세부정보 보기를 엽니다.<br/>![사건 세부 정보](../../media/mtp-incidentdetails-tabs.png)

4. **조사** 탭의 목록에서 조사를 선택 합니다.

## <a name="investigation-details"></a>조사 세부정보

조사 세부정보 보기를 사용 하여 과거, 현재 및 보류 중인 활동을 확인하고 조사합니다. 조사 세부정보 보기는 다음 이미지와 유사 합니다.

![조사 세부정보](../../media/mtp-air-investdetails.png)

조사 세부정보 보기에서 아래 테이블에 설명되어 있는 것 처럼 **조사 그래프**, **알람**, **장치**, **항목**, **주요 발견 사항**, **대상**, **로그** 및 **보류 활동**을 확인할 수 있습니다. 

|Tab    |설명 |
|--------|--------|
|조사 그래프    |조사 내용이 시각적으로 표시 됩니다. 위협 대상과 목록 알람과 현재 활동이나 보류중인 활동을 보여줍니다. <br/>그래프에서 항목을 클릭 하면 세부정보를 볼 수 있습니다. 예를들어, **찾은 위협** 아이콘을 클릭하면 **주요 발견 사항**으로 이동합니다.  |
|알람 |조사와 관련 된 알람목록을 보여줍니다.  사용자 컴퓨터의 위협 방지 기능, Office 앱, 클라우드 앱 보안 및 기타 Microsoft 365 Threat Protection에서 알람이 발생합니다. |
|장치|재구성 수준과 함께 조사에 포함된 기기 목록을 보여줍니다. |
|주요 발견 사항   |검사 결과 및 상황, 활동 중이거나 보류중인 작업 목록을 보여줍니다.  이 탭에서 장치 빛 식별 보류 작업을 승인할 수 있습니다. |
|항목   |조사에 관련된 사용자 활동, 파일, 프로세스, 서비스, 드라이버, IP 주소 및 유지 방법과 함께 수행된 활동과 상태 목록을 보여줍니다. |
|로그    |조사 중에 수행된 모든 단계의 세부정보와 상태를 보여줍니다. |
|보류 중인 작업    |진행 하려면 승인이 필요한 항목을 나열 합니다.|

## <a name="next-steps"></a>다음 단계

- [자동화 조사 및 대응과 관련된 작업 승인 또는 거부](mtp-autoir-actions.md)

