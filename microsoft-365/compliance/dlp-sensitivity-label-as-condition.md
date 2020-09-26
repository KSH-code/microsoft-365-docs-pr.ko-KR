---
title: 민감도 레이블을 DLP 정책의 조건으로 사용(미리 보기)
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
ms.custom:
- seo-marvel-apr2020
description: DLP 정책에서 민감도 레이블을 조건으로 사용할 수 있는 서비스 및 항목 형식에 대해 배워봅니다.
ms.openlocfilehash: bb06ed6919a396bef1e5d1f1cb04731fa11267ae
ms.sourcegitcommit: c1ee4ed3c5826872b57339e1e1aa33b4d2209711
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48235725"
---
# <a name="use-sensitivity-labels-as-conditions-in-dlp-policies-preview"></a>민감도 레이블을 DLP 정책의 조건으로 사용(미리 보기)

[민감도 레이블](sensitivity-labels.md)을 이들 위치에서 DLP 정책의 조건으로 사용할 수 있습니다.

- Exchange Online 전자 메일 메시지
- SharePoint Online
- 비즈니스용 OneDrive 사이트
- Windows 10 장치

민감도 레이블은 **콘텐츠가 포함하는 ** 목록에 옵션으로 표시됩니다.

![조건으로서의 민감도 레이블](../media/dlp-sensitivity-label-as-a-condition.png)

## <a name="supported-items-scenarios-and-policy-tips"></a>지원되는 항목, 시나리오 및 정책 팁

이러한 항목 및 이러한 시나리오에 대해 민감도 레이블을 조건으로 사용할 수 있습니다.

### <a name="supported-items"></a>지원되는 항목

|서비스  |항목 유형  |사용 가능한 정책 팁  |적용 가능  |
|---------|---------|---------|---------|
|Exchange    |전자 메일 메시지         |예         |예         |
|Exchange    |전자 메일 첨부 파일         |아니요 *         |아니요 *         |
|SharePoint Online     |SharePoint Online의 항목         |예         |예         |
|비즈니스용 OneDrive     |항목         |예         |예         |
|Teams     |Teams 채팅 및 채널 메시지         |해당 없음         |해당 없음         |
|Teams     |첨부 파일         |예 **         |예 **         |
|Windows 10 장치(미리 보기)     |항목         |예         |예         |
|MCAS (미리 보기) |항목         |예         |예         |

\* 전자 메일에 민감도 레이블의 DLP 감지가 지원됩니다. 민감도 레이블이 부착된 전자 메일 첨부 파일의 DLP 감지는 지원되지 않습니다.

\** 1:1 채팅 혹은 채널을 통해 Teams 로 보낸 첨부 파일은 비즈니스용 One drive 및 SharePoint에 자동으로 업로드 됩니다. 따라서 SharePoint Online 또는 비즈니스용 One Drive가 DLP 정책에서 위치로 포함되는 경우, Teams에서 보낸 레이블이 지정된 첨부 파일은 이 조건의 범위에 자동으로 포함됩니다. DLP 정책에서 Teams를 위치로 선택할 필요가 없습니다.

### <a name="supported-scenarios"></a>지원되는 시나리오

- DLP 관리자는 하나 이상의 민감도 레이블을 조건으로 포함하도록 선택할 때 테넌트의 모든 민감도 레이블 목록을 볼 수 있습니다.
- 위의 지원 행렬에 표시된 것과 같이 모든 작업에서 민감도 레이블을 조건으로 사용하는 것은 지원됨
- DLP 정책 팁은 민감도 레이블을 조건으로 포함하는 DLP 정책에 대해 작업 전반에 결쳐 계속해서 표시됩니다(Outlook Win32 제외)
- 민감도 레이블이 조건과 일치하는 DLP 정책에서 일치하는 경우 민감도 레이블도 인시던트 보고서 전자 메일의 일부로서 표시됩니다.
- 민감도 레이블 세부 정보는 또한 민감도 레이블이 조건으로 포함된 DLP 정책 일치에 대한 DLP 규칙 일치 감사 로그에도 표시됩니다.


### <a name="support-policy-tips"></a>지원 정책 팁


|워크로드  |지원되는 정책 팁/지원되지 않음  |
|---------|---------|
|OWA |    지원     |
|Outlook Win 32    |  지원되지 않음       |
|SharePoint   |   지원      |
|비즈니스용 OneDrive    |    지원     |
|끝점 장치   |  지원되지 않음       |
