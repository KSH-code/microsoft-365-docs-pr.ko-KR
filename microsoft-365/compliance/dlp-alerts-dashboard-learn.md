---
title: 데이터 손실 방지 알림 대시보드에 대한 자세한 정보
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
ms.custom:
- seo-marvel-apr2020
description: 데이터 손실 방지 경고 및 경고 대시보드에 대해 자세히 알아보습니다.
ms.openlocfilehash: ea5d01e580b88445ba64e4ed26fc01fb51c97d5d
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60175218"
---
# <a name="learn-about-the-data-loss-prevention-alerts-dashboard"></a>데이터 손실 방지 알림 대시보드에 대한 자세한 정보

DLP(데이터 손실 방지) 정책의 기준이 사용자가 중요한 항목에 대해 수행하고 있는 작업과 일치하면 정책에서 경고를 생성할 수 있습니다. 이로 인해 많은 경고가 생성될 수 있습니다. DLP 경고는 경고 대시보드에서 수집됩니다. 알림 대시보드에서는 정책 일치와 관련한 모든 세부 정보를 심도 깊게 조사할 수 있는 단일 장소를 제공합니다.  

<!-- [Microsoft 365 compliance center](https://compliance.microsoft.com/)-->

## <a name="workloads"></a>워크로드

DLP [경고 관리](https://compliance.microsoft.com/datalossprevention?viewid=dlpalerts) [대시보드](https://compliance.microsoft.com/)의 Microsoft 365 규정 준수 센터 워크로드에 대한 DLP 정책에 대한 경고가 표시됩니다.

- Exchange
- SharePoint
- OneDrive
- Teams
- Windows 10 장치 

> [!TIP]
> Teams DLP를 사용할 수 있는 끝점 [DLP를](endpoint-dlp-learn-about.md) 사용하는 고객에게는 끝점 DLP 정책 경고 및 [DLP](dlp-microsoft-teams.md) Teams 관리 대시보드에서 DLP 정책 경고가 표시됩니다.

## <a name="single-alert-and-aggregate-alert"></a>단일 경고 및 집계 경고

DLP 정책에서 구성할 수 있는 두 가지 유형의 경고가 있습니다.

**단일 이벤트** 경고는 일반적으로 조직 외부로 10개 이상의 고객 신용 카드 번호가 전송되는 단일 전자 메일과 같이 낮은 볼륨으로 발생하는 매우 중요한 이벤트를 모니터링하는 정책에 사용됩니다.

**집계 이벤트 경고는** 일반적으로 일정 기간 동안 더 많은 볼륨으로 발생하는 이벤트를 모니터링하는 정책에 사용됩니다. 예를 들어 48시간 넘게 고객 신용 카드 번호가 하나인 개별 전자 메일 10개가 각각 48시간 넘게 전송되면 집계 경고가 트리거될 수 있습니다.

## <a name="types-of-events"></a>이벤트 유형

다음은 경고와 관련된 몇 가지 이벤트입니다. UI에서 특정 이벤트를 선택하면 세부 정보를 볼 수 있습니다. 

### <a name="event-details"></a>이벤트 세부 정보

|속성 이름  |설명  |이벤트 유형  |
|---------|---------|---------|
|ID |이벤트와 연결된 고유 ID |모든 이벤트 |
|위치 |이벤트가 검색된 워크로드|모든 이벤트 |
|활동 시간     |DLP 정책의 조건과 일치하는 사용자 활동의 시간 |

### <a name="impacted-entities"></a>영향을 미치는 엔터티

|속성 이름 |설명| 이벤트 유형|
|---------|---------|---------|
|사용자 | 정책 일치를 유발한 작업을 수행한 사용자 | 모든 이벤트|
|hostname | DLP 정책 일치가 발생한 컴퓨터의 호스트 이름 | 장치 이벤트|
|IP 주소 | DLP 정책 일치가 발생한 컴퓨터의 IP 주소 | 장치 이벤트|
|sha1 |파일의 SHA-1 해시 | 장치 이벤트|
|sha256 | 파일의 SHA-256 해시 | 장치 이벤트|
|MDATP 장치 ID | 끝점 장치 MDATP ID|
|파일 크기 | 파일의 크기| SharePoint, OneDrive 및 장치 이벤트|
|파일 경로 | DLP 정책 일치와 관련된 항목의 절대 경로 | SharePoint, OneDrive 및 장치 이벤트|
|전자 메일 받는 사람 |전자 메일이 DLP 정책과 일치하는 중요한 항목인 경우 이 필드에는 해당 전자 메일의 받는 사람이 포함됩니다.| Exchange 이벤트|
|전자 메일 제목 |DLP 정책과 일치하는 전자 메일의 제목 |Exchange 이벤트|
|전자 메일 첨부 파일 | DLP 정책과 일치하는 전자 메일의 첨부 파일 이름| Exchange 이벤트|
|사이트 소유자 |사이트 소유자의 이름| SharePoint 및 OneDrive 이벤트|
|사이트 URL |DLP 정책이 일치하는 SharePoint OneDrive 사이트의 URL 전체 |SharePoint 및 OneDrive 이벤트|
|만든 파일 |DLP 정책과 일치하는 파일을 만들 때의 시간 |SharePoint 및 OneDrive 이벤트|
|마지막으로 수정한 파일 | DLP 정책과 일치하는 파일이 마지막으로 변경된 시간 | SharePoint 및 OneDrive 이벤트|
|파일 크기 | DLP 정책과 일치하는 파일의 크기 |SharePoint 및 OneDrive 이벤트|
|파일 소유자 |DLP 정책과 일치하는 파일의 소유자 |SharePoint 및 OneDrive 이벤트|  

### <a name="policy-details"></a>정책 세부 정보

|속성 이름 |설명 |이벤트 유형 |
|---------|---------|---------|
|일치하는 DLP 정책 |일치하는 DLP 정책의 이름 |모든 이벤트|
|일치하는 규칙 |일치하는 DLP 정책 규칙의 이름 |모든 이벤트|
|SIT(중요한 정보 유형) 검색|DLP 정책 일치의 일부로 검색된 SITS |모든 이벤트|
|수행한 작업 |DLP 정책 일치를 유발한 작업을 수행했습니다.| 모든 이벤트|
|위반 작업 | DLP 경고를 발생한 끝점 장치에 대한 작업| 장치 이벤트 | 
|사용자 과도 정책 |사용자가 정책 팁을 통해 정책을 오버라이드했기 | 모든 이벤트|
|의회 정당성에 대한 사용 |사용자가 해당 이유에 대해 제공한 이유 텍스트 | 모든 이벤트|   

## <a name="see-also"></a>참고 항목

- [데이터 손실 방지 경고 대시보드 시작](dlp-alerts-dashboard-get-started.md)
- [데이터 손실 방지로 시작하는 위치](create-test-tune-dlp-policy.md#where-to-start-with-data-loss-prevention)