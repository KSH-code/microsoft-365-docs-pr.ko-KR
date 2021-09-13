---
title: 활동 탐색기에서 보고된 작업의 레이블 지정
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: 활동 탐색기에서 사용할 수 있는 레이블 지정 활동 목록입니다.
ms.openlocfilehash: 163231d4d1e7c6a2d1b75c0f81a17443cfafe246
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59184203"
---
# <a name="labeling-activities-that-are-available-in-activity-explorer"></a>활동 탐색기에서 사용할 수 있는 레이블 지정 활동

## <a name="sensitivity-label-applied"></a>적용된 민감도 레이블

이 이벤트는 레이블이 지정되지 않은 문서에 레이블이 지정되거나 민감도 레이블이 있는 전자 메일을 보낼 때마다 생성됩니다. 

- 기본 응용 프로그램 및 웹 응용 프로그램에 Office 캡처됩니다. 
- Azure Information Protection 추가 기능에서 발생 시 캡처됩니다. 
- 레이블 이벤트 유형 필드 및 필터를 통해  레이블 업그레이드 및 다운그레이드 작업을 모니터링할 수도 있습니다.   


|원본  |활동 탐색기에서 보고 | 참고  |
|---------|---------|---------|
| Word, Excel, PowerPoint|예 |
|Outlook| 예 | |
|SharePoint 온라인 OneDrive|예 | |
|Exchange        |예         | |
|AIP(Azure Information Protection) 통합 클라이언트 및 AIP 통합 스캐너 |예 |AIP *새 레이블 동작이* 활동 탐색기에서 *적용된 레이블에* 매핑됩니다.   |
|MIP(Microsoft 정보 보호) SDK         |예|AIP *새 레이블 동작이* 활동 탐색기에서 *적용된 레이블에* 매핑됩니다.|
|RMS(권한 관리 서비스)         |해당 없음         | |
|Power BI 및 웹        | 아니요| 감사 로그에서 Microsoft 365 액세스할 수 있습니다.         |
|Microsoft Cloud App Security(MCAS)         |아니요|         |

## <a name="sensitivity-label-changed"></a>민감도 레이블 변경

이 이벤트는 문서 또는 전자 메일에서 민감도 레이블이 업데이트될 때마다 생성됩니다.

- AIP 통합 클라이언트, 통합 스캐너 및 MIP SDK 원본의 경우  *AIP* 업그레이드 레이블 및 다운그레이드 레이블 작업이 변경된 활동 탐색기 레이블에 *매핑됩니다.*

- 기본 응용 프로그램 및 웹 응용 프로그램에서 저장 Office 캡처됩니다. 
- Azure Information Protection 통합 클라이언트 추가 기능 및 스캐너 적용에서 발생 시 캡처됩니다.
- 레이블 이벤트 유형 필드 및 필터를 통해  레이블 업그레이드 및 다운그레이드 작업을 모니터링할 수도 있습니다. 온라인 *및* 온라인을 제외한 SharePoint 텍스트도 OneDrive.
- Office 기본 앱에서 수행한 민감도 레이블 Outlook 파일 저장/전자 메일 보내기 작업 전에 생성된 마지막 작업을 수집합니다. 예를 들어 사용자가 보내기 전에 전자 메일에서 레이블을 여러 번 변경하는 경우 전자 메일이 전송될 때 찾은 마지막 레이블이 감사 로그에 캡처된 다음 활동 탐색기에서 보고됩니다. 


|원본  |활동 탐색기에서 보고|참고  |
|---------|---------|---------| 
|Word, Excel, PowerPoint         |예         |
|Outlook         |예         |
|SharePoint 온라인, OneDrive         |예         |
|Exchange         |예         |
|AIP 통합 클라이언트         |예         |
|AIP 통합 스캐너         |예         |
|MIP SDK         |예         |
|RMS 서비스         |해당 없음         |
|Power BI 및 웹         |아니요         |감사 로그에서 Microsoft 365 액세스할 수 있습니다. |
|MCAS     |아니요         |         |

## <a name="sensitivity-label-removed"></a>민감도 레이블 제거됨

이 이벤트는 파일이나 문서에서 민감도 레이블을 제거할 때마다 생성됩니다.

- 이 이벤트는 기본 응용 프로그램 및 웹 응용 프로그램에 Office 캡처됩니다.
- Azure Information Protection 추가 기능에서 발생 시 캡처됩니다. 
- 기본 MIP 레이블을 Office 민감도 레이블을 Outlook 파일 저장/전자 메일 보내기 작업 전에 생성된 마지막 레이블 지정 이벤트를 수집합니다.

|원본  |활동 탐색기에서 보고 | 참고  |
|---------|---------|---------| 
|Word, Excel, PowerPoint         |예         |
|Outlook         |예         ||
|SharePoint 온라인, OneDrive         |예         |
|Exchange         |예         |
|AIP 통합 클라이언트         |예         |AIP *레이블 제거 작업은* 활동 탐색기에서 레이블 제거 *동작에* 매핑됩니다.|
|AIP 통합 스캐너         |예         |AIP *레이블 제거 작업은* 활동 탐색기에서 레이블 제거 *동작에* 매핑됩니다. |
|MIP SDK         |예         |AIP *레이블 제거 작업은* 활동 탐색기에서 레이블 제거 *동작에* 매핑됩니다. |
|RMS 서비스         |해당 없음         |
|Power BI 및 웹         |아니요         |감사 로그에서 Microsoft 365 액세스할 수 있습니다. |
|MCAS     |아니요         |         |
 

## <a name="sensitivity-label-file-read"></a>민감도 레이블 파일 읽기

이 이벤트는 레이블이 지정되거나 보호된 문서를 열 때마다 생성됩니다.

|원본  |활동 탐색기에서 보고 | 참고  |
|---------|---------|---------| 
|Word, Excel, PowerPoint         |예         |
|Outlook         |아니요         |
|SharePoint 온라인, OneDrive         |아니요         |
|Exchange         |아니요         |
|AIP 통합 클라이언트         |예         |AIP *액세스 작업이* 활동 탐색기에서 *파일* 읽기 작업으로 매핑됩니다.|
|AIP 통합 스캐너         |예         |AIP *액세스 작업이* 활동 탐색기에서 *파일* 읽기 작업으로 매핑됩니다.|
|MIP SDK         |예         |AIP *액세스 작업이* 활동 탐색기에서 *파일* 읽기 작업으로 매핑됩니다.|
|RMS 서비스         |예         |액세스 *작업이* 활동 탐색기에서 *파일 읽기* 작업으로 매핑됩니다. |
|Power BI 및 웹         |아니요         |감사 로그에서 Microsoft 365 액세스할 수 있습니다. |
|MCAS     |아니요         |         |


## <a name="files-discovered"></a>검색된 파일

이 이벤트는 AIP 스캐너를 사용하여 여러 위치에서 중요한 데이터를 검색하고 파일을 찾을 때마다 생성됩니다.

|원본  |활동 탐색기에서 보고 | 참고  |
|---------|---------|---------| 
|Word, Excel, PowerPoint         |해당 없음         |
|Outlook         |해당 없음         |
|SharePoint 온라인, OneDrive         |해당 없음         |
|Exchange         |해당 없음         |
|AIP 통합 클라이언트         |해당 없음       |
|AIP 통합 스캐너         |예         |AIP *검색 작업이* 활동 탐색기에서 검색된 파일에 매핑됩니다. |
|MIP SDK         |예         |AIP *검색 작업이* 활동 탐색기에서 검색된 파일에 매핑됩니다. |
|RMS 서비스         |해당 없음         |
|Power BI 및 웹         |해당 없음         |
|MCAS     |해당 없음         |         |


## <a name="sensitivity-label-file-renamed"></a>민감도 레이블 파일 이름 변경

이 이벤트는 민감도 레이블이 있는 문서의 이름을 변경할 때마다 생성됩니다. 

|원본  | 활동 탐색기에서 보고 | 참고  |
|---------|---------|---------| 
|Word, Excel, PowerPoint         |예         |
|Outlook         |해당 없음         |
|SharePoint 온라인, OneDrive         |아니요        |
|Exchange         |해당 없음         |
|AIP 통합 클라이언트         |아니요         |
|AIP 통합 스캐너         |아니요         |
|MIP SDK         |아니요         |
|RMS 서비스         |아니요      |
|Power BI 및 웹         |아니요         |
|MCAS     |아니요         |         |


## <a name="file-removed"></a>파일 제거됨

이 이벤트는 AIP 스캐너가 이전에 검색한 파일이 제거된 것으로 감지될 때마다 생성됩니다.

|원본  |활동 탐색기에서 보고 | 참고  |
|---------|---------|---------| 
|Word, Excel, PowerPoint         |해당 없음         |
|Outlook         |해당 없음         |
|SharePoint 온라인, OneDrive         |해당 없음           |
|Exchange         |해당 없음         |
|AIP 통합 클라이언트         |해당 없음            |
|AIP 통합 스캐너         |예         |
|MIP SDK         |해당 없음            |
|RMS 서비스         |해당 없음         |
|Power BI 및 웹         |해당 없음  |
|MCAS     |해당 없음        |         |

### <a name="protection-applied"></a>적용된 보호

이 이벤트는 레이블이 없는 항목에 처음 보호가 수동으로 추가될 때 생성됩니다.

|원본  |활동 탐색기에서 보고 | 참고  |
|---------|---------|---------| 
|Word, Excel, PowerPoint         |아니요         |
|Outlook         |아니요         |
|SharePoint 온라인, OneDrive         |해당 없음           |
|Exchange         |아니요       |
|AIP 통합 클라이언트         |예            |
|AIP 통합 스캐너         |해당 없음         |
|MIP SDK         |예            |
|RMS 서비스         |해당 없음         |
|Power BI 및 웹         |해당 없음            |
|MCAS     |해당 없음        |         |

## <a name="protection-changed"></a>보호가 변경된 경우

이 이벤트는 기록되지 않은 문서의 보호가 수동으로 변경될 때마다 생성됩니다.

|원본  |활동 탐색기에서 보고 |
|---------|---------| 
|Word, Excel, PowerPoint         |아니요         |
|Outlook         |아니요         |
|SharePoint 온라인, OneDrive         |해당 없음           |
|Exchange         |아니요       |
|AIP 통합 클라이언트         |예            |
|AIP 통합 스캐너         |해당 없음         |
|MIP SDK         |예            |
|RMS 서비스         |해당 없음         |
|Power BI 및 웹         |해당 없음            |
|MCAS     |해당 없음        |

## <a name="protection-removed"></a>보호 제거됨

이 이벤트는 기록되지 않은 문서의 보호가 수동으로 변경될 때마다 생성됩니다.

|원본  |활동 탐색기에서 보고 |
|---------|---------| 
|Word, Excel, PowerPoint         |아니요         |
|Outlook         |아니요         |
|SharePoint 온라인, OneDrive         |해당 없음           |
|Exchange         |아니요       |
|AIP 통합 클라이언트         |예            |
|AIP 통합 스캐너         |해당 없음         |
|MIP SDK         |예            |
|RMS 서비스         |해당 없음         |
|Power BI 및 웹         |해당 없음            |
|MCAS     |해당 없음        |

## <a name="dlp-policy-matched"></a>일치하는 DLP 정책

이 이벤트는 문서 또는 전자 메일에서 DLP 정책이 일치할 때마다 생성됩니다.

|원본  |활동 탐색기에서 보고 |
|---------|---------| 
|Exchange         |예       |
|SharePoint Online|예          |
|OneDrive |예|
|Teams |예   |
|Windows 10 장치         |예 |
|MAC         |아니요     |
|On-premises         |아니요|
|MCAS     |아니요        | 

끝점 DLP(Windows 10 장치)에 대한 이벤트는 다음입니다.

- 파일이 삭제되었습니다.
- 만든 파일
- 파일을 클립보드로 복사함
- 파일 수정
- 파일 읽기
- 인쇄된 파일
- 파일 이름 변경
- 파일을 네트워크 공유에 복사함
- 허용되지 않은 앱에서 액세스하는 파일


## <a name="retention-label-applied"></a>적용된 보존 레이블 

이 이벤트는 레이블이 지정되지 않은 문서에 레이블이 지정되거나 보존 레이블이 있는 전자 메일을 보낼 때마다 생성됩니다.

- 이 문서는 문서 저장 시와 전자 메일 전송 시에 캡처됩니다.

|원본  |활동 탐색기에서 보고 |
|---------|---------| 
|Exchange         |아니요       |
|SharePoint Online|예          |
|OneDrive |예|

## <a name="retention-label-changed"></a>보존 레이블 변경

이 이벤트는 문서 또는 전자 메일에서 레이블이 업데이트될 때마다 생성됩니다.

- 이 문서는 문서 저장 시와 전자 메일 전송 시에 캡처됩니다.

|원본  |활동 탐색기에서 보고 |
|---------|---------| 
|Exchange         |아니요       |
|SharePoint Online|예          |
|OneDrive |예|
 
## <a name="retention-label-removed"></a>보존 레이블 제거됨

이 이벤트는 파일이나 문서에서 레이블을 제거할 때마다 생성됩니다.

- 이 문서는 문서 저장 시와 전자 메일 전송 시에 캡처됩니다.

|원본  |활동 탐색기에서 보고 |
|---------|---------| 
|Exchange         |아니요       |
|SharePoint Online|예          |
|OneDrive |예|


## <a name="known-issues"></a>알려진 문제
  
- 최종 사용자에게 권장 레이블 도구 팁이 표시되어 있는 경우 캡처되지 않습니다. 그러나 사용자가 권장 레이블을 적용하도록 선택한 경우 레이블은  적용 방법 필드에 *권장으로 표시됩니다.*  

- 사유 텍스트는 현재 민감도 레이블 다운그레이드에서 사용할 수 SharePoint OneDrive.  

- 중요한 정보 유형은 현재 Word, Excel, PowerPoint, Outlook, SharePoint Online 및 OneDrive.
