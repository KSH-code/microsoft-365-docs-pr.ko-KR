---
title: 고급 eDiscovery 보고서
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ROBOTS: NOINDEX, NOFOLLOW
description: ''
ms.openlocfilehash: 387709ebdd84968d2b93992f6b92ef1548117569
ms.sourcegitcommit: 9ed3283dd6dd959faeca5c22613f9126261b9590
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2020
ms.locfileid: "43528361"
---
# <a name="advanced-ediscovery-reports-preview"></a>고급 eDiscovery 보고서 (미리 보기)

고급 eDiscovery 보고서는 조직 전체의 사례 데이터를 집계 하 여 데이터 분석 및 조직 보고를 간소화 하는 데 도움이 됩니다. 고급 eDiscovery 보고서 기능에는 다음과 같은 질문에 답할 수 있도록 몇 가지 기본 제공 보고서가 포함 되어 있습니다.

- 조직의 모든 사례에 대 한 활성 custodians 수

- 내 조직의 모든 경우에 대해 보류 중인 데이터 원본 수

- 조직의 모든 경우에 대해 지난 달에 실행 된 보류 알림 개수

- 조직에 있는 활성 및 닫힌 사례는 몇 개입니까?

## <a name="before-you-begin"></a>시작하기 전에

- 고급 eDiscovery 보고서에 액세스 하려면 eDiscovery 관리 역할 그룹의 구성원 이어야 합니다. 이 역할 그룹의 구성원 인 경우 보고서의 데이터를 보고, 필터링 하 고, 내보내야 하는 데 필요한 권한이 제공 됩니다. 자세한 내용은 [eDiscovery 권한 할당](assign-ediscovery-permissions.md)을 참조하세요.

- 고급 eDiscovery 보고서는 매일 새로 고쳐집니다. 따라서 새로운 사례, custodians, 데이터 원본 및 통신이 만들어지고 해당 보고서에 표시 될 때 지연이 있을 수 있습니다.

고급 eDiscovery 보고서에 액세스 하려면:

1. https://protection.office.com으로 이동합니다.
  
2. 회사 또는 학교 계정을 사용 하 여 Office 365에 로그인 합니다.
  
3. 보안 & 준수 센터에서 **eDiscovery > Advanced eDiscovery**를 클릭 합니다.
  
   **고급 eDiscovery** 홈 페이지에서는 사례, Custodian, 데이터 원본 및 통신 보고서 탭이 페이지 위쪽에 표시 됩니다. 
  
   ![홈 페이지의 고급 eDiscovery 보고서](../media/report-home.png)

5. 보고서를 보려면 보고서 탭을 클릭 하 고 필요한 경우 다음 작업 중 하나를 수행할 수 있습니다.

   ![보고서 데이터를 필터링 하거나 다운로드할 수 있습니다.](../media/AeDReportsFilterDownload.png)

   a. **필터** 를 클릭 하 여 보고서 데이터의 범위를 좁힙니다. 각 보고서에 대해 서로 다른 속성을 필터링 할 수 있습니다.
  
   b. **Csv로 다운로드** 를 클릭 하 여 보고서 데이터를 csv 파일로 내보냅니다.

## <a name="case-report"></a>사례 보고서

사례 보고서는 조직의 활성 및 닫힌 진행 중인 eDiscovery 사례에 대 한 정보를 집계 합니다.

|열        |설명|
|:-------------|:-------------|
|사례 ID | 각 사례에 대 한 고유 식별자입니다.| 
|사례 이름 | 대/소문자를 구분 하는 사용자 정의 이름입니다.|
|상태 | 케이스가 활성 상태 인지 닫혀 있는지를 나타냅니다.|
|만든 날짜 |사례를 만든 번째 날짜입니다. 날짜는 UTC 형식입니다.|
|마지막으로 수정한 날짜 |사례가 종료 되거나 마지막으로 업데이트 된 날짜입니다. 날짜는 UTC 형식입니다.| 
|||

## <a name="custodian-report"></a>Custodian 보고서

EDiscovery 워크플로에서 법적 사례 또는 조사를 수행 하는 사용자를 *데이터 custodians* (또는 *custodians*) 라고 하며 "문서 또는 전자 파일의 관리 제어 권한"으로 정의 됩니다. Custodian 보고서는 조직의 모든 경우에 대해 데이터 원본이 보존 되는 모든 custodians을 식별 하는 데 도움이 됩니다.

|열         |설명|
|:-------------|:-------------|
|Custodian 이름| Active Directory에 있는 custodian의 이름입니다.|
|Custodian UPN | Custodian의 사용자 계정 이름입니다.|
|Custodian ID | 지정 된 사례 내의 custodian에 대 한 고유 식별자입니다. |
|사례 이름 | 사례에 대 한 사용자 정의 이름입니다.|
|보류 상태 | Custodian가 현재 보류 중인 상태 인지 또는 사례에서 해제 되었는지 여부를 나타냅니다.|
|사례 Id | 사례에 대 한 고유 식별자입니다.|
|통신 상태 |Custodian에서 법적 보존 알림을 실행 했는지 여부를 나타냅니다. |
|Custodian 추가 됨 | Custodian가 사례에 추가 된 날짜입니다. 날짜는 UTC 형식입니다.|
|||

## <a name="data-source-report"></a>데이터 원본 보고서

고급 eDiscovery 사례를 사용 하 여 서비스 케이스와 관련이 있을 수 있는 콘텐츠를 보존 하는 보류를 만들 수 있습니다. Advanced eDiscovery 보존 기능을 사용 하 여 custodians 및 해당 데이터 원본에 대해 보류를 배치할 수 있습니다. 또한 사서함과 비즈니스용 OneDrive 계정에 custodial이 없는 보류를 배치할 수 있습니다. 데이터 원본 보고서를 사용 하 여 조직의 모든 경우에 대해 보류 중인 콘텐츠 위치에 대 한 세부 정보를 집계할 수 있습니다.

|열        |설명|
| -------------|-------------|
|사례 ID |각 사례에 대 한 고유 식별자입니다. |
|작업량 |보류 된 콘텐츠 위치의 유형 (예: Exchange 또는 SharePoint)을 나타냅니다.
|위치 이름 |Exchange 사서함의 SMTP 주소 또는 콘텐츠 위치의 URL (SharePoint 사이트용)을 나타냅니다. | 
|Custodian ID |데이터 원본이 custodian에 속하는 경우이 열에는 지정 된 사례의 custodian에 대 한 고유 식별자가 표시 됩니다. Custodial가 아닌 위치에 대해서는이 열이 null이 됩니다.|
|Custodian 이름 |Active Directory에 있는 custodian의 이름입니다.| 
|사례 이름 |사례에 대 한 사용자 정의 이름입니다.| 
|상태 |콘텐츠 위치가 현재 보류 상태 인지 여부를 나타냅니다. | 
|보존 정책 ID |콘텐츠 위치를 포함 하는 보류에 대 한 고유 식별자입니다. | 
|만든 날짜 유지 |보류 정책이 만들어진 날짜를 나타냅니다. 날짜는 UTC 형식입니다. | 
|보류 정책 이름 |콘텐츠 위치를 포함 하는 보류의 이름입니다. |
|수정 된 날짜 유지 |보류를 마지막으로 수정한 날짜입니다. 날짜는 UTC 형식입니다.| 
|마지막으로 수정한 사람 보존|보류를 마지막으로 수정한 사용자의 이름입니다.| 
|||

## <a name="communication-report"></a>통신 보고서

조직은 법적 정보 보호를 위해 법적 고 지 사항에 대 한 의무를 custodians 사용자에 게 알릴 수 있습니다. 통신 보고서를 사용 하 여 승인, 미리 알림, 에스컬레이션 및 기타 유형의 통신에 대 한 집계 데이터를 볼 수 있습니다.

|열         |설명|
| -------------|-------------|
|사례 ID | 사례에 대 한 고유 식별자입니다.|
|사례 이름 | 대/소문자를 구분 하는 사용자 정의 이름입니다.|
|Custodian ID |지정 된 사례에서 custodian에 대 한 고유 식별자입니다.|
|Custodian 이름 |Custodian의 이름입니다.|
|알림 유형 |Custodian에 대해 실행 된 알림의 유형을 나타냅니다.|
|관리자 발급 |법적 보존 알림을 실행 한 사용자의 이름입니다.|
|알림 이벤트|사용자에 게 전송 된 법적 보존 알림 메시지를 나타냅니다. 가능한 값은 미리 알림, 에스컬레이션, 확인 및 유지 발급입니다.|
|보낸 날짜 |통신이 실행 된 날짜입니다. 감사의 경우이 열에는 custodian에서 통지가 승인 된 시간이 표시 됩니다. 날짜는 UTC 형식입니다.|
|||
